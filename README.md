# Black-gold- 


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
        #map {
            width: 100vw;
            height: 100vh;
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
    <div id="map">
        <img src="player1.jpg" class="unit" style="top: 100px; left: 100px;" draggable="true" ondragstart="drag(event)" id="unit1">
        <img src="player2.jpg" class="unit" style="top: 200px; left: 200px;" draggable="true" ondragstart="drag(event)" id="unit2">
    </div>
    
    <script>
        function drag(event) {
            event.dataTransfer.setData("text", event.target.id);
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
    </script>
</body>
</html>
