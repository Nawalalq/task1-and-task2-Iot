# task1-and-task2-Iot
task1:strps ESP32 task2:Programming a web page

# task1:Writing a wisdom ESP32 operating algorithm

 1- Download Arduino IDE 2. To know the ESP32 bit 2-Click on File at the top and then click on Preferences 3- Add the following command:
 https://dl.espressif.com/dl/package_esp32_index.json

 4- Then click on OK

 2- Click on tools, then choose Arduino uno, then click on board manager, then a screen appears, type ESP32, then press Enter, then it will be loaded.

 4- If we go to the port, we find the ESP32 Arduino - the ESP32 piece is connected to the USB wire - to connect we click on the tools panel
 
 5- Selecting the Arduino uno, then selecting the ESP32 Arduino
 
 6- Then choose this type of WEMOS D1 MINI ESP32 controller.
 
 7- Then we go to tools and connect to a piece
 By going to … “com3” and then clicking on port “com3 .”
 
 code Task1:
 <html>
<head> <title></title>
link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/twitter-> </"bootstrap/4.6.0/css/bootstrap.min.css
<head/>
<"body class="bg-primary>
<"div class="container>
<"div class="row>
<"div class="col-md-8 offset-2>
<"div class="card mt-4>
<"div class="card-header>
<"div class="row>
<"div class="col-md-12>
<h5>Speech to Text in Javascript</h5>
<div/>
<div/>
<div/>
<"div class="card-body>
<"div class="row>
<"div class="col-md-12>
<"div class="form-group>
<"textarea name="" readonly id="textbox" rows="6" class="form-control> <textarea/>
<div/>
<div/>
<"div class="col-md-12>
<button id="start-btn" class="btn btn-success btn-block">Start</button>
button id="create" class="btn btn-danger btn-block" style="display: > <none">End</button

<div/>
<div/>
<div/>
<"div class="card-footer> <"div class="row>
<"div class="col-md-12>
<p id="instration">Press Start Voice Recognition</p>
a>
<a\
<div/>
<div/>
<div/>
<div/>
<div/>
<div/>
<div/>
script > <src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script
<script type="text/javascript" src="script.js"></script>
< script>
;var SpeechRecogntion = window.webkitSpeechRecognition
;()var recognition = new window.SpeechRecogntion ;var textbox = $('#textbox')
;var instration = $('#instration')
;'' = var content

