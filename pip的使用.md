`pip`是基于python的软件，用`--user`的选项可以使服务器的用户在自己的目录下安装软件

在安装multiqc的过程中，使用`pip`遇到了问题：
```
pip install --user multiqc
显示了如下的错误
Traceback (most recent call last):
  File "/share/apps/anaconda3/bin/pip", line 7, in <module>
    from pip._internal import main
ImportError: No module named 'pip._internal'
```

经过google，找到了解决的方案,对`pip`进行更新：
```
python3 -m pip install --upgrade --user pip
```

更新过后的`pip`成功安装了multiqc软件

