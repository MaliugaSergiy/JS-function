# JS-function
1. Date Time Countdown Tutorial Christmas 2012 Doomsday
2. Countdown Timer Tutorial setTimeout clearTimeout
3. Smooth Auto Scroll 
4. countdowntimer

1. Date Time Countdown Tutorial Christmas 2012 Doomsday

<!DOCTYPE html>
<html>
<head>
<script>
function cdtd() {
	var xmas = new Date("December 25, 2012 00:01:00");
	var now = new Date();
	var timeDiff = xmas.getTime() - now.getTime();
	if (timeDiff <= 0) {
                clearTimeout(timer);
		document.write("Christmas is here!");
		// Run any code needed for countdown completion here
        }
	var seconds = Math.floor(timeDiff / 1000);
	var minutes = Math.floor(seconds / 60);
	var hours = Math.floor(minutes / 60);
	var days = Math.floor(hours / 24);
	hours %= 24;
        minutes %= 60;
        seconds %= 60;
	document.getElementById("daysBox").innerHTML = days;
	document.getElementById("hoursBox").innerHTML = hours;
	document.getElementById("minsBox").innerHTML = minutes;
	document.getElementById("secsBox").innerHTML = seconds;
	var timer = setTimeout('cdtd()',1000);
}
</script>
</head>
<body>
Days Remaining:
<div id="daysBox"></div>
Hours Remaining:
<div id="hoursBox"></div>
Minutes Remaining:
<div id="minsBox"></div>
Seconds Remaining:
<div id="secsBox"></div>
<script>cdtd();</script>
</body>
</html>


2. Countdown Timer Tutorial setTimeout clearTimeout
<script>
function countDown(secs,elem) {
	var element = document.getElementById(elem);
	element.innerHTML = "Please wait for "+secs+" seconds";
	if(secs < 1) {
		clearTimeout(timer);
		element.innerHTML = '<h2>Countdown Complete!</h2>';
		element.innerHTML += '<a href="#">Click here now</a>';
	}
	secs--;
	var timer = setTimeout('countDown('+secs+',"'+elem+'")',1000);
}
</script>
<div id="status"></div>
<script>countDown(10,"status");</script>


3. Smooth Auto Scroll 
<!DOCTYPE html>
<html>
<head>
<style>
div.contentbox {
	background: #FFF;
	height: 500px;
	margin: 20px;
	font-size: 28px;
	border: #CCC 1px dashed;
}
</style>
<script src="autoScrollTo.js"></script>
</head>
<body>
<h2 id="myheading">JavaScript Smooth Animated Auto Scroll Tutorial</h2>
<a href="#" onclick="return false;" onmousedown="autoScrollTo('div1');">
  Document Section 1</a><br />
<a href="#" onclick="return false;" onmousedown="autoScrollTo('div2');">
  Document Section 2</a><br />
<a href="#" onclick="return false;" onmousedown="autoScrollTo('div3');">
  Document Section 3</a><br />
<a href="#" onclick="return false;" onmousedown="autoScrollTo('div4');">
  Document Section 4</a><br />
<div id="div1" class="contentbox">Div 1 content...</div>
<a href="#" onclick="return false;" onmousedown="resetScroller('myheading');">
  go back to top</a>
<div id="div2" class="contentbox">Div 2 content...</div>
<a href="#" onclick="return false;" onmousedown="resetScroller('myheading');">
  go back to top</a>
<div id="div3" class="contentbox">Div 3 content...</div>
<a href="#" onclick="return false;" onmousedown="resetScroller('myheading');">
  go back to top</a>
<div id="div4" class="contentbox">Div 4 content...</div>
<a href="#" onclick="return false;" onmousedown="resetScroller('myheading');">
  go back to top</a>
</body>
</html>

var scrollY = 0;
var distance = 40;
var speed = 24;
function autoScrollTo(el) {
	var currentY = window.pageYOffset;
	var targetY = document.getElementById(el).offsetTop;
	var bodyHeight = document.body.offsetHeight;
	var yPos = currentY + window.innerHeight;
	var animator = setTimeout('autoScrollTo(\''+el+'\')',24);
	if(yPos > bodyHeight){
		clearTimeout(animator);
	} else {
		if(currentY < targetY-distance){
		    scrollY = currentY+distance;
		    window.scroll(0, scrollY);
	    } else {
		    clearTimeout(animator);
	    }
	}
}
function resetScroller(el){
	var currentY = window.pageYOffset;
    var targetY = document.getElementById(el).offsetTop;
	var animator = setTimeout('resetScroller(\''+el+'\')',speed);
	if(currentY > targetY){
		scrollY = currentY-distance;
		window.scroll(0, scrollY);
	} else {
		clearTimeout(animator);
	}
}



4. https://www.npmjs.com/package/countdowntimer
