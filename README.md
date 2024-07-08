# Standard calculator
## Program
### calc.html
```
<html>
<head>
 <meta charset="UTF-8">
 <meta http-equiv="X-UA-Compatible" content="IE=edge">
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
 <title>Calculator App</title>
 <link rel="stylesheet" href="theme.css">
 </head>
 <body style= "background-image: url('https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.vecteezy.com%2Ffree-vector%2Fwebsite-background&psig=AOvVaw3EIdfK6ksFGI2l-x_yDrtZ&ust=1715630509393000&source=images&cd=vfe&opi=89978449&ved=0CBIQjRxqFwoTCODI1u7ziIYDFQAAAAAdAAAAABAE')" align="center">
    
    <div class="card">
        

      <div class="calculator">
        <h3 class="card-title" >S HARSHINI<br> 212221220018</h3>
        
        <form>
          <div class="display">
            <input type="text" name="display">
          </div>
          <div>
            <input type="button" value="AC" onclick="display.value = '' " class="operator">
            <input type="button" value="DEL" onclick="display.value =  display.value.toString().slice(0,-1)" class="operator">
            <input type="button" value="." onclick="display.value += '.' " class="operator">
            <input type="button" value="/" onclick="display.value += '/' " class="operator">
          </div>
          <div>
            <input type="button" value="7" onclick="display.value += '7' ">
            <input type="button" value="8" onclick="display.value += '8' ">
            <input type="button" value="9" onclick="display.value += '9' ">
            <input type="button" value="*" onclick="display.value += '*' " class="operator">
          </div>
          <div>
            <input type="button" value="4" onclick="display.value += '4' ">
            <input type="button" value="5" onclick="display.value += '5' ">
            <input type="button" value="6" onclick="display.value += '6' ">
            <input type="button" value="-" onclick="display.value += '-' " class="operator">
          </div>
          <div>
            <input type="button" value="1" onclick="display.value += '1' ">
            <input type="button" value="2" onclick="display.value += '2' ">
            <input type="button" value="3" onclick="display.value += '3' ">
            <input type="button" value="+" onclick="display.value += '+' "class="operator">
          </div>
          <div>
            <input type="button" value="%" onclick="display.value +='%' " class="operator">
            <input type="button" value="0" onclick="display.value += '0' ">
            <input type="button" value="=" onclick="display.value = eval(display.value)"class="equal operator">
          </div>
        </form>
      </div>
    </div>
    
    <script src="code.js"></script>
</body>
</html>
```
### Code.js
```
const display = document.querySelector(".display");
const buttons = document.querySelectorAll("button");
const specialChars = ["%", "*", "/", "-", "+", "="];
let output = "";

const calculate = (btnValue) => {
  display.focus();
  if (btnValue === "=" && output !== "") {
    output = eval(output.replace("%", "/100"));
  } else if (btnValue === "AC") {
    output = "";
  } else if (btnValue === "DEL") {
    output = output.toString().slice(0, -1);
  } else {
    if (output === "" && specialChars.includes(btnValue)) return;
    output += btnValue;
  }
  display.value = output;
};

buttons.forEach((button) => {
  button.addEventListener("click", (e) => calculate(e.target.dataset.value));
});
```
### theme.js
```
body{
    width:95%;
    height:90vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(90deg, #000000 0,#000000 58%);
    background-attachment: fixed;
    background-repeat: no-repeat;
    background-size: cover;
  }
  h3{
    color: #000000;
  }
  
  .card-title {
    font-size: 22px;
  }
  
  p, a {
    font-size: 1rem;
  }
  
  a {
    color: #4d4ae8;
    text-decoration: none;
  }
  .shape {
    position: absolute;
    width: 150px;
    top: .5rem;
    left: .5rem;
  }
  .calculator{
    background: #3a4452;
    padding: 20px;
    border-radius: 10px;
    width: 400px;
    height: auto;
      backdrop-filter: blur(50%);
    background-color: rgba(255, 255, 255, 0.2); /* Semi-transparent background */
    border-radius: 10px;
    box-shadow: 0 15px 30px rgb(0, 0, 0); /* Soft, diffused shadow */
    backdrop-filter: blur(4px); /* Creates the blurry, frosted glass effect */
    -webkit-backdrop-filter: blur(4px); /* For Safari */
    padding: 20px;
  }
  .calculator form input{
    border: 0;
    outline: 0;
    width: 60;
    height: 60px;
    border-radius: 10px;
    box-shadow: -8px -8px 15px rgb(0, 0, 0),5px 5px 15px rgb(0, 0, 0);
    background: transparent;
    font-size: 20px;
    color: #000000;
    cursor: pointer;
    margin: 10px;
  }
  
  form .display{
    display: flex;
    justify-content: flex-end;
    margin: 20px 0;
  }
  form .display input{
    border: 0;
    outline: 0;
    width: 400;
    text-align: right;
    height: 60px;
    border-radius: 10px;
    background: transparent;
    font-size: 30px;
    color: #000000;
    cursor: pointer;
    margin: 10px;
  }
  form input.equal{
    width: 145px;
  }
  form input.operator{
    color:#000000;
  }
  ```
## Output

