## 开发环境
**Anaconda + theano / Tensorflow / Keras / scikit-learn**

## Anaconda 安装
Anaconda 实际上是一个python开发环境的集成包，安装好后就已经等于安装好了python + Spyder + Jupyter Notebook 等等基本工具了，至于Spyder 和 Jupyter Notebook等是何物以及有何用就不细说了。
Anaconda 下载连接：https://www.anaconda.com/download/
NOTE: 
1. 由于目前Tensorflow、Keras等DL库只支持64bit版本，所以在选择Anaconda发行版本时一定要选择64bit的
2. 在Anaconda的安装过程中，记得选择
Install for： All Users(requires admin privileges),
否则在安装完后无法在开始菜单中找到安装好的Anaconda的所有工具

## 安装Keras/Tensorflow/theano 等深度学习库及scikit-learn机器学习库
安装完成后，配置path变量——
右键我的电脑->属性->高级选项->环境变量->系统变量->path->在path中添加路径：需要添加的有三个，以我的Anaconda安装目录为例，分别为：
 E:\ProgramFiles_for_Major\Anaconda3;
E:\ProgramFiles_for_Major\Anaconda3\Scripts;
E:\ProgramFiles_for_Major\Anaconda3\Library\bin;

在安装好的Anaconda 套件中打开 Anaconda Prompt，直接进入到command模式。

更新conda
`conda update conda`
`conda update --all`
将pip升级到最新版：
`python -m pip install -U pip`
 
> -- CREATE ENVIRONMENT/WORKSPACE FOR PYTHON 3.6:
`conda create --name neuralnets python=3.6`
`activate neuralnets`
-- INSTALL EVERYTHING (notice the neuralnets workspace in parenthesis on each line). ACCEPT ANY DEPENDENCIES EACH OF THOSE STEPS WANTS TO INSTALL:
`conda install theano`
`conda install mingw libpython`
`pip install tensorflow`
`pip install keras`
`conda install scikit-learn`
注意，上述命令均在激活了neuralnets这个环境下执行，这里比较麻烦的是每次使用都要先激活 neuralmets 这个环境：
`activate neuralnets`

## 验证是否安装成功
在Prompt 终端直接进入python环境并import 这些库
`python`
1. `>>>import tensorflow`
若下一行出现>>>，则说明TensorFlow安装成功
2. `>>>import keras`
若显示Using TensorFlow backed，则说明安装成功
3. `>>>import theano`
如果你看到“>>>”三个箭头，没有别的乱七八糟的东西了，就说明：你！安！装！成！功！啦！
如果有提示需要添加环境变量的，就需要按照提示在系统环境变量中添加
MKL_THREADING_LAYER=GNU
然后**重启prompt终端**，再次`import theano`
4. `>>>import sklearn`
若下一行出现>>>，则说明scikit-learn安装成功

若一切顺利，恭喜你，环境基本配好了！
在Spyder中使用可以参考下面的链接。


几个重要的参考连接：
- http://www.bubuko.com/infodetail-2485059.html
- https://www.jianshu.com/p/b8a703df5318
- https://stackoverflow.com/questions/34097988/how-do-i-install-keras-and-theano-in-anaconda-python-on-windows
- http://www.cnblogs.com/AriesQt/p/6773811.html
- http://deeplearning.net/software/theano/index.html
- https://conda.io/docs/user-guide/overview.html