recognition.continuous = true
}() recognition.onstart = function instration.text('Voice Recognition is on') {
}() recognition.onspeechend = function ;instration.text('No Activity')
{
}recognition.onerror = function (event) ;instration.text('Try Again') ;console.log(event)
{
} recognition.onresult = function(event)
;var current = event.resultIndex
;var transcript = event.results[current][0].transcript ;var confidence = event.results[current][0].confidence ;console.log(transcript)
;content += transcript ;('#textbox').val(content)$
;{
} (('#start-btn').click(function(event$ }if(content.length)
'' =+ content
{ ;('#textbox').val('welcome to nicesnippets.com')$

;('#downloadlink').css('display','none')$ ;('#create').css('display','block')$ ;(this).css('display','none')$ ()recognition.start
;({
,var textFile = null
} makeTextFile = function (text)
;var data = new Blob([text], {type: 'text/plain'})
If we are replacing a previously generated file we need to // .manually revoke the object URL to avoid memory leaks // } if (textFile !== null) ;window.URL.revokeObjectURL(textFile)
{
;textFile = window.URL.createObjectURL(data) ;return textFile
;{
,var create = document.getElementById('create') ;textbox = document.getElementById('textbox')
} () create.addEventListener('click', function
;var link = document.getElementById('downloadlink') ;link.href = makeTextFile(textbox.value) ;'link.style.display = 'block

;('#start-btn').css('display','block')$ ;('#create').css('display','none')$ ()recognition.stop
;'' = content ;('#instration').text('Press Start Voice Recognition')$ ;(false ,{
< script/>
<body/>
<html/>
  
  
# task2:Programming a web page to control the arm and writing the Arduino code to control:
 code task2:
 ARDUINO CODE
#include
<Servo.h>
Servo gripper;
Servo wrist;
Servo elbow;
Servo shoulder;
Servo base;
double base_angle=90;
double shoulder_angle=90;
double elbow_angle=90;
double wrist_angle=90;
void setup() {
 Serial.begin(115200); //Baud Rate 115200
   base.attach(8);
  shoulder.attach(9);
  elbow.attach(10);
  wrist.attach(11);
  gripper.attach(12);
  base.write(base_angle);
  shoulder.write(shoulder_angle);
  elbow.write(elbow_angle);
  wrist.write(wrist_angle);
}
String getValue(String values, char sep, int i1)
{
  int found = 0;
  int stIndex[] = {0, -1};
  int largIndex = values.length()-1;
  for(int i=0; i<=largIndex && found<=i1; i++){
    if(values.charAt(i)==sep || i==largIndex){
        found++;
        stIndex[0] = stIndex[1]+1;
        stIndex[1] = (i == largIndex) ? i+1 : i;
    }
}
  return found>i1 ? values.substring(stIndex[0], stIndex[1]) : "";
}
void loop(){
  String computerT = Serial.readStringUntil('@');
  computerT.trim();

}￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼
Web serial api
if (computerT.length() == 0) {
  return;
}
String command = getValue(computerT, ' ',0);
if (command == "right" || command == "يمين" || command == "Right") { base.write(base_angle -= 30);
}
{ )"يسار" == if (command == "left" || command == "Left" || command
   base.write(base_angle += 30);
}  
if (command == "top" || command == "فوق" || command == "Top") { shoulder.write(shoulder_angle -= 30);
}
if (command == "bottom"|| command == "تحت" || command == "Bottom") {
   shoulder.write(shoulder_angle += 30);
}  
  Serial.println(command);
  Serial.println("running");
delay(1000);
￼￼￼let
isConnectted
= false;
let port;
let writer;
var target_id;
const enc = new TextEncoder();
async function onChangespeech() {
  if (!isConnectted) {
    alert("connect to the usb in order to use this.");
    return; }
  try {
    const comlist = content;
    const comSplit = comlist.split(" ")
    const command = comSplit.slice(-1);
    const computerT = `${command}@`;
    await writer.write(enc.encode(computerT));
  } catch (e) {
    console.log(e);
￼￼￼￼￼￼￼￼
}
}
async function onConnectUsb() {
try {
    const requestOptions = {
      // Filter on devices with the Arduino USB vendor ID.
      filters: [{ usbVendorId: 0x2341 }],
    };
    // Request an Arduino from the user.
    port = await navigator.serial.requestPort(requestOptions);
    await port.open({ baudRate: 115200 });
    writer = port.writable.getWriter();
    isConnectted = true;
} catch (e) {
    console.log("eror", e);
}
}
                Html code
<!DOCTYP
E html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-
scale=1.0">
    <title>Speech to text</title>
    <link rel="stylesheet"
href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.mi
n.css">
</head>
<body background="image1.jpg">
    <div class="container">
        <h1 class="text-center mt-5">
            speech to text in Arabic language
        </h1>
            <div class="form-group">
                <textarea id="textbox"  rows="6" class="form-
control"></textarea>
            </div>
<div class="form-group">

             Script code
                <button id="start-btn" class="btn btn-danger btn-block"
style="background-color:black ;">
                    Start Recognition
                </button>
                <button id="pause-record-btn" class="btn btn-danger btn-
block" style="background-color:black;">
                    Pause Recognition
                </button>
                <p id="instructions">
                        Press the Start button </p>
            </div>
    </div>
</body>
<script
src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"><
/script>
<script src="script.js"></script>
</html>
 var SpeechRecognition =
window.webkitSpeechRecognition
 var recognition = new SpeechRecognition()
var textbox = $("#textbox")
var instructions = $("#instructions")
var content = ''
recognition.continuous = true
recognition.lang='ar';
recognition.onstart = function () {
instructions.text("Voive Recognition is on")
}
recognition.onspeechend = function () {
instructions.text("No Activity")
}
recognition.onerror = function (){
instructions.text("Try Again")
}
recognition.onresult= function (event){
var current = event.resultIndex;
var transcript=
event.results[current][0].transcript
       
   content += transcript
textbox.val(content)
}
$("#start-btn").click(function(event) {
if (content.length){
content += ''
}
recognition.start()
})
$('#pause-record-btn').click(function(event) {
recognition.stop();
instructions.text('Voice recognition paused');
});
textbox.on('input', function (){
content = $(this).val()
})
 
 
 
  
