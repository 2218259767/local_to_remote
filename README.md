 好的，下面是第10和第11部分的详细教学内容，适合你在VSCode终端边学边练。

---

## 10. 关联本地仓库与远程仓库（5分钟）

### 10.1 添加远程仓库

**场景：**  
你已经在 Gitee、GitHub 或 GitLab 上新建了一个空仓库，比如地址为：  
`https://gitee.com/yourname/yourrepo.git`

**添加远程仓库命令：**
```bash
git remote add origin https://gitee.com/yourname/yourrepo.git
```
- `origin` 是远程仓库的默认名称，可以自定义。

**查看远程仓库地址：**
```bash
git remote -v
```

---

### 10.2 推送代码到远程仓库

**首次推送（如果是新建的主分支，且远程为空）：**
```bash
git push -u origin master
```
或（如果你的主分支叫 main）：
```bash
git push -u origin main
```
- `-u` 参数让本地分支和远程分支建立跟踪关系，后续可直接用 `git push`。

**后续推送：**
```bash
git push
```

---

### 10.3 从远程仓库拉取代码

**拉取最新代码：**
```bash
git pull
```
- 会把远程仓库的最新内容同步到本地。

---

## 11. Gitee的使用与GitLab本地化部署（10分钟）

### 11.1 Gitee注册与新建仓库

1. **访问 Gitee 官网**：[https://gitee.com](https://gitee.com)
2. **注册账号**：用邮箱或手机号注册。
3. **新建仓库**：
   - 登录后点击右上角“+” → “新建仓库”。
   - 填写仓库名、描述，选择公开或私有。
   - 创建后会看到仓库的 HTTPS 或 SSH 地址。

4. **将本地仓库关联到 Gitee 仓库**（见上面第10部分）。

---

### 11.2 GitLab本地化部署简介及资源推荐

#### 什么是 GitLab 本地化部署？

- **GitLab** 是一个类似于 GitHub、Gitee 的代码托管平台，可以在自己公司的服务器上搭建，适合企业内部使用。
- 支持私有化部署，数据完全掌控在自己手里。

#### 部署方式简介

1. **官方一键安装包（Omnibus）**  
   推荐使用官方 Omnibus 安装包，支持 Linux 各主流发行版。
   - 官方文档：[https://about.gitlab.com/install/](https://about.gitlab.com/install/)
2. **Docker 部署**  
   也可以用 Docker 快速部署：
   ```bash
   docker run --detach \
     --hostname gitlab.example.com \
     --publish 443:443 --publish 80:80 --publish 22:22 \
     --name gitlab \
     --restart always \
     --volume /srv/gitlab/config:/etc/gitlab \
     --volume /srv/gitlab/logs:/var/log/gitlab \
     --volume /srv/gitlab/data:/var/opt/gitlab \
     gitlab/gitlab-ce:latest
   ```
   - 详细步骤见 [GitLab Docker 文档](https://docs.gitlab.com/omnibus/docker/)

#### 资源推荐

- [GitLab 官方安装文档](https://about.gitlab.com/install/)
- [GitLab 中文社区](https://gitlab.cn/)
- [B站视频教程：GitLab 本地部署](https://www.bilibili.com/video/BV1hK4y1C7hA)
- [Gitee 帮助文档](https://gitee.com/help)

---

### 小结

- 用 `git remote add` 关联远程仓库，`git push` 推送代码，`git pull` 拉取代码。
- Gitee 注册简单，适合国内用户。
- GitLab 支持本地化部署，适合企业内部使用，推荐官方文档和 Docker 部署方式。

---

如需实际操作演示或遇到具体问题，欢迎随时提问！

