[[flying fly flies]] [[css]]
https://github.com/whyt-byte/Blue-Topaz_Obsidian-css

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20200930201511.png)
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20200930201530.jpg)

```
/*flying fly flies 修改，欢迎使用及分享，感谢ABC、_ph*/
/*modified by flying fly flies, feel free to use, share and modify, thanks to ABC and _ph*/

.theme-dark {
  --background-primary: #3f3f3f; /*笔记内背景颜色*/
  --background-primary-alt: #383838;
  --background-secondary: #303030;/*两边侧框颜色*/
  --background-secondary-alt: #000000; /*两边细条颜色*/
  --background-accent: #000;
  --background-modifier-border: #565656;/*图谱线色*/
  --background-modifier-form-field: rgba(0, 0, 0, 0.3);
  --background-modifier-form-field-highlighted: rgba(0, 0, 0, 0.22);
  --background-modifier-box-shadow: rgba(0, 0, 0, 0.3);
  --background-modifier-success: #539126;
  --background-modifier-error: #3d0000;
  --background-modifier-error-rgb: 61, 0, 0;
  --background-modifier-error-hover: #470000;
  --background-modifier-cover: rgba(0, 0, 0, 0.6);
  --text-accent: #53aaf5;/*[[]]文字颜色*/
  --text-accent-hover: #cadcfb; /*笔记内文字鼠标悬浮颜色*/
  --text-normal: #eeeeeee8; /*笔记内文字颜色，左右窗口鼠标悬浮文字颜色*/
  --text-muted: #8b8b8b;  /*未被选中的文字颜色 图谱点色  左侧菜单文字颜色鼠标未悬浮颜色*/
  --text-faint: rgb(121, 121, 121);
  --text-error: #e16d76;
  --text-error-hover: #c9626a;
  --text-highlight-bg: #bb7900;/*文字标记颜色*/
  --text-selection: #e6c2755e;/*鼠标选中文本颜色*/
  --text-on-accent: #dcddde;
  --interactive-normal: #20242b;
  --interactive-hover: #353b47;
  --interactive-accent: #3187d3; /*图谱点颜色 文件栏背景颜色 鼠标悬浮颜色*/ 
  --interactive-accent-rgb: 45, 135, 211;     /*图谱线颜色 鼠标悬浮，和--interactive-accent一致*/  
  --interactive-accent-hover: #5082df;
  --panel-border-color: #18191e;
  --search-text: #e0e0e0;
  --folder-title: #ffffff;

  --gray-1: #5C6370;
  --gray-2: #abb2bf;
  --red: #e06c75;
  --orange: #d19a66;
  --green: #98c379;
  --aqua: #56b6c2;
  --purple: #c678dd;
  --blue: #61afef;
  --yellow: #e5c07b;
  --yykys: #7590ca67;  /*![[]]颜色 */
  --btys: #7292B1;     /*H6 标题颜色 */
  --bqys: #ffffff;     /*标签颜色*/
  --bqds: #404b5ef5;     /*标签底色*/
  --zzsyck: #3187d3;   /*正在使用窗口提示条*/
  --btblj: #96b7e4;    /*标题被链接*/
  --dgxs: #515953;     /*- 缩进大纲颜色*/
  --ztys:  #3187d3;
  --ztysop: #3187d388;
  --tag1: #cf0000;
  --tag2: #cf7c00;
  --tag3: #00a71c;

  --bqys1: #df7e7ebb;
  --bqys2: #d39461bb;
  --bqys3: #c7cc37bb;
  --bqys4: #8fd389bb;
  --bqys5: #5ccbcfbb;
  --bqys6: #5b94d6bb;
  --bqys7: #9859e0bb;
  --bqys8: #cd64d6bb;
  --bqys9: #b3b3b3bb;

  /*标题文字颜色*/
  --h1ys: #7aaed8;
  --h2ys: #77cf7b;
  --h3ys: #cecf70;
  --h4ys: #d4a55e;
  --h5ys: #cc5353;
  --h6ys: #c262df;

  /*关系图谱*/
  --tpsh: #3187d3;   /*鼠标悬浮，关系图谱色环，和图谱点色  --interactive-accent保持一致会好看*/
  --tpwzys: #B5B5B5; /*--tpwzys图谱文字颜色，夜间比  图谱点色--interactive-accent 略暗*/   
  /*--graphtag: #d1d43eb2;
  --graph-attach: #4ad43eb2;
  --graph-circle: #99b4d8b2;
  --graph-line: #646464;
  --graph-unresolved: #db4e4eb2;*/
  --graphtag: #88d842bb;
  --graph-attach: #b2cfe0bb;
  --graph-circle: #55a2d6bb;
  --graph-line: #646464;
  --graph-unresolved: #db4e4ebb;
  --graph-arrow: #c23917;
}

.theme-light {
  --background-primary: #ffffff; /*笔记内背景颜色*/
  --background-primary-alt: #f3f3f3;
  --background-secondary: #f0f0f0;/*两边侧框颜色*/
  --background-secondary-alt: #dbdbdb;/*两边细条颜色*/
  --background-accent: #fff;
  --background-modifier-border: #e1dfdf;/*图谱线色*/
  --background-modifier-form-field: #fff;
  --background-modifier-form-field-highlighted: #fff;
  --background-modifier-box-shadow: rgba(0, 0, 0, 0.1);
  --background-modifier-success: #A4E7C3;
  --background-modifier-error: #e68787;
  --background-modifier-error-rgb: 230, 135, 135;
  --background-modifier-error-hover: #FF9494;
  --background-modifier-cover: rgba(0, 0, 0, 0.8);
  --text-accent: #3995ff;/*[[]]文字颜色*/
  --text-accent-hover: #095385;/*笔记内文字鼠标悬浮颜色*/
  --text-normal: #000000; /*笔记内文字颜色，左右窗口鼠标悬浮文字颜色*/
  --text-muted: #666666;/*未被选中的文字颜色 图谱点色  左侧菜单文字颜色鼠标未悬浮颜色*/
  --text-faint: #7a7a7a;
  --text-error: #e75545;
  --text-error-hover: #f86959;
  --text-highlight-bg: #ffaa00e0;           /*文字标记颜色*/
  --text-selection: #ffe23d48;/*鼠标选中文本颜色*/
  --text-on-accent: #f2f2f2;
  --interactive-normal: #eaeaeb;
  --interactive-hover: #dbdbdc;
  --interactive-accent-rgb: 70, 142, 235;  /*图谱线颜色 鼠标悬浮，和--interactive-accent一致*/ 
  --interactive-accent: #468eeb;       /*图谱点颜色 文件栏颜色 鼠标悬浮颜色*/ 
  --interactive-accent-hover: #445bd1;
  --panel-border-color: #dbdbdc;
  --search-text: #000000;
  --folder-title: #000000;

  --gray-1: #383a42;
  --gray-2: #383a42;
  --red: #e75545;
  --green: #4ea24c;
  --blue: #3d74f6;
  --purple: #a625a4;
  --aqua: #0084bc;
  --yellow: #e35649;
  --orange: #db9600;
  --yykys: #468eeb27;    /*![[]]颜色 */
  --btys: #b6bdc0;     /*H6 标题颜色 */
  --bqys: #ffffff;   /*标签颜色*/
  --bqds: #eaeaea;     /*标签底色*/
  --zzsyck: #468eeb;   /*正在使用窗口提示条*/
  --btblj: #468eeb;     /*标题被链接*/
  --dgxs: #d0d3d5;      /*- 缩进大纲颜色*/
  --ztys:  #468eeb;
  --ztysop:#468eeba2;
  --tag1: #ff0000;
  --tag2: #ff9900;
  --tag3: #00a030;

  --bqys1: #e77e7e;
  --bqys2: #e4c282;
  --bqys3: #ccce4f;
  --bqys4: #71d668;
  --bqys5: #71dde0;
  --bqys6: #6da1dd;
  --bqys7: #9270db;
  --bqys8: #d67cdf;
  --bqys9: #6b6b6b;

  /*标题文字颜色*/
  --h1ys: #0060dd;
  --h2ys: #0060dd;
  --h3ys: #0060dd;
  --h4ys: #0060dd;
  --h5ys: #0060dd;
  --h6ys: #0060dd;
  /*关系图谱*/
  --tpsh: #468eeb; 
  --tpwzys: #696969; /*--tpwzys图谱文字颜色，白天比  图谱点色--interactive-accent 略亮*/
  --graphtag: #77d425cc;
  --graph-attach: #afcfe0cc;
  --graph-circle: #1f78b4cc;
  --graph-line: #dadada;
  --graph-unresolved: #db4e4ecc; 
  --graph-arrow: #e25300; 
}

span.search-result-file-matched-text{
color: var(--search-text);
background-color: var(--text-highlight-bg);
opacity: 0.8;
}

.view-header-title-container:after {
display: none;
}

.workspace-leaf.mod-active .view-header-title::selection {
  background-color: var(--text-highlight-bg);
  color: var(--interactive-accent);
}

.view-action > svg.link {
  color: var(--red);
}

.workspace-leaf.mod-active .view-header-icon {
  color: var(--interactive-accent);
  cursor: grab;
  position: relative;
}

.titlebar {
  background-color: var(--background-secondary-alt);
}

.titlebar-inner {
  -webkit-app-region: drag;
  display: flex;
  flex-grow: 1;
  color: var(--text-normal);
}
.titlebar-left {
  width: 30px;
}
.titlebar-button.mod-back, .titlebar-button.mod-forward {
  line-height: 28px;
}
.titlebar-button {
  -webkit-app-region: no-drag;
  padding: 0 8px;
  cursor: pointer;
  opacity: 0.7;
}
.titlebar-button:hover {
  opacity: 1;
}

/*后退前进符号*/
/*
.titlebar-button.mod-back svg {
  display:none;
}
.titlebar-button.mod-back:before {
  content:"<<prev";
  font-size: 11px; 
  top:-2px;
  position:relative;
}
.titlebar-button.mod-forward svg {
  display:none;
}
.titlebar-button.mod-forward:before {
  content:"next>>";
  font-size: 11px; 
  top:-2px;
  position:relative;
}
*/

.titlebar-text {
  flex-grow: 1;
  margin-right: 120px;
  font-size: 15px;
  text-align: center;
  letter-spacing: 0.05em;
  line-height: 20px;
  opacity: 1;
  color: var(--text-accent);
  position: relative;
}
/*添加其他文字*/
/*
.titlebar-text:after {
  content: " ";
  font-size: 10px;
  text-align: center;
  right:-1px;
  color: var(--text-accent2);
  position: relative;
}
.titlebar-text:before{
  content: " ";
  font-size: 11px;
  text-align: center;
  right:1px;
  color: var(--text-accent);
  position: relative;
}

.titlebar-button-container {
  position: absolute;
  height: 26px;
  top: 0px;
}
*/

.side-dock-ribbon-tab:hover, .side-dock-ribbon-action:hover {
  color: var(--ztys);
}

.nav-folder.mod-root > .nav-folder-title {
  padding-left: 0px;
  font-size: 14px;
  font-weight: bolder;
  top: 0px; 
  cursor: default;
  position: sticky;
  z-index: 900;
  background-color: var(--background-secondary-alt);
}

.workspace-tab-header:hover {
  color: var(--ztys);
  text-align: center;
  stroke-width: 2px;
}

/*==== separators =====*/
.workspace-split.mod-root .workspace-split.mod-vertical .workspace-leaf-content {
  padding-right: 0px;
}
.workspace-leaf-resize-handle {
  background-color: var(--background-secondary-alt);
}

body {
  -webkit-font-smoothing: auto;
}

.search-result-file-title {
  color: var(--btblj);
}

.search-result-file-matched-text {

  color: var(--text-muted); /*标题被链接 提示黑字减淡 */
}

li {
  padding-top: 0.5px;
  padding-bottom: 0.5px;
}

.search-input {
  display: block;
  margin: 0 auto 10px auto;
  width: calc(100% - 20px);
}

.nav-action-button > svg {
  width: 17px;
  height: 17px;
}

.tag, .tag:hover {
  color: var(--bqys);                  /*标签颜色*/
  /*background-color: var(--bqds);    /*标签底色*/
  padding: 2px 4px;
  border-radius: 4px;
}


/*tag标签9色*/
.tag:nth-child(9n+1){background-color: var(--bqys1);} /*1*/
.tag:nth-child(9n+2){background-color: var(--bqys6);} /*6*/
.tag:nth-child(9n+3){background-color: var(--bqys2);} /*2*/
.tag:nth-child(9n+4){background-color: var(--bqys7);} /*7*/
.tag:nth-child(9n+5){background-color: var(--bqys3);} /*3*/
.tag:nth-child(9n+6){background-color: var(--bqys8);} /*8*/
.tag:nth-child(9n+7){background-color: var(--bqys4);} /*4*/
.tag:nth-child(9n+8){background-color: var(--bqys9);} /*9*/
.tag:nth-child(9n){background-color: var(--bqys5);}   /*5*/

/* ====== Tag Pills ======== */
.tag:not(.token) {
	border: none;
	color: white;
	padding: 1px 8px;
	text-align: center;
	text-decoration: none;
	margin: 0px 0px;
	cursor: pointer;
	border-radius: 15px;
}
.tag:not(.token):hover {
	color: white;
	background-color: var(--text-accent-hover);
}
.tag[href^="#important"] {
  background-color: var(--tag1);
  font-weight: 600;
  font-family: Lucida Handwriting;
}
.tag[href^="#重要"] {
  background-color: var(--tag1);
  font-weight: 600;
  font-family: Webdings, Microsoft YaHei;
}
.tag[href^="#complete"] {
  background-color: var(--tag3);
  font-weight: 600;
  font-family:  Lucida Handwriting;
}
.tag[href^="#完成"] {
  background-color: var(--tag3);
  font-family: Origin, Microsoft YaHei;
  font-weight: 600;
}
.tag[href^="#inprogress"] {
  background-color: var(--tag2);
  font-weight: 600;
  font-family: Lucida Handwriting;
}
.tag[href^="#进行中"] {
  background-color: var(--tag2);
  font-weight: 600;
  font-family: Wingdings, Microsoft YaHei;
}

/* task lists! */
.markdown-preview-view .task-list-item-checkbox {
  -webkit-appearance: none;
  box-sizing: border-box;
  border: 1px solid var(--text-normal);
  position: relative;
  width: 15px;
  height: 15px;
  margin: 0;
  margin-right: 5px;
  margin-bottom: 1px;
  filter: hue-rotate(var(--ztys));
  transition: background-color 200ms ease-out 0s;
  cursor: pointer;
}
.markdown-preview-view .task-list-item-checkbox:checked {
  border:none;
  background-color: var(--interactive-accent);
}
.markdown-preview-view .task-list-item-checkbox:hover {
  background-color: var(--background-primary-alt);
}
/* the SVG check mark */
.markdown-preview-view .task-list-item-checkbox:checked::before {
  content: ' ';
  position: absolute;
  background-color: white;
  left:3px;
  top:3px;
  right:2px;
  bottom:2px;
  -webkit-mask-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 14 14'%3E%3Cpolygon points='5.5 11.9993304 14 3.49933039 12.5 2 5.5 8.99933039 1.5 4.9968652 0 6.49933039'%3E%3C/polygon%3E%3C/svg%3E");
}

/* this should strike through checked off items, once CSS supports :has
  (it's draft right now) */
.markdown-preview-view .task-list-item:has(.task-list-item-checkbox:checked) {
  text-decoration: line-through;
  color: var(--text-muted);
}

.markdown-preview-view h1 {
  font-size: 25px; font-weight:550;
  line-height: 28px;
  padding-bottom:1px;
  border-bottom: 2px solid var(--h1ys);
}

.markdown-preview-view h2 {
  font-size: 23px; font-weight:550;
  line-height: 28px;
  padding-bottom: 1px;
  border-bottom: 1px solid var(--h2ys);
}
.markdown-preview-view h3 {font-size: 21px; font-weight:550;}
.markdown-preview-view h4 {font-size: 19px; font-weight:550;}
.markdown-preview-view h5 {font-size: 17px; font-weight:550;}
.markdown-preview-view h6 {font-size: 15px; font-weight:550;}
	
.markdown-preview-view h1 {color: var(--h1ys);}
.markdown-preview-view h2 {color: var(--h2ys);}
.markdown-preview-view h3 {color: var(--h3ys);}
.markdown-preview-view h4 {color: var(--h4ys);}
.markdown-preview-view h5 {color: var(--h5ys);}
.markdown-preview-view h6 {color: var(--h6ys);}

.cm-header-1 {font-size: 25px; font-weight:550;}
.cm-header-2 {font-size: 23px; font-weight:550;}
.cm-header-3 {font-size: 21px; font-weight:550;}
.cm-header-4 {font-size: 19px; font-weight:550;}
.cm-header-5 {font-size: 17px; font-weight:550;}
.cm-header-6 {font-size: 15px; font-weight:550;}
.cm-s-obsidian .cm-header, .cm-s-obsidian .cm-strong {font-weight:550;}

.cm-header-1 {color: var(--h1ys);}
.cm-header-2 {color: var(--h2ys);}
.cm-header-3 {color: var(--h3ys);}
.cm-header-4 {color: var(--h4ys);}
.cm-header-5 {color: var(--h5ys);}
.cm-header-6 {color: var(--h6ys);}

.nav-file-title, .nav-folder-title {
  display: flex;
  align-items: baseline;
  flex-direction: row;
}

.nav-files-container {
  flex-grow: 1;
  overflow-y: auto;
  padding-left: 0px;  /* reduce to 0 for more space */
  padding-bottom: 10px;
  margin-bottom: 10px;
}

.markdown-preview-view blockquote {
	padding-top: 8px;
	padding-bottom: 8px;
	padding-left: 10px;
	padding-right: 8px;
	margin-bottom: 0px;
	margin-top: 0px;
	border-right-width:0; 
	border-top-width: 0px;
	border-bottom-width: 0px;
  border-left-width: 7px;
  border-color: var(--ztys);
  background-color: var(--background-primary-alt);
  border-radius: 0%;
}

.markdown-preview-view blockquote p {
  margin-left: 1px;
	margin-right: 0px;
}

.markdown-preview-view.is-readable-line-width .markdown-preview-section,
.markdown-source-view.is-readable-line-width .CodeMirror {
  max-width: 900px !important;
  line-height: 26px;
}

blockquote {
  margin: 20px 0;
}

mjx-container[jax='CHTML'] {
  text-align: left;
  outline: none;
  font-size: 20px;
}

.theme-dark .cm-s-obsidian pre.HyperMD-codeblock,
.theme-dark .cm-s-obsidian span.cm-inline-code,
.theme-dark .cm-s-obsidian span.cm-math:not(.cm-formatting-math-begin):not(.cm-formatting-math-end),
.theme-dark .markdown-preview-view code {
  color: #e48900;
}

.cm-s-obsidian span.cm-inline-code,
.cm-s-obsidian span.cm-math,
.cm-s-obsidian span.hmd-fold-math-placeholder {
  font-weight: 600;
  font-style: normal;
}

.cm-hmd-list-indent .cm-tab, ul ul { 
	position: relative; 
	padding-right: 20px;
	}
.cm-hmd-list-indent .cm-tab::before, ul ul::before {
 content:'';
 border-left: 1px solid ;/*粗/rgba(114, 165, 223, 0.9);*/
 color: var(--dgxs);
 position: absolute;
}

.cm-hmd-list-indent .cm-tab::before 
{ left: 0; 
	top: -10px; /*高*/
	bottom: -4px; 
}
ul ul::before { left: -11px; top: 0; bottom: 0; 
} 
ul{
list-style-type: disc;/*圆点变成实心*/
}

.markdown-preview-view code {
  vertical-align: auto;
}

.markdown-preview-section:not(:first-child) h1,
.markdown-preview-section:not(:first-child) h2,
.markdown-preview-section:not(:first-child) h3,
.markdown-preview-section:not(:first-child) h4,
.markdown-preview-section:not(:first-child) h5 {
  margin-top: 40px !important;
}

.markdown-preview-section:not(:first-child) h6 {
	margin-top: 0px !important;
	margin-bottom: 0px !important;
}

h1, h2, h3, h4, h5, h6, strong, b, .view-header-title {
  font-weight: 600;
}

/*大纲竖状线条*/
.outline .collapsible-item-children {
  margin-left: 20px;
  border-left: 2px solid rgba(148, 148, 148, 0.2);
  border-radius: 0px;
  transition:all 300ms ease-in-out;
}
.outline .collapsible-item-children:hover {
  border-left-color: rgba(45, 135, 211, 0.5);
}

/*===*/
.workspace > .workspace-split > .workspace-leaf:first-of-type:last-of-type .view-header {  border: none;} 

/*缩小标题*/
.view-header-title {
  font-size: 12px;
  font-weight: 600;
  overflow: auto;
  padding: 0px 0px 0px 0px;
  white-space: nowrap;
  line-height: 0px;
  top: -1px;
  border-top: 3px transparent;
  border-bottom: 3px transparent;
  color: var(--text-muted);
  background-color: transparent;
  display:inline;
  position: relative;
}

/*============bigger link popup preview  ================*/
.popover.hover-popover {
  position: absolute;
  z-index: var(--layer-popover);
  max-height: 800px; /* was 300 */
  min-height: 100px;
  width: 550px;
  overflow: hidden;
  padding: 0;
  border-bottom: none;
  transform: scale(0.9);
}
.popover {
  background-color: var(--background-primary);
  border: 1px solid var(--text-accent);
  box-shadow: 1px 1px 1px 1px var(--text-accent);
  border-radius: 0px;
  padding: 15px 20px 10px 20px;
  position: relative;
  font-weight: 400;
  text-align: justify; 
  -webkit-text-stroke: 0.0px;
  -webkit-font-smoothing: none;
  color:var(--text-normal);
  overflow-y: scroll;
}

.popover mark {
  background-color: var(--text-highlight-bg);     /* mark background color */
  color:var(--text-normal)     /* color for marked text */
}

.workspace-leaf.mod-active .view-header {

  border-bottom: 3px solid var(--zzsyck); /*正在使用窗口提示条*/
}

.status-bar, .side-dock.mod-right, .side-dock.mod-left {
  border-color: var(--panel-border-color);
  border-width: 1px;
}

.status-bar {
  --bar-vertical-padding: 4px;
  --bar-height: calc(22px + (var(--bar-vertical-padding) * 2));
  line-height: 20px;
  padding: 0 20px;
  height: var(--bar-height);
  max-height: var(--bar-height);
  min-height: var(--bar-height);
  overflow: hidden;
  color: var(--text-muted);
}

.status-bar-item {
  margin: auto 0;
}

.status-bar-item > * {
  padding-top: var(--bar-vertical-padding) !important;
  padding-bottom: var(--bar-vertical-padding) !important;
}

.nav-file.is-active {
  --background-secondary-alt: var(--interactive-accent);
  --text-normal: #ffffff;
}

.nav-file:not(.is-active):hover .nav-file-title,
.nav-folder:hover .nav-folder-content {
  background-color: var(--ztysop);
  color: #ffffff;
  font-weight: 500;
}

.side-dock-plugin-panel-inner {
  padding-left: 6px;
}

a,
.markdown-preview-view .internal-link {
  text-decoration: none;
}

a:hover,
.markdown-preview-view .internal-link:hover {
  text-decoration: underline;
}

.theme-dark :not(pre) > code[class*='language-'],
.theme-dark pre[class*='language-'] {
  background: var(--background-primary-alt);
  border-radius: 15px;
}

.theme-light :not(pre) > code[class*='language-'],
.theme-light pre[class*='language-'] {
  background: var(--background-primary);
  box-shadow: inset 0 0 0 2px var(--background-primary-alt);
  border-radius: 15px;
}

.theme-dark code[class*="language-"], .theme-dark pre[class*="language-"] {
  color: #f8f8f2;
}


/*==============TRANSCLUSION TWEAKS=============*/

/*绑定页面
body.is-hovering-clickable, body.is-hovering-clickable{
cursor: pointer !important;
}
*/

.markdown-preview-view .markdown-embed,
.markdown-preview-view .file-embed {

  background-color: var(--yykys); /* ![[]]引用块颜色 */
  border: 0px sold var(--yykys);  /* ![[]]引用块边线 */
  margin: 0;
  border-radius: 4px;
  border: 0;
  border-left: 1px solid var(--background-accent);
  margin: 0px -10px;
}

.markdown-embed {
  display: block;
  top: 0px;
}

.markdown-preview-view .markdown-embed-content {
  padding-right: 0px;
  display: inline;
  max-height: 100%;
  max-width: 100%;
  margin: 0px 0px -15px -10px;
  padding: 20px 0px 0px 0px;
  overflow: hidden; 
}

.markdown-preview-view .markdown-embed,
.markdown-view .file-embed {
  padding: 10px 10px 10px 10px; /*引用框大小显示*/
}

.markdown-embed-title, .file-embed-title {
  font-weight: 400; /*引用框标题文字粗细显示*/
  text-align: left; /*引用框标题文字位置显示*/
  font-size: 20px;  /*引用框标题文字显示*/
  height: 35px; /*引用框标题文字框大小*/
}

.theme-light .token.operator,
.theme-light .token.entity,
.theme-light .token.url,
.theme-light .language-css .token.string,
.theme-light .style .token.string {
  background: transparent;
}

/* Source: https://github.com/AGMStudio/prism-theme-one-dark */

code[class*='language-'],
pre[class*='language-'] {
  text-align: left !important;
  white-space: pre !important;
  word-spacing: normal !important;
  word-break: normal !important;
  word-wrap: normal !important;
  line-height: 1.5 !important;
  -moz-tab-size: 4 !important;
  -o-tab-size: 4 !important;
  tab-size: 4 !important;
  -webkit-hyphens: none !important;
  -moz-hyphens: none !important;
  -ms-hyphens: none !important;
  hyphens: none !important;
}

/* Inline code */
:not(pre) > code[class*='language-'] {
  padding: .1em !important;
  border-radius: .3em !important;
  white-space: normal !important;
}

.token.comment,
.token.prolog,
.token.doctype,
.token.cdata {
  color: var(--gray-1) !important;
}

.token.punctuation {
  color: var(--gray-2) !important;
}

.token.selector,
.token.tag {
  color: var(--red) !important;
}

.token.property,
.token.boolean,
.token.number,
.token.constant,
.token.symbol,
.token.attr-name,
.token.deleted {
  color: var(--orange) !important;
}

.token.string,
.token.char,
.token.attr-value,
.token.builtin,
.token.inserted {
  color: var(--green) !important;
}

.token.operator,
.token.entity,
.token.url,
.language-css .token.string,
.style .token.string {
  color: var(--aqua) !important;
}

.token.atrule,
.token.keyword {
  color: var(--purple) !important;
}

.token.function,
.token.macro.property {
  color: var(--blue) !important;
}

.token.class-name {
  color: var(--yellow) !important;
}

.token.regex,
.token.important,
.token.variable {
  color: var(--purple) !important;
}

.token.important,
.token.bold {
  font-weight: bold !important;
}

.token.italic {
  font-style: italic !important;
}

.token.entity {
  cursor: help !important;
}

pre.line-numbers {
  position: relative !important;
  padding-left: 3.8em !important;
  counter-reset: linenumber !important;
}

pre.line-numbers > code {
  position: relative !important;
}

.line-numbers .line-numbers-rows {
  position: absolute !important;
  pointer-events: none !important;
  top: 0 !important;
  font-size: 100% !important;
  left: -3.8em !important;
  width: 3em !important; /* works for line-numbers below 1000 lines */
  letter-spacing: -1px !important;
  border-right: 0 !important;

  -webkit-user-select: none !important;
  -moz-user-select: none !important;
  -ms-user-select: none !important;
  user-select: none !important;
}

.line-numbers-rows > span {
  pointer-events: none !important;
  display: block !important;
  counter-increment: linenumber !important;
}

.line-numbers-rows > span:before {
  content: counter(linenumber) !important;
  color: var(--syntax-gray-1) !important;
  display: block !important;
  padding-right: 0.8em !important;
  text-align: right !important;
}

/* ==== fold icons ==== */
.CodeMirror-guttermarker-subtle {
  color: var(--text-normal);
}

/*-- wider folding zone--*/
.CodeMirror-foldgutter {
  width: 1.5em;
}


/*=============== DIRTY WYSIWYM HEADERS by _ph =====================*/
/*=============== replace H1-H6 markup in edit mode ================*/

/* Header folder icon */
.CodeMirror-foldgutter-open, .CodeMirror-foldgutter-folded {
  padding-left: -10px;
}

.CodeMirror-sizer{
  margin-left: 35px !important;
}

/*-- reduce left padding --*/
.CodeMirror {
  height: 100%;
  direction: ltr;
  padding: 0 5px;
}

/*-- header color --*/
.cm-header.cm-header-1{
  color: var(--h1ys);
  left:0px;
  position: relative;
}
.cm-header.cm-header-2{
  color: var(--h2ys);
  left:0px;
  position: relative;
}

/*-- hide # markup--*/
.cm-formatting.cm-formatting-header.cm-formatting-header-1.cm-header.cm-header-1,
.cm-formatting.cm-formatting-header.cm-formatting-header-2.cm-header.cm-header-2,
.cm-formatting.cm-formatting-header.cm-formatting-header-3.cm-header.cm-header-3,
.cm-formatting.cm-formatting-header.cm-formatting-header-4.cm-header.cm-header-4,
.cm-formatting.cm-formatting-header.cm-formatting-header-5.cm-header.cm-header-5,
.cm-formatting.cm-formatting-header.cm-formatting-header-6.cm-header.cm-header-6
{font-size:0px;}

/*-- display H1-h6 in gutter--*/
.cm-formatting.cm-formatting-header.cm-formatting-header-1.cm-header.cm-header-1:before{
  content:"H1";
  font-size:14px;
  color: var(--h1ys);
  left:-27px;
  top:-13px;
  position:absolute;
}
.cm-formatting.cm-formatting-header.cm-formatting-header-2.cm-header.cm-header-2:before{
  content:"H2";
  font-size:13px;
  color: var(--h2ys);
  left:-26.5px;
  top:-11px;
  position:absolute;
}
.cm-formatting.cm-formatting-header.cm-formatting-header-3.cm-header.cm-header-3:before{
  content:"H3";
  font-size:12px;
  color: var(--h3ys);
  left:-21px;
  top: 9px;
  position:absolute;
}
.cm-formatting.cm-formatting-header.cm-formatting-header-4.cm-header.cm-header-4:before{
  content:"H4";
  font-size:11px;
  color: var(--h4ys);
  left:-20.5px;
  top: 7px;
  position:absolute;
}
.cm-formatting.cm-formatting-header.cm-formatting-header-5.cm-header.cm-header-5:before{
  content:"H5";
  font-size:10px;
  color: var(--h5ys);
  left:-20px;
  top: 9px;
  position:absolute;
}
.cm-formatting.cm-formatting-header.cm-formatting-header-6.cm-header.cm-header-6:before{
  content:"H6";
  font-size:9px;
  color: var(--h6ys);
  left:-19.5px;
  top: 9px;
  position:absolute;
}

/*-- is active line, hide H[1-6] in gutter --*/
.CodeMirror-activeline span.cm-formatting.cm-formatting-header.cm-formatting-header-1.cm-header.cm-header-1:before,
.CodeMirror-activeline span.cm-formatting.cm-formatting-header.cm-formatting-header-2.cm-header.cm-header-2:before,
.CodeMirror-activeline span.cm-formatting.cm-formatting-header.cm-formatting-header-3.cm-header.cm-header-3:before,
.CodeMirror-activeline span.cm-formatting.cm-formatting-header.cm-formatting-header-4.cm-header.cm-header-4:before,
.CodeMirror-activeline span.cm-formatting.cm-formatting-header.cm-formatting-header-5.cm-header.cm-header-5:before,
.CodeMirror-activeline span.cm-formatting.cm-formatting-header.cm-formatting-header-6.cm-header.cm-header-6:before
{font-size:0px;}

/*-- is active line, display # markup --*/
.CodeMirror-activeline > pre > span .cm-formatting.cm-formatting-header.cm-formatting-header-1.cm-header.cm-header-1{
  font-size:24px;
  display:inline;
}
.CodeMirror-activeline > pre > span .cm-formatting.cm-formatting-header.cm-formatting-header-2.cm-header.cm-header-2{
  font-size:22px;
  display:inline;
}
.CodeMirror-activeline > pre > span .cm-formatting.cm-formatting-header.cm-formatting-header-3.cm-header.cm-header-3{
  font-size:20px;
  display:inline;
}
.CodeMirror-activeline > pre > span .cm-formatting.cm-formatting-header.cm-formatting-header-4.cm-header.cm-header-4{
  font-size:18px;
  display:inline;
}
.CodeMirror-activeline > pre > span .cm-formatting.cm-formatting-header.cm-formatting-header-5.cm-header.cm-header-5{
  font-size:16px;
  display:inline;
}
.CodeMirror-activeline > pre > span .cm-formatting.cm-formatting-header.cm-formatting-header-6.cm-header.cm-header-6{
  font-size:16px;
  display:inline;
}

/*预览模式H1-H6*/
/* add some header prefix in preview */
/*
h1::before
{
  content: 'H1 ';
  font-size: 12px;
  color: var(--h1ys)
}

h2::before
{
  content: 'H2 ';
  font-size: 12px;
  color: var(--h2ys)
}

h3::before
{
  content: 'H3 ';
  font-size: 12px;
  color: var(--h3ys)
}

h4::before
{
  content: 'H4 ';
  font-size: 12px;
  color: var(--h4ys)
}

h5::before
{
  content: 'H5 ';
  font-size: 12px;
  color: var(--h5ys)
}

h6::before
{
  content: 'H6 ';
  font-size: 12px;
  color: var(--h6ys)
}
*/

/*=============== FOCUS MODE by death_au + transparency mod ================*/
/*
.cm-s-obsidian div:not(.CodeMirror-activeline) > pre.CodeMirror-line,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-link,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-hmd-internal-link,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-url,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-hmd-escape-backslash,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-inline-code,
.cm-s-obsidian div:not(.CodeMirror-activeline) > pre.CodeMirror-line.HyperMD-codeblock,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-hashtag,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-builtin,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-hr,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-footref,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line pre.HyperMD-footnote span.cm-hmd-footnote,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-formatting-highlight,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-highlight,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-formatting-list,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-formatting-task,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-quote,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-math,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.hmd-fold-math-placeholder {
  opacity:0.8;
  filter: saturate(0.8);
}
*/

/*focus模式，高亮取消*/
/*
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-formatting-highlight,
.cm-s-obsidian div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-highlight {
  background-color: transparent;
}
.CodeMirror-activeline {
  opacity:1;
} 
*/

/* inline formatting, link targets and [[ ]] disappears if not active line
div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-formatting,
div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-string.cm-url,
div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-formatting-link
{ display: none; }

/* hide all html tags -- IT IS COMMENTED OUT BY DEFAULT 
/* div:not(.CodeMirror-activeline) > .CodeMirror-line span.cm-tag{ display: none; } */


/* except list markers span.cm-formatting-list,
/*code block backticks  span.cm-formatting-code-block.cm-hmd-codeblock,
/* optionally header hashes  span.cm-formatting-header
{ display: inline !important; }

/* and task checkboxes 
span.cm-formatting-task { display: inline !important; font-family: monospace; }
*/

/* images : reduce displayed size of embedded files, zoom on hover */
.markdown-preview-view img, .markdown-preview-view video {
  width: auto;
  height: auto;
  object-fit: contain;
  max-height: 300px;
  max-width: 550px;
  outline: 0px solid var(--text-accent);
}
.markdown-preview-view img:hover , .markdown-preview-view video:hover {
  width: 100%;
  height:100%;
  max-width: min(100%, 80vw);
  max-height: min(100%, 80vh);
  outline: none;
  cursor: zoom-in;
}

/*file explorer columns view : slightly buggy ----*/
.nav-folder-children {
  column-width:150px;
  /*column-rule: 1px solid var(--text-accent);*/
}

/* file explorer :Wrap long nav text and some paddings */
.nav-file-title,
.nav-folder-title {
  white-space: normal;
  width: auto;
}

/* file explorer : Indent wrapped nav text */
.nav-file-title-content {
  margin-left: 0px;
  text-indent: 0px;
}
.nav-file-title-content.is-being-renamed {
  margin-left: 0px;
  text-indent: 0px;
}

/* Cursor color in normal vim mode and opacity */
.cm-fat-cursor .CodeMirror-cursor, .cm-animate-fat-cursor {
  width: 0.6em;
  background: #db9a1f;
  opacity: 60% !important;
}

/*an active line highlight in vim normal mode */
.cm-fat-cursor .CodeMirror-activeline .CodeMirror-linebackground{
  background-color: rgba(70, 142, 235, 0.20) !important;
}

/*if you want the highlight to present in both normal and insert mode of vim*/
.CodeMirror-activeline .CodeMirror-linebackground{
  background-color: rgba(70, 142, 235, 0.20) !important;
}

/*----file explorer smaller fonts & line height----*/
.nav-file-title,
.nav-folder-title {
  font-size: 13px;
  line-height: 14px;
  cursor: pointer;
  position: relative;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  border-image: initial;
  border-radius: 0px;
  padding: 1px 5px 0px 20px;
  color: var(--text-muted)
}

.nav-folder-title {
  font-weight: 600;
  color: var(--text-normal);
  opacity: 0.8;
}

/*---- nav arrows adjust location ----*/
.nav-folder-collapse-indicator {
  position: absolute;
  left: 8px;
  top: 4px;
  transition: transform 20ms linear 0s;
}

.nav-folder-collapse-indicator::after {
  position: absolute;
  content : "↓";
  left: 1px;
  top: -1px;
  font-size: 12px;
  color: var(--text-accent);
  transition: transform 10ms linear 0s;
}

.nav-folder-collapse-indicator svg {
  display: none;
  color:var(--accent-strong);
  height:7px;
  width:87x;
}

.nav-folder.is-collapsed .nav-folder-collapse-indicator {
  transform: translateX(1px) translateY(4px) rotate(-90deg);
}

::-webkit-scrollbar{
  background-color: transparent;
}

/* ======= graph view ==============*/
.graph-view.color-fill {
  color: var(--graph-circle);
}

.graph-view.color-circle {
  color: var(--tpsh);
}

.graph-view.color-line {
  color: var(--graph-line);
}

.graph-view.color-text {
  color: var(--tpwzys); 
}

.graph-view.color-fill-highlight {
  color: var(--interactive-accent);
}

.graph-view.color-line-highlight {
  color: rgb(var(--interactive-accent-rgb));
}

.graph-view.color-fill-tag {
  color: var(--graphtag) !important;
}

.graph-view.color-fill-attachment {
  color: var(--graph-attach) !important;
}
.graph-view.color-fill-unresolved {
  color: var(--graph-unresolved);
  opacity: 1;
}

.graph-view.color-arrow {
  color: var(--graph-arrow);
  opacity: 1;
}
```