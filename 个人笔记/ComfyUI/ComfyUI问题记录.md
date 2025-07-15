## ComfyUI报错：No module named 'insightface'
这个问题就是说没有安装insightface模块
解决方案：
### 1、下载insightface
https://github.com/Gourieff/Assets/tree/main/Insightface
从上面链接下载insightface包，一定要选择和comfyui在安装的时候相同版本的python。

### 2、安装insightface
2.1 将下载好的insightface安装文件”insightface-xxx-xxx-xxx-win_amd64.whl“随便放在一个目录下，我这里直接放到了ComfyUI的Python虚拟环境文件夹下
![[../../images/Pasted image 20250715113945.png]]
2.2 windows + R打开“运行”，输入cmd回车进入命令行界面
![[../../images/Pasted image 20250715114430.png]]
cd跳转到虚拟环境的Scripts目录下，之后运行即可安装
```
python -m pip install insightface-xxx-xxx-xxx-win_amd64.whl
```


## ImportError: DLL load failed while importing onnxruntime_pybind11_state: 动态链接库(DLL)初始化例程失败。
这个问题是因为版本问题，我这边测试需要降级到1.17.1的版本就可以解决。
解决方案：
1.1 windows + R打开“运行”，输入cmd回车进入命令行界面
1.2 cd跳转到虚拟环境的Scripts目录下，之后执行如下命令
```
python -m pip uninstall onnxruntime
python -m pip install onnxruntime==1.17.1
```
