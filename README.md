<html lang="en">
    <head>
        <title>Stopwatch</title>
        <style>
            body{
                background-color: darkslateblue;
                display: flex;
                justify-content: center;
                align-items: center;
                height: 100vh;
            }
            #container{
                /* width: 500vw; */
                text-align: center;
                padding: 20px;
                /* background-color: aliceblue; */
            }
            .number{
                font-size: 150px;
                font-weight: bold;
                color: gold;
            }
            .txt{
                font-size: 40px;
                font-weight: bold;
                color: gold;
            }
            #buttons{
                margin-top: 50px;
            }
            .btn{
                padding: 5px;
                width: 80px;
                font-weight: bold;
                margin-right: 7px;
                cursor: pointer;
            }
            #start{
                background-color: #41b341;
                color: white;
                border: 0px;
            }
            #stop{
                background-color: #F64C72;
                color: white;
                border: 0px;
            }
            #reset{
                background-color: #659DBD;
                color: white;
                border: 0px;
            }
            .container-lg{
                display: hidden !important;
            }
        </style>
    </head>
    <body>
        <div id="container">
            <span class="number" id="hr">00</span>
            <span class="txt" id="hr-txt">Hr</span>
            <span class="number" id="min">00</span>
            <span class="txt" id="min-txt">Min</span>
            <span class="number" id="sec">00</span>
            <span class="txt" id="sec-txt">Sec</span>
            <span class="number" id="count">00</span>
            <div id="buttons">
                <button class="btn" id="start" onclick="myStart()">Start</button>
                <button class="btn" id="stop" onclick="myStop()">Stop</button>
                <button class="btn" id="reset" onclick="myReset()">Reset</button>
            </div>
        </div>
        <script>
            let hr=0;
            let min=0;
            let sec=0;
            let count=0;
            let timer=false;
            function myStart(){
                timer=true;
                stopWatch();
            }
            function myStop(){
                timer=false;
            }
            function myReset(){
                timer=false;
                hr=0;
                min=0;
                sec=0;
                count=0;
                document.getElementById('count').innerHTML='0'+count;
                document.getElementById('sec').innerHTML='0'+sec;
                document.getElementById('min').innerHTML='0'+min;
                document.getElementById('hr').innerHTML='0'+hr;
            }
            function stopWatch(){
                if(timer){
                    count+=1;
                    if(count==100){
                        sec+=1;
                        count=0;
                    }
                    if(sec==60){
                        min+=1;
                        sec=0;
                    }
                    if(min==60){
                        hr+=1;
                        min=0;
                    }
                    document.getElementById('count').innerHTML=count;
                    if(sec<10){
                        document.getElementById('sec').innerHTML='0'+sec;
                    }else{
                        document.getElementById('sec').innerHTML=sec;
                    }
                    if(min<10){
                        document.getElementById('min').innerHTML='0'+min;
                    }else{
                        document.getElementById('min').innerHTML=min;
                    }
                    if(hr<10){
                        document.getElementById('hr').innerHTML='0'+hr;
                    }else{
                        document.getElementById('hr').innerHTML=hr;
                    }
                    setTimeout("stopWatch()",7);
                }
            }
        </script>
    </body>
</html>
