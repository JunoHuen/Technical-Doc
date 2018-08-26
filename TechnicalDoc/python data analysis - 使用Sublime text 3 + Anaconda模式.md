## 简单记录一些配置时的要点

- #### 在Sublime中安装package control
参考: https://blog.csdn.net/zhuangailing/article/details/79046187
1. view -> show console
输入如下网址中内容:
https://packagecontrol.io/installation

2. 在preferences中的packages control中输入  install package
在里面输入Anaconda, 完成后显示如下信息:
![](https://upload-images.jianshu.io/upload_images/538619-171a21193ea1af94.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
3. 修改python路径
由于插件本身无法知道Python安装的路径，所以需要手动设置Python主程序的位置。选择Preferences-package Setting-Anaconda-Settings-Default。
![](https://upload-images.jianshu.io/upload_images/538619-d5884d3e627bd328.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4. 新建User Setting
选择Preferences-package Setting-Anaconda-Settings-Users选项，键入以下json数据, 修改其中的"python_interpreter" 为你的python使用路径。保存，重启sublime即可.
(python使用目录: 打开Prompt命令行, 在激活路径(conda info --env)下输入where python)
>{
	"python_interpreter":"E:/Anaconda3/envs/neuralnets",
	"suppress_word_completions":true,
	"suppress_explicit_completions":true,
	"comlete_parameters":true,
	"swallow_startup_errors":true,
	"anaconda_linting":false
}

接下来，sublime3编写python代码时会有提示功能。

- #### 配置Anaconda运行
参考: https://blog.csdn.net/zhihaoma/article/details/50917915

1.打开Sublime Text 3，工具-->编译系统-->新编译系统，就会打开文件sublime-build，
2. 修改以下内容：
>{
"cmd": ["python", "-u", "$file"],
"path":"E:/Anaconda3/envs/neuralnets",
"file_regex": "^[ ]*File \"(...*?)\", line ([0-9]*)",
"selector": "source.python",
"shell": true
}

把path里面的内容修改为Anaconda编译器的安装目录即可。保存文件并命名为Anaconda3.sublime-build，文件自动保存在E:\SublimeText3\Data\Packages\User目录下，此时在sublime的工具-> 编译系统中就会有Anaconda3，就选择这个编译环境，ctrl+b便可以运行python代码了。

- #### Trouble Shooting
*如果你没有保存一个文件就build，有可能出来以下的错误：

E:/Anaconda3/envs/neuralnets\python.exe: can't find '__main__' module in ''
           这个问题其实有点蠢, 就是因为没将要build的文件先保存再ctrl+b运行导致的, 所以记得先保存再运行,以便Python能够运行起来。