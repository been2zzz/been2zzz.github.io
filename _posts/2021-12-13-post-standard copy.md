---
title: "Node.js 교과서 - 핵심 개념 이해하기"
excerpt_separator: "<!--more-->"
---

<html><head><meta http-equiv="Content-Type" content="text/html; charset=utf-8"/><title>핵심 개념 이해하기</title><style>
/* cspell:disable-file */
/* webkit printing magic: print all background colors */
html {
	-webkit-print-color-adjust: exact;
}
* {
	box-sizing: border-box;
	-webkit-print-color-adjust: exact;
}

html,
body {
	margin: 0;
	padding: 0;
}
@media only screen {
	body {
		margin: 2em auto;
		max-width: 900px;
		color: rgb(55, 53, 47);
	}
}

body {
	line-height: 1.5;
	white-space: pre-wrap;
}

a,
a.visited {
	color: inherit;
	text-decoration: underline;
}

.pdf-relative-link-path {
	font-size: 80%;
	color: #444;
}

h1,
h2,
h3 {
	letter-spacing: -0.01em;
	line-height: 1.2;
	font-weight: 600;
	margin-bottom: 0;
}

.page-title {
	font-size: 2.5rem;
	font-weight: 700;
	margin-top: 0;
	margin-bottom: 0.75em;
}

h1 {
	font-size: 1.875rem;
	margin-top: 1.875rem;
}

h2 {
	font-size: 1.5rem;
	margin-top: 1.5rem;
}

h3 {
	font-size: 1.25rem;
	margin-top: 1.25rem;
}

.source {
	border: 1px solid #ddd;
	border-radius: 3px;
	padding: 1.5em;
	word-break: break-all;
}

.callout {
	border-radius: 3px;
	padding: 1rem;
}

figure {
	margin: 1.25em 0;
	page-break-inside: avoid;
}

figcaption {
	opacity: 0.5;
	font-size: 85%;
	margin-top: 0.5em;
}

mark {
	background-color: transparent;
}

.indented {
	padding-left: 1.5em;
}

hr {
	background: transparent;
	display: block;
	width: 100%;
	height: 1px;
	visibility: visible;
	border: none;
	border-bottom: 1px solid rgba(55, 53, 47, 0.09);
}

img {
	max-width: 100%;
}

@media only print {
	img {
		max-height: 100vh;
		object-fit: contain;
	}
}

@page {
	margin: 1in;
}

.collection-content {
	font-size: 0.875rem;
}

.column-list {
	display: flex;
	justify-content: space-between;
}

.column {
	padding: 0 1em;
}

.column:first-child {
	padding-left: 0;
}

.column:last-child {
	padding-right: 0;
}

.table_of_contents-item {
	display: block;
	font-size: 0.875rem;
	line-height: 1.3;
	padding: 0.125rem;
}

.table_of_contents-indent-1 {
	margin-left: 1.5rem;
}

.table_of_contents-indent-2 {
	margin-left: 3rem;
}

.table_of_contents-indent-3 {
	margin-left: 4.5rem;
}

.table_of_contents-link {
	text-decoration: none;
	opacity: 0.7;
	border-bottom: 1px solid rgba(55, 53, 47, 0.18);
}

table,
th,
td {
	border: 1px solid rgba(55, 53, 47, 0.09);
	border-collapse: collapse;
}

table {
	border-left: none;
	border-right: none;
}

th,
td {
	font-weight: normal;
	padding: 0.25em 0.5em;
	line-height: 1.5;
	min-height: 1.5em;
	text-align: left;
}

th {
	color: rgba(55, 53, 47, 0.6);
}

ol,
ul {
	margin: 0;
	margin-block-start: 0.6em;
	margin-block-end: 0.6em;
}

li > ol:first-child,
li > ul:first-child {
	margin-block-start: 0.6em;
}

ul > li {
	list-style: disc;
}

ul.to-do-list {
	text-indent: -1.7em;
}

ul.to-do-list > li {
	list-style: none;
}

.to-do-children-checked {
	text-decoration: line-through;
	opacity: 0.375;
}

ul.toggle > li {
	list-style: none;
}

ul {
	padding-inline-start: 1.7em;
}

ul > li {
	padding-left: 0.1em;
}

ol {
	padding-inline-start: 1.6em;
}

ol > li {
	padding-left: 0.2em;
}

