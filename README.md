# 综合 · 计算器页面集

一组单文件、零依赖的静态计算页面，托管在 GitHub Pages，自定义域名 **oxygen.asia**。
所有计算都在浏览器本地完成，不向服务器上传任何输入。

## 页面

| 页面 | 文件 | 说明 |
| --- | --- | --- |
| 首页导航 | `index.html` | 卡片式索引，列出全部页面 |
| 净水器计算器 | `净水器计算器.html` | 按纯度、水量与模组，推算一晚或多晚之后的净化结果（深色主题） |
| 水培健康度计算器 | `水培健康度计算器.html` | Hydroponic Health Lab，按水质与环境指标评估水培健康度 |
| 罗非鱼净化计算器 | `罗非鱼净化计算器.html` | 排污 → 矿化 → 吸收 三步结算，测算重金属与化学残留 |
| 芦苇净化方案对比 | `芦苇净化方案对比.html` | 对比各种「预处理 + 每日芦苇」方案达到 99.9% 所需的天数 |

## 目录约定

- 仓库根目录只放**要发布**的内容：`index.html`、四个计算器页面、`CNAME`、`.gitignore`、`README.md`。
- `test-local/` 是本地工作区，已写入 `.gitignore`：截图、临时导出、备份、草稿一律放这里，不进版本库，也不会部署到线上。
- 该目录里可能留有本机修复用的备份与还原脚本；若其中记录了绝对路径，文件移动后需要按新位置调整才能执行。

## 新增一个页面

1. 把 HTML 文件放进仓库根目录。
2. 在 `index.html` 里复制一张卡片，改标题、描述和 `href`。
3. 可选：在页面底部加统计标签，并引入计数脚本。

   ```html
   <script defer src="https://events.vercount.one/js"></script>
   ```

   显示位置用 `busuanzi_value_page_pv`（本页阅读量）、`busuanzi_value_page_uv`（本页访客数）。
4. 提交并推送，GitHub Pages 通常 1–2 分钟内更新。

## 访问统计

由 [Vercount](https://github.com/EvanNotFound/vercount) 提供——不蒜子（busuanzi）的兼容实现，标签 id 完全相同：

| 位置 | 指标 | 标签 id |
| --- | --- | --- |
| 首页 | 全站总访问量 | `busuanzi_value_site_pv` |
| 首页 | 全站总访客数 | `busuanzi_value_site_uv` |
| 各计算器页 | 本页阅读量 | `busuanzi_value_page_pv` |
| 各计算器页 | 本页访客数 | `busuanzi_value_page_uv` |

数字取回之前显示 `—`；离线打开或被浏览器插件拦截时保持 `—`，不影响计算功能。

## 部署

`main` 分支直接发布到 GitHub Pages，域名由 `CNAME`（`oxygen.asia`）指定。
