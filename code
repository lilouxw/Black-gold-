<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stratégie de Combat</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
        }
        #map-container {
            width: 100vw;
            height: 100vh;
            overflow: auto;
            -webkit-overflow-scrolling: touch; /* Ensure smooth scrolling on iOS */
        }
        #map {
            width: 2000px; /* Adjust the width to fit the entire map */
            height: 2000px; /* Adjust the height to fit the entire map */
            background: url('https://github.com/lilouxw/Black-gold-/raw/main/map.jpg') no-repeat center center;
            background-size: cover;
            position: relative;
        }
        .unit {
            width: 50px;
            height: 50px;
            position: absolute;
            cursor: grab;
            border-radius: 50%;
            object-fit: cover;
            border: 2px solid white;
        }
    </style>
</head>
<body>
    <div id="map-container">
        <div id="map">
            <img src="player1.jpg" class="unit" style="top: 100px; left: 100px;" draggable="true" ondragstart="drag(event)" id="unit1">
            <img src="player2.jpg" class="unit" style="top: 200px; left: 200px;" draggable="true" ondragstart="drag(event)" id="unit2">
        </div>
    </div>
    
    <script>
        function drag(event) {
            event.dataTransfer.setData("text", event.target.id);
        }

        function touchMove(event) {
            let touch = event.touches[0];
            let element = document.elementFromPoint(touch.clientX, touch.clientY);
            if (element && element.classList.contains('unit')) {
                element.style.left = touch.clientX - 25 + 'px';
                element.style.top = touch.clientY - 25 + 'px';
            }
        }

        document.getElementById("map").addEventListener("dragover", function(event) {
            event.preventDefault();
        });

        document.getElementById("map").addEventListener("drop", function(event) {
            event.preventDefault();
            let data = event.dataTransfer.getData("text");
            let unit = document.getElementById(data);
            unit.style.left = event.clientX - 25 + "px";
            unit.style.top = event.clientY - 25 + "px";
        });

        document.getElementById("map-container").addEventListener("touchmove", function(event) {
            event.preventDefault();
            touchMove(event);
        });
    </script>
</body>
</html>