.mono ol {
	padding-inline-start: 2em;
}

.mono ol > li {
	text-indent: -0.4em;
}

.toggle {
	padding-inline-start: 0em;
	list-style-type: none;
}

/* Indent toggle children */
.toggle > li > details {
	padding-left: 1.7em;
}

.toggle > li > details > summary {
	margin-left: -1.1em;
}

.selected-value {
	display: inline-block;
	padding: 0 0.5em;
	background: rgba(206, 205, 202, 0.5);
	border-radius: 3px;
	margin-right: 0.5em;
	margin-top: 0.3em;
	margin-bottom: 0.3em;
	white-space: nowrap;
}

.collection-title {
	display: inline-block;
	margin-right: 1em;
}

.simple-table {
	margin-top: 1em;
	font-size: 0.875rem;
}

.simple-table-header {
	background: rgb(247, 246, 243);
	color: black;
	font-weight: 500;
}

time {
	opacity: 0.5;
}

.icon {
	display: inline-block;
	max-width: 1.2em;
	max-height: 1.2em;
	text-decoration: none;
	vertical-align: text-bottom;
	margin-right: 0.5em;
}

img.icon {
	border-radius: 3px;
}

.user-icon {
	width: 1.5em;
	height: 1.5em;
	border-radius: 100%;
	margin-right: 0.5rem;
}

.user-icon-inner {
	font-size: 0.8em;
}

.text-icon {
	border: 1px solid #000;
	text-align: center;
}

.page-cover-image {
	display: block;
	object-fit: cover;
	width: 100%;
	max-height: 30vh;
}

.page-header-icon {
	font-size: 3rem;
	margin-bottom: 1rem;
}

.page-header-icon-with-cover {
	margin-top: -0.72em;
	margin-left: 0.07em;
}

.page-header-icon img {
	border-radius: 3px;
}

.link-to-page {
	margin: 1em 0;
	padding: 0;
	border: none;
	font-weight: 500;
}

p > .user {
	opacity: 0.5;
}

td > .user,
td > time {
	white-space: nowrap;
}

input[type="checkbox"] {
	transform: scale(1.5);
	margin-right: 0.6em;
	vertical-align: middle;
}

p {
	margin-top: 0.5em;
	margin-bottom: 0.5em;
}

.image {
	border: none;
	margin: 1.5em 0;
	padding: 0;
	border-radius: 0;
	text-align: center;
}

.code,
code {
	background: rgba(135, 131, 120, 0.15);
	border-radius: 3px;
	padding: 0.2em 0.4em;
	border-radius: 3px;
	font-size: 85%;
	tab-size: 2;
}

code {
	color: #eb5757;
}

.code {
	padding: 1.5em 1em;
}

.code-wrap {
	white-space: pre-wrap;
	word-break: break-all;
}

.code > code {
	background: none;
	padding: 0;
	font-size: 100%;
	color: inherit;
}

blockquote {
	font-size: 1.25em;
	margin: 1em 0;
	padding-left: 1em;
	border-left: 3px solid rgb(55, 53, 47);
}

.bookmark {
	text-decoration: none;
	max-height: 8em;
	padding: 0;
	display: flex;
	width: 100%;
	align-items: stretch;
}

.bookmark-title {
	font-size: 0.85em;
	overflow: hidden;
	text-overflow: ellipsis;
	height: 1.75em;
	white-space: nowrap;
}

.bookmark-text {
	display: flex;
	flex-direction: column;
}

.bookmark-info {
	flex: 4 1 180px;
	padding: 12px 14px 14px;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
}

.bookmark-image {
	width: 33%;
	flex: 1 1 180px;
	display: block;
	position: relative;
	object-fit: cover;
	border-radius: 1px;
}

.bookmark-description {
	color: rgba(55, 53, 47, 0.6);
	font-size: 0.75em;
	overflow: hidden;
	max-height: 4.5em;
	word-break: break-word;
}

.bookmark-href {
	font-size: 0.75em;
	margin-top: 0.25em;
}

