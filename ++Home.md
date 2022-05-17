
# 版本控制软件（VCS)
- 集中式版本控制（CVC）- Subversion
- 分布式版本控制（DVCS）- Git


Git 通过拍摄**快照**来记录项目的每一个变化；
2005年，Linus Torvalds 推出。

常规的创建流程
1. 在**中央服务器**上创建一个[[Repository]]
2. 下载这个[[Repository]]到你的计算机上。在VCS中，该步骤被称为 **cloning**
3. 在本地的[[Repository]]中添加文件，并**Commit** 它们；Git将在你commit时，为这个项目建立一个快照。然后会维护这个快照的历史记录以备后面使用。
4. 上传修改的文件到**中央服务器**
5. 然后就可以下载任何团队成员修改的文件






## 💡概念列表 


![[Pasted image 20220517132400.png|300x200]]


基本上，Git的开发环境就三个步骤：
1. Working directory
2. Staging Area（暂存区）
	1. 在提交任何文件到[[Repository]]之前，需要将文件安置在暂存区。可以方便的添加或删除暂存区中的文件。
	2. [[git add]]
	3. [[git commit]] 将文件提交到[[Repository]]
3. [[Repository]]



* Configure


## 链接本地Repository到服务器

- 链接到远程服务器 [[git remote]] add remote_name remote_url
	- 可以设定`remote_name`为任何你想要的名称，但通常使用**origin**
	- 而 `remote_url` 是服务器上 Git 存储库的路径。此 URL 将由您的 Git 托管服务提供商提供。
* 链接完成后，可以使用 [[git remote ]] -v 查看有多少远程的[[Repository]]关联到当前本地[[Repository]]

### 提交修改到服务器
![[Pasted image 20220517143931.png|500]]


[[git push]]

```text
git push [remote_name] [branch_name]
```

通常只有一个branch ，名字叫 '[[Master]]'；当然还有其他的


### 下载修改到本地

![[Pasted image 20220517144721.png|500]]


[[git pull]]

```text
git pull [remote_name] [branch_name]
```

默认情况下，执行上述命令，git将下载修改的文件，然后执行合并到你的repository中。但是，如果你只想是否远程服务器上的文件有修改与否，可以使用下面的命令。
```text
git fetch origin master
```



## branches
![[Pasted image 20220517145813.png]]


Git 分支模型很像是树杈结构。这对添加新功能或修改bug非常有用。
基本上，你创建一个新的分支，进行测试。当你工作完成时，可以简单的合并到主分支（比如：[[master]]）；当发现新的修改并不需要时，可进行舍弃。

[[git branch]] branch name

要对特定分支进行修改，必须先进入该分支
[[git checkout]] branch name



## Merge

![[Pasted image 20220517153538.png]]



[[Git merge]] branch_name

如果一个特定的文件在两个不同的分支中，将会产生合并冲突，这需要手工查看文件并删除其中一个。



## ⌨️操作 #操作

```dataview
table desc as "简述",type as "类型",step as "STEP"
from #command 
sort type
```



- [ ] Git扩展阅读 📅 2022-05-18
https://livecodestream.dev/post/five-advanced-git-concepts-that-make-you-look-like-a-pro/ 
https://www.atlassian.com/git/tutorials/making-a-pull-request#where-to-go
https://www.codecademy.com/learn/learn-git