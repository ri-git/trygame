<!DOCTYPE html>

<html>
  <head>
    <title>Color Game</title>
    <link rel="stylesheet" href="./index.css" />
  </head>
  <body onload="newGame()">
    <div id="header">
      <h2>The Great</h2>
      <h1 id="header-clue">rgb(xxx,xxx,xxx)</h1>
      <h2>Guessing Game</h2>
    </div>
    <table style="width: 100%" class="arrange" >
    <div style = " width: 210 px;" class="wrap" id="container ">
      <tr>
      <th><div class="tile" id="1">1</div></th>
      <th><div class="tile" id="2">2</div></th>
      <th><div class="tile" id="3">3</div></th>
    </tr>
    <tr>
      <th><div class="tile" id="4">4</div></th>
      <th><div class="tile" id="5">5</div></th>
      <th><div class="tile" id="6">6</div></th>
     </tr>
    </div>
  </table>
     <div id="reloading">
      <div class = "main" id ="1">
      <button class="refresh-button">New Game</button>
      </div>
      <div class = "main" id="2">
        <button id="attempts">click here to find out how many attempts have been made</button>
        Guess the colour with the hint given- only 3 tries allowed!
      </div>
     </div>
     
     

    
    

    <script>
      var t1 = document.getElementById("1");
      var t2 = document.getElementById("2");
      var t3 = document.getElementById("3");
      var t4 = document.getElementById("4");
      var t5 = document.getElementById("5");
      var t6 = document.getElementById("6");
      var x;
      var correctColor;
      var ctr = 0;
      var result = -1;

      function getRandomColor() {
        var letters = "0123456789ABCDEF";
        var color = "#";
        for (var i = 0; i < 6; i++) {
          color += letters[Math.floor(Math.random() * 16)];
        }
        return color;
      }
      var button = document.getElementById("attempts"),
      count=0;
      button.onclick= function(){
        
        button.innerHTML = "number of tries"+ctr ;
      }
      /*var button = document.getElementById("refresh"),
      count=0;
      button.onClick= function(){
        location.reload();
        return false;
        
      }*/
    

      function newGame() {
        t1.style.background = getRandomColor();
        t2.style.background = getRandomColor();
        t3.style.background = getRandomColor();
        t4.style.background = getRandomColor();
        t5.style.background = getRandomColor();
        t6.style.background = getRandomColor();

        x = Math.floor(Math.random() * 6 + 1);

        if (x == 1) correctColor = t1.style.background;
        if (x == 2) correctColor = t2.style.background;
        if (x == 3) correctColor = t3.style.background;
        if (x == 4) correctColor = t4.style.background;
        if (x == 5) correctColor = t5.style.background;
        if ( x== 6) correctColor = t6.style.background;
        /* console.log(x);
        console.log(correctColor); */

        document.getElementById("header-clue").innerHTML = correctColor;
      }


const refreshButton = document.querySelector('.refresh-button');

const refreshPage = () => {
  location.reload();
}

refreshButton.addEventListener('click', refreshPage)



      t1.addEventListener("click", function () {
        if ((t1.style.background == correctColor)&&(result==-1)) {
          result = 1;
          t2.style.background = correctColor;
          t3.style.background = correctColor;
          t4.style.background = correctColor;
          t5.style.background = correctColor;
          t6.style.background = correctColor;
          document.getElementById("header").style.background = correctColor;
        } else {
          t1.style.background = "black";
          ctr+=1;
          if (ctr > 3){
            result = 0;
          }
        }
      });
      t2.addEventListener("click", function () {
        if ((t2.style.background == correctColor)&&(result==-1)) {
          result = 1;
          t1.style.background = correctColor;
          t3.style.background = correctColor;
          t4.style.background = correctColor;
          t5.style.background = correctColor;
          t6.style.background = correctColor;
          document.getElementById("header").style.background = correctColor;
        } else {
          t2.style.background = "black";
          ctr+=1;
          if (ctr > 3){
            result = 0;
          }
        }
      });
      t3.addEventListener("click", function () {
        if ((t3.style.background == correctColor)&&(result==-1)) {
          result = 1;
          t2.style.background = correctColor;
          t1.style.background = correctColor;
          t4.style.background = correctColor;
          t5.style.background = correctColor;
          t6.style.background = correctColor;
          document.getElementById("header").style.background = correctColor;
        } else {
          t3.style.background = "black";
          ctr+=1;
          if (ctr > 3){
            result = 0;
          }
        }
      });
      t4.addEventListener("click", function () {
        if ((t4.style.background == correctColor)&&(result==-1)) {
          result = 1;
          t2.style.background = correctColor;
          t3.style.background = correctColor;
          t1.style.background = correctColor;
          t5.style.background = correctColor;
          t6.style.background = correctColor;
          document.getElementById("header").style.background = correctColor;
        } else {
          t4.style.background = "black";
          ctr+=1;
          if (ctr > 3){
            result = 0;
          }
        }
      });
      t5.addEventListener("click", function () {
        if ((t5.style.background == correctColor)&&(result==-1)) {
          result = 1;
          t2.style.background = correctColor;
          t3.style.background = correctColor;
          t4.style.background = correctColor;
          t1.style.background = correctColor;
          t6.style.background = correctColor;
          document.getElementById("header").style.background = correctColor;
        } else {
          t5.style.background = "black";
          ctr+=1;
          if (ctr > 3){
            result = 0;
          }
        }
      });
      t6.addEventListener("click", function () {
        if ((t6.style.background == correctColor)&&(result==-1)) {
          result = 1;
          t2.style.background = correctColor;
          t3.style.background = correctColor;
          t4.style.background = correctColor;
          t5.style.background = correctColor;
          t1.style.background = correctColor;
          document.getElementById("header").style.background = correctColor;
        } else {
          t6.style.background = "black";
          ctr+=1;
          if (ctr > 3){
            result = 0;
          }
        }
      });

      /*t2.addEventListener("click", function () {
        if (t2.style.background == correctColor) {
          t1.style.background = correctColor;
          document.getElementById("header").style.background = correctColor;
        } else {
          t2.style.background = "black";
        }
      });*/
    </script>
  </body>
</html>
