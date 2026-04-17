# 面向设计师的 Git 实操教学稿

## 这份稿子怎么用

这不是给工程师的 Git 课，而是给设计师、产品、运营、内容同学的零基础入门课。

目标只有 3 个：

1. 听懂 Git 到底是干什么的
2. 会用图形界面完成最基本的协作
3. 知道在 Agent 场景里不用背命令，直接说自然语言即可

默认教学方式：

- 工具以 `GitHub Desktop` 为主
- 不要求记命令
- 不从终端入门
- 先会操作，再补概念

---

## 一句话先讲清楚 Git 是什么

可以直接这样说：

> Git 不是“程序员写代码的黑话工具”，它本质上是一个管理版本和协作的系统。  
> 它记录的不是“代码”本身，而是“变化”。  
> 谁改了、改了什么、为什么改、能不能退回去、能不能并行做多个方案，Git 都能帮你管住。

再换成设计师更容易理解的话：

> 如果 Figma 的版本历史是管理单个设计文件的变化，Git 更像是在管理整个项目文件夹的版本历史。  
> 它不只管设计稿，也可以管文档、图片、网页文件、设计系统资产、演示材料，甚至任何团队要长期协作的内容。

---

## 把几个核心词翻译成设计语言

### `repository`

项目仓库。

可以理解成一个“项目空间”或者“受版本控制的项目文件夹”。

### `commit`

一次正式存档。

不是普通的保存，而是“带说明的保存”。  
保存只告诉电脑“现在写下来了”，`commit` 则告诉团队“这次具体改了什么”。

### `branch`

一个分支方案。

可以把它理解成：

- 备选方案
- 新方向探索稿
- 不影响主线的试验版本

### `merge`

把分支成果合并回来。

比如你做了一个“官网改版尝试”，验证通过后，把它合回主版本。

### `push`

把你本地已经存好的版本，上传到远端团队仓库。

### `pull`

把团队远端的最新变化，拉回自己电脑。

---

## 建议的开场说法

可以这样开场：

> 今天这节课不要求大家会命令行，也不要求大家理解 Git 的所有概念。  
> 我们只解决一件事：让大家能安全地改文件、留痕、同步、分支尝试、回退，并且能跟工程或其他设计师协作。  
> 你们今天学到的不是“背命令”，而是掌握一种协作方式。

---

## 为什么设计师也应该会 Git

可以直接讲这些实际场景：

- 改官网文案、图片、插画、落地页资源时，需要知道是谁改了什么
- 多人同时改项目文件时，尽量避免互相覆盖
- 想大胆试一个方案时，不想影响线上主版本
- 设计系统文档、组件说明、资源文件需要长期维护
- 交接项目时，希望能看清楚项目是怎么一步步变化的
- 与工程协作时，不再只能“发文件”，而是直接参与同一套版本流程

一句总结：

> 会 Git，不是为了变成工程师，而是为了拥有更稳的协作能力。

---

## 推荐教学方式

对零基础设计师，建议顺序是：

1. 先用 `GitHub Desktop`
2. 先做“新建仓库 -> 改文件 -> 提交 -> 上传”
3. 再做“分支 -> 切换 -> 合并”
4. 最后再讲冲突、回退、Pull Request

不要一上来讲：

- `rebase`
- `cherry-pick`
- `stash`
- 一堆终端命令

这些会迅速把人劝退。

---

## 课前准备

### 需要的东西

- 一个 GitHub 账号
- 安装 `GitHub Desktop`
- 一个文本编辑器

如果是设计师培训，文本编辑器甚至可以先用系统自带文本工具，重点不是编辑器，而是理解版本流程。

### 为什么选 GitHub Desktop

因为它是图形界面，适合入门。GitHub 官方文档明确把它定位为可用 GUI 完成常见 Git 操作的工具，并且提供了从新建仓库、提交、推送、分支到拉取请求的一整套入门流程。  
参考：

