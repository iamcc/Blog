---
title: Sublime text 3 配置
date: 2016-02-17 16:29:50
tags: [sublime, editor, exp, tools]
categories: tools
---


> 此文是基于`Mac`下的`Sublime text 3`版本的插件配置，不保证兼容`Sublime text 2`。

<!-- more -->


## 插件
名称 | 说明
--- | ---
Package Control | 安装插件必备，[下载](https://packagecontrol.io/installation)
AutoFileName | 文件路径提示
Babel | ES6 代码高亮
Babel Snippets | ES6 代码提示
BracketHighlighter | 括号和标签的高亮
CSS3 | CSS3 代码提示
CSScomb | CSS 代码格式化
DocBlockr | 快速生成注释文档
Emmet | 快速编写 html
FileHeader | 自动生成文件头
Git | Git 工具（需要安装Git）
HTML5 | HTML5 帮助插件
jQuery | jQuery api 提示
JSCS-Formatter | js 格式化插件（需要安装 jscs `npm i -g jscs`）
LESS | less 代码高亮
SFTP | ftp 插件
SideBarEnhancements | 侧边栏增强插件
SublimeCodeIntel | 代码提示插件
SublimeLinter | 代码格式检查基础插件
SublimeLinter-contrib-eslint | eslint 代码格式检查插件（需要安装eslint@1 `npm i -g eslint@1`）
SublimeLinter-json | json 格式检查
SVN | svn 插件
Terminal | 快速打开命令行
TrailingSpaces | 自动删除多余的空格
Volt | Volt 文件高亮
Vue Syntax Highlight | vue 文件代码高亮

## 皮肤
推荐一套看起来比较舒服的皮肤`Seti_UI`

## Sublime 配置文件
```
{
	"Seti_SB_big": true,
	"Seti_SB_med": true,
	"Seti_no_blue_bar": true,
	"Seti_tabs_med": true,
	"Seti_tabs_small": true,
	"additional_path_items":
	[
		"/usr/local/bin"
	],
	"always_show_minimap_viewport": true,
	"bold_folder_labels": true,
	"color_scheme": "Packages/User/SublimeLinter/Oceanic Next (SL).tmTheme",
	"default_line_ending": "unix",
	"ensure_newline_at_eof_on_save": true,
	"font_face": "Fira Mono",
	"ignored_packages":
	[
		"JavaScript",
		"Markdown",
		"Vintage"
	],
	"line_padding_bottom": 3,
	"line_padding_top": 3,
	"overlay_scroll_bars": "enabled",
	"tab_size": 2,
	"theme": "Seti.sublime-theme",
	"translate_tabs_to_spaces": true,
	"trim_trailing_white_space_on_save": true,
	"word_wrap": "false"
}
```
> 注意这里我用到`Fira Mono`字体，没有的可以去下载安装，等宽字体，看起来比较舒服。

## 如何让 Sublime 帮我检查代码格式
1. `npm i -g eslint@1 eslint-config-airbnb eslint-plugin-react`
2. 在项目根目录创建`.eslintrc`文件内容
```
{
  "extends": "airbnb"
}
```
3. 现在只要在`Sublime`编写`javascript`就会提示错误了。
