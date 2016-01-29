# Travis-CI

[Travis CI](https://travis-ci.org/)是一个基于云的持续集成项目, 目前支持大多数的主流语言。


## 使用步骤
1. 进入Travis CI 官网，使用github账号登录。

2. 进入Accounts页面，开启仓库开关。

3. 在你的项目中添加`.travis.yml`文件。

4. 在`.travis.yml`的文件中配置所需信息。

	例如：
	这部分只是为了说明可以配置写什么内容，与下文中的代码不是一体的。谢谢，请勿黏贴。

	```
	language: ruby

	rvm:
  		- 2.2.3

	env:
  		- TRAVIS_NODE_VERSION="4"

	services:
		- mysql

	install:
  		- rm -rf ~/.nvm && git clone https://github.com/creationix/nvm.git ~/.nvm && (cd ~/.nvm && git checkout `git describe --abbrev=0 --tags`) && source ~/.nvm/nvm.sh && nvm install $TRAVIS_NODE_VERSION
  		- bundle install --path vendor/bundle

	before_script:
  		- mysql -e 'create database ILearnC_test;' -uroot
  		- bundle install
  		- npm install -g gulp
  		- npm install

	script:
  		- npm test && gulp build
	```
	具体的牌子可以看Travis CI的官方文档。链接在这里：[点我](https://docs.travis-ci.com/user/getting-started/)

5. 添加测试，使其测试通过。

6. commit & push (当这一切都配置好后，只需push代码到github的仓库即可)。

**案例，请点击DEMO.md文件**
