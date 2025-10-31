---
title: 
uid: 202108160803
aliases: []
tags: []
from: 
---
[[寡人]]
最新的图文版：https://wws.lanzoui.com/ivW46spygfi


> 翻译自 [Dataview](https://blacksmithgu.github.io/obsidian-dataview/intro/)，翻译了一部分，有不对的自行辨别，希望可以帮助更多人使用 dataview 这款优秀的 obsidian 插件。

# dataview

## 查询语法格式

该插件的 dataview 代码块的使用方法类似于SQL，下面是一个普通的SQL语句：

```sql
SELECT field1 (AS "自定义显示名称"),field2……,fieldn 
FROM tablename 
WHERE field1==value1 or field2==value2
ORDER BY field1 DESC
……(LIMIT 10)
```

dataview的查询格式如下：

```sql
​```dataview
TABLE|LIST|TASK <field> (AS "Column Name"), <field>, ..., <field> 
FROM <source>
WHERE <expression>
SORT <expression> (ASC/DESC)
... other data commands
​```
```
可以看到，二者很像，可以清楚的看到其中的对应关系，tablename对应着source等等。

## 关键字

介绍 dataview 查询格式中的关键字的用途。

```sql
​```dataview
TABLE|LIST|TASK <field> (AS "Column Name"), <field>, ..., <field> 
FROM <source>
WHERE <expression>
SORT <expression> (ASC/DESC)
... other data commands
​```
```

### 1. TABLE/LIST/TASK 指定查询的方式

dataview 现支持以下3中查询方式：

1. **TABLE**：表格视图，可以输出一个页面的多个该页面的字段值，后面可跟多个 field 并输出字段值。
   下面的例子以表格的形式输出文件的标签和创建时间：

   ```sql
   ​```dataview
   table file.tags as 标签,file.ctime
   limit 100
   ​```
   ```

1. **LIST**：列表视图，每个页面只能输出一个该页面的字段值，或者使用加号输出多个字段值（不建议）。
   下面的例子输出文件的标签加文件创建时间：

   ```sql
   ​```dataview
   list file.tags + file.ctime
   limit 100
   ​```
   ```

1. **TASK**：任务视图。
   下面的例子用于展示5个有任务的文档的任务：

   ```sql
   ​```dataview
   task
   where file.tasks
   limit 5
   ​```
   ```

### 2. FROM 查询的文档源

指定查询源，即文档的初步筛选，详见 [source](#1. source 源)。

### 3. WHERE 条件筛选

根据字段筛选页面，只有表达式结果为 `true` 的页面才会被输出。

```
WHERE <clause>
```

1. 获取最近24h内修改过的页面：

   ```
   LIST WHERE file.mtime >= date(today) - dur(1 day)
   ```

1. 获取未完成并且创建时间距今1个月的项目：

   ```
   LIST FROM #projects
   WHERE !completed AND file.ctime <= date(today) - dur(1 month)
   ```

### 4. SORT 排序

按一个或多个字段对所有结果进行排序。

```
SORT date [ASCENDING/DESCENDING/ASC/DESC]
```

您还可以提供多个字段进行排序。将根据第一个字段进行排序。然后，如果出现平局，第二个字段将用于对平局字段进行排序。如果仍然存在平局，则第三类将解决它，依此类推。

```
SORT field1 [ASCENDING/DESCENDING/ASC/DESC], ..., fieldN [ASC/DESC]
```

### 5. GROUP BY 分组

将所有结果分组到一个字段上。为每个唯一字段值生成一行，该字段有两个属性：一个对应于要分组的字段，另一个是 `rows` 多行数组字段，其中包含匹配的所有页面。

```
GROUP BY field
GROUP BY (computed_field) AS name
```

为了使用 `rows` 多行数组更容易，Dataview 支持字段 “swizzling”。如果要从 `rows` 多行数组中的每个对象获取字段 `test`，则 `rows.test` 将自动从 `rows` 多行数组中的每个对象获取 `test` 字段，从而生成一个新数组。然后可以对结果数组应用聚合运算符，如 `sum()`。

例如，使用以下代码可以依照标签分组并输出文件名称：

```sql
​```dataview
table rows.file.name as 文件名称
where file.tags
group by file.tags
​```
```

### 6. FLATTEN 扁平化

展平每行中的数组，在数组中的每个条目中生成一个结果行。（不会用，总是报错）

```sql
FLATTEN field
FLATTEN (computed_field) AS name
```

### 7. LIMIT 输出结果数目限制

限制输出结果的数目。

下面的例子输出2个结果：

```sql
​```dataview
table file
limit 2
​```
```

## 关键字后面的内容

介绍 dataview 查询格式中关键字后面的内容怎么填。

```sql
​```dataview
TABLE|LIST|TASK <field> (AS "Column Name"), <field>, ..., <field> 
FROM <source>
WHERE <expression>
SORT <expression> (ASC/DESC)
... other data commands
​```
```

### 1. source 源

- **标签**：选择一个标签， `FROM #tag`.
- **文件夹**：选择一个文件夹,  `FROM "folder"`.
- **链接文件**：选择链接到某文档的文档，或被某文档所链接的文档：
  - 链接到某文档的文档，`FROM [[note]]`.
  - 某文档链接的文档， `FROM outgoing([[note]])`.
- 上面的源也可以使用 `and` 和 `or` 组合起来进行使用，举例说明：
  - `#tag and "folder"` 会返回所有在 `folder` 文件夹下且带有 `#tag` 标签的文档。
  - `[[Food]] or [[Exercise]]` 会返回任何链接到 `[[Food]]` 或 `[[Exercise]]` 的文件。


### 2. field 字段

- 内置字段：

  - 想查看 file 有哪些属性？可以使用下列代码来进行查看

    ```sql
    ​```dataview
    table file
    limit 1
    ​```
    ```

- 自定义字段：
  - 在文档中以 `字段名1::值1` 的格式创建新的字段值

### 3. expression 表达式

```sql
# 一般操作
field				(直接指向一个field)
simple-field		(指向带有空格或标点的fields，例如"Simple Field!")
a.b					(如果 a 是一个对象，返回其字段'b'的值)
a[expr]             (如果 a 是一个对象或者数组，返回带有名称为 'expr' 的 field)
f(a, b, ...)        (调用名为 `f` 的函数并输入参数：a, b, ...)

# 数学运算
a + b               (加法)
a - b               (减法)
a * b               (乘法)
a / b               (除法)

# 比较
a > b               (检查 a 是否大于 b)
a < b               (检查 a 是否小于 b)
a = b               (检查 a 是否等于 b)
a != b              (检查 a 是否不等于 b)
a <= b              (检查 a 是否小于等于 b)
a >= b              (检查 a 是否大于等于 b)

# 特殊操作
[[Link]].value      (从页面 `Link` 获取 `value` 的值)
```

上述表达式的详细信息见下方。

#### fields 字段名

- 最简单的就是直接指向"字段名"。
  - 例如你在某个文档内有一个字段名叫 "field"，那么你就可以直接指向字段的名字 `field` 以获得拥有该字段名的文档。
- 如果"字段名"中包含空格、标点符号或者其它的非字母或数字的字符，那么你就可以使用 Dataview 的简化名称，它会将所有字母小写，并将空格替换为"-"。例如：
  - 使用 `this-is-a-field` 可以获得字段名诸如 `this is a field` 、`THIS is a FIELD` 等的文档
  - 使用 `hello` 可以获得拥有字段名诸如 `Hello!` 等的文档。（经测试无效）

#### 数学运算

可以使用标准运算符组合字段：加(`+`)，减(`-`)，乘 (`*`)，除 (`/`)。例如 `field1 + field2` 是一个求取字段和的表达式。

#### 比较

您可以使用各种比较运算符来比较大多数值：`<`、`>`、`<=`、`>=`、`=`、`=`、`！=`。这将产生一个布尔真值（true）或假值（false）。

#### 数组/对象索引

您可以通过索引操作符 `array[<index>]` 从**数组**中检索数据，其中 `<index>` 是**任何计算表达式**。数组的第一个元素的索引是0，第二个元素是索引1，依此类推。例如列表 `(1，2，3)[0]=1`。

还可以使用索引操作符从**对象**（将文本映射到数据值）检索数据，其中索引现在是**字符串/文本，而不是数字**。您还可以使用缩写 `object.<name>`，其中 `<name>` 是要检索的值的名称。例如 `object("yes", 1).yes=1`。

#### 函数调用

Dataview支持各种用于操作数据的函数，这些函数在 [functions documentation](https://blacksmithgu.github.io/obsidian-dataview/query/expressions/functions) 中有详细描述。

它们具有一般语法`function(arg1, arg2, ...)`，例如：`lower("yes")` 或者 `regexmatch("text", ".+")`。

具体函数详见 [function 函数](#function 函数)。

#### 特殊类型及其值

大多数 dataview 类型都与运算符有特殊的交互，或者可以通过索引运算符来检索附加字段。

##### Dates 日期

您可以通过以下方式检索日期的各个部分：`date.year`、`date.month`、`date.day`、`date.hour`、`date.minute`、`date.second`、`date.week`。您还可以向日期添加持续时间以获取新日期。

使用举例：

```
​```dataview
TABLE file.ctime.year as "这是文件创建日期的年份"
LIMIT 1
​```
```

##### Durations 周期

持续时间可以相互添加，也可以添加到日期。您可以通过索引检索持续时间的各个组成部分：`duration.years`、`duration.months`、`duration.days`、`duration.hours`、`duration.minutes`、`duration.seconds`。

##### Links 链接

您可以通过“索引”链接来获取相应页面上的值。例如 `[[Link]].value` 将从页面链接获取值。



## function 函数

大多数函数既可以应用于单个值（如数字、字符串、日期等），也可以应用于这些值的列表。如果将函数应用于列表，则在将函数应用于列表中的每个元素后，它也会返回一个列表。例如：

```sql
lower("YES") = "yes"
lower(list("YES", "NO")) = list("yes", "no")

replace("yes", "e", "a") = "yas"
replace(list("yes", "ree"), "e", "a") = list("yas", "raa")
```

### Constructors 构造函数

构造器用于创建值。

#### `object(key1, value1, ...)` 对象构造器

Creates a new object with the given keys and values. Keys and values should alternate in the call, and keys should always be strings/text.

```
object() => empty object
object("a", 6) => object which maps "a" to 6
object("a", 4, "c", "yes") => object which maps a to 4, and c to "yes"
```

#### `list(value1, value2, ...)` 列表构造器

创造一个新列表并为其赋值。

```
list() => empty list
list(1, 2, 3) => list with 1, 2, and 3
list("a", "b", "c") => list with "a", "b", and "c"
```

#### `date(any)` 日期构造器

解析字符串、日期或者链接的对象以获取日期。

```
date("2020-04-18") = <date object representing April 18th, 2020>
date(today) = <date object 今天的日期>
date([[2021-04-16]]) = <date object for the given page, refering to file.day>
```

#### `dur()` 周期构造器

未找到说明

```
dur(1 day) = 1天的周期
```

#### `number(string)` 数字构造器

Pulls the first number out of the given string, returning it if possible. Returns null if there are no numbers in the string.

```
number("18 years") = 18
number(34) = 34
number("hmm") = null
```

#### `link(path, [display])` 链接

根据参数中的path路径构造一个链接对象。如果输入display参数，则该链接显示名称为display。

```
link("Hello") => link to page named 'Hello'
link("Hello", "Goodbye") => link to page named 'Hello', displays as 'Goodbye'
```

#### `elink(url, [display])` 外部链接

构造一个外部链接(例如 `www.google.com`)。如果输入display参数，则该外链显示名称为display。

```
elink("www.google.com") => link element to google.com
elink("www.google.com", "Google") => link element to google.com, displays as "Google"
```

### Numeric Operations 数字操作函数

#### `round(number, [digits])` 

将数字四舍五入到给定的位数。如果未指定第二个参数，则四舍五入到最接近的整数；否则，四舍五入到给定的位数。

```
round(16.555555) = 7
round(16.555555, 2) = 16.56
```

### Objects, Arrays, and String Operations 对象、数组、字符串操作

操作对象内部的值。

#### `contains(object|list|string, value)` 是否包含某值？

检查给定的容器类型中是否包含给定的值。根据第一个参数是对象、列表还是字符串，此函数的行为略有不同。

- 对于对象，检查对象是否具有具有给定名称的键。例如：

  ```
  contains(file, "ctime") = true
  contains(file, "day") = true (if file has a date in its title, false otherwise)
  ```

- 对于列表，检查是否有任何数组元素等于给定值。例如：

  ```
  contains(list(1, 2, 3), 3) = true
  contains(list(), 1) = false
  ```

- 对于字符串，检查给定值是否为字符串的子字符串。例如：

  ```
  contains("hello", "lo") = true
  contains("yes", "no") = false
  ```

#### `extract(object, key1, key2, ...)` 提取对象中的键值

从对象中提取多个字段，然后可以使用这些字段创建新对象。例如：

```
extract(file, "ctime", "mtime") = object("ctime", file.ctime, "mtime", file.mtime)
extract(object("test", 1)) = object()
```

#### `sort(list)` 列表排序

对列表排序并返回新列表。

```
sort(list(3, 2, 1)) = list(1, 2, 3)
sort(list("a", "b", "aa")) = list("a", "aa", "b")
```

#### `reverse(list)` 反转列表

反转列表，按相反顺序返回新列表。

```
reverse(list(1, 2, 3)) = list(3, 2, 1)
reverse(list("a", "b", "c")) = list("c", "b", "a")
```

#### `length(object|array)` 长度

返回对象中的字段数或数组中的条目数。

```
length(list()) = 0
length(list(1, 2, 3)) = 3
length(object("hello", 1, "goodbye", 2)) = 2
```

#### `sum(array)` 数组求和

对数组中的所有数值求和。

```
sum(list(1, 2, 3)) = 6
```

#### `all(array)` 数组值均为真？

仅当数组中的所有值均为truthy时，才返回 `true`。您还可以将多个参数传递给此函数，在这种情况下，只有当所有参数都为truthy时，它才会返回 `true`。

```
all(list(1, 2, 3)) = true
all(list(true, false)) = false
all(true, false) = false
all(true, true, true) = true
```

#### `any(array)` 数组值存在真？

如果数组中的任何值为truthy，则返回 `true`。您还可以将多个参数传递给此函数，在这种情况下，如果任何参数为truthy，它将返回 `true`。

```
any(list(1, 2, 3)) = true
any(list(true, false)) = true
any(list(false, false, false)) = false
all(true, false) = true
all(false, false) = false
```

#### `none(array)` 数组值均为假？

如果数组中的值都不是真的，则返回 `true`。

#### `join(array)` 数组拼接成字符串

将数组中的元素合并为单个字符串。如果提供了第二个参数，则每个元素将由给定的分隔符（即第二个参数）分隔。

```
join(list(1, 2, 3)) = "1, 2, 3"
join(list(1, 2, 3), " ") = "1 2 3"
join(6) = "6"
join(list()) = ""
```

### String Operations 字符串操作

#### `regexmatch(pattern, string)` 正则匹配

检查给定字符串是否与给定模式匹配（使用JavaScript正则表达式引擎）。

```
regexmatch("\w+", "hello") = true
regexmatch(".", "a") = true
regexmatch("yes|no", "maybe") = false
```

#### `regexreplace(string, pattern, replacement)` 正则替换

将 `string` 中正则匹配式 `pattern` 匹配的所有实例替换为 `replacement`。

这里使用JavaScript替换方法，因此您可以使用诸如 `$1` 之类的特殊字符来引用第一个匹配的字符串（`$2` 就是第二个匹配的字符串），等等。

```
regexreplace("yes", "[ys]", "a") = "aea"
regexreplace("Suite 1000", "\d+", "-") = "Suite -"
```

#### `replace(string, pattern, replacement)` 替换

将 `string` 中 `pattern` 匹配的所有字符串替换为 `replacement`。

```
replace("what", "wh", "h") = "hat"
replace("The big dog chased the big cat.", "big", "small") = "The small dog chased the small cat."
replace("test", "test", "no") = "no"
```

#### `lower(string)` 转小写

将字符串转换为全小写。

```
lower("Test") = "test"
lower("TEST") = "test"
```

#### `upper(string)` 转大写

将字符串转换为全大写。

```
upper("Test") = "TEST"
upper("test") = "TEST"
```

### Utility Functions 实用功能函数

#### `default(field, value)` 字段默认值

如果 `field` 为空，则返回 `value`；否则返回 `field` 的值。

用于用默认值替换空值。例如，要显示尚未完成的项目，使用 `incomplete`作为其默认值：

```
default(dateCompleted, "incomplete")
```

默认值的两个参数中都是矢量化的；如果需要使用列表参数上的默认值，即不对列表的空值做出改变，就使用 `ldefault`，它与 `default` 相同，但不是矢量化的。

```
default(list(1, 2, null), 3) = list(1, 2, 3)
ldefault(list(1, 2, null), 3) = list(1, 2, null)
```

#### `choice(bool, left, right)` 判断输出语句

如果第一个参数为真，则返回 `left`；否则返回 `right`。

```
choice(true, "yes", "no") = "yes"
choice(false, "yes", "no") = "no"
choice(x > 4, y, z) = y if x > 4, else z
```

#### `striptime(date)` 

去掉日期的时间部分，只留下年、月和日。如果你不在乎具体时间的话，就可以用它来比较日期。

```
striptime(file.ctime) = file.cday
striptime(file.mtime) = file.mday
```

# dataviewjs

Dataview JavaScript API允许通过访问Dataview的索引和查询引擎以执行任意JavaScript，这有利于复杂视图或与其他插件的互操作。

## 概览

```js
​```dataviewjs
<code>
​```
```

在这些代码块中执行的代码可以访问 `dv` 变量，该变量提供了与代码块相关的dataview API的全部内容（如 `dv.table()`、`dv.pages()` 等）。更多信息见[代码块参考](#代码块参考)。

## DataArray 数据数组

Dataview中的结果列表的一般抽象成 `DataArray`，它是一个具有附加功能的代理数组。

数据数组支持索引和迭代（通过 `for` 和 `for ... of` 来遍历数组中的项目），还包括许多数据操作符，如 `sort`，`groupBy`，`distinct`，`where` 等，这使得表格数据的维护变得简单。

### 创建 DataArray

`DataArray` 由大多数Dataview API返回，并可以返回多个结果，例如 `dv.pages()` 返回所有的文档数据数组。

### DataArray 与普通数组的转换

您还可以使用 `dv.array(<array>)` 将普通JavaScript 数组显式转换为Dataview数组。

如果要将数据数组转换回普通数组，请使用 `DataArray#array()`。

### DataArray 索引

数据数组支持常规索引，就像普通数组一样（比如 `array[0]`）。

但重要的是，它们还支持查询语言风格的“swizzling”：如果使用字段名（比如 `array.field`）对数据数组进行索引，它会自动将数组中的每个元素映射到 `field`，如果 `array.field` 对应的值本身也是一个数组，则会将 `field` 变平。

例如，`dv.pages().file.name` 将返回库中所有文件名的数据数组。`dv.pages（“#books”）.genres`将返回书籍中所有类型的扁平列表。

### DataArray 原始接口

下面提供了 `DataArray` 实现的完整的接口以供参考：

```js
/** A function which maps an array element to some value. */
export type ArrayFunc<T, O> = (elem: T, index: number, arr: T[]) => O;

/** A function which compares two types (plus their indices, if relevant). */
export type ArrayComparator<T> = (a: T, b: T) => number;

/**
 * Proxied interface which allows manipulating array-based data. All functions on a data array produce a NEW array
 * (i.e., the arrays are immutable).
 */
export interface DataArray<T> {
    /** The total number of elements in the array. */
    length: number;

    /** Filter the data array down to just elements which match the given predicate. */
    where(predicate: ArrayFunc<T, boolean>): DataArray<T>;
    /** Alias for 'where' for people who want array semantics. */
    filter(predicate: ArrayFunc<T, boolean>): DataArray<T>;

    /** Map elements in the data array by applying a function to each. */
    map<U>(f: ArrayFunc<T, U>): DataArray<U>;
    /** Map elements in the data array by applying a function to each, then flatten the results to produce a new array. */
    flatMap<U>(f: ArrayFunc<T, U[]>): DataArray<U>;
    /** Mutably change each value in the array, returning the same array which you can further chain off of. */
    mutate(f: ArrayFunc<T, any>): DataArray<any>;

    /** Limit the total number of entries in the array to the given value. */
    limit(count: number): DataArray<T>;
    /**
     * Take a slice of the array. If `start` is undefined, it is assumed to be 0; if `end` is undefined, it is assumbed
     * to be the end of the array.
     */
    slice(start?: number, end?: number): DataArray<T>;
    /** Concatenate the values in this data array with those of another data array. */
    concat(other: DataArray<T>): DataArray<T>;

    /** Return the first index of the given (optionally starting the search) */
    indexOf(element: T, fromIndex?: number): number;
    /** Return the first element that satisfies the given predicate. */
    find(pred: ArrayFunc<T, boolean>): T | undefined;
    /** Find the index of the first element that satisfies the given predicate. Returns -1 if nothing was found. */
    findIndex(pred: ArrayFunc<T, boolean>): number;
    /** Returns true if the array contains the given element, and false otherwise. */
    includes(element: T): boolean;

    /**
     * Return a sorted array sorted by the given key; an optional comparator can be provided, which will
     * be used to compare the keys in leiu of the default dataview comparator.
     */
    sort<U>(key: ArrayFunc<T, U>, direction?: 'asc' | 'desc', comparator?: ArrayComparator<U>): DataArray<T>;

    /**
     * Return an array where elements are grouped by the given key; the resulting array will have objects of the form
     * { key: <key value>, rows: DataArray }.
     */
    groupBy<U>(key: ArrayFunc<T, U>, comparator?: ArrayComparator<U>): DataArray<{ key: U, rows: DataArray<T> }>;

    /**
     * Return distinct entries. If a key is provided, then rows with distinct keys are returned.
     */
    distinct<U>(key?: ArrayFunc<T, U>, comparator?: ArrayComparator<U>): DataArray<T>;

    /** Return true if the predicate is true for all values. */
    every(f: ArrayFunc<T, boolean>): boolean;
    /** Return true if the predicate is true for at least one value. */
    some(f: ArrayFunc<T, boolean>): boolean;
    /** Return true if the predicate is FALSE for all values. */
    none(f: ArrayFunc<T, boolean>): boolean;

    /** Return the first element in the data array. Returns undefined if the array is empty. */
    first(): T;
    /** Return the last element in the data array. Returns undefined if the array is empty. */
    last(): T;

    /** Map every element in this data array to the given key, and then flatten it.*/
    to(key: string): DataArray<any>;
    /**
     * Recursively expand the given key, flattening a tree structure based on the key into a flat array. Useful for handling
     * heirarchical data like tasks with 'subtasks'.
     */
    expand(key: string): DataArray<any>;

    /** Run a lambda on each element in the array. */
    forEach(f: ArrayFunc<T, void>): void;

    /** Convert this to a plain javascript array. */
    array(): T[];

    /** Allow iterating directly over the array. */
    [Symbol.iterator](): Iterator<T>;

    /** Map indexes to values. */
    [index: number]: any;
    /** Automatic flattening of fields. */
    [field: string]: any;
}
```

## 代码块参考

### 查询

#### `dv.current()` 当前页面

得到当前页面（脚本运行的页面）的信息。

#### `dv.pages(source)` 指定源的页面

此处的 `source` 同 dataview 中的一样，详见 [source](#1. source 源)。

```
dv.pages("#books") => all pages with tag 'books'
dv.pages('"folder"') => all pages from folder "folder"
dv.pages("#yes or -#no") => all pages with tag #yes, or which DON'T have tag #no
```

#### `dv.pagePaths(source)` 指定源的页面的路径

```
dv.pagePaths("#books") => the paths of pages with tag 'books'
```

#### `dv.page(path)` 指定路径的页面

将简单路径映射到包含所有页面字段的完整页面对象。自动执行链接解析，如果不存在，将自动补充扩展名。

```
dv.page("Index") => The page object for /Index
dv.page("books/The Raisin.md") => The page object for /books/The Raisin.md
```

### 渲染

#### `dv.header(level, text)` 渲染标题

使用所给的文本渲染 1~6 级标题。

```
dv.header(1, "Big!");
dv.header(6, "Tiny");
```

#### `dv.paragraph(text)` 渲染文本

在段落中呈现任意文本。

```
dv.paragraph("This is some text");
```

### 数据展示

#### `dv.list(elements)` 列表视图

呈现元素的dataview列表。参数允许普通数组和数据数组。

```
dv.list([1, 2, 3]) => list of 1, 2, 3
dv.list(dv.pages().file.name) => list of all file names
dv.list(dv.pages().file.link) => list of all file links
dv.list(dv.pages("#book").where(p => p.rating > 7)) => list of all books with rating greater than 7
```

#### `dv.taskList(tasks, groupByFile)` 任务视图

呈现由 `page.file.tasks` 获得的“Task”对象的dataview列表。只需要第一个参数；如果提供了第二个参数“groupByFile”（且为true），则任务将根据它们来自的文件自动分组。

```
// List all tasks from pages marked '#project'
dv.taskList(
	dv.pages("#project").file.tasks
)

// List all *uncompleted* tasks from pages marked #project
dv.taskList(
	dv.pages("#project").file.tasks
    .where(t => !t.completed)
)

// List all tasks tagged with '#tag' from pages marked #project
dv.taskList(
	dv.pages("#project").file.tasks
    .where(t => t.text.includes("#tag"))		// 这里的 t 指代的是 dv.pages("#project").file.tasks 中的每个项目，在这里即为任务对象
)
```

#### `dv.table(headers, elements)` 表格视图

使用给定的表头列表和二维元素数组呈现dataview表。

```
// Render a simple table of book info sorted by rating.
dv.table(
	["File", "Genre", "Time Read", "Rating"], 
	dv.pages("#book")
    .sort(b => b.rating)	// 这里的 b 指代的是 dv.pages("#book") 中的每个项目，在这里即为文件对象
    .map(b => [b.file.link, b.genre, b["time-read"], b.rating]))
```

### 实用功能函数

#### `dv.array(value)` 普通数组转数据数组

在[DataArray中的转换](#DataArray 与普通数组的转换)中介绍过。

```
dv.array([1, 2, 3]) => dataview data array [1, 2, 3]
```

#### `dv.compare(a, b)` 比较

根据dataview的默认比较规则比较两个任意JavaScript值；如果您正在编写自定义比较器并希望返回默认行为，则此选项非常有用。如果 `a<b`，则返回负值；如果 `a=b`，则返回0；如果 `a>b`，则返回正值。

```
dv.compare(1, 2) = -1
dv.compare("yes", "no") = 1
dv.compare({ what: 0 }, { what: 0 }) = 0
```

#### `dv.equal(a, b)` 相等？

根据Dataview的默认比较规则，比较两个任意JavaScript值，如果它们相等，则返回true。

```
dv.equal(1, 2) = false
dv.equal(1, 1) = true
```

## JS 的代码调试方法

可以使用 `alert()` 输出想要的信息（不推荐）；

也可以打开控制台：<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>i</kbd> ，然后使用 `console.log()` 输出信息到控制台（**推荐**）。

想看 `DataArray` 类型的文件都含有什么属性？使用以下代码即可在控制台查看其属性，然后调用就可以了：

```sql
​```dataviewjs
console.log("这是 file 的属性");
console.log(dv.current().file);
console.log("这是 file.tasks 的属性");
console.log(dv.current().file.tasks);
​```
```

## 例子

都是自用的例子，只是能用的级别。

我的文件存放方式大致如下：

- `根目录`
  - `主 moc.md`（这个用来索引资源、项目的 moc 文件）
  - `项目`（项目文件夹）
    - `水质检测项目`（这个是一个项目文件夹）
      - `水质检测项目.md`（这个是和文件夹相同名称的文档，也是该文件夹下所有文件的索引，即 moc）
      - `文档1.md`
      - `文档2.md`
      - ……
    - ……
  - `资源`（资源文件夹）
    - `markdown`（这个是一个资源文件夹）
      - `markdown.md`（这个是和文件夹相同名称的文档，也是该文件夹下所有文件的索引，即 moc）
      - `文档1.md`
      - `文档2.md`
      - ……
    - ……

下面结合我的文件存放方式说几个例子。

### 示例一：获取当前文件所在文件夹下所有文件的任务并计算总进度

该代码块可以放入某个项目或者资源文件夹中的moc文件，用于总览该项目或资源的任务进度。当然你也可以将代码放入该文件夹下的其他文件，这就看个人需求了，重点是看懂代码。

例如将代码放入下图所示的 `水质检测项目.md` 文件中：

`![image-20210816104300278](assets/image-20210816104300278.png)` (文件缺失)

```sql
​```dataviewjs
// 计算任务进度
var allTask = 0;		//用于计算任务总数
var completedTask = 0;	//用于计算文件完成数目
for(var task of dv.pages().file.tasks.where(t => t.path.match(dv.current().file.folder))){
	if(task.completed){
		completedTask++;
	}
	allTask++;
}

// 展示任务进度
if(allTask){
	dv.paragraph('任务完成进度：**' + (completedTask/allTask * 100).toFixed(1) + '%**')
}

// 获取并展示当前文件夹下所有文件的任务
dv.taskList(
	dv.pages().file.tasks
	.where(t => t.path.match(dv.current().file.folder))
	.sort(t => t.ctime)
)
​```
```

### 示例二：获取当前文件所在文件夹下未被本文档链接的文档

我的文件存储方式是某个项目或资源的文件夹中的 moc 文档会使用 `[[文档名]]` 来链接其它文档，例如：

```markdown
这是 markdown.md 文件

markdown 使用很方便，可以通过 [[简介]] 了解，然后通过 [[快速上手]] 进行学习。
```

上面的这个资源文件 moc 只引用其文件夹下的 2 个文档，有时一个资源文件夹下有很多文档，有的可能并未被链接，我们也很难发现，这时使用下列代码来实现获取当前文件夹下未被本文档链接的文档。

```sql
​```dataviewjs

// 初步筛选，筛选2次，先获得当前文件夹下的文档，再去除当前文档
var currentFolderFilesExceptThis = dv.pages().file
	.where(b => b.path.indexOf(dv.current().file.folder)!=-1)
	.where(b => b.path!=dv.current().file.path);

// 进一步筛选，获取未被当前文档链接的文档
var pages = new Array();	//创建新数组用于存放未被链接的文件
var linked;
for(var file of currentFolderFilesExceptThis){
	linked = 0;
	for(var outlink of dv.current().file.outlinks){
		if(outlink.path==file.path){
			linked = 1;
			break;
		}
	}
	if(!linked){
		pages.push(file)
	}
}

// 将普通数组转换为DataArray类型
dv.list(dv.array(pages).link);

​```
```

### 示例三：获取某目录下资源或项目文件夹的 moc 文档链接、标签和任务进度

这个文件放在 `主 moc.md` 中，它可以某目录下资源或项目文件夹的 moc 文档链接、标签和任务进度。

下方是获取资源文件夹中的资源文件的 moc 文档链接、标签和任务进度：

```sql
​```dataviewjs

// 写入 moc文件所在文件夹的父文件夹的路径
const Path = "资源/";	// x

// 获取指定目录下各文件夹中的 moc 文件
var mocFiles = dv.pages().file
	.where(b => b.path.indexOf(Path)!=-1)
	.where(b => b.path.endsWith(b.name + '/' + b.name + '.md'))

// 处理 moc 文件的标签、任务进度
for(var mocFile of mocFiles){
	// 处理标签：获取该 moc 所在文件夹下的所有标签（无重复显示标签）
	var allTags = new Array();
	for(var file of dv.pages().file.where(b => b.path.match(mocFile.folder))){
		for(var tag of file.tags){
			if(allTags.indexOf(tag)==-1){
				allTags.push(tag)
			}
		}
	}
	mocFile["myTags"] = '';
	for(var tag of allTags){
		mocFile["myTags"] = mocFile["myTags"] + tag + ' ';
	}
	
	// 处理任务进度：获取该 moc 文件所在文件夹下所有的任务并计算任务进度
	var allTask = 0;
	var completedTask = 0;
	for(var task of dv.pages().file.tasks.where(t => t.path.match(mocFile.folder))){
		if(task.completed){
			completedTask++;
		}
		allTask++;
	}
	if(allTask){
		mocFile["jindu"] = '任务完成进度：**' + (completedTask/allTask * 100).toFixed(1) + '%**';
	}
}

// 展示成表格的形式
dv.table(
	['文件', '标签', '任务'],
	mocFiles
	.map(b => [b.link, b.myTags, b.jindu])
)
​```
```

