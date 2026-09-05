# 取件码助手 (PickupCodeGrabber)

一个 **LSPosed 模块**：自动捕获快递取件短信 → 提取取件码 → 写入小米笔记「待办」
（一码一条、新码堆栈置顶）→ 弹出通知（点击复制 / 一键标记已取件）。

适用于 **小米 / 红米（MIUI·HyperOS）+ Root (Magisk) + LSPosed** 环境。

## ✨ 特性

- **100% 覆盖短信来源**：Hook 短信库写入必经点（SmsProvider），普通短信与小米网络短信全覆盖
- **一键部署 sqlite3**：APK 内置经实机验证的 sqlite3（arm64），体检发现缺失时点一下自动部署，告别 adb/Termux 手工操作
- **部署体检 6 项**：LSPosed 注入 / root / 作用域自动比对 / 通知权限 / sqlite3 / 笔记库，逐项 ✅❌ + 修复指引
- **智能提取**：多码簇、多种真实短信格式、来源识别（菜鸟/丰巢/京东/顺丰/中通/圆通/韵达/申通/邮政）
- **去重**：按「取件码 + 地点」指纹去重
- **通知交互**：点击复制取件码 + 打开笔记待办；每条码带「已取件」按钮
- **三种模板**：极简 / 完整 / 自定义占位符（`{code}` `{source}` `{place}` `{time}`）
- **黑名单关键词**：过滤 12306 / 验证码 / 银行 / 广告等误报
- **一键导出诊断报告**：自动收集日志与配置、脱敏后分享，出问题发一个文件即可
- **隐私友好**：零网络、零短信权限（Hook 层直接取数），全程本地处理

## 🔧 环境要求

| 项目 | 要求 |
|---|---|
| 设备 | 小米 / 红米（MIUI / HyperOS） |
| 系统 | Android 12+ |
| Root | Magisk |
| 框架 | LSPosed |
| 工具 | sqlite3（App 内可一键部署，无需手工准备） |
| 实测 | Redmi K90 Pro Max / HyperOS 4.0 / Android 17 ✅ |

## 📲 安装

1. 在 Releases 下载 APK 安装；
2. LSPosed 管理器 → 模块 → 取件码助手 → 启用，作用域勾选 **5 项**：
   `android`、`com.android.phone`、`com.android.mms`、`com.android.providers.telephony`、`com.miui.notes`；
3. 重启手机；
4. 打开 App → 「🩺 部署体检」全绿 → 「🧪 一键测试」验证。

## 📖 完整文档

- 使用说明 / FAQ / 风险说明：[GitHub 源码仓库 README](https://github.com/O-kai/Xiaomi-HyperOs-pickup-code-grabber#readme)
- 更新日志：[CHANGELOG](https://github.com/O-kai/Xiaomi-HyperOs-pickup-code-grabber/blob/main/CHANGELOG.md)
- 开发历程：[docs/15-journey.md](https://github.com/O-kai/Xiaomi-HyperOs-pickup-code-grabber/blob/main/docs/15-journey.md)

## ⚠️ 声明

- 本模块直写小米笔记数据库，不承诺云同步；只增行 / 定点标记，不删改用户已有数据；
- 仅实测部分设备（见上），其他版本兼容性欢迎反馈；
- 与小米公司无任何关联，非官方作品；MIT 许可，使用风险自担。
