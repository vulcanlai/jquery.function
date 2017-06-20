jQuery function
===
jquery 初始架構及各類事件


#### 預設架構
~~~
$(document).ready(function() {
})

$(function() {
})
~~~


#### load 事件，載入頁面完成後執行
~~~
$(window).on("load", function(event) {
});
~~~


#### scroll 事件，捲軸改變
~~~
$(window).on("scroll", function(event) {
});
~~~


#### resize 事件，視窗尺寸改變 頁面重新整理
~~~
$(window).on("resize", function(event) {
});
$(window).resize(function() {
});
var width = $(window).width(), height = $(window).height();
if ($(window).width() != width && $(window).height() != height) {
    //Do something
}
~~~

~~~
$(window).bind({
    load: function() {
    },
    resize: function() {
    },
    scroll: function() {
    }
});
~~~

~~~
$(window).on({
    load: function() {
    },
    resize: function() {
    },
    scroll: function() {
    }
});
~~~

~~~
$(function() {
    $(window).load(function() {
        $(window).bind('scroll resize', function() {
        }).scroll();
    });
});
~~~


#### 各類事件 load || scroll || resize || orientationchange
~~~
$(window).on("orientationchange", function(event) {
});

//載入頁面完成後執行、改變視窗尺寸、捲軸改變：
$(window).on("load resize scroll", function(e) {
})
~~~


#### resize 頁面重新整理
~~~
window.onresize = function() {
    location = location
};

//移動載具 旋轉後 重整頁面
$(window).on("orientationchange", function(event) {
    location.reload();
});
~~~


#### 點擊事件
~~~
$('#BUTTON').click(function(){
})

$('#CONTAINER').on('click', '#BUTTON', function(){
});
~~~


#### 迴圈
~~~
$(function(){
	for (var i = 0; i < 5; i++) { // 跑五次迴圈
		if(i === 2) { // i 迴圈到 2 時
			return false; // 以下停止
		}
		console.log(i);
	}
})
~~~
