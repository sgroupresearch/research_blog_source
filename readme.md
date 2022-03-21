# SGroup Research Blog

## Quick Start
1. Install Hugo: https://www.gohugo.org/

## Add Blog
1. 参考 `content/adaspeech2.md` 写法，支持html标签

## Debug
`hugo server`

## Update and Push
```bash
git add .
git pull origin main
git commit -m "add xxx"
git push origin main
```
执行完毕以后会自动更新到 http://sgroupresearch.github.io/

## Documents
https://www.gohugo.org/
https://gohugo.io/documentation/

## Hint
1. git clone下来绝对路径中请不要使用空格。
2. hugo server的作用仅仅是debug，严格来讲并不需要在本地执行网页的编译任务（网络编译被自动配置在github的后台完成）。因此，实际上大家只需要上传.md文件即可，整体的执行流称为：用户clone/pull本repo -> 用户更新.md文件 -> 用户上传至github -> github后台编译完成线上更新。由于后台编译需要时间，因此上传完成后可能需要等待5分钟左右后，线上网页才会完成更新。
3. markdown文件命名时请使用小写字母。

## Developer
Yuzi Yan (github ID: Chaojidahoufeng)

Thanks to Yi Ren (github ID: RayeRen)