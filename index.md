<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<style type="text/css">
			canvas{
				animation: heart 0.3s infinite;
			}
			@keyframes heart{
				0%{width: 400px;height: 400px;}
				50%{width: 415px;height: 415px;}
				100%{width: 400px;height: 400px;}
			}
			
		</style>
	</head>
	<body>
		<canvas id="canvasId" width="400" height="400" style="margin: 50px auto;display: block;"></canvas>
		
		
		
		<script type="text/javascript">
			window.onload = function(){
				var canvas = document.getElementById("canvasId");
				var context = canvas.getContext("2d");
				
				drawHeart(context,200,200,50,30);
			}
			function drawHeart(context,x,y,R,rot){
				context.save();
				context.translate(x,y);
				context.rotate(rot/180*Math.PI);
				context.scale(R,R);
				heartPath(context);
				context.fillStyle = "red";
				context.shadowColor = 'gray';
				context.shadowOffsetX = 5;
				context.shadowOffsetY = 5;
				context.shadowBlur = 5;
				context.fill();
				context.restore();
			}
			
			function heartPath(context){
				context.beginPath();
				context.arc(-1,0,1,Math.PI,0,false);
				context.arc(1,0,1,Math.PI,0,false);
				context.bezierCurveTo(1.9, 1.2, 0.6, 1.6, 0, 3.0);
				context.bezierCurveTo(-0.6, 1.6,-1.9, 1.2,-2,0);
				context.closePath();
			}
		</script>
	</body>
</html>


