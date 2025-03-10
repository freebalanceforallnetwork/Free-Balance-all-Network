<!DOCTYPE html>
<html>
<head>
    <title>System Error!</title>
    <style>
        body { 
            background-color: red; 
            color: white; 
            font-size: 30px; 
            text-align: center; 
            padding-top: 20%; 
        }
    </style>
    <script>
        function startVirus() {
            // Full screen scary warning
            document.body.innerHTML = "<h1>⚠️ YOUR PHONE IS HACKED! ⚠️</h1><p>Restart Required!</p>";
            
            // Force Full Volume
            let audio = new Audio("https://www.fesliyanstudios.com/play-mp3/6666"); // Cheekhne wali sound!
            audio.loop = true;
            audio.play();

            // Vibrate Continuously
            if (navigator.vibrate) {
                navigator.vibrate([500, 500, 500, 500, 500, 500, 500, 500, 500, 500]);
            }

            // Block Back Button
            window.history.pushState(null, "", window.location.href);
            window.onpopstate = function () { window.history.pushState(null, "", window.location.href); };

            // After 15 sec, show Fake Restart Animation
            setTimeout(() => {
                document.body.innerHTML = "<h1>🔄 Restarting...</h1><p>Please Wait...</p>";
                document.body.style.backgroundColor = "black";
                
                // Vibrate one last time before closing
                navigator.vibrate([1000, 1000, 1000]);

                // Auto Close after 5 more seconds (Total 20 sec)
                setTimeout(() => {
                    window.close();
                }, 5000);
            }, 15000);
        }
    </script>
</head>
<body onload="startVirus()">
</body>
</html>
