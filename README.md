# 🐾 桃桃的日记本

<p align="center">
  <img src="assets/cover.png" alt="桃桃的日记本封面" width="800"/>
</p>

**温暖可爱的桃桃日记本。** 这是一个可直接托管在 GitHub Pages 的纯静态日记网站，日记源数据保存在仓库根目录的 `diary.json`。

[![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)](LICENSE)

## 介绍

桃桃的日记本是一个记录小猫桃桃日常生活的静态小站：晒太阳、午睡、吃饭、玩耍、观察窗外，以及每一天不经意的小快乐。

项目只使用 HTML、CSS、JavaScript 和 JSON，不需要框架、后端或额外构建工具，也可以直接部署到 GitHub Pages。

## 主要功能

- 温暖可爱的桃桃猫咪手帐风格
- 首页桃桃配图 `assets/taotao-home.png`
- 打字机式副标题效果
- 日期切换、最多七篇的横向日期窗口、前后篇翻阅和键盘方向键
- 月份归档与日期、标题、正文、天气、心情、标签搜索
- 新增、编辑、删除日记；导入或导出完整 JSON
- 浏览器草稿恢复提示和定期备份提示
- 当前日记打印
- 亮色与暗色主题，并保存浏览器偏好
- 桌面端与移动端响应式布局
- 关于页支持中英文切换

## 本地预览

必须通过静态服务器预览，浏览器需要通过 HTTP 读取 `diary.json`；直接双击打开 `index.html` 时，日记数据可能无法加载。在仓库根目录启动 Python 自带的静态服务器：

```powershell
py -m http.server 8000
```

然后在浏览器访问 `http://localhost:8000`。停止服务器时在终端按 `Ctrl+C`。

## 修改内容

| 文件 | 用途 |
|------|------|
| `diary.json` | 仓库中的完整日记数据，页面默认从这里读取 |
| `index.html` | 日记展示、搜索归档、浏览器本地草稿和导入导出 |
| `about.html` | 关于桃桃、双语维护和备份说明 |
| `assets/taotao-home.png` | 首页主图 |
| `assets/cover.png` | README 项目封面 |
| `README.md` | 中文项目说明 |
| `README_zh.md` | 中文项目说明副本 |

## 维护日记

### 在仓库中维护（推荐作为正式备份）

直接编辑 `diary.json`，在最外层数组中增加一篇日记对象。日期必须唯一且使用 `YYYY-MM-DD`；页面会自动按日期排序，不需要修改 HTML：

```json
{
  "date": "2026-11-21",
  "title": "阳光下的午觉",
  "weather": "晴",
  "mood": "舒服又满足",
  "content": ["第一段正文。", "第二段正文。"],
  "noteTitle": "今日小确幸",
  "note": "可选的小记。",
  "tags": ["晒太阳", "午觉"],
  "image": "assets/taotao-home.png"
}
```

`content` 是纯文本段落数组，不解析 Markdown；`note`、`noteTitle`、`tags` 和 `image` 可省略。配图只填写已有的相对路径，不会把图片内容写进 JSON。

### 在网页中编辑

首页可新增、编辑、删除日记，也可通过“导入 JSON”和“导出完整 JSON”操作整份数据。网页内的更改会保存到**当前浏览器的 localStorage**，下次访问时会提示是否恢复；它不会写回仓库，不会跨设备同步，也可能因清理浏览器数据而丢失。请定期导出备份。要把草稿正式发布或同步到仓库，请导出完整 JSON，再用导出的 `diary.json` 替换仓库文件并提交。

导入会替换当前列表，但不会修改仓库原文件；导入前可先导出备份。若更换设备或浏览器，可在新设备上导入备份 JSON。

## 许可证

[MIT](LICENSE)
