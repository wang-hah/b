# b
xinxin
//垂直方向内容滚动
sliderY(".choose-time", ".choose-time .box", 3, 1);
function sliderY(wrap, box, n, k) {
    var wrap = $(wrap);
    var box = $(box);
    var i = 0;
    var listH = box.find("li").outerHeight();
    var size = Math.ceil(box.find("li").size() / k);
    box.css({
        "height": listH * n
    });
    if (size < n || size == n) {
        wrap.find(".next").addClass("disabled");
    }
    wrap.find(".btn").click(function() {
        if ($(this).hasClass("disabled")) {
            return false
        } 
        else {
            if ($(this).hasClass("prev")) {
                i--
            } 
            else {
                i++
            }
            wrap.find(".btn").removeClass("disabled");
            if (size - i * n < n) {
                box.find("ul").stop().animate({
                    "margin-top": -size * listH + n * listH
                });
            } 
            else {
                box.find("ul").stop().animate({
                    "margin-top": -i * listH * n
                });
            }
            if (i == 0) {
                wrap.find(".prev").addClass("disabled");
            }
            if (i == Math.ceil(size / n - 1)) {
                wrap.find(".next").addClass("disabled");
            }
        }
    });
}

$(document).ready(function() {
    $(".honor-body .honor-content").load("ry/ry1.html");
    $(".honor-body .choose-time li").each(function(index) {
        $(this).click(function() {
            $(this).addClass("active").siblings().removeClass("active");
            if (index == 0) {
                $(".honor-body .honor-content").load("ry/ry1.html");
            } 
            
            else if (index == 1) {
                $(".honor-body .honor-content").load("ry/ry2.html");
            }

            else if (index == 2) {
                $(".honor-body .honor-content").load("ry/ry3.html");
            }

            else if (index == 3) {
                $(".honor-body .honor-content").load("ry/ry4.html");
            }

            else if (index == 4) {
                $(".honor-body .honor-content").load("ry/ry5.html");
            }

            else if (index == 5) {
                $(".honor-body .honor-content").load("ry/ry6.html");
            }

            else if (index == 6) {
                $(".honor-body .honor-content").load("ry/ry7.html");
            }

            else if (index == 7) {
                $(".honor-body .honor-content").load("ry/ry8.html");
            }

        });
    });
});




// 返回顶部
$(".go-top").click(function() {
	$("body,html").animate({
		"scrollTop": "0px"
	},
	300);
});
