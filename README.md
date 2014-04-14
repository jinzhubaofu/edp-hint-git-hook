## [GIT-HOOK]代码风格检查小工具

### 功能

使用`edp jshint`或者`edp csslint`对`git commit`提交的文件进行语法检测。如果没有通过检测，会强制中止`git commit`。

### 使用

首先，请先安装`edp`以及`edp hint`， 你可以使用下面脚本来安装

```shell
[sudo]npm install -g edp
[sudo]edp jshint
```

然后，将`hooks/pre-commit`文件放到你的项目`.git/hooks`下，就可以了

当你使用`git commit`时，如果被提交的文件中包含有`.js`或`.css`文件，那就会相应的edp hint命令来进行检测。若代码中存在问题，那么就会显示问题并中止提交。例如：

```shell
edp INFO test.js
edp WARN → line 3, col 9: Missing semicolon.


Aborting commit due to hint error
```

### 未来功能

1. 添加htmlhint
