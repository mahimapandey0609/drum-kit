# drum-kit








<!DOCTYPE html>
<html lang="en" dir="ltr">

<head>
  <meta charset="utf-8">
  <title>Drum Kit</title>
  <link rel="stylesheet" href="styles.css">
  <link href="https://fonts.googleapis.com/css?family=Arvo" rel="stylesheet">
</head>

<body>

  <h1 id="title">Drum 🥁 Kit</h1>
  <div class="set">
    <button class="w drum">w</button>
    <button class="a drum">a</button>
    <button class="s drum">s</button>
    <button class="d drum">d</button>
    <button class="j drum">j</button>
    <button class="k drum">k</button>
    <button class="l drum">l</button>
  </div>


  <footer>
    Made with ❤️ in Ayodhya.
  </footer>
  <script src="index.js"></script>
</body>

</html>

#css file 
body {
  text-align: center;
  background-color: #283149;
}

h1 {
  font-size: 5rem;
  color: #DBEDF3;
  font-family: "Arvo", cursive;
  text-shadow: 3px 0 #DA0463;

}

footer {
  color: #DBEDF3;
  font-family: sans-serif;
}

.w {
   background-image: url("images/tom1.png");
}

.a {
  background-image: url("images/tom2.png");
}

.s {
  background-image: url("images/tom3.png");
}

.d {
  background-image: url("images/tom4.png");
}

.j {
  background-image: url("images/snare.png");
}

.k {
  background-image: url("images/crash.png");
}

.l {
  background-image: url("images/kick.png");
} 

.set {
  margin: 10% auto;
}

.game-over {
  background-color: red;
  opacity: 0.8;
}

.pressed {
  box-shadow: 0 3px 4px 0 #DBEDF3;
  opacity: 0.5;
}

.red {
  color: red;
}

.drum {
  outline: none;
  border: 10px solid #404B69;
  font-size: 5rem;
  font-family: 'Arvo', cursive;
  line-height: 2;
  font-weight: 900;
  color: #DA0463;
  text-shadow: 3px 0 #DBEDF3;
  border-radius: 15px;
  display: inline-block;
  width: 150px;
  height: 150px;
  text-align: center;
  margin: 10px;
  background-color: white;
}

#java script
for (let i = 0; i < document.querySelectorAll(".drum").length; i++) {
    document.querySelectorAll(".drum")[i].addEventListener("click",handleclick);
function handleclick() {
  var buttoninnerHTML = this.innerHTML ;
  clickme(buttoninnerHTML);
  buttonanimation(buttoninnerHTML);
}
    
}


document.addEventListener("keypress",function(event){
  clickme(event.key);
  buttonanimation(event.key);
})


function clickme(key) 
{
  
  switch (key) {
    case 'w':
      var tom1 =  new Audio('sounds/tom-1.mp3');
       tom1.play(); 
      break;
      case 'a':
      var tom2 =  new Audio('sounds/tom-2.mp3');
       tom2.play(); 
      break;
      case 's':
      var tom3 =  new Audio('sounds/tom-3.mp3');
       tom3.play(); 
      break;
      case 'd':
      var tom4 =  new Audio('sounds/tom-4.mp3');
       tom4.play(); 
      break;
      case 'j':
      var snare =  new Audio('sounds/snare.mp3');
       snare.play(); 
      break;
      case 'k':
      var crash =  new Audio('sounds/crash.mp3');
       crash.play(); 
      break;
      case 'l':
        var kick =  new Audio('sounds/kick-bass.mp3');
        kick.play(); 
       break;
      

    default: console.log(key);
      
    
  }
  
}

function buttonanimation(currentkey) {
  var activebutton= document.querySelector("."+ currentkey);
  activebutton.classList.add("pressed");
  setTimeout( function() {
    activebutton.classList.remove("pressed");
    
  }, 10.0);
  
}
