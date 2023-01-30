# Git Workflow

1. clone repo 然後確認 compile, setup 都沒有問題
1. 在 repo 裡面建立一個 branch，要在 local 從 master checkout 一個 branch 出去
    1. 想要創建同時切換到新 branch：`$ git checkout -b <branch-name>`
    1. 想要創建新的 branch 但不切換：`$ git branch <branch_name>`
1. 撰寫測試（或修改程式碼）、commit 後 push 回 remote
1. 往 Master 發一個 Pull Request
1. 等人 Review 然後依照 comment 修正
1. 沒問題這個 branch 就會 merge

```
git clone
git checkout -b add-my-context

# Write some code...

git add .
git commit -m "add-my-context-v1"
git push

# Pull Request
```

* 現行的開發團隊基本上都會透過[這份文件](https://docs.github.com/en/get-started/quickstart/github-flow)來建置 Work Flow還有其他額外功能 audit branch & releasing 
* flowPR 會跑 CI build，流程可以參考[這個檔案](https://github.com/consenlabs/tokenlon-contracts/blob/master/.github/workflows/node.js.yml)，推上去之前可以先在 local 跑一些基本的做驗證


## PR Problem

### Conflict 
> *This branch has conflicts that must be resolved.*

```
git checkout master
git pull
git checkout <branch>
git merge master
[ ... resolve any conflicts ... ]
git add [files that were conflicted]
git commit
git push
```

![](https://i.imgur.com/xdoXJxP.jpg)

### Squash

https://stackoverflow.com/questions/5189560/how-do-i-squash-my-last-n-commits-together

---

## Others

### gh-pages
- [Deployment | Create React App](https://create-react-app.dev/docs/deployment/#github-pages)
- [Deploy an Nx React App to GitHub Pages](https://emilyxiong.medium.com/deploy-a-nx-react-app-to-github-pages-a83de7551ec0)

### GitHub Profile README
- [awesome-github-profile-readme](https://github.com/abhisheknaiidu/awesome-github-profile-readme)
- [GitHub Readme Stats](https://github.com/anuraghazra/github-readme-stats)
- [GitHub Profile README Generator](https://github.com/rahuldkjain/github-profile-readme-generator)
- [Dev Metrics in Readme with added feature flags 🎌](https://github.com/marketplace/actions/profile-readme-development-stats)

---

## Reference

* [連猴子都能懂的 Git 入門指南](https://backlog.com/git-tutorial/tw/intro/intro1_1.html)
* [Git 版本控制：如何進行多人協作 & 同步分支](https://hackmd.io/@Heidi-Liu/git-workflow)
* [GIT Push and Pull Tutorial](https://www.datacamp.com/tutorial/git-push-pull)
* [Learn Git Branching](https://learngitbranching.js.org/?locale=zh_TW)
