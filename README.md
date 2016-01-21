# js总结

按照原计划在1.17-1.21是应该完成js的学习的 然而由于高估了自己的能力 并没有很好地完成自己的既定目标。在以后的学习中要加强对js的理解。
//每日一练 拖拽

<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<link rel="stylesheet"  href="index.css">
</head>
<style>
	*{
	margin: 0;
	padding: 0;
	}
	#div1{
		width: 100px;
		height: 100px;
		background: red;
		position: absolute;
	}
</style>
<body>
	<p>aaaaaaaaaaaaaaaaaaaaaaaaaaaaaa</p>
	<div id="div1"></div>

	<script type="text/javascript">
		var oDiv = document.getElementById('div1');
		oDiv.onmousedown = function(e){
			e = e || window.event;
			var iDisX = e.clientX - oDiv.offsetLeft;
			var iDisY = e.clientY - oDiv.offsetTop;

			document.onmousemove = function(e){
				e = e || window.event;
				oDiv.style.left = e.clientX - iDisX +'px';
				oDiv.style.top = e.clientY - iDisY + 'px';
				
				if(e.preventDefault){
					e.preventDefault();
				}else{
					e.returnValue = false;
				}
			};
			oDiv.onmouseup = function(){
				document.onmousemove = null;
			};
		};
	</script>
</body>
</html>
