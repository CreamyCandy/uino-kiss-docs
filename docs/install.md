### 命令行工具 (CLI)
!> Kiss 使用 Vue 为模板方式开发项目，如果你没有使用 Vue 的经验，在熟悉 Vue 本身之后再使用 CLI [Vue 官方文档](https://cn.vuejs.org/)。<br>
Kiss 提供了一个官方的 CLI，为基于 Vue 的单页面工程快速搭建繁杂的脚手架，只需要几分钟的时间就可以运行起来并带有热重载，以及生产环境可用的构建版本。

**安装 Cli Service**
```bash
$ npm install uino-kiss-cli -g --registry https://npm.udolphin.com
```

**创建项目**
```bash
$ kiss
```
创建选项为：
* 项目名称(必填)，同时也是目录名: 当前仅支持 `数字/字母/下划线/减号`
* 项目仓库地址(可选): 仅支持 `git@` 开头的 `ssh地址` 或不填
* UI组件库(可选): 默认选择 `particle`