.sans { font-family: ui-sans-serif, -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, "Apple Color Emoji", Arial, sans-serif, "Segoe UI Emoji", "Segoe UI Symbol"; }
.code { font-family: "SFMono-Regular", Menlo, Consolas, "PT Mono", "Liberation Mono", Courier, monospace; }
.serif { font-family: Lyon-Text, Georgia, ui-serif, serif; }
.mono { font-family: iawriter-mono, Nitti, Menlo, Courier, monospace; }
.pdf .sans { font-family: Inter, ui-sans-serif, -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, "Apple Color Emoji", Arial, sans-serif, "Segoe UI Emoji", "Segoe UI Symbol", 'Twemoji', 'Noto Color Emoji', 'Noto Sans CJK JP'; }
.pdf:lang(zh-CN) .sans { font-family: Inter, ui-sans-serif, -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, "Apple Color Emoji", Arial, sans-serif, "Segoe UI Emoji", "Segoe UI Symbol", 'Twemoji', 'Noto Color Emoji', 'Noto Sans CJK SC'; }
.pdf:lang(zh-TW) .sans { font-family: Inter, ui-sans-serif, -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, "Apple Color Emoji", Arial, sans-serif, "Segoe UI Emoji", "Segoe UI Symbol", 'Twemoji', 'Noto Color Emoji', 'Noto Sans CJK TC'; }
.pdf:lang(ko-KR) .sans { font-family: Inter, ui-sans-serif, -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, "Apple Color Emoji", Arial, sans-serif, "Segoe UI Emoji", "Segoe UI Symbol", 'Twemoji', 'Noto Color Emoji', 'Noto Sans CJK KR'; }
.pdf .code { font-family: Source Code Pro, "SFMono-Regular", Menlo, Consolas, "PT Mono", "Liberation Mono", Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK JP'; }
.pdf:lang(zh-CN) .code { font-family: Source Code Pro, "SFMono-Regular", Menlo, Consolas, "PT Mono", "Liberation Mono", Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK SC'; }
.pdf:lang(zh-TW) .code { font-family: Source Code Pro, "SFMono-Regular", Menlo, Consolas, "PT Mono", "Liberation Mono", Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK TC'; }
.pdf:lang(ko-KR) .code { font-family: Source Code Pro, "SFMono-Regular", Menlo, Consolas, "PT Mono", "Liberation Mono", Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK KR'; }
.pdf .serif { font-family: PT Serif, Lyon-Text, Georgia, ui-serif, serif, 'Twemoji', 'Noto Color Emoji', 'Noto Serif CJK JP'; }
.pdf:lang(zh-CN) .serif { font-family: PT Serif, Lyon-Text, Georgia, ui-serif, serif, 'Twemoji', 'Noto Color Emoji', 'Noto Serif CJK SC'; }
.pdf:lang(zh-TW) .serif { font-family: PT Serif, Lyon-Text, Georgia, ui-serif, serif, 'Twemoji', 'Noto Color Emoji', 'Noto Serif CJK TC'; }
.pdf:lang(ko-KR) .serif { font-family: PT Serif, Lyon-Text, Georgia, ui-serif, serif, 'Twemoji', 'Noto Color Emoji', 'Noto Serif CJK KR'; }
.pdf .mono { font-family: PT Mono, iawriter-mono, Nitti, Menlo, Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK JP'; }
.pdf:lang(zh-CN) .mono { font-family: PT Mono, iawriter-mono, Nitti, Menlo, Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK SC'; }
.pdf:lang(zh-TW) .mono { font-family: PT Mono, iawriter-mono, Nitti, Menlo, Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK TC'; }
.pdf:lang(ko-KR) .mono { font-family: PT Mono, iawriter-mono, Nitti, Menlo, Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK KR'; }
.highlight-default {
	color: rgba(55, 53, 47, 1);
}
.highlight-gray {
	color: rgba(120, 119, 116, 1);
	fill: rgba(145, 145, 142, 1);
}
.highlight-brown {
	color: rgba(159, 107, 83, 1);
	fill: rgba(187, 132, 108, 1);
}
.highlight-orange {
	color: rgba(217, 115, 13, 1);
	fill: rgba(215, 129, 58, 1);
}
.highlight-yellow {
	color: rgba(203, 145, 47, 1);
	fill: rgba(203, 148, 51, 1);
}
.highlight-teal {
	color: rgba(68, 131, 97, 1);
	fill: rgba(108, 155, 125, 1);
}
.highlight-blue {
	color: rgba(51, 126, 169, 1);
	fill: rgba(91, 151, 189, 1);
}
.highlight-purple {
	color: rgba(144, 101, 176, 1);
	fill: rgba(167, 130, 195, 1);
}
.highlight-pink {
	color: rgba(193, 76, 138, 1);
	fill: rgba(205, 116, 159, 1);
}
.highlight-red {
	color: rgba(212, 76, 71, 1);
	fill: rgba(225, 111, 100, 1);
}
.highlight-gray_background {
	background: rgba(241, 241, 239, 1);
}
.highlight-brown_background {
	background: rgba(244, 238, 238, 1);
}
.highlight-orange_background {
	background: rgba(251, 236, 221, 1);
}
.highlight-yellow_background {
	background: rgba(251, 243, 219, 1);
}
.highlight-teal_background {
	background: rgba(237, 243, 236, 1);
}
.highlight-blue_background {
	background: rgba(231, 243, 248, 1);
}
.highlight-purple_background {
	background: rgba(244, 240, 247, 0.8);
}
.highlight-pink_background {
	background: rgba(249, 238, 243, 0.8);
}
.highlight-red_background {
	background: rgba(253, 235, 236, 1);
}
.block-color-default {
	color: inherit;
	fill: inherit;
}
.block-color-gray {
	color: rgba(120, 119, 116, 1);
	fill: rgba(145, 145, 142, 1);
}
.block-color-brown {
	color: rgba(159, 107, 83, 1);
	fill: rgba(187, 132, 108, 1);
}
.block-color-orange {
	color: rgba(217, 115, 13, 1);
	fill: rgba(215, 129, 58, 1);
}
.block-color-yellow {
	color: rgba(203, 145, 47, 1);
	fill: rgba(203, 148, 51, 1);
}
.block-color-teal {
	color: rgba(68, 131, 97, 1);
	fill: rgba(108, 155, 125, 1);
}
.block-color-blue {
	color: rgba(51, 126, 169, 1);
	fill: rgba(91, 151, 189, 1);
}
.block-color-purple {
	color: rgba(144, 101, 176, 1);
	fill: rgba(167, 130, 195, 1);
}
.block-color-pink {
	color: rgba(193, 76, 138, 1);
	fill: rgba(205, 116, 159, 1);
}
.block-color-red {
	color: rgba(212, 76, 71, 1);
	fill: rgba(225, 111, 100, 1);
}
.block-color-gray_background {
	background: rgba(241, 241, 239, 1);
}
.block-color-brown_background {
	background: rgba(244, 238, 238, 1);
}
.block-color-orange_background {
	background: rgba(251, 236, 221, 1);
}
.block-color-yellow_background {
	background: rgba(251, 243, 219, 1);
}
.block-color-teal_background {
	background: rgba(237, 243, 236, 1);
}
.block-color-blue_background {
	background: rgba(231, 243, 248, 1);
}
.block-color-purple_background {
	background: rgba(244, 240, 247, 0.8);
}
.block-color-pink_background {
	background: rgba(249, 238, 243, 0.8);
}
.block-color-red_background {
	background: rgba(253, 235, 236, 1);
}
.select-value-color-pink { background-color: rgba(245, 224, 233, 1); }
.select-value-color-purple { background-color: rgba(232, 222, 238, 1); }
.select-value-color-green { background-color: rgba(219, 237, 219, 1); }
.select-value-color-gray { background-color: rgba(227, 226, 224, 1); }
.select-value-color-orange { background-color: rgba(250, 222, 201, 1); }
.select-value-color-brown { background-color: rgba(238, 224, 218, 1); }
.select-value-color-red { background-color: rgba(255, 226, 221, 1); }
.select-value-color-yellow { background-color: rgba(253, 236, 200, 1); }
.select-value-color-blue { background-color: rgba(211, 229, 239, 1); }

.checkbox {
	display: inline-flex;
	vertical-align: text-bottom;
	width: 16;
	height: 16;
	background-size: 16px;
	margin-left: 2px;
	margin-right: 5px;
}

.checkbox-on {
	background-image: url("data:image/svg+xml;charset=UTF-8,%3Csvg%20width%3D%2216%22%20height%3D%2216%22%20viewBox%3D%220%200%2016%2016%22%20fill%3D%22none%22%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%3E%0A%3Crect%20width%3D%2216%22%20height%3D%2216%22%20fill%3D%22%2358A9D7%22%2F%3E%0A%3Cpath%20d%3D%22M6.71429%2012.2852L14%204.9995L12.7143%203.71436L6.71429%209.71378L3.28571%206.2831L2%207.57092L6.71429%2012.2852Z%22%20fill%3D%22white%22%2F%3E%0A%3C%2Fsvg%3E");
}

.checkbox-off {
	background-image: url("data:image/svg+xml;charset=UTF-8,%3Csvg%20width%3D%2216%22%20height%3D%2216%22%20viewBox%3D%220%200%2016%2016%22%20fill%3D%22none%22%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%3E%0A%3Crect%20x%3D%220.75%22%20y%3D%220.75%22%20width%3D%2214.5%22%20height%3D%2214.5%22%20fill%3D%22white%22%20stroke%3D%22%2336352F%22%20stroke-width%3D%221.5%22%2F%3E%0A%3C%2Fsvg%3E");
}
	
</style><article id="a5f6c452-1f45-4be0-87ee-9896d9898d78" class="page sans"><header><h1 class="page-title">핵심 개념 이해하기</h1></header><div class="page-body"><h2 id="8dfb309e-c509-40cb-9049-991766ed8753" class="">서버</h2><p id="78b9c482-ae15-450b-b9ab-ae75837c4df1" class="">네트워크를 통해 클라이언트에 정보나 서비스를 제공하는 컴퓨터 또는 프로그램</p><ul id="162bec80-2551-419b-8fce-a65a4f271a1f" class="bulleted-list"><li style="list-style-type:disc">클라이언트의 요청에 대한 응답</li></ul><hr id="d0186007-98a9-4fc7-b5ff-fb16f49f2727"/><h2 id="370c44ab-36d0-4cdb-8456-ee73ff3f08db" class="">자바스크립트 런타임</h2><ul id="178ecf28-21aa-46e7-b6b8-cd12abd3d09d" class="bulleted-list"><li style="list-style-type:disc">특정 언어로 만든 프로그램들을 실행할 수 있는 환경을 뜻함 (자바스크립트 실행기)</li></ul><ul id="d3994075-c993-47b1-974f-2529611f07aa" class="bulleted-list"><li style="list-style-type:disc">Node.js는  Chrome V8 Javascript 엔진으로 빌드</li></ul><figure id="62307489-c6fb-4f51-a6d9-59a42ba4d170" class="image"><a href="%E1%84%92%E1%85%A2%E1%86%A8%E1%84%89%E1%85%B5%E1%86%B7%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%8B%E1%85%B5%E1%84%92%E1%85%A2%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%2062307489c6fb4f51a6d959a42ba4d170/Untitled.png"><img style="width:432px" src="%E1%84%92%E1%85%A2%E1%86%A8%E1%84%89%E1%85%B5%E1%86%B7%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%8B%E1%85%B5%E1%84%92%E1%85%A2%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%2062307489c6fb4f51a6d959a42ba4d170/Untitled.png"/></a><figcaption>노드의 내부 구조</figcaption></figure><ul id="432545b8-e756-4dfe-a257-77220c0e41df" class="bulleted-list"><li style="list-style-type:disc">libuv 라이브러리<ul id="380b4849-7931-44b0-bc04-23150555a450" class="bulleted-list"><li style="list-style-type:circle">노드의 특성인 이벤트 기반, 논 블로킹 I/O 모델을 구현하고 있음</li></ul></li></ul><hr id="82687f5d-fef5-4e04-967b-379d8b759073"/><h2 id="a1033d16-7fed-41aa-ac85-90d0aefe80a9" class="">이벤트 기반</h2><p id="1e3f0349-e6f5-456c-8811-b227fa6ec73f" class="">이벤트가 발생할 때 미리 지정해둔 작업을 수행하는 방식</p><ul id="10f634b3-4e5a-4051-b8f3-6282675fda46" class="bulleted-list"><li style="list-style-type:disc">이벤트: 클릭이나, 네트워크 요청 등</li></ul><ul id="7f26b8c9-866d-4af6-bdca-84592c400191" class="bulleted-list"><li style="list-style-type:disc">특정 이벤트가 발생할 때 무엇을 할지 미리 등록<ul id="0d720997-8e66-4fc2-8167-0ca2fe56b44a" class="bulleted-list"><li style="list-style-type:circle">이벤트 리스너에 콜백함수를 등록한다고 표현</li></ul></li></ul><ul id="c3b0db46-2bdf-414d-bad8-1df99dcbdb9d" class="bulleted-list"><li style="list-style-type:disc">노드는 다음 이벤트가 발생할 때까지 대기함</li></ul><h3 id="c2adc785-5641-403b-a2b9-8731380c78ae" class="">이벤트 루프</h3><p id="30c6d4c4-0ed6-4691-ac17-b0a6259383fb" class="">여러 이벤트가 동시에 발생했을 때 어떤 순서로 호출할지 판단</p><p id="f77bfd0f-8119-4371-a5f4-ff9b248e0965" class="">⇒ 노드가 종료될 때까지 이벤트 처리를 위한 작업을 반복하므로 루프(loop)라고 부름</p><pre id="96c86bef-130e-46f8-bc6d-a791b1f84255" class="code"><code>function first() {
	second();
	console.log(&#x27;first&#x27;);
}
function second() {
	third();
	console.log(&#x27;second&#x27;);
}
function third() {
	console.log(&#x27;third&#x27;);
}
first(); // third second first</code></pre><figure id="79aceaca-c354-45de-94a6-faefea8e5a82" class="image"><a href="%E1%84%92%E1%85%A2%E1%86%A8%E1%84%89%E1%85%B5%E1%86%B7%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%8B%E1%85%B5%E1%84%92%E1%85%A2%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%2062307489c6fb4f51a6d959a42ba4d170/Untitled%201.png"><img style="width:442px" src="%E1%84%92%E1%85%A2%E1%86%A8%E1%84%89%E1%85%B5%E1%86%B7%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%8B%E1%85%B5%E1%84%92%E1%85%A2%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%2062307489c6fb4f51a6d959a42ba4d170/Untitled%201.png"/></a></figure><p id="def11bf7-a722-466e-925f-3f7a2970d4f4" class="">⇒ anonymous : 처음 실행 시 전역 컨텍스트(global context) 의미 <div class="indented"><p id="488e0bab-635f-4bc1-8035-64fdbd966f7f" class="">context: 함수가 호출되었을 때 생성되는 환경</p></div></p><pre id="eb6910c7-ba48-472e-ba15-cf221b531c89" class="code"><code>function run(){
	console.log(&#x27;3초 후 실행&#x27;);
}
console.log(&#x27;start&#x27;);
setTimeout(run, 3000);
console.log(&#x27;end&#x27;);

// start end 3초 후 실행</code></pre><ul id="8f478432-5069-4390-8a80-e902db2ca50e" class="bulleted-list"><li style="list-style-type:disc">백그라운드: setTimeout  같은 타이머나 이벤트 리스너들이 대기하는 곳, 여러 작업 동시 실행 가능</li></ul><ul id="7708a914-628f-42b6-9ab8-e1e679f7e5bc" class="bulleted-list"><li style="list-style-type:disc">태스크 큐: 이벤트 발생 후, 백그라운드에서 태스크 큐로 타이머나 이벤트 리스너의 콜백함수를 보냄. 정해진 순서대로 콜백들이 줄을 서 있어 콜백 큐라고도 부름. </li></ul><figure id="7ee35a93-7897-41ad-a395-18cc71d90391" class="image"><a href="%E1%84%92%E1%85%A2%E1%86%A8%E1%84%89%E1%85%B5%E1%86%B7%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%8B%E1%85%B5%E1%84%92%E1%85%A2%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%2062307489c6fb4f51a6d959a42ba4d170/Untitled%202.png"><img style="width:501px" src="%E1%84%92%E1%85%A2%E1%86%A8%E1%84%89%E1%85%B5%E1%86%B7%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%8B%E1%85%B5%E1%84%92%E1%85%A2%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%2062307489c6fb4f51a6d959a42ba4d170/Untitled%202.png"/></a><figcaption>setTimeout ⇒ anonymous ⇒ run 순으로 실행</figcaption></figure><h2 id="2a22ccd7-6c46-4f59-856b-2fdead72b914" class="">논 블로킹 I/O</h2><p id="042aa881-5be8-4f38-bdda-dd7fb96bfb3f" class="">노드는 I/O 작업을 백그라운드로 넘겨 동시에 처리함</p><p id="9a0d3642-8d2e-4469-ae5d-7a3c117fb278" class="">→ 동시에 처리될 수 있는 작업들은 최대한 묶어서 넘겨야 시간 절약</p><figure id="444ab8cf-3a84-4f1d-bc06-81ccaed30d34" class="image"><a href="%E1%84%92%E1%85%A2%E1%86%A8%E1%84%89%E1%85%B5%E1%86%B7%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%8B%E1%85%B5%E1%84%92%E1%85%A2%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%2062307489c6fb4f51a6d959a42ba4d170/Untitled%203.png"><img style="width:420px" src="%E1%84%92%E1%85%A2%E1%86%A8%E1%84%89%E1%85%B5%E1%86%B7%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%8B%E1%85%B5%E1%84%92%E1%85%A2%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%2062307489c6fb4f51a6d959a42ba4d170/Untitled%203.png"/></a></figure><h2 id="ba891b4d-26dd-4668-8808-9b85d460d549" class="">싱글 스레드</h2><ul id="739af5f5-fb17-42dc-9478-04ca59dcbce8" class="bulleted-list"><li style="list-style-type:disc">프로세스<ul id="aac1b3f4-a51b-4e5f-b6a3-1cb86567197d" class="bulleted-list"><li style="list-style-type:circle">운영체제에서 할당하는 작업의 단위</li></ul><ul id="28d606de-31ed-4c17-839d-e8346df5bd7b" class="bulleted-list"><li style="list-style-type:circle">노드나 웹 브라우저 같은 프로그램은 개별적인 프로세스</li></ul><ul id="7a620cd5-83c4-430e-aff7-62fbd0e55cfc" class="bulleted-list"><li style="list-style-type:circle">프로세스 간 메모리 등 자원 공유하지 않음</li></ul></li></ul><ul id="4228a25a-24ad-48ab-b6d8-38cd91c91ab3" class="bulleted-list"><li style="list-style-type:disc">스레드<ul id="43c1308c-1754-471c-a0c7-e0d3da1e6fd8" class="bulleted-list"><li style="list-style-type:circle">프로세스 내에서 실행되는 흐름의 단위</li></ul><ul id="48811dd2-cd27-4f70-a40c-d2d6fa0560cb" class="bulleted-list"><li style="list-style-type:circle">프로세스는 스레드를 여러개 생성해 여러 작업 동시 처리 가능</li></ul><ul id="f1ae6fcb-a3cf-48cd-aa2e-caf9311d6bad" class="bulleted-list"><li style="list-style-type:circle">부모 프로세스의 자원을 공유, 같은 주소의 메모리에 접근 간으하므로 데이터 공유 가능</li></ul></li></ul><ul id="06a8a68b-5d5b-487c-8fb1-eeccb5fda00d" class="bulleted-list"><li style="list-style-type:disc">노드 실행 시 프로세스 생성 그 후 내부적으로 스레드 여러 개 생성, 하지만 <strong>직접 제어할 수 있는 스레드는 하나뿐</strong></li></ul><ul id="936d6a70-e9e6-43e0-8960-7523fafeceac" class="bulleted-list"><li style="list-style-type:disc">스레드풀과 워커 스레드<ul id="587c82ed-5f56-4071-a91b-93499fa72d93" class="bulleted-list"><li style="list-style-type:circle">스레드풀 : 특정 동작 수행할 때 스스로 멀티 스레드 사용. 예) 암호화, 파일 입출력, 압축 등</li></ul><ul id="b64e02c0-8c17-4172-b835-7e5ebdb4c9c4" class="bulleted-list"><li style="list-style-type:circle">워커 스레드: 노드 12 버전에서 안정화된 기능으로 CPU 작업이 많은 경우 사용</li></ul><table id="2baf47ae-01e7-404f-b801-0de3c0641a00" class="simple-table"><thead><tr id="bca592fc-5559-4421-8306-d57e2ac2539d"><th id="vSJH" class="simple-table-header">멀티스레딩</th><th id="EpT:" class="simple-table-header">멀티 프로세싱</th></tr></thead><tbody><tr id="5855fc38-6923-4ac9-b923-78958b914b93"><td id="vSJH">하나의 프로세스 안 여러개 스레드</td><td id="EpT:">여러 개의 프로세스 사용</td></tr><tr id="a26327cb-6a7d-4110-ac25-36c83d62c1b5"><td id="vSJH">CPU 작업 많을 때</td><td id="EpT:">I/O 요청이 많을 때</td></tr><tr id="24604a12-de58-40d4-8854-5db7adcb3509"><td id="vSJH">프로그래밍이 어려움</td><td id="EpT:">프로그래밍 비교적 쉬움</td></tr></tbody></table></li></ul></div></article>