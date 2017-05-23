# Reaction-Tester
Calculates the reaction time taken by the user

<!DOCTYPE html>
<html>
<head>
	<title>
		JavaScrpit
	</title>
	<style type="text/css">
	body{
		background-color: #f4b042;
	}
	#shapes{
		
		display: "none";
		position: relative ;
		
	}	
	</style>
</head>
<body>
<p style="text-align: center;"><h1>Reaction Tester<h1></p>
<p> Your time taken: <span id="time"></span></p>
<div id="shapes"></div>
<script type="text/javascript">
	
	var start= window.performance.now();

	<!--Random Colour Generator-->
	function randomcolour(){
		var letter='0123456789ABCDEF';
		var color= '#';
        
        for(var i=0;i<6;i++){
        	color = color+ letter[(Math.floor(Math.random()*16))];
        }
        return color;
	}
	
	function makeShapesAppear()
	{   var rad=350;
		var width= Math.random()*rad;
		if(Math.random()<0.5){
			document.getElementById("shapes").style.borderRadius= "50%";
		}
		else{
			document.getElementById("shapes").style.borderRadius= "0";
		}
		document.getElementById("shapes").style.top= Math.random()*400+"px";
		document.getElementById("shapes").style.left= Math.random()*400+"px";
		document.getElementById("shapes").style.width= width+"px";
		document.getElementById("shapes").style.height= width+"px";
		document.getElementById("shapes").style.backgroundColor= randomcolour();
		document.getElementById("shapes").style.display="block";
		start = window.performance.now();
		}

	function delay()
	{
		setTimeout(makeShapesAppear,Math.random()*2000);
	}

	
	delay();
	
	document.getElementById("shapes").onclick= function()
	{
			document.getElementById("shapes").style.display= "none";
			var end= window.performance.now();
			var timeTaken=(end-start)/1000;
			
			document.getElementById("time").innerHTML= timeTaken+"s";
			delay();

	}



</script>

</body>
</html>
