# MyBlog
[参考链接](https://www.cnblogs.com/wumz/p/8030244.html)
[域名配置](https://blog.csdn.net/simba1949/article/details/79252352)
# 1.Git安装后SSH密钥生成
## 1.1Generating a new SSH key
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
EG:
The key fingerprint is:
The key's randomart image is:
+---[RSA 4096]----+
|                 |
+----[SHA256]-----+
## 1.2配置GitHub的SSH keys
[GitHub增加SSH keys](https://git-scm.com/book/zh/v2/GitHub-%E8%B4%A6%E6%88%B7%E7%9A%84%E5%88%9B%E5%BB%BA%E5%92%8C%E9%85%8D%E7%BD%AE)
# 2.HEXO安装
在hexo目录：npm install hexo-cli -g
初始化
hexo init blog
cd blog
安装
npm install
生成页面
hexo generate
启动服务
hexo server
变更hexo端口
$ hexo s --p 8081
浏览器里面应该可以看到了
目录结构：
.
├── _config.yml		// 站点配置文件
├── package.json	// node应用信息
├── scaffolds		// 模板文件夹
├── source			// 资源存放目录
|   ├── _drafts		// 草稿
|   └── _posts		// 微博正文
└── themes			// 主题存放目录

# 3.HEXO部署到GitHub
## 3.1修改_config.yml 配置文件
```
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: git@github.com:nidegexing/nidegexing.github.io.git
  branch: master
  message:
```
## 3.2安装hexo部署插件
[Desc](https://github.com/hexojs/hexo-deployer-git)
cnpm install hexo-deployer-git --save
- for npm version under 4
$ npm install git+git@github.com:hexojs/hexo-deployer-git.git --save
- for npm version 5
$ npm install git+ssh://git@github.com:hexojs/hexo-deployer-git.git --save
## 3.3部署 4ddf3a8a265ad9c32d07292d3552cb85893a98d2
$ hexo clean
$ hexo generate
$ hexo deploy
民工三连：hexo clean && hexo g && hexo d
# 4.安装HEXO主题
git clone https://github.com/iissnan/hexo-theme-next themes/next
git clone https://github.com/litten/hexo-theme-yilia themes/yilia
修改站点配置文件：themes：next
## 4.1HEXO常用指令
hexo clean #清除缓存
hexo g  #保存修改，生成文件
hexo s  #启动本地服务
hexo d  #发布到远程
hexo init #生成站点
hexo new page "xxx" #生成页面
hexo new "" #生成文章
npm install --save xxx  #安装插件
npm unstall xxx #卸载插件
## 4.2.HEXO整体流程(阿里云)
[HEXO教程](https://www.cnblogs.com/visugar/p/6821777.html)
# 5.日常的维护
## 5.1HEXO是根据source文件来渲染public中的文件，进而发布。
所以我们只要维护source就可以
## 5.2为了个性化，要调整模板，就比较困难了哦

# TIPS:
1.使用yilia主题，加了下面标签才有MORE
<!--more--> //在需要阶段的地方插入该代码语句
