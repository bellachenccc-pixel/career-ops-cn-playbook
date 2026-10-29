# GitHub 发布前检查清单

## 个人信息

- [ ] 删除手机号、邮箱、住址、证件信息和私人日历链接。
- [ ] 删除真实简历文件及其导出 PDF。
- [ ] 检查截图中的头像、姓名、浏览器标签和通知。
- [ ] 确认示例公司、岗位和数字已经脱敏或明确标为虚构。

## 密钥与连接信息

- [ ] 不提交 `.env`、Cookie、App Secret、Access Token 或 Refresh Token。
- [ ] 不提交飞书 Base Token、Table ID 和内部文档 ID。
- [ ] 如果密钥曾出现在聊天、终端输出或提交历史中，先轮换再发布。
- [ ] 使用 GitHub Secret Scanning 或同类工具检查整个提交历史。

建议执行：

```bash
git status --short
git diff --cached
git grep -nEi 'secret|token|password|cookie|app_id|app_secret'
```

不要只检查当前文件；如果仓库已经有提交历史，还要检查历史记录。

## 内容与归属

- [ ] 没有把使用过的工具写成自己开发的工具。
- [ ] 没有发布前雇主的内部数据、客户名称或未公开策略。
- [ ] 已注明对上游开源项目的引用与关系。
- [ ] 已确认第三方素材、字体和图片可以公开使用。

## 最后预览

- [ ] GitHub Markdown、表格和 Mermaid 图能够正常显示。
- [ ] 所有相对链接均可访问。
- [ ] 示例文件可以独立看懂。
- [ ] README 说明了项目能做什么，也说明了不会自动做什么。

## 首次发布命令

在确认目录和远程仓库名称无误后：

```bash
git init
git add .
git commit -m "Initial public playbook"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/career-ops-cn-playbook.git
git push -u origin main
```

发布前请再次运行本清单，不要直接复制命令后跳过检查。
