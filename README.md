# 🌈 Containly

Containly 是一个现代化的 Docker 容器仪表盘，提供清晰直观的容器可视化体验。

你可以使用它查看容器状态、端口映射、网络模式，并快速跳转访问服务。它还内置端口在线检测、夜间模式、自动刷新等实用功能，适合运维、自托管开发者、云原生团队使用。

---

## 🚀 特性亮点

- 🧊 **美观 UI**：渐变背景 + 卡片分组，支持暗黑模式切换
- 🔍 **容器状态分类**：自动识别 running / paused / exited 容器
- 🌐 **主机端口跳转**：支持宿主机 IP 输入并生成跳转链接
- 🧪 **端口存活探测**：实时检测每个容器服务是否在线
- 🔄 **自动刷新**：每 30 秒自动刷新容器状态
- 📋 **端口一键复制**：点击即可复制端口号

---

## 🧰 快速部署（使用 Docker Compose）

1. **克隆仓库**

```bash
git clone https://github.com/yourname/containly.git
cd containly
```

````

2. **构建并运行容器**

```bash
docker-compose up --build -d
```

3. **访问仪表盘**

浏览器打开：http://localhost:5000
首次使用请在顶部输入宿主机的 IP，用于生成端口跳转链接。

---

## 📦 Docker Compose 配置

```yaml
version: "3.8"

services:
  containly:
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "5000:5000"
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
    restart: unless-stopped
```

---

## 🔧 本地开发（可选）

如果你希望运行源码：

```bash
# 安装依赖
pip install flask docker

# 启动服务
python app.py
```

默认监听：`http://127.0.0.1:5000`

---

## 📸 页面预览

> ![](https://your-screenshot-link.com/containly-preview.png)

---

## 📖 文件结构说明

```
containly/
├── app.py                 # Flask 后端
├── templates/
│   └── index.html         # 前端页面（Jinja2 模板）
├── static/                # （可选）CSS/JS 文件夹
├── Dockerfile             # Docker 镜像构建文件
├── docker-compose.yml     # 启动配置
└── README.md
```

---

## 📝 许可证

本项目采用 MIT License，欢迎自由使用、修改和部署。

---

> Made with ❤️ by [Your Name] — Contain your chaos, beautifully.
````
