# Focus-Attention 集中注意力

## Focus On What you Originally Want To Do!!!——专注于你原本想做的事！！！

## 描述

开启学习模式，保持专注，保持注意力集中！！！

清除百度首页、搜素页的热搜内容、去除b站首页、播放页的推荐的相似视频和广告，防止被无关内容吸引注意力、忘记原本想干什么。

## 使用

复制以下代码到 油猴 (Tampermonkey) 中
```js
// ==UserScript==
// @name         Focus On What you Originally Want To Do!!!——专注于你原本想做的事！！！
// @namespace    http://dingdingdang.online/
// @version      0.2
// @description  清除百度首页、搜素页的热搜内容、去除b站首页、播放页的推荐内容
// @author       DingYigui
// @include      *://*.baidu.com/*
// @include      *://*.bilibili.com/*
// @require      https://cdn.staticfile.org/jquery/3.2.1/jquery.min.js
// @icon         https://dingdingdang.online/images/favicon_icon.jpg
// ==/UserScript==

//清除网页中会分散注意力的内容
function clear(){
    $("#s-hotsearch-wrapper").hide();//百度首页热搜内容清除
    $("#content_right").hide();//百度搜素页热搜内容清除
    $(".feed2").hide();// b站首页推荐内容清除
    $("#reco_list").hide();//b站视频播放页推荐内容清除
    $(".ad-report").hide();//b站视频播放页广告内容清除
    return clear;
}
//定时删除
var myInterval=null;
function autoClear(){
    myInterval && clearInterval(myInterval);
    myInterval = setInterval(clear(),1000);
}
$(document).ready(function() {
    autoClear();
});
```
