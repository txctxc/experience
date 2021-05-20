# Font: source code pro
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

```
  147  sudo pip install numpy
  149  sudo pip install scipy
  151  sudo pip install matplotlib
  152  sudo pip install pandas
  162  sudo pip install scikit-learn -i http://pypi.douban.com/simple --trusted-host pypi.douban.com
```
# 编写python代码时不要乱加Tab键
