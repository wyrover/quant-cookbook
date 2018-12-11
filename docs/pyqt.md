## 安装 PyQt

用了全局 shadowsocket 就不用改源了，下载速度很快

```
pip install PyQt5-tools -i https://pypi.douban.com/simple
```

```
pip install PyQt5
pip install PyQt5-tools
```

将 pyqt5_tools 添加到环境变量

```
D:\Anaconda3\envs\quant\Lib\site-packages\pyqt5_tools
```

如运行时出现以下错误

```
ModuleNotFoundError: No module named 'PyQt5.sip'
```

重新卸载安装 PyQt5

```
pip uninstall PyQt5
pip uninstall PyQt5-tools

pip install PyQt5
pip install PyQt5-tools
```
