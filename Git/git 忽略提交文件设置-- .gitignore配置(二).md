**操作前提** ： 已经安装好了 git
<br/>

**操作方式**
1.  在项目根目录 按住 shift + 右键， 选择 Git Bash Here，打开 Git 命令控制台
2. 使用命令在项目根目录下 新建一个 .gitignore文件 命令： ==touch .gitignore== （注意： 这里的命令用 在 cmd 中是无法使用的哦）
3. 用编辑器或者相关文本编辑器打开刚刚新建的.gitignore文件，将需要忽略的文件在这里写明即可
<br/>

**文件 .gitignore 的格式规范**

1. 所有空行或者以 ＃ 开头的行都会被 Git 忽略，#开头的文件标识注释，可以使用反斜杠进行转义。。
2.  可以使用标准的 glob 模式匹配。可以使用标准的 glob 模式匹配。6. 可以使用标准的 glob 模式匹配。可以使用标准的 glob 模式匹配。
3. 匹配模式可以以（/）开头防止递归。匹配模式可以以（/）开头防止递归。
4. 匹配模式可以以（/）结尾指定目录。匹配模式可以以（/）结尾指定目录。
5. 要忽略指定模式以外的文件或目录，可以在模式前加上惊叹号（!）取反。要忽略指定模式以外的文件或目录，可以在模式前加上惊叹号（!）取反。
6.  glob 模式是指 shell 所使用的简化了的正则表达式
7. 星号（*）匹配零个或多个任意字符；
8. [abc] 匹配任何一个列在方括号中的字符（这个例子要么匹配一个 a，要么匹配一个 b，要么匹配一个 c）；
9. 问号（?）只匹配一个任意字符；
10. 如果在方括号中使用短划线分隔两个字符，表示所有在这两个字符范围内的都可以匹配（比如 [0-9] 表示匹配所有 0 到 9 的数字）;
11. 使用两个星号（*) 表示匹配任意中间目录，比如`a/**/z` 可以匹配 a/z, a/b/z 或 `a/b/c/z`等。
<br/>

**.gitignore 文件例子：**

```javascript
#               表示此为注释,将被Git忽略
1.txt             表示忽略1.txt 文件
*.txt           表示忽略所有 .txt 结尾的文件
!2.txt           不忽略2.txt这个文件
/TODO           表示仅仅忽略项目根目录下的 TODO 文件，如果这个文件不在根目录下，则不会忽略
build/          表示忽略 build/目录下的所有文件，过滤整个build文件夹，不管是否在根目录下；
```
<br/>

**.gitignore忽略规则的优先级**
在 .gitingore 文件中，每一行指定一个忽略规则，Git检查忽略规则的时候有多个来源，它的优先级如下（由高到低）：
1）从命令行中读取可用的忽略规则
2）当前目录定义的规则
3）父级目录定义的规则，依次递推
4）$GIT_DIR/info/exclude 文件中定义的规则
5）core.excludesfile中定义的全局规则

参考推荐：https://www.cnblogs.com/kevingrace/p/5690241.html
官网文档： https://github.com/github/gitignore
