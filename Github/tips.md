![uTools_1619807530278](https://user-images.githubusercontent.com/53358372/116738835-8bbf1600-aa25-11eb-8e30-65dffd9a45b7.png)
# 1
如何笨办法在仓库新建文件夹，再在仓库新建文件夹内上传你文件夹里的源码文件。
我们先点击【Add file】选择【Create new file】，然后在输入框里输入文件夹名字加“/”。
# 2
GitHub Page里的Jekyll虽然支持Markdown，但是不能正确显示公式，可以借用MathJax帮助渲染。

方法：

1 设置markdown引擎为kramdown，方法为在 _config.yml 里添加：

markdown: kramdown

2 在md文件开始输入代码：

<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            inlineMath: [['$','$']]
            }
        });
    </script>
</head>
然后正文就可以写公式：$ e = m c^2 $ 这样就能正确显示了。

