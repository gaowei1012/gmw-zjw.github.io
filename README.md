
## 2017年6月10日
 ### 在Ubuntu系统下用Github和Hexo建立自己的博客
作为一名前端攻城狮,怎么会没有自己的博客展示自己的技能, 今天自己搞了一个博客(Ubuntu 下搭建 hexo),好了我们接下来进入正题.

## 使用环境:
  - Ubuntu 14.04LTS
  - nodejs
  - hexo
  - github：已注册账户并且创建了仓库

## 方法步骤：

### 安装Git,终端输入以下命令，下同:

```
 sudo apt-get install git
```
### 绑定github账户:

```
it config --global user.name "Github用户名"
git config --global user.email "注册Github用的邮箱"
```
### 生成新的SSH key

```
ssh-keygen -t rsa -C "注册Github用的邮箱"
```
看到 ```Enter file in which to save the key (/home/bruce/.ssh/id_rsa): ```直接敲回车<br/>
看到 ```Enter passphrase (empty for no passphrase): ```设置一个密码<br/>
看到 ```Enter same passphrase again: ```重复上面的密码<br/>

### 找到刚生成的SSH key，打开id_rsa.pub复制里面的内容：
```cd ~/.ssh
   gedit id_rsa.pub
```
### 在github里New SSH key 并粘贴。然后测试：<br/>
``` 
   ssh -T git@github.com 
```
看到 ```Are you sure you want to continue connecting (yes/no)?``` 输入yes。<br/>
   *** 安装过node可以跳过这步 ***
### 安装Node.js:
```
  sudo apt-get install nodejs
```
### 安装npm:
```
  sudo apt-get install npm 
```
### 安装hexo-deployer-git:
```
  sudo npm install hexo-deployer-git --save
```
### 建立博客：
在blog目录（如果没有blog目录，hexo会自动创建）初始化hexo:
```
  sudo hexo init blog
```
该命令执行完默认会生成以下目录和文件：<br/>
├── node_modules <br/>
├── scaffolds <br/>
├── source <br/> 
├── themes <br/>
├── _config.yml <br/>
├── db.json <br/>
└── package.json <br/>
解释：scaffolds文件夹存放模板文件（新建文章、页面、草稿等需要基于模板创建）； <br/>
source文件夹存放用户内容(文章、图片、CSS、JS等)； <br/>
themes文件夹存放主题文件； <br/>
_config.yml是网站的配置文件，可以用文本编辑器编辑； <br/>
db.json是缓存文件； <br/>
package.json为应用程序数据文件。 <br/>

#### 进入blog文件夹内,安装配置文件:
``` sudo npm install ```
#### 安装完配置文件后,启动服务:
``` sudo hexo server ``` <br/>
好了, 现在你会看到命令行窗口的链接地址,打开浏览器输入该地址就可以访问了

 
