# Git随笔

## 1.1 创建版本库

​		首先，选择一个合适的地方创建一个空目录 `mkdir xxxxx`，可用 `pwd`命令用于显示当前目录 。

​		第二步，通过`git init`命令把这个目录变成Git可以管理的仓库 , 你会发现当前目录下多了一个`.git`的目录 ，它默认为隐藏的，可通过`ls -ah`命令在控制台查看，若想在文件夹中查看可通过修改文件夹相关属性查看。

## 1.2 把文件添加到版本库

 		添加文件到Git仓库，分两步： 1)使用命令`git add filename`， 把文件添加到仓库 。*注：可反复多次使用，添加多个文件；*   2)使用命令`git commit -m "提交说明"`， 把文件提交到仓库 。

![MrDXh4.png](https://s2.ax1x.com/2019/11/17/MrDXh4.png)



## 1.3 版本回退

先修改文件，然后把修改后的文件提交到Git版本库 

![Mrrva8.png](https://s2.ax1x.com/2019/11/17/Mrrva8.png)

 `git log`命令显示从最近到最远的提交日志，我们可以看到有3次提交。

*注：加上`--pretty=oneline`参数可简化输出信息。*

<img src="https://s2.ax1x.com/2019/11/17/MrsCxs.png" alt="MrsCxs.png" border="0" />

 ![Mrskq0.png](https://s2.ax1x.com/2019/11/17/Mrskq0.png)

 这一大串`f91dd9e...`是`commit id`（版本号），可以通过`git reset --hard 版本号`回退到指定版本。

Git必须知道当前版本是哪个版本，在Git中，用`HEAD`表示当前版本，  上一个版本就是`HEAD^`，上上一个版本就是`HEAD^^`，当然往上100个版本写100个`^`比较容易数不过来，所以写成`HEAD~100`。 

<img src="https://s2.ax1x.com/2019/11/17/MrTtx0.png" alt="MrTtx0.png" border="0" />

那万一回退到上上个版本你却想回退到现在怎么办呢？放心，要重返未来的话可以用`git reflog`查看命令历史，以便确定要回到未来的哪个版本并通过版本号进行回退。 

![MrTWqO.png](https://s2.ax1x.com/2019/11/17/MrTWqO.png)

![Mr7dSI.png](https://s2.ax1x.com/2019/11/17/Mr7dSI.png)