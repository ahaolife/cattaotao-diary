---
name: taotao-diary
version: 2.0.0
description: |
  Maintain a simple static diary website for a little cat named Taotao.
---

# Taotao Diary

This static repository records Taotao's daily life. It does not require an agent,
API key, cron task, or backend service.

## Content Guidelines

- Keep the tone warm, gentle, and light.
- Use everyday topics such as naps, meals, playtime, window-watching, and small discoveries.
- Do not add invented photographs of Taotao.
- Keep the existing `assets/cover.png` unless the owner replaces it themselves.
- Avoid assistant, robot, and other technical branding in user-facing copy.

## Editing

- Add and maintain diary entries in `diary.json` (one object per date, unique `YYYY-MM-DD` dates). The page reads data from this file; do not hand-edit entry text into `index.html`.
- Update descriptions and project copy in `about.html`.
- Keep the `.date-tab`, `#diary-content`, `showDate()`, `setTheme()`, `.typing`, and calendar dialog (`#calendar-backdrop`) structures in `index.html`.
- Keep `README.md` and `README_zh.md` identical as Chinese project documentation.
