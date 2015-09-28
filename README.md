# mouse_coord

<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8" />
<title>mouse coordinates</title>
<style>
	html, body {
		width: 100%;
		height: 100%;
		padding: 0;
		margin: 0;
	}
	body {
		background-color: rgba(100,100,100,0.2);
		overflow: hidden;
	}

	#wrapper {
		width: 100%;
		min-height: 100%;
		margin: 0 auto;
		position: relative;
	}

	#pp {
		width: 100px;
		height: 100px;
		background-color: rgba(100,0,0,0.3);
		position: absolute;
		bottom: 0;
		left: 0;
		right: 0;
		margin: 0 auto;
	}

	svg {
		outline: 1px solid blue;
		position: absolute;
		bottom: 0;
		left: 0;
		right: 0;
		margin: 0 auto;
		width: 100%;
		height: 100%;
	}
</style>
</head>

<body>
	<div id="wrapper" onmousemove="coords(event)" onmouseout="clear_coords()">
		<p id="disp"></p>
		<p id="pp_size"></p>
		<div id="pp"></div>
		<svg id="mysvg" width="300" height="300">
			<polyline points="0,0 150,150, 230,100 300,450 400,350" style="fill:none;stroke:#ccc;stroke-width:1" />
		</svg>
	</div><!--/#wrapper-->
	<script>
	/*var rand_num = 1;
	setInterval(function(){
		rand_num = Math.floor(Math.random()*10);
	}, 1000);*/

		function coords(test) {
			//coordinates of mouse pointer relative to window size in pixels
			var x = test.clientX;
			var y = test.clientY;

			//width and height of window
			var win_width = document.getElementById("wrapper").offsetWidth;
			var win_height = document.getElementById("wrapper").offsetHeight;

			//center point relative to viewport
			var x_center = win_width / 2;

			var y_initial = win_height - 100;
			var y_initial2 = win_height - 50;
			var y_initial3 = win_height - 75;
			var y_initial4 = win_height - 60;

			
			var win_width_half = x_center + ((x-x_center)/2);
			var y_rand = y_initial - 5;

			//coordinates in percentage
			var x_per = (x/win_width)*100;
			var y_per = (y/win_height)*100;

			//coordinates in percentage divided by 100
			var x_per_dec = (x/win_width);
			var y_per_dec = (y/win_height);

			//x,y value converted by percentage
			//var x_con = x*x_per_dec;
			var x_con = x_center + (x - x_center);

			if(x_con <= x_center) {
				x_con = x_center;
			}



			var x_rev = x - (x - x_center);





			var y_con = y*y_per_dec;

			var x_con_mid0 = x_center + ((x - x_center)/4);

			if(x_con_mid0 <= x_center) {
				x_con_mid0 = x_center;
			}

			var x_con_mid1 = x_center + ((x - x_center)/3);

			if(x_con_mid1 <= x_center) {
				x_con_mid1 = x_center;
			}

			var x_con_mid2 = x_center + ((x - x_center)/2);

			if(x_con_mid2 <= x_center) {
				x_con_mid2 = x_center;
			}

			var x_con_mid3 = x_center + (((x - x_center)/3)*2);

			if(x_con_mid3 <= x_center) {
				x_con_mid3 = x_center;
			}

			var x_con_mid4 = x_center + (((x - x_center)/4)*3);

			if(x_con_mid4 <= x_center) {
				x_con_mid4 = x_center;
			}

			var rand_num0 = Math.floor(Math.random()*15);
			var rand_num1 = Math.floor(Math.random()*15);
			var rand_num2 = Math.floor(Math.random()*15);
			var rand_num3 = Math.floor(Math.random()*15);
			var rand_num4 = Math.floor(Math.random()*15);
			var rand_num5 = Math.floor(Math.random()*15);
			var rand_num6 = Math.floor(Math.random()*15);
			var rand_num7 = Math.floor(Math.random()*15);
			var rand_num8 = Math.floor(Math.random()*15);
			var rand_num9 = Math.floor(Math.random()*15);
			var rand_num10 = Math.floor(Math.random()*15);
			var rand_num11 = Math.floor(Math.random()*15);
			var rand_num12 = Math.floor(Math.random()*15);
			var rand_num13 = Math.floor(Math.random()*15);
			var rand_num14 = Math.floor(Math.random()*15);
			var rand_num15 = Math.floor(Math.random()*15);
			var rand_num16 = Math.floor(Math.random()*15);
			var rand_num17 = Math.floor(Math.random()*15);
			var rand_num18 = Math.floor(Math.random()*15);
			var rand_num19 = Math.floor(Math.random()*15);

			var x_rev = x;

			
			document.getElementById("disp").innerHTML = "Coordinates relative to viewport<br>X coords: " + x + "<br>Y coords: " + y + "<br><br>Coordinates in Percentage relative to viewport<br>(X%): "+ x_per + "<br>(Y%): " + y_per + "<br><br>(X decimal): " + x_per_dec + "<br>(Y decimal): " + y_per_dec + "<br><br>Viewport Size<br>Viewport X Width: " + win_width + "<br>Viewport Y Height: " + win_height + "<br><br>X center: " + x_center + "<br>Y initial: " + y_initial + "<br><br>x converted: " + x_con + "<br>y converted: " + y_con;

			var line_input_1 = '<polyline points="' + x_center + ',' + y_initial + ' ' + x_con_mid0 + ',' + ((y_initial-5)+rand_num0) + ' ' + x_con_mid1 + ',' + ((y_initial-5)+rand_num1) + ' ' + x_con_mid2 + ',' + ((y_initial-5)+rand_num2) + ' ' + x_con_mid3 + ',' + ((y_initial-5)+rand_num3) + ' ' + x_con_mid4 + ',' + ((y_initial-5)+rand_num4) + ' ' + (x_con-10) + ',' + (y_initial-25) + '" style="fill:none;stroke:#000;stroke-width:15" />';
			var line_input_2 = '<polyline points="' + (x_center+50) + ',' + y_initial2 + ' ' + x_con_mid0 + ',' + ((y_initial2-5)+rand_num5) + ' ' + x_con_mid1 + ',' + ((y_initial2-5)+rand_num6) + ' ' + x_con_mid2 + ',' + ((y_initial2-5)+rand_num7) + ' ' + x_con_mid3 + ',' + ((y_initial2-5)+rand_num8) + ' ' + x_con_mid4 + ',' + ((y_initial2-5)+rand_num9) + ' ' + (x_con-5) + ',' + y_initial2 + '" style="fill:none;stroke:#000;stroke-width:15" />';
			var line_input_3 = '<polyline points="' + (x_center+50) + ',' + y_initial3 + ' ' + x_con_mid0 + ',' + ((y_initial3-5)+rand_num10) + ' ' + x_con_mid1 + ',' + ((y_initial3-5)+rand_num11) + ' ' + x_con_mid2 + ',' + ((y_initial3-5)+rand_num12) + ' ' + x_con_mid3 + ',' + ((y_initial3-5)+rand_num13) + ' ' + x_con_mid4 + ',' + ((y_initial3-5)+rand_num14) + ' ' + (x_con-20) + ',' + (y_initial3+15) + '" style="fill:none;stroke:#000;stroke-width:15" />';
			var line_input_4 = '<polyline points="' + (x_center+50) + ',' + y_initial4 + ' ' + x_con_mid0 + ',' + ((y_initial4-5)+rand_num15) + ' ' + x_con_mid1 + ',' + ((y_initial3-4)+rand_num16) + ' ' + x_con_mid2 + ',' + ((y_initial4-5)+rand_num17) + ' ' + x_con_mid3 + ',' + ((y_initial4-5)+rand_num18) + ' ' + x_con_mid4 + ',' + ((y_initial4-5)+rand_num19) + ' ' + (x_con-10) + ',' + (y_initial4+40) + '" style="fill:none;stroke:#000;stroke-width:15" />';
			var line_input_5 = '<polyline points="' + (x_center+35) + ',' + y_initial + ' ' + x_con_mid0 + ',' + ((y_initial4-65)+rand_num15) + ' ' + x_con_mid1 + ',' + ((y_initial3-85)+rand_num16) + ' ' + x_con_mid2 + ',' + ((y_initial4-100)+rand_num17) + ' ' + x_con_mid3 + ',' + ((y_initial4-130)+rand_num18) + ' ' + x_con_mid4 + ',' + ((y_initial4-155)+rand_num19) + ' ' + (x_con-30) + ',' + (y_initial4-160) + '" style="fill:none;stroke:#000;stroke-width:15" />';
			var line_input_6 = '<polyline points="' + (x_center+60) + ',' + y_initial + ' ' + x_con_mid0 + ',' + ((y_initial4-85)+rand_num15) + ' ' + x_con_mid1 + ',' + ((y_initial3-105)+rand_num16) + ' ' + x_con_mid2 + ',' + ((y_initial4-135)+rand_num17) + ' ' + x_con_mid3 + ',' + ((y_initial4-155)+rand_num18) + ' ' + x_con_mid4 + ',' + ((y_initial4-175)+rand_num19) + ' ' + (x_con-60) + ',' + (y_initial4-200) + '" style="fill:none;stroke:#000;stroke-width:15" />';
			var line_input_7 = '<polyline points="' + x_center + ',' + y_initial + ' ' + x_rev + ',' + (y_initial-25) + '" style="fill:none;stroke:#f00;stroke-width:15" />';
			document.getElementById("mysvg").innerHTML = line_input_1 + line_input_2 + line_input_3 + line_input_4 + line_input_5 + line_input_6 + line_input_7;

		}

		function clear_coords() {
			var win_width = document.getElementById("wrapper").offsetWidth;
			var win_height = document.getElementById("wrapper").offsetHeight;
			document.getElementById("disp").innerHTML = "X coords: 0<br>Y coords: 0<br>X Width: " + win_width + "<br>Y Height: " + win_height;
		}

	</script>
</body>
</html>
