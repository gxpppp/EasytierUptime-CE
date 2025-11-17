# EasyTier Uptime CE

EasyTier Uptime CE 是一个开源的网络节点监控系统，用于实时监控和管理分布式网络节点的运行状态。

## 功能特性

- **实时监控**: 监控网络节点的在线状态和性能指标
- **分页显示**: 支持大量节点的分页浏览和搜索
- **详细视图**: 提供单个节点的详细信息查看
- **API接口**: 完整的RESTful API接口
- **现代化界面**: 响应式设计，支持移动端访问

## 技术栈

### 后端
- Python 3.8+
- Flask Web框架
- MySQL数据库
- SQLAlchemy ORM

### 前端
- 原生HTML/CSS/JavaScript
- 响应式设计
- 现代化UI组件

## 项目结构

```
├── backend/           # 后端应用
│   ├── app.py        # Flask主应用
│   ├── create_tables.py # 数据库表创建脚本
│   └── setup_mysql.py   # MySQL配置脚本
├── frontend/          # 前端资源
│   ├── index.html    # 主页面
│   ├── css/          # 样式文件
│   └── js/           # JavaScript文件
├── scripts/           # 实用脚本
├── docs/             # 文档
└── dataimport/       # 数据导入文件
```

## 快速开始

### 环境要求

- Python 3.8+
- MySQL 5.7+
- Windows/Linux/macOS

### 安装步骤

1. 克隆项目到本地
2. 安装Python依赖：
   ```bash
   pip install -r requirements.txt
   ```

3. 配置MySQL数据库：
   - 修改`.env`文件中的数据库连接信息
   - 运行数据库初始化脚本：
   ```bash
   python backend/setup_mysql.py
   python backend/create_tables.py
   ```

4. 启动应用：
   ```bash
   python backend/app.py
   ```

5. 访问应用：
   - 前端界面：http://127.0.0.1:5000
   - API文档：http://127.0.0.1:5000/docs

## API接口

### 节点管理

- `GET /api/nodes` - 获取节点列表（支持分页和搜索）
- `GET /api/nodes/<node_id>` - 获取单个节点详情
- `POST /api/nodes` - 创建新节点
- `PUT /api/nodes/<node_id>` - 更新节点信息
- `DELETE /api/nodes/<node_id>` - 删除节点

### 监控数据

- `GET /api/monitor` - 获取监控统计数据
- `GET /api/monitor/history` - 获取历史监控数据

## 配置说明

### 环境变量

在`.env`文件中配置以下环境变量：

```
# 数据库配置
DB_HOST=localhost
DB_PORT=3306
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=easytier_uptime

# 应用配置
DEBUG=True
SECRET_KEY=your_secret_key
```

### 数据库配置

项目使用MySQL数据库，需要预先创建数据库并配置连接信息。

## 部署说明

### 开发环境

直接运行`python backend/app.py`启动开发服务器。

### 生产环境

建议使用以下方式部署：
- 使用Gunicorn或uWSGI作为WSGI服务器
- 配置Nginx作为反向代理
- 使用systemd或supervisor管理进程

## 贡献指南

欢迎提交Issue和Pull Request来改进项目。

## 许可证

本项目采用MIT许可证，详见LICENSE文件。

## 联系方式

- 项目主页：https://github.com/gxpppp/EasytierUptime-CE
- 问题反馈：GitHub Issues

## 更新日志

### v1.0.0 (2024-11-17)
- 初始版本发布
- 基础节点监控功能
- 分页显示和搜索功能
- API接口文档