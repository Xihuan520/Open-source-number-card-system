# 开源-数字-卡系统

English | 简体中文

开源号卡分销系统，专为号卡运营商输送代理商团队打造的高性能号卡分销管理系统。

![License](https://img.shields.io/badge/license-Apache2.0-green)
![Hyperf](https://img.shields.io/badge/Hyperf-3.1-blue)
![PHP](https://img.shields.io/badge/PHP-8.2-purple)

## 项目简介
专为号卡运营商、代理商团队打造的高性能号卡分销管理系统，支持全链路号卡业务流转、多级代理管理、自动分佣结算。

## 核心特性
- 基于Hyperf协程架构，支持1000+并发请求
- 支持多渠道聚合支付
- 内置敏感词审核、违规内容拦截规则
- 可视化多级分佣配置
- 容器化一键部署，分钟级启动服务

## 快速启动
```bash
# 克隆项目
git clone https://github.com/你的用户名/开源-数字-卡系统.git

# 安装依赖
composer install

# 启动服务
php bin/hyperf.php start# Open-source-number-card-system
QQ: 624015796, the author of Open Source Card System
# OpenHaoka 开源号卡分销系统
[![License](https://img.shields.io/badge/license-Apache2.0-green.svg)]()
[![Hyperf Version](https://img.shields.io/badge/Hyperf-3.1-blue.svg)]()
[![PHP Version](https://img.shields.io/badge/PHP-8.2-purple.svg)]()

## 项目简介
专为号卡运营商、代理商团队打造的高并发分销管理系统，支持号卡上架、多级分佣、订单实时通知、支付全链路闭环。

## 核心特性
- 协程架构单实例支持1000+并发订单处理
- 支持聚合支付自动对账
- 内置敏感词审核防违规
- 可视化分销数据大屏
- 容器化一键部署5分钟启动

## 快速启动
```bash
git clone 项目地址
docker compose up -d
访问后台：http://localhost:8080/admin
默认账号：admin@openhaoka.com 密码：123456
贡献指南
欢迎提交Issue与PR，所有合并代码需通过单元测试校验。
### 3. 一键部署docker-compose.yml
```yaml
version: '3.8'
services:
  php:
    image: hyperf/hyperf:8.2-alpine-v3.18-swoole
    volumes:
      - ./:/opt/www
    ports:
      - "9501:9501"
    working_dir: /opt/www
    command: php bin/hyperf.php start
  mysql:
    image: mysql:8.0
    environment:
      MYSQL_ROOT_PASSWORD: openhaoka123
  redis:
    image: redis:7.2-alpine
4..env.example示例
APP_NAME=OpenHaoka
DB_HOST=mysql
DB_PORT=3306
REDIS_HOST=redis
以上所有基础文件全部可直接使用，仅需补充对应业务模块的逻辑代码即可投入开发。
