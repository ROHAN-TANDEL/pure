# pure
pure html css and js
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="description" content="loader js css and javascript">
<meta name="keywords" content="HTML,CSS,JavaScript">
<meta name="author" content="Rohan Tandel">
<meta name="viewport" content="width=device-width, initial-scale=1">

<style>
.loader {
  border: 16px solid #f3f3f3;
  border-radius: 50%;
  border-top: 16px solid #3498db;
  width: 120px;
  height: 120px;
  -webkit-animation: spin 2s linear infinite; /* Safari */
  animation: spin 2s linear infinite;
}
/* Safari */
@-webkit-keyframes spin {
  0% { -webkit-transform: rotate(0deg); }
  100% { -webkit-transform: rotate(360deg); }
}
@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
h1, h3, .loader, button {
  position: relative;
  color: green;
}
body {
  background-color: lightblue;
}
button {
  background-color: lightgreen;
  box-shadow: 0 0 0;
  border: solid 1px grey;
}
/*/ start -- popup styling/*/
.popupbox {
  width: 25%;
  background: floralwhite;
  box-shadow: 0px 0px 10px 10px #b9b0a9;
}
.popup-close {
  padding: 1% 10%;
}
/*/ end -- popup styling/*/
/*----------start---overlay for popup----------*/
#overlay {
    position: fixed;
    display: none;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0,0,0,0.5);
    z-index: 2;
    cursor: pointer;
}
#text{
    position: absolute;
    top: 50%;
    left: 50%;
    font-size: 50px;
    color: white;
    transform: translate(-50%,-50%);
    -ms-transform: translate(-50%,-50%);
}
/*----------end---overlay for popup----------*/
</style>
</head>
<body style="margin:0;">
<center>
<h1>Welcome</h1>
<h3 id="loading-text">Loading...</h3>
<h3 id="loading-success">Successful...</h3>
<div id="loader" class="loader"></div>

<br>
<button id="loader-button" onclick="loadingButton()"><h3>Start - Loading</h3></button>
<!-- <button onclick="success()">Stop - Loading</button> -->
</center>
<div id="overlay" onclick="off()">
  <div id="text">
      <center>
  <div id="popupbox" class="popupbox">
    <div>
      <h2>Refresh completed !</h2>
      <br><br><br>
      <button onclick="hideCallPopUp();" id="popup-close" class="popup-close"><h3>close</h3></button>
    </div>
  </div>
</center>
  </div>
</div>
<script>
/*------------start----loader Js----------------------*/
var myVar;
/*---------------start loader----------------*/
function loadingButton() {
  console.log('loadingButton --- --- --');
    hideCallPopUp();
    showLoader();
    setTimeout(function(){ success(); }, 3000);
}
function hideLoader() {
  console.log('hideLoader --- --- --');
  document.getElementById("loader").style.display = "none";
  document.getElementById("loading-text").style.display = "none";
  document.getElementById("loading-success").style.display = "none";
  hideCallPopUp();
  off();//show overlay function 
}
function success() {
  console.log('success --- --- --');
  hideLoader();
  document.getElementById("loader-button").style.display = "block";
  document.getElementById("loading-success").style.display = "block"; 
  showCallPopUp();
}
function showLoader() {
  console.log('showLoader --- --- --');
  document.getElementById("loader-button").style.display = "none";
  document.getElementById("loading-success").style.display = "none";
  document.getElementById("loading-text").style.display = "block";
  document.getElementById("loader").style.display = "block";
}
/*----------------end loader------------------*/
/*------------------start popup---------------*/
function showCallPopUp() {
  on();//show overlay function
  document.getElementById("popupbox").style.display = "block";
}
function hideCallPopUp() {
  off();//hide overlay function
  document.getElementById("popupbox").style.display = "none";
}
/*---------------stop popup--------------*/
/*---------------start overlay-----------*/
/*show overlay*/
function on() {
    document.getElementById("overlay").style.display = "block";
}
/*hide overlay*/
function off() {
    document.getElementById("overlay").style.display = "none";
}
/*---------------stop overlay-------------*/
hideLoader();//default hide activity
</script>

</body>
</html>
![images](https://raw.githubusercontent.com/ROHAN-TANDEL/pure/master/Screenshot%20from%202018-11-01%2014-07-39.png)
![images](https://raw.githubusercontent.com/ROHAN-TANDEL/pure/master/Screenshot%20from%202018-11-01%2014-07-42.png)
![images](https://raw.githubusercontent.com/ROHAN-TANDEL/pure/master/Screenshot%20from%202018-11-01%2014-07-45.png)
![images](https://raw.githubusercontent.com/ROHAN-TANDEL/pure/master/Screenshot%20from%202018-11-01%2014-07-47.png)
