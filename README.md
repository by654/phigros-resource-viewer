# Phigros 资源检索

一个纯前端的 Phigros 资源检索 / 试听 / 批量下载工具。所有数据来自 [7aGiven/Phigros_Resource](https://github.com/7aGiven/Phigros_Resource)，无需后端，部署在 GitHub Pages 上即可直接使用。

## 功能

- **全文检索**：支持按曲名、曲师、谱师、画师、收藏品、Tips、难度值搜索
- **难度筛选**：EZ / HD / IN / AT 四档独立开关
- **内容筛选**：歌曲 / 文件 / 收藏品 / 头像 / Tips 五类内容
- **排序**：相关度、曲名、资源 ID、曲师、最高难度
- **收藏**：歌曲、头像、文件、收藏品均可收藏，支持只看收藏
- **在线试听**：音频边下边播，支持进度条拖动、播放模式切换（列表循环 / 单曲 / 随机 / 播完即止）
- **可视化**：播放时显示 30 根实时频谱动画
- **多线程下载**：无 Token 4 线程 / 有 Token 8 线程（可自定义），支持批量打包成 ZIP
- **资源全量缓存**：一键把曲绘 / 谱面 / 文本 / 音频缓存到浏览器 IndexedDB
- **多代理回退**：GitHub raw / jsDelivr / Gcore / ghproxy / ghfast 自动切换
- **代理锁定**：手动选定代理后不会被自动回退覆盖，回退时弹提示
- **主题切换**：浅色 / 深色跟随系统或手动切换
- **设置中心**：字体缩放、行距、最大列数、是否显示可视化 / Tips / 猜你想搜、线程数、缓存清理等
- **URL 深链**：`#q=xxx&song=xxx` 可直接分享搜索结果或指定歌曲

## 使用

直接访问部署好的地址即可。

### 快捷键

| 按键 | 功能 |
|------|------|
| `/` | 聚焦搜索框 |
| `空格` | 播放 / 暂停当前曲目 |
| `Esc` | 关闭灯箱 / 弹窗 / 退出批量模式 |
| `←` / `→` | 播放时快退 / 快进 5 秒 |

### 首次使用建议

1. 打开右上角 ⚙️ → **代理**，选择访问速度最快的源
2. 如果经常加载失败，去 **令牌** 里配置一个 GitHub Personal Access Token（只读即可），能把 API 额度从每小时 60 次提升到 5000 次
3. 需要批量下载时点右上角 📦 进入批量模式，勾选后统一打包成 ZIP

## 部署到 GitHub Pages

1. Fork 或新建一个仓库，把 `index.html` 放到仓库根目录
2. 仓库 → **Settings** → **Pages**
3. Source 选 `Deploy from a branch`，Branch 选 `main`，目录 `/ (root)`
4. 保存后等待 1 分钟，访问 `https://<你的用户名>.github.io/<仓库名>/`

也可以直接下载 `index.html` 用浏览器打开本地运行，但注意部分浏览器对 `file://` 协议下的跨域请求有限制，建议用 `python -m http.server` 之类的本地服务器。

## 技术栈

- 纯原生 HTML / CSS / JavaScript，无构建步骤，无框架依赖
- 唯一外部依赖：[JSZip](https://stuk.github.io/jszip/)（用于批量打包）
- 数据缓存：IndexedDB
- 用户偏好：localStorage

## 数据来源

所有歌曲信息、曲绘、音频、谱面均来自：

**https://github.com/7aGiven/Phigros_Resource**

本项目只做展示和检索，不存储任何资源副本。

## 免责声明

本项目为非官方工具，与 Pigeon Games 及 Phigros 官方无关。所有游戏资源的版权归原版权方所有，仅供学习交流使用，请勿用于商业用途。

## License

MIT
