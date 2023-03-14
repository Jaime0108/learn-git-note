

# 常用命令

### Linux的命令

+ 编辑文件

  ```
  vim 1.txt
  
  按i键 变成 INSERT 模式
  
  编辑完成 ESC > shift+: > wq+Enter
  ```

+ 查看文件

  ```
  cat 1.txt
  ```





### 设置用户签名

> 用以区分不同开发人员的标识   可以在任意目录中设置

```java
git config --global user.name 'Jaime'
git config --global user.email '1006788336@qq.com'    
```

+ 执行命令生成的文件

  ![](D:\project\GIT\images\执行设置用户签名命令生成的文件.png)

+ 文件的具体内容信息

  ![](D:\project\GIT\images\文件记录的用户信息.png)





### 初始化本地仓库（git init）

> 在项目的文件夹下

```javascript
git init
```

+ 初始化

  ![](D:\project\GIT\images\初始化git目录命令.png)

+ 初始化的结果

  ![](D:\project\GIT\images\初始化的结果.png)







### GIT的工作流程

+ 本地仓库 & 远程仓库工作流程图

  ![](D:\project\GIT\images\git本地仓库&远程仓库的工作流程.png)

##### 查看当前目录状态（git status）

+  查看当前目录状态

  ```javascript
  git status
  ```

  ![](D:\project\GIT\images\查看当前目录git管理状态.png)

##### 添加当前目录所有文件到暂存区（git add .）

+ 添加当前目录所有文件到暂存区

  ```javascript
  git add .
  ```

  ![](D:\project\GIT\images\把当前目录下所有文件都添加到暂存区.png)

+ 把文件添加到暂存区后新的状态

  ![](D:\project\GIT\images\把文件添加到暂存区后新的状态.png)

##### 提交到本地仓库（git commit -m ‘描述’）

+ 提交到本地仓库

  ```javascript
  git commit -m '描述'
  ```

  ![](D:\project\GIT\images\保存到本地仓库.png)

+ 这里有个坑 git commit 不添加 -m '描述'有可能会出现这种情况或者直接报错

  ![](D:\project\GIT\images\在commit时不添加描述可能会发生的情况.png)

##### 查看本地仓库提交历史记录（git log）

+ 查看本地仓库提交历史记录

  ```
  git log
  ```

  ![](D:\project\GIT\images\查看提交本地仓库记录.png)

+ 查看所有的版本

  > 使用git log 只能查看当前指针所在的版本之前的版本

  ```
  git reflog
  ```

##### 版本回退（git reset --hard HEAD^）

+ 版本回退

  ```
  git reset --hard HEAD^
  
  git reset --hard HEAD^^
  
  git reset --hard HEAD~2
  
  git reset --hard 指定前6位commit
  
  git revert
  ```

+ 新建1.txt文件

  ![](D:\project\GIT\images\新建1.txt文件.png)

+ 1.txt文件完成了1功能

  ![](D:\project\GIT\images\项目完成1功能.png)

+ 完成1功能后提交到本地仓库

  ![](D:\project\GIT\images\完成1功能提交到本地仓库.png)

+ 项目完成2功能

  ![](D:\project\GIT\images\项目完成2功能.png)

+ 完成2功能提交到本地仓库

  ![](D:\project\GIT\images\完成2功能提交到本地仓库.png)

+ 项目完成3功能

  ![](D:\project\GIT\images\项目完成3功能.png)

+ 完成3功能提交到本地仓库

  ![](D:\project\GIT\images\完成3功能提交到本地仓库.png)

+ 版本回退

  ![](D:\project\GIT\images\版本回退.png)

+ 版本回退后git的结果

  ![](D:\project\GIT\images\回退版本git的结果.png)

+ 版本回退后1.txt文件的结果

  ![](D:\project\GIT\images\回退版本1.txt文件的结果.png)



##### 回退到指定的版本(git reset --hard 指定前6位commit)

+ 使用reflog查看所有的记录

  ![](D:\project\GIT\images\使用reflog查看所有的操作记录.png)

+ 使用git reset --hard 指定前7位commit 回退到指定的版本

  ```
  git reset --hard 指定前7位commit
  ```

##### 软回退（git reset --soft HEAD^）

+ git reset --hard的这种方式是直接让本地仓库的内容回到工作区

+ 这样会直接修改本地工作区的代码

+ 使用软回退让本地仓库的代码回到暂存区，不会修改本地工作区代码

+ 就类似与撤销一条提交信息,重新commit

  ```
  git reset --soft HEAD^
  ```

##### revert版本回退，并且会生成一条记录

+ 和reset的区别 工作区的代码的变化是一样的（工作区都会变）
+ reset的指针是直接移动，revert是会新生成一条记录 



##### 查看分支（git branch）

+ 查看分支

  ```javascript
  git branch
  ```

  ![](D:\project\GIT\images\使用git branch查看分支.png)



##### 创建分支（git branch 新分支名称）

+ 创建分支

  ```
  git branch jaime
  ```

  ![](D:\project\GIT\images\创建分支并查看分支.png)



##### 切换分支（git checkout 分支名称）

+ 切换分支

  ```
  git checkout jaime
  ```

  ![](D:\project\GIT\images\切换分支并查看当前分支.png)

+ 在新分支上创建新的文件

  ![](D:\project\GIT\images\在jaime分支上创建新的文件.png)

+ 在切回master分支对比之前必须提交到本地仓库

  ![](D:\project\GIT\images\在切换分支回到master之前必须提交.png)

+ 在jaime分支查看日志，在master分支上是看不到jaime分支的日志的

  ![](D:\project\GIT\images\在jaime分支上查看日志.png)

+ 切回master分支

  ![](D:\project\GIT\images\切回master分支.png)

  ![](D:\project\GIT\images\切回master分支后jaime分支下的jaime文件消失了.png)



##### 合并分支（git merge 分支名称）

+ 合并分支

  > 合并分支要切换到 你想要合并到的那条分支

  ```javascript
  git merge 要合并的分支的名称
  ```

  ![](D:\project\GIT\images\合并分支,出现了合并失败的状况.png)

  > 这里出现了合并失败的情况，后面处理

  ![](D:\project\GIT\images\合并后master分支也有jaime分支的内容了.png)



##### 合并冲突

> 合并冲突产生的原因 两个分支都同时修改同一个文件， 并且要合并

+ 合并冲突

  ![](D:\project\GIT\images\master分支下utils文件的内容.png)

  ![](D:\project\GIT\images\jaime分支下有同名的文件utils也有修改.png)

  ![](D:\project\GIT\images\在master分支下merge jaime分支 有两个文件冲突了.png)

  ![](D:\project\GIT\images\utils文件的冲突情况.png)

  ![](D:\project\GIT\images\手动解决utils文件的冲突，并重新commit.png)
  

##### 删除分支（git branch -b 分支名称）

+ 删除分支

  ```
  git branch -d 指定分支名
  ```

  ![](D:\project\GIT\images\删除分支.png)





# 远程仓库

##### 查看远程仓库

+ 查看远程仓库

  >remote 是远程的意思

  ```
  git remote -v
  ```



##### 添加（连接）远程仓库

+ 添加远程仓库

  > 可以添加多个远程仓库的地址

  ```
  git remote add origin（远程仓库的别名） 远程仓库地址
  ```

  ![](D:\project\GIT\images\添加远程仓库地址.png)



##### 在本地查看连接到了哪些远端仓库

+ 在本地查看连接到了哪些远端仓库

  ```
  git branch -a
  ```

  ![](D:\project\GIT\images\在本地查看远端仓库.png)

##### 移除远程仓库（连接）

+ 移除远程仓库

  ```
  git remote remove origin
  ```



##### 推送到远程仓库

+ 推送到远程仓库

  ```
  git push origin master（本地分支）:master（远程仓库的分支）
  
  简写：git push origin master
  
  git push -u origin master
  *添加了-u的选项后，以后就可以直接git push 不用添加别名 和 分支了
  *但是之前没有用过这个选项是不可以的
  *以后想改就git push 新的地址别名 新的分支
  ```

  ![](D:\project\GIT\images\推送到远程仓库要求提供token.png)

  ![](D:\project\GIT\images\凭据管理.png)

  ![](D:\project\GIT\images\使用push推送到远程仓库.png)



##### 远程仓库拉取到本地仓库

+ 远程仓库拉取到本地仓库

  > 只会拉取更新的文件，并且会自动的merge
  >
  > 会merge就有可能会出现合并冲突的问题
  ```
  git pull 远程仓库别名 分支
  ```



##### 推送到远程仓库失败的情况

+ 推送到远程仓库失败的情况

  > 这不是冲突，是远程仓库有文件的变动（新增、删除、修改）

  ![](D:\project\GIT\images\push失败的情况.png)

+ 你没有权限推送到远程仓库

  > 这里没办法演示，就直接告诉你怎么做吧

  ![](D:\project\GIT\images\添加这个仓库拥有push权限的成员.png)

+ 推送到远程仓库有冲突的情况

  > 当本地 和 远程 都修改了同一个文件，就会有冲突

  ![](D:\project\GIT\images\远程pull下来有冲突的情况.png)


##### 克隆

+ 克隆

  ```
  git clone 仓库地址
  ```



##### 远程仓库分支

+ 把本地仓库的分支推送到远程仓库的分支（远程没有分支会自动生成）

  ```
  git chekcout login
  
  git push 远程仓库别名 login(本地仓库分支):login（远程仓库分支）
  这样远程仓库就会生成login分支
  ```

+ 拉取远程仓库分支

  ```
  git pull origin（远程仓库别名） login(远程仓库分支)
  
  git checkout login 
  ```

+ 删除远程仓库分支

  ```javascript
  git push origin (空):要删除的分支
  ```


# 跨团队协作



# 使用vscode集成工具

+ 1

  ![](D:\project\GIT\images\使用vscode集成的git初始化本地仓库.png)

+ 2

  ![](D:\project\GIT\images\使用vscode集成的git初始化本地仓库2.png)

+ 3

+ 

