# 1.way to programmatically prevent Google Colab from disconnecting on a timeout
https://stackoverflow.com/questions/57113226/how-to-prevent-google-colab-from-disconnecting

+ ctrl+shift+i调出console

+ 粘贴以下代码，按下回车
```
function ClickConnect(){
  console.log("Connnect Clicked - Start"); 
  document.querySelector("#top-toolbar > colab-connect-button").shadowRoot.querySelector("#connect").click();
  console.log("Connnect Clicked - End"); 
};
setInterval(ClickConnect, 60000)
```
# 2.python安装cv2命令
```
python -m pip install -i https://pypi.tuna.tsinghua.edu.cn/simple opencv-python
```

# 关于谷歌Colab使用心得的总结
https://blog.csdn.net/xyl295528322/article/details/107736182
