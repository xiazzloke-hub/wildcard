# ColoCrossing 独立服务器通过 IPMI 安装 Debian 12 系统完整指南

## 准备工作
1. **登录后台**：进入 ColoCrossing 控制面板，选择 DEVICES 查看账户中的独立服务器
2. **选择服务器**：找到需要安装系统的独立服务器
3. **启动 IPMI**：
   - 点击 LIFT MULL ROUTE
   - 确认操作
   - 默认有效期为4小时，如需延长可点击 RENEW LIFT

## 获取 IPMI 登录信息
ColoCrossing 开通服务器后会发送包含以下信息的邮件：
- 服务器 IP 地址
- 子网掩码
- 网关信息
- IPMI 登录凭证

👉 [【点击查看】2025年最新 ColoCrossing 优惠码及特价云服务器方案汇总](https://bit.ly/ColoCrossing)

## IPMI 登录与配置
1. 通过浏览器访问 IPMI 的 IP 地址
2. 输入账号密码登录
3. 导航至 Remote Control > Console Redirection
4. 点击 Launch Console 下载 launch.jnlp 文件
   - 需提前安装 Java 7U79 版本（最新版本可能不兼容）

## 系统安装步骤
### 1. 挂载安装镜像
- 进入 Virtual Media > Virtual Storage
- 选择 Debian 12 安装镜像
- 点击 Plug in 确认挂载

### 2. 启动设置
- 重启服务器
- 出现启动界面时按 DEL 或 F11 进入 BIOS
- 选择 IPMI Virtual Disk 3000 启动

### 3. Debian 12 安装流程
1. 选择 INSTALL（非图形安装）
2. 网络配置：
   - 选择 eno1 网卡
   - 手动配置网络参数（参考邮件信息）
   - 将 DNS 服务器改为 8.8.8.8 或 1.1.1.1
3. 系统设置：
   - 设置 root 密码
   - 创建新用户（可选）
   - 选择时区
4. 磁盘分区：
   - 选择 Guided - use entire disk
   - 确认分区方案
5. 软件选择：
   - 最小化安装（根据需求可选桌面环境）
6. 安装 GRUB 引导程序（必须选择 Yes）

## 安装完成
- 卸载安装镜像
- 重启系统
- 使用 root 或创建的用户登录

## 注意事项
1. 确保网络配置正确，特别是 DNS 设置
2. 安装过程中保持 IPMI 会话活跃
3. 建议使用稳定的网络连接进行操作
4. 安装完成后及时更新系统

如需更多服务器配置方案，可参考 ColoCrossing 官方文档获取最新技术支持。