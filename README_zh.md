# 🐾 桃桃的日记本

<p align="center">
  <img src="assets/cover.png" alt="桃桃的日记本封面" width="800"/>
</p>

**温暖可爱的桃桃日记本。** 这是一个可直接托管在 GitHub Pages 的纯静态日记网站，日记源数据保存在仓库根目录的 `diary.json`。

## 介绍

桃桃的日记本是一个记录小猫桃桃日常生活的静态小站：晒太阳、午睡、吃饭、玩耍、观察窗外，以及每一天不经意的小快乐。

项目只使用 HTML、CSS、JavaScript 和 JSON，不需要框架、后端或额外构建工具，也可以直接部署到 GitHub Pages。

## 主要功能

- 温暖可爱的桃桃猫咪手帐风格
- 首页桃桃配图 `assets/taotao-home.png`
- 打字机式副标题效果
- 日期切换、最多七篇的横向日期窗口、前后篇翻阅和键盘方向键
- 弹层日历：按月份翻页，在有日记的日子上显示心情，点日期直接跳转
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
| `diary.json` | 仓库中的日记数据，页面默认从这里读取 |
| `index.html` | 日记展示、日期切换、弹层日历和打印 |
| `about.html` | 关于桃桃的双语说明 |
| `assets/taotao-home.png` | 首页主图 |
| `assets/cover.png` | README 项目封面 |
| `README.md` | 中文项目说明 |
| `README_zh.md` | 中文项目说明副本 |

## 维护日记

直接编辑 `diary.json`，在最外层数组中增加一篇日记对象。日期必须唯一且使用 `YYYY-MM-DD`；页面会自动按日期排序，不需要修改 HTML：

```json
{
  "date": "2026-11-21",
  "title": "阳光下的午觉",
  "weather": "晴",
  "mood": "舒服又满足",
  "content": ["第一段正文。", "第二段正文。"],
  "note": "可选的小记。",
  "tags": ["晒太阳", "午觉"],
  "image": "assets/taotao-home.png"
}
```

`content` 是纯文本段落数组，不解析 Markdown；`note`、`tags` 和 `image` 可省略。配图只填写 `assets/` 下已有的相对路径，不会把图片内容写进 JSON。保存后刷新页面即可看到更新。

## 许可证

本项目为静态展示站点，未附带独立许可证文件。
