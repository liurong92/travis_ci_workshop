# DEMO

### 步骤
1. 初始一个项目，创建`test`文件夹，并在[Github](https://github.com/)上创建一个仓库。确保你的电脑上安装过[node](https://nodejs.org/en/)，如果没有，请安装。

	*步骤如下*

	推荐使用[nvm](https://github.com/creationix/nvm)安装, 你也可以使用[Homebrew](http://brew.sh/)安装`nvm`，在用`nvm`安装`node`。

	**当所有准备好后，现在开始了**
	* `npm init`初始化项目。
	* 安装[jest](https://facebook.github.io/jest/)测试框架，`npm install jest-cli --save-dev`。
	* 配置`package.json`文件。

		```
		"scripts": {
   			"test": "jest"
 		}
		```

2. 创建`__tests__`和`src`文件夹。

3. 添加测试，命名为：`sum-test.js`。

	```
	var sum = function (a, b) {
  		return a + b;
	}
	module.exports = sum;
	```

4. 在`sum.js`中实现。

	```
	jest.dontMock('../src/sum');

	describe('sum', function() {
 		it('adds 1 + 2 to equal 3', function() {
   			var sum = require('../src/sum');
   			expect(sum(1, 2)).toBe(3);
 		});
	});
	```
5. 运行测试`npm test`。

6. push 到github上。这一步就要与travis连接了。
