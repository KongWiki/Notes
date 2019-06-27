## Git 学习笔记

### git 的三种状态

- 已提交（committed）

  安全保存到本地数据库

- 已修改（modified）

  修改了文件但是没有存入本地数据库

- 已暂存（staged）

  对已经修改的文件目前的版本做了标记

### git 的三种工作区域

![image](https://raw.githubusercontent.com/KongWiki/Notes/master/pictures/wordStatus.jpg)

- Git仓库（Git Repository）

  保存项目中各种数据

- 工作目录（Working Directory）

  存储在磁盘中，是对某个独立版本的内容的提取。

- 暂存区域（Staging Area）

  保存了下次将要提交的文件列表信息，一般在Git仓库中，也被称作为“索引”

### 工作流程

1. 在工作目录中进行文件的修改。
2. 暂存文件，将文件快照放入暂存区域。
3. 提交跟新，在暂存文件中找到相应的文件，然后将其快照永久存入Git仓库目录。

### Git中文件生命周期

![image](https://raw.githubusercontent.com/KongWiki/Notes/master/pictures/gitCircle.png)





## 杂记

```
git add 
```

可以理解为`添加内容到下一次的提交中`而不是`将一个文件添加到项目中`

```git
$ git status -s
 M README
MM Rakefile
A lib/git.rb
M lib/simplegit.rb
?? LICENSE.txt
```

- `M` 

  修改过的均有该标记，

  - 靠右边表示该文件被修改了，但是没有放入暂存区
  - 靠左边表示该文件被修改了，并且放入了暂存区

- `MM` 

  放入暂存区并且又修改了

- `??` 

  新添加未跟踪文件

- `A`  

  新添加到暂存区