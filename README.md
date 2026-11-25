<!-- release-skill:safe-first-command -->
<!-- release-skill:external-write-boundary -->

# Skill Family Foundation 公开文档站

本仓库对应 `ifoohoo/skill-family-foundation-site`，承载 Skill Family Foundation 四个公开发行单元的统一静态知识站产物，涵盖架构分工、安装与五分钟接入、共享机制与采用裁决、十宿主兼容矩阵、命令行参考及常见报错排障手册。阅读站点无需安装任何运行环境。

在线访问地址：<https://ifoohoo.github.io/skill-family-foundation-site/>

## 关联公开发行单元

- `skill-family-contracts`（机器契约与协议注册表）：[ifoohoo/skill-family-contracts](https://github.com/ifoohoo/skill-family-contracts)
- `skill-family-harness-node`（Node.js 受收容机制运行时）：[ifoohoo/skill-family-harness-node](https://github.com/ifoohoo/skill-family-harness-node)
- `skill-family-engineering-kit`（四大构建期与检查期工程命令）：[ifoohoo/skill-family-engineering-kit](https://github.com/ifoohoo/skill-family-engineering-kit)
- `foundation-adoption-review`（采用诊断、静态审阅与工程初始化插件）：[ifoohoo/foundation-adoption-review](https://github.com/ifoohoo/foundation-adoption-review)

## 组件安装与最小只读示例

当对应精确版本已在公开仓库发布就绪时，技能族项目可固定安装契约与受收容运行时底座，将工程工具包作为开发期依赖接入，并执行只读帮助命令核对入口：

```sh
npm install --save-exact skill-family-contracts@0.39.1 skill-family-harness-node@0.39.1
npm install --save-dev --save-exact skill-family-engineering-kit@0.39.1
npx skill-family-kit --help
```

## 本地只读浏览

直接在浏览器中打开静态产物入口即可阅读；若需模拟 GitHub Pages 的静态路径行为，可在站点产物目录内启动只读本地静态服务：

```sh
python3 -m http.server 8000
```

页面、样式表、离线搜索索引与架构图全部采用相对路径与内容 SHA-256 指纹，不依赖第三方运行时 CDN 或外部字体，也不发起远端网络请求。

## 常见故障排查

- 若直接以文件协议打开页面导致浏览器限制离线搜索索引加载，请改用上方 `python3 -m http.server 8000` 通过本地静态端口访问。
- 若技能族接入或门禁运行过程中遇到路径收容拒绝、受管文件锁漂移、三包依赖分层违规或版本锁步不一致等故障，请参阅排障手册：<https://ifoohoo.github.io/skill-family-foundation-site/troubleshooting.html>；下一步接入步骤可参阅快速上手：<https://ifoohoo.github.io/skill-family-foundation-site/quickstart.html>。

<!-- release-skill:capability:safe-first-command -->
> **安全起点：** 在已发布精确版本可用后，可使用只读命令 `npm exec --package=skill-family-engineering-kit@0.39.1 -- skill-family-kit --help` 查看工程命令说明，不修改任何本地文件或远端状态。

<!-- release-skill:capability:external-write-boundary -->
> **外部写入边界：** 站点 HTML 与 `site-baseline.json` 由源工作区的确定性渲染器统一生成并经泄漏扫描与摘要门禁核验；切勿直接手改生成的静态文件。推送分支、创建标签、发布 GitHub Release 与变更 GitHub Pages 设置均须取得当次任务的明确授权。

## 许可证

Apache-2.0，详见根目录 `LICENSE`。
