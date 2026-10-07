# SmithyLegend 铁匠铺传奇 · iOS 版打包指南

这是一个**完全开源**（Godot 4.7 项目）的铸造经营游戏，本文件已为你配置好 iOS 打包所需的全部设置。你的电脑是 Windows，无法直接生成 iOS 安装包（必须在 Mac 上构建），所以我们用 **GitHub 的免费云端 Mac** 来完成打包。

## 已完成的工作
- ✅ iOS 导出预设已配置（Bundle ID、最低系统 iOS 15、arm64 架构、无签名模式）
- ✅ 云端自动打包脚本已写好（`.github/workflows/ios.yml`）
- ✅ 本地已实测：资源打包、Xcode 工程生成全部正常

---

## 第 1 步：准备 GitHub 账号
打开 https://github.com 注册账号（已有则跳过）。

## 第 2 步：创建仓库
1. 登录后点右上角 **+** → **New repository**
2. Repository name 填：`SmithyLegend`
3. 选 **Public**（公共仓库云端打包免费）
4. 点 **Create repository**

## 第 3 步：上传项目文件
在仓库页面点 **Add file → Upload files**，然后把电脑上这个文件夹里的**所有内容**拖进去：

```
D:\SmithyLegend\SmithyLegend-main\
```

> 注意：需要把文件夹内的文件全选上传（包括 `.github` 文件夹）。页面下方点 **Commit changes** 提交。

## 第 4 步：触发云端打包
1. 进入仓库页面的 **Actions** 标签
2. 左侧点 **Build iOS IPA**
3. 右侧点 **Run workflow** → 绿色按钮确认运行
4. 等待约 5-10 分钟（云端 Mac 会自动下载 Godot、编译游戏）

## 第 5 步：下载安装包
1. 构建完成后，进入该次运行的详情页
2. 最底部 **Artifacts** 区域，下载 **SmithyLegend-iOS.zip**
3. 解压得到 `ios.ipa`

---

## 安装到手机（iOS 15 + 巨魔商店）
1. 手机上需已安装 **TrollStore（巨魔商店）**（iOS 15 专属，无需越狱，永久签名）
2. 把 `ios.ipa` 通过「文件」App 或网盘存到手机
3. 打开 TrollStore → 右上角 **+** → 选择 `ios.ipa` → 自动安装
4. 桌面出现游戏图标，直接开玩，永久有效

---

## 常见问题
| 问题 | 解决 |
|---|---|
| Actions 显示红色失败 | 点进运行详情看报错日志，截图发我帮你排查 |
| 上传太慢 | 可用电脑装 Git 后用命令行 push，速度更快 |
| 没有巨魔商店 | iOS 15 的 iPhone 支持 TrollStore，按对应机型教程安装（有风险，操作前先备份） |
| 想改游戏内容 | 改完源码后重新上传，再跑一次 Actions 即可出新的 ipa |

## 游戏是什么
像素铁匠接单玩法：熔炼矿石 → 锻打武器 → 把控品质 → 交付村民赚钱，和《铸剑纳贡》思路一致，且完全免费开源（GitHub: Yanxiyimengya/SmithyLegend，作者：烟汐忆梦_YM）。
