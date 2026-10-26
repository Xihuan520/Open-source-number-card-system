# OpenHaoka - Telecom Card Distribution System

[简体中文](README.md) | English

A high-performance, open-source telecom card (号卡) distribution management system built on the **Hyperf** framework. It leverages Swoole coroutines to handle **1000+ concurrent connections**, covering the full lifecycle of card inventory, multi-level agent management, and commission settlement.

## ✨ Features

- 🚀 **High Performance** - Built on Hyperf + Swoole coroutines, supporting 1000+ concurrent connections
- 🎫 **Card Management** - Full lifecycle management of telecom cards: import, allocate, activate, and archive
- 🤝 **Multi-level Agent System** - Multi-tier agent architecture with role-based permissions
- 💰 **Commission Settlement** - Automatic commission calculation and settlement for distribution channels
- 📊 **Real-time Dashboard** - Business statistics, order analytics, and agent performance overview
- 🔐 **Secure Authentication** - JWT-based API authentication with fine-grained access control
- 🐳 **One-click Deployment** - Docker Compose support for quick environment setup

## 🛠 Tech Stack

| Component   | Technology        |
|-------------|-------------------|
| Framework   | Hyperf 3.x        |
| Language    | PHP 8.2+          |
| Database    | MySQL 8.0+        |
| Cache       | Redis 6.0+        |
| Server      | Swoole 5.0+       |
| Deployment  | Docker / Compose  |

## 📋 Requirements

- PHP 8.2+
- Swoole 5.0+
- MySQL 8.0+
- Redis 6.0+
- Docker & Docker Compose *(optional, for containerized deployment)*

## 🚀 Quick Start

### Option A: Docker Deployment (Recommended)

```bash
# 1. Clone the repository
git clone https://github.com/你的用户名/openhaoka.git
cd openhaoka

# 2. Copy environment configuration
cp .env.example .env

# 3. Start all services
docker compose up -d

# 4. Install PHP dependencies
docker exec -it openhaoka-app composer install

# 5. Run database migrations
docker exec -it openhaoka-app php bin/hyperf.php migrate

# 6. Access the application
# Frontend:   http://localhost:8080
# Admin Panel: http://localhost:8080/admin
Option B: Local Development
# 1. Install dependencies
composer install

# 2. Configure environment
cp .env.example .env

# 3. Start Hyperf server
php bin/hyperf.php start

# 4. Run database migrations
php bin/hyperf.php migrate
😊 Default Account
Security Notice: Please change the default password immediately after your first login!
Role Username Default Password
Admin admin admin123
📁Project Structure
openhaoka/
├── app/
│   ├── Controller/     # HTTP controllers
│   ├── Model/          # ORM models
│   ├── Service/        # Business logic layer
│   └── Middleware/     # Middleware
├── config/             # Configuration files
├── database/           # Migrations & seeders
├── .env.example        # Environment template
├── docker-compose.yml  # Docker orchestration
└── composer.json       # PHP dependencies
📚 API Documentation

After starting the application, interactive API docs are available at:
http://localhost:8080/swagger
🗺 Roadmap

☑ Agent management

☑ Card inventory management

☑ Commission settlement

☐ Carrier API integration templates

☐ Commission detail reports

☐ Mobile payment integration

🤝 Contributing

Contributions are welcome! Feel free to submit issues and pull requests.

1. Fork the repository

2. Create your feature branch: git checkout -b feature/amazing-feature

3. Commit your changes: git commit -m 'Add some amazing feature'

4. Push to the branch: git push origin feature/amazing-feature

5. Open a Pull Request

Please read CONTRIBUTING.md(CONTRIBUTING.md) for details.

📄 License

This project is licensed under the MIT License - see the LICENSE(LICENSE) file for details.

📬 Contact

• GitHub Issues: https://github.com/你的用户名/openhaoka/issues(https://github.com/你的用户名/openhaoka/issues)

• Email: 624015796@qq.com

⭐ Support

If this project helps you, please gi