# QQchatLog2Html

将QQ导出的mht格式聊天记录文件转换为Html



## 背景

有时需要将QQ的聊天记录导出整理,方便存储,比如:群内的针对一个话题的讨论,需要将聊天记录整理导出,便于存储学习.

## 问题分析
QQ的导出聊天记录支持3中格式:
> .bak 加密文件,支持导入,图片也会存储
> .mht 网页文件,不支持导入,图片已base64格式存储
> .txt 文本文件,不支持导入,图片不存储

所以选择.mht格式的文件比较合适,其实就是html格式,但因为图片已base64格式包含在文件里,导致文件很大,用浏览器很难打开

## 处理思路

对mht格式聊天记录处理

1. 将其中的图片剥离为图片文件
2. 删除mht文件头部无效的内容
3. 手动删除无关的聊天的记录
4. 清理无关记录中包含的图片

## 本工具要做的

上面的1,2,4就是本工具要做的,将聊天记录变小,文件剥离,删除无用图片,这样就变成一个体积小的html了.

基本思路:

用正则表达式匹配内容,完成处理转换

