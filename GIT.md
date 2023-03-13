

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





### 初始化本地仓库

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

+ 查看当前目录状态

  ```javascript
  git status
  ```

  ![](D:\project\GIT\images\查看当前目录git管理状态.png)

+ 添加当前目录所有文件到暂存区

  ```javascript
  git add .
  ```

  ![](D:\project\GIT\images\把当前目录下所有文件都添加到暂存区.png)

+ 把文件添加到暂存区后新的状态

  ![](D:\project\GIT\images\把文件添加到暂存区后新的状态.png)

+ 提交到本地仓库

  ```javascript
  git commit -m '描述'
  ```