- [About GitHub Desktop](https://docs.github.com/desktop/overview/about-github-desktop)
- [Getting started with GitHub Desktop](https://docs.github.com/desktop/guides/getting-started)
- [Creating your first repository using GitHub Desktop](https://docs.github.com/en/desktop/installing-and-configuring-github-desktop/overview/creating-your-first-repository-using-github-desktop)

---

## 一堂 45 到 60 分钟的实操课怎么带

### Part 1. 先建立心智模型，5 分钟

只讲一句主线：

> Git 的核心不是“写代码”，而是“管理变化”。

再讲一个流程图：

`本地改文件 -> commit 存档 -> push 上传 -> 团队看到 -> pull 同步`

如果要配合口头解释，可以这样说：

- 本地：你电脑上的项目
- 远端：团队共享的项目
- commit：一次有说明的存档
- push：把本地存档传上去
- pull：把别人传上去的更新拉下来

---

### Part 2. 第一轮最基础实操，15 分钟

这一步的目标是：  
让大家完成一次完整闭环。

#### 练习目标

每个人都做完这 6 步：

1. 新建仓库
2. 创建一个 README 文件
3. 改一行内容
4. 提交 commit
5. 发布到 GitHub
6. 在网页上看到自己的提交

#### 教学动作

##### 第一步：打开 GitHub Desktop

如果是第一次打开，会看到类似 `Let's get started` 的界面。

可以告诉学员：

> 这里你可以新建仓库、克隆仓库，或者直接用 GitHub Desktop 自带教程仓库练习。  
> GitHub 官方也建议新手先从 tutorial repository 或新建仓库开始。

##### 第二步：新建一个仓库

引导词：

> 点击 `Create a New Repository on your Hard Drive`

推荐填写：

- Name: `designer-git-practice`
- Description: `Git practice for designers`
- 勾选 `Initialize this repository with a README`

解释：

> 这一步相当于创建一个“被 Git 管理的项目文件夹”。

##### 第三步：发布仓库

仓库建好后，顶部通常会看到 `Publish repository`。

引导词：

> 点击 `Publish repository`，把本地仓库发布到 GitHub。

这里可以顺手讲清楚：

- 本地仓库：只在你电脑里
- 发布后：GitHub 上也有一份
- 这时团队协作才真正开始成立

##### 第四步：打开 README 文件并修改

引导词：

> 打开 `README.md`，写三行自我介绍或者项目介绍，比如：

```md
# Designer Git Practice

This repository is for Git learning.
Created by [你的名字].
```

##### 第五步：回到 GitHub Desktop 看变化

引导词：

> 回到 GitHub Desktop，点击左侧 `Changes`。  
> 你会看到刚才哪个文件变了、变了哪几行。

重点解释：

> 这一步很重要，因为 Git 不是只管“结果”，它还管“变化的细节”。

##### 第六步：写 commit message 并提交

引导词：

> 在底部 `Summary` 输入一句话，比如：`Add self introduction to README`

然后点：

> `Commit to main`

解释要点：

> commit message 不是给机器看的，是给未来的自己和团队看的。  
> 最好写“做了什么”，而不是写“update”“修改了一下”这种模糊表述。

##### 第七步：推送到远端

引导词：

> 点击顶部的 `Push origin`

解释：

> 现在这次提交才真正同步到 GitHub 上。  
> 只 commit 不 push，别人还看不到。

##### 第八步：在网页上验证

引导词：

> 打开 GitHub 上的仓库页面，确认 README 已更新，且能看到提交记录。

到这里，第一轮闭环就完成了。

---

### Part 3. 第二轮实操，理解 branch，15 分钟

这一步的目标是：

> 让大家知道“分支不是高级功能，而是安全试错空间”。

#### 给设计师的解释方式

不要说“分布式版本控制的隔离开发分支”。  
直接说：

> branch 就像你开了一个平行方案，不会直接把主版本弄乱。  
> 对设计师来说，它最像“探索稿”。

#### 练习动作

##### 第一步：创建一个新分支

引导词：

> 点击顶部 `Current Branch` -> `New Branch`

分支名建议：

`homepage-visual-test`

解释：

> 分支名最好一看就知道你要试什么。

##### 第二步：切到新分支

GitHub Desktop 创建分支后通常会自动切过去。

提醒学员看顶部是否已经不再是 `main`，而是新分支名。

##### 第三步：继续修改 README

让学员新增一段：

```md
## Visual Exploration

This branch is for testing a new visual direction.
```

##### 第四步：提交并推送

commit message 示例：

`Add visual exploration note`

然后继续：

- `Commit to homepage-visual-test`
- `Push origin`

##### 第五步：讲清楚现在发生了什么

可以这样说：

> 现在我们并没有动主线版本。  
> 我们只是把一个实验方案放到了自己的支线里。  
> 如果这个方案不错，再合回主分支；如果不好，删掉分支即可。

---

### Part 4. 第三轮实操，理解 merge，10 分钟

这一步的目标是让学员理解：

> merge 不是神秘操作，只是把“支线成果”带回主线。

#### 操作步骤

##### 第一步：切回主分支

引导词：

> 点击 `Current Branch`，切回 `main`

##### 第二步：合并分支

引导词：

> 继续点击 `Current Branch`，选择 `Choose a branch to merge into main`

然后选中刚才的分支，执行合并。

##### 第三步：推送主分支

合并完成后，再点：

> `Push origin`

##### 第四步：解释给学员听

> 这一步代表我们确认这个实验方案值得保留，所以把它正式带回主线。  
> 如果不想保留，也可以不合并，甚至删除这个分支。

---

## 如果还想再进一层，可以加一个 Pull Request 演示

对设计师来说，不一定一上来就需要完整理解 PR，但至少可以知道它是什么：

> Pull Request 就像一个“正式提案”。  
> 你不是直接改主线，而是把你的方案提交出来，请团队 review，再决定是否合并。

一句翻译版：

> branch 是方案，PR 是提案，merge 是采纳。

---

## 可以直接照着讲的讲稿版本

### 开场 1 分钟

> 很多人一听 Git，就以为那是工程师才用的命令行工具。  
> 其实不是。Git 真正解决的是“多人怎么安全协作”这件事。  
> 对设计师来说，它最重要的价值不是写代码，而是管理版本、追踪改动、保留实验空间，以及随时能回退。

### 讲 commit

> 你可以把 commit 理解成一次带说明的存档。  
> 普通保存只是在本机把文件写下来，但 commit 是告诉团队：我这次做了什么改动。

### 讲 branch

> branch 就像你开了一个探索稿。  
> 你可以在里面大胆试，不会直接弄乱主版本。

### 讲 merge

> merge 就是当这个探索稿验证通过后，把它带回主线。

### 讲 push / pull

> push 是把你本地的成果同步到团队远端。  
> pull 是把团队最新的成果同步回你这里。

---

## 学员最容易卡住的点

### 1. 以为保存了就等于提交了

不是。  
保存只是改了本地文件。  
要让 Git 正式记录，需要 `commit`。  
要让团队看到，还需要 `push`。

### 2. 以为分支很高级，不敢用

恰恰相反。  
分支是最适合新手保护自己的功能。  
因为它让你试错时不伤主线。

### 3. commit message 写得太随意

尽量不要写：

- `update`
- `改一下`
- `fix`

更好的是：

- `Update homepage banner copy`
- `Add icon assets for onboarding`
- `Revise README for project intro`

### 4. 不知道自己当前在哪个分支

养成一个习惯：  
每次操作前，先看顶部 `Current Branch`。

### 5. 没 pull 就开始改

多人协作时，先同步最新版本，再开始改，会少很多问题。

---

## 给设计师的最低可用流程

如果只要求学会最小闭环，那就记住这 5 步：

1. 先 `Pull` 最新版本
2. 开一个 `Branch`
3. 改文件
4. 写清楚 `Commit`
5. `Push` 并发起 PR 或通知同事

这 5 步已经足够覆盖很多日常协作。

---

## 在 Agent 的使用场景里怎么讲

这一段建议你明确说出来：

> 在 Agent 的使用场景里，默认不应该要求大家记命令。  
> 用户直接用自然语言描述目标即可。  
> 命令、参数、固定格式，应该是高级玩法，不应该是门槛。

### 可以直接对外说的版本

> 你可以把 Agent 理解成一个能听懂任务意图的协作者，而不是一个要求你背指令的命令行工具。  
> 大多数情况下，你直接说“帮我做什么”就够了。

### 示例

不要要求用户说：

- `/create-branch homepage-v2`
- `/summarize-last-3-commits`
- `/review-this-file`

而应该鼓励用户直接说：

- “帮我开一个新分支，准备试试首页改版。”
- “帮我看看这个仓库最近都改了什么。”
- “帮我把这个说明文档整理得更适合设计师阅读。”
- “帮我检查一下这次改动会不会影响主版本。”
- “把我这次修改整理成一个清楚的 commit message。”

### 为什么自然语言更重要

因为大多数真实工作场景不是“我知道命令，只是懒得打”，而是：

- 我知道目标，但不知道怎么操作
- 我知道大概方向，但不知道流程
- 我怕做错，不敢点

这时最好的交互方式不是命令，而是自然语言。

---

## 你可以现场演示的 Agent 配合 Git 话术

如果要把 Git 和 Agent 放在一起讲，可以演示这些话：

### 场景 1：不会起 commit message

> “根据我这次改动，帮我写一个清楚的 commit message。”

### 场景 2：不确定该不该开分支

> “我准备试一个新的视觉方案，这种情况是不是应该开新分支？”

### 场景 3：不理解最近项目变化

> “帮我总结一下这个项目最近一周改了哪些内容，用设计师能听懂的话说。”

### 场景 4：准备发 PR

> “帮我把这次修改整理成一段可以发给团队 review 的说明。”

### 场景 5：不敢合并

> “我现在在这个分支上，帮我判断一下能不能合回 main，需要注意什么。”

重点结论：

> Agent 应该降低 Git 的使用门槛，而不是再造一层命令门槛。

---

## 一页总结，可以放到 PPT 结尾

### Git 对设计师的意义

- 管理版本
- 记录变化
- 安全试错
- 支持协作
- 随时回退

### 设计师最该先会的不是命令，而是流程

`改文件 -> commit -> push -> branch -> merge`

### Agent 的默认交互方式

不是背指令。  
是直接用自然语言说目标。

---

## 课后练习建议

给学员留 3 个作业即可：

1. 新建一个练习仓库，完成一次 README 修改并 push
2. 新建一个分支，写一段“方案探索说明”，再合回 main
3. 用自然语言问 Agent：  
   “帮我总结这次练习里我做了哪些 Git 操作，它们分别是干什么的”

---

## 备用参考资料

以下是本稿采用的官方参考资料：

- GitHub Docs: [About GitHub Desktop](https://docs.github.com/desktop/overview/about-github-desktop)
- GitHub Docs: [Getting started with GitHub Desktop](https://docs.github.com/desktop/guides/getting-started)
- GitHub Docs: [Creating your first repository using GitHub Desktop](https://docs.github.com/en/desktop/installing-and-configuring-github-desktop/overview/creating-your-first-repository-using-github-desktop)
- GitHub Docs: [Committing and reviewing changes to your project in GitHub Desktop](https://docs.github.com/en/desktop/making-changes-in-a-branch/committing-and-reviewing-changes-to-your-project-in-github-desktop)
- GitHub Docs: [Managing branches in GitHub Desktop](https://docs.github.com/en/desktop/making-changes-in-a-branch/managing-branches-in-github-desktop)
- GitHub Docs: [Syncing your branch in GitHub Desktop](https://docs.github.com/enterprise-server%403.20/desktop/working-with-your-remote-repository-on-github-or-github-enterprise/syncing-your-branch-in-github-desktop)

