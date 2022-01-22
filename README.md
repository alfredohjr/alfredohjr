### Hi there 👋

Olá!!!

<div>
<canvas id="stage" width="300" height="300"></canvas>
<hr>
<p>Ponto:<p id="ponto"></p></p>
<p>X:<div id="ix"></div></p>
<p>Y:<p id="iy"></p></p>
<p>Obj1X:<p id="obj1x"></p></p>
<p>Obj1Y:<p id="obj1y"></p></p>

<script type="text/javascript">
    window.onload = function(){
        var stage = document.getElementById("stage");
        var ctx = stage.getContext("2d");

        setInterval(game,1);

        var x = 200;
        var y = 200;

        var obj1x = Math.round(Math.random()*260);
        var obj1y = Math.round(Math.random()*260);

        var ponto = 0;

        function game(){

            ctx.fillStyle = "blue";
            ctx.fillRect(0,0,stage.width,stage.height);

            ctx.fillStyle = "green";
            ctx.fillRect(obj1x,obj1y,20,20);

            if(x === obj1x & y === obj1y){
                obj1x = Math.round(Math.random()*260);
                obj1y = Math.round(Math.random()*260);
                ponto ++;
            }

            if(y < obj1y) {
                y++;
            } else if (y == obj1y) {

            } else {
                y--;
            }

            if(x < obj1x) {
                x++;
            } else if (x == obj1x) {

            } else {
                x--;
            }

            ctx.fillStyle = "yellow";
            ctx.fillRect(x,y,20,20);

            var ix = document.getElementById("ix");
            var iy = document.getElementById("iy");

            ix.innerHTML = x;
            iy.innerHTML = y;

            var iobj1x = document.getElementById("obj1x");
            var iobj1y = document.getElementById("obj1y");

            iobj1x.innerHTML = obj1x;
            iobj1y.innerHTML = obj1y;

            var iponto = document.getElementById("ponto");
            iponto.innerHTML = ponto;


        }

    }
</script>
</div>
