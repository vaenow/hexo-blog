title: sed 在Mac下日常使用的差异
date: 2016-08-07 12:42:20
tags: bash
---

linux下可选参数在Mac下被强制要求
执行命令 sed -i "s/aaa/bbb/g" test.txt 后提示

 

`sed command a expects xxx followed by text`  (这里xxx可能是任何字母)

操作失败，linux下是OK的。因为两个系统下对参数“i”的要求不一样。

参数`“-i”`的用途是直接在文件中进行替换。为防止误操作，可提供一个后缀名，使sed在替换前对文件进行备份,如 sed -i ".bak" "s/aaa/bbb/g" test.txt。mac下是强制要求备份的，但linux下是可选的。

所以如果不需要备份，传入空字符串 sed -i "" "s/aaa/bbb/g" test.txt 替代linux下用法即可

<!-- more -->