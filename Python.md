# way to programmatically prevent Google Colab from disconnecting on a timeout
https://stackoverflow.com/questions/57113226/how-to-prevent-google-colab-from-disconnecting

+ ctrl+shift+i调出console

+ 粘贴以下代码，按下回车
```py
function ClickConnect(){
  console.log("Connnect Clicked - Start"); 
  document.querySelector("#top-toolbar > colab-connect-button").shadowRoot.querySelector("#connect").click();
  console.log("Connnect Clicked - End"); 
};
setInterval(ClickConnect, 60000)
```
