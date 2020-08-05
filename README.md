# ClockK
<!DOCTYPE html>
<html>
    <head>
        <title>JS - Digital Clock</title>
        <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Orbitron" rel="stylesheet" 
        type="text/css">
        <style type="text/css">
        body{
            background: #000;
        }
        .clock{
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translateX(-50%) translateY(-50%);
            color: #17d4fe;
            font-family: Orbitron;
            letter-spacing: 7px;
            font-weight: bold;
            font-size: 80px;
        }
        </style>
    </head>
    <body>
        <div id="MyClockDisplay" class="clock"></div>
        <script type="text/javascript">
        
        function showTime(){
            var date = new Date();
            var h = date.getHours(); // 0 - 23
            var m = date.getMinutes(); // 0 - 59
            var s = date.getSeconds(); // 0 - 59
            var session = "AM";

            if(h == 0){
                h = 12;
            }

            if(h > 12){
                h = h -12;
                session = "PM";
            }

            h = (h < 10) ? "" + h : h;
            m = (m < 10) ? "0" + m : m;
            s = (s < 10) ? "0" + s : s;

            var time = h + ":" + m + ":" + s + " " + session;
            document.getElementById("MyClockDisplay").innerText = time;
            document.getElementById("MyClockDisplay").textContent = time;

            setTimeout(showTime, 1000);1
        }

        showTime();

        </script>
    </body>
</html>
