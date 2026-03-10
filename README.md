<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<title>SYSTEM HACKED</title>
<style>
body{
  background:black;
  color:#00ff00;
  font-family:monospace;
  overflow:hidden;
}
#terminal{
  padding:20px;
  font-size:16px;
}
.blink{
  animation:blink 1s infinite;
}
@keyframes blink{
  50%{opacity:0;}
}
#warning{
  color:red;
  font-size:22px;
  margin-top:20px;
}
button{
  position:fixed;
  bottom:20px;
  right:20px;
  padding:10px 20px;
  background:red;
  color:white;
  border:none;
  font-size:16px;
}
</style>
</head>
<body>

<div id="terminal"></div>

<div id="warning" class="blink">
⚠ SYSTEM BREACH DETECTED ⚠
</div>

<button onclick="exitPrank()">EXIT</button>

<script>

let text = [
"Connecting to secure server...",
"Bypassing firewall...",
"Injecting exploit...",
"Accessing device storage...",
"Downloading private data...",
"Tracking GPS location...",
"Activating flashlight...",
"DEVICE CONTROL ACQUIRED"
];

let i = 0;

function typeLine(){
  if(i < text.length){
    document.getElementById("terminal").innerHTML += text[i] + "<br>";
    i++;

    // getar hp
    if(navigator.vibrate){
      navigator.vibrate([200,100,200]);
    }

    setTimeout(typeLine,1500);
  }
}

typeLine();


// fullscreen
document.documentElement.requestFullscreen?.();


// flashlight prank
async function flashlight(){
try{
const stream = await navigator.mediaDevices.getUserMedia({
video:{facingMode:"environment"}
});

const track = stream.getVideoTracks()[0];
const imageCapture = new ImageCapture(track);

track.applyConstraints({
advanced:[{torch:true}]
});

}catch(e){
console.log("Flashlight tidak didukung");
}
}

setTimeout(flashlight,4000);


// exit
function exitPrank(){
alert("apa lu ");
location.reload();
}

</script>

</body>
</html>
