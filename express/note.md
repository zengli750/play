## npm
node package Manager （随node自动按照）
JavaScript生态中用于管理代码包的工具
<!-- 降低开发初步 避免重复造轮子 -->

### 基础命令
- 检测版本   `npm -v` 

<!-- 下载了node 还是报错 没权限 -->
1. **以管理员身份运行PowerShell**：右键点击PowerShell应用程序，选择“以管理员身份运行”。
PowerShell是什么 就看图片Power.png

2. **查看当前执行策略**：在以管理员身份运行的PowerShell中输入 `Get-ExecutionPolicy`，回车。这会显示当前的执行策略，可能是 `Restricted`（受限的），这意味着禁止运行脚本。

3. **更改执行策略**：输入 `Set-ExecutionPolicy RemoteSigned -Force`，
回车。这会将执行策略更改为 `RemoteSigned`，允许运行本地创建的脚本，
并且运行从互联网下载的脚本前需要进行签名确认。

4. **再次尝试运行 `npm -v`**：就能正常显示npm的版本信息了。

## 下载express 

- 下载模块之前 初始化项目  `npm init`
输入之后 一直点击回车 结束后 出现一个package.json文件 记录信息

- 安装包  `npm install 包名` 简写 `npm i 包名`

- 安装express 
npm i express 
<!-- 如果很慢 换个源 这个很好 
npm config set registry https://registry.npmmirror.com
将npm默认包下载源 切换淘宝镜像 加上国内用户下载npm包的速度
-->

<!-- 切回官方源
npm config set registry https://registry.npmjs.org -->

- 更新  `npm update [包名]`