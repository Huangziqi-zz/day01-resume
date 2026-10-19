# 首次推送步骤

> **状态：已完成（2026-10-19）**
> 仓库地址：https://github.com/Huangziqi-zz/day01-resume
> 日常提交只需要三条命令：`git add .` → `git commit -m "feat: 今天做了什么"` → `git push`。
> 下面内容留作备用，换电脑或新建仓库时再照着走。

本地仓库已经初始化并完成首次提交，接下来只差把代码推到 GitHub。

## 第 1 步：先在 GitHub 建空仓库

打开 https://github.com/new

- Repository name：`day01-resume`
- 可见性：选 **Public**（作品集要给别人看）
- **不要勾** Add a README file、Add .gitignore、Choose a license

> 勾了会生成一条 GitHub 侧的历史，推送时会报 `rejected (fetch first)`，新手最容易卡在这。

## 第 2 步：确认 SSH 通了

```bash
ssh -T git@github.com
```

期望输出：`Hi Huangziqi-zz! You've successfully authenticated...`

（如果还是 `Permission denied`，说明公钥没加到 GitHub：
https://github.com/settings/keys → New SSH key → 粘贴公钥）

## 第 3 步：绑定远程并推送

在本文件夹打开终端（VS Code 里按 <kbd>Ctrl</kbd> + <kbd>`</kbd>）：

```bash
git remote add origin git@github.com:Huangziqi-zz/day01-resume.git
git branch -M main
git push -u origin main
```

## 第 4 步：验证

刷新 https://github.com/Huangziqi-zz/day01-resume ，能看到 README 就成功了。

之后每天只需要三条命令：

```bash
git add .
git commit -m "feat: 今天做了什么"
git push
```

## 常见报错对照

| 报错 | 原因 | 解决 |
| --- | --- | --- |
| `Permission denied (publickey)` | 公钥没加到 GitHub | 去 settings/keys 添加 |
| `remote origin already exists` | 重复添加远程 | `git remote set-url origin git@github.com:Huangziqi-zz/day01-resume.git` |
| `rejected ... fetch first` | GitHub 建仓时勾了 README | `git pull --rebase origin main` 再 push |
| `src refspec main does not match any` | 还没有提交 | 先 `git add .` + `git commit` |
