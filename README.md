Hyperf 号卡分销系统
 
🚀 基于 Hyperf 协程框架的企业级开源号卡 / 物联网卡分销 SaaS 系统，集成多级分销、订单生产、聚合支付、实时通信、AI 运营、可视化拓扑、增量数据同步等完整能力，前后端分离架构，可快速私有化部署与二次开发。
 
License
PHP Version
Hyperf Version
Stars
 
 
 
📌 项目简介
 
本项目面向号卡代理商、渠道商、物联网卡运营方，提供从号卡商品管理、多级分销、订单生产、财务结算到运营分析的全流程解决方案。系统采用 PHP 协程技术实现高性能并发，支持靓号销售、普通号卡分销、物联网卡设备管理等多种业务场景，可作为号卡行业的基础业务系统快速落地。
 
项目基于  hyperf-iot  业务底座扩展，融合 Ant Design、AntV G6、Canal、funNLP、IJPay 等多个开源项目的优秀设计与能力。
 
✨ 核心特性
 
- 号卡业务核心：号池管理、靓号智能筛选、多渠道对接、订单全生命周期管理
​
- 多级分销体系：无限级代理商层级、自定义佣金规则、专属推广小店、分销关系可视化
​
- 聚合支付结算：微信/支付宝/银联多渠道支付、多商户隔离、分账提现、自动对账
​
- 实时交互能力：订单状态秒级推送、代理商在线客服、系统异常预警通知
​
- AI 智能运营：智能客服问答、推广文案生成、订单异常分析、分销规则自然语言解读
​
- 数据可视化：分销拓扑图、渠道链路图、设备在线图谱、实时运营数据大屏
​
- 增量数据引擎：基于 Canal 的 MySQL Binlog 订阅，实现缓存实时刷新、全文检索、零侵入操作审计
​
- 合规风控体系：中文敏感词过滤、内容自动审核、手机号/身份证格式校验与脱敏
​
- 设备运维能力：物联网卡终端远程诊断、WebSSH 在线终端管理
 
🧱 技术栈
 
后端
类别技术选型说明核心框架Hyperf 3.1 + SwoolePHP 协程高性能框架开发语言PHP >= 8.1支持强类型与新特性支付组件自研聚合支付模块参考 IJPay 模块化架构设计NLP 能力中文词库工具基于 funNLP 开源词库实现AI 能力DeepSeek / Dify 接口对接支持大模型问答与工作流编排
前端
类别技术选型说明核心框架Vue 3 + Vite现代化前端工程体系UI 组件库Ant Design Vue企业级后台组件体系可视化引擎AntV G6关系图谱与拓扑图渲染
中间件 & 存储
 
- 增量同步：Canal（MySQL Binlog 订阅分发）
​
- 消息队列：RabbitMQ
​
- 缓存与会话：Redis 7+
​
- 全文检索：Elasticsearch（可选）
​
- 主数据库：MySQL 8.0+
 
🏗️ 系统架构
┌─────────────────────────────────────────────────────┐
│                  前端展示层                          │
│  管理后台  │  代理商端  │  店铺端  │  可视化大屏  │
│  (Ant Design Vue)  (AntV G6 拓扑图谱)             │
└───────────────────┬─────────────────────────────────┘
                    │ HTTP / WebSocket
┌───────────────────▼─────────────────────────────────┐
│                  业务服务层 (Hyperf PHP)            │
│  商品中心 │ 分销中心 │ 订单中心 │ 支付结算中心    │
│  AI 助手 │ 客服系统 │ 运维中心 │ 风控合规模块    │
│                  MQ 消费者 / 事件驱动               │
└───────────────────┬─────────────────────────────────┘
                    │
┌───────────────────▼─────────────────────────────────┐
│                  中间件层                           │
│  Canal  │  RabbitMQ  │  Redis  │  Elasticsearch   │
└───────────────────┬─────────────────────────────────┘
                    │
┌───────────────────▼─────────────────────────────────┐
│                  数据存储层                          │
│              MySQL 业务主库                         │
└─────────────────────────────────────────────────────┘
📦 快速开始
 
环境要求
 
- PHP >= 8.1
​
- Swoole PHP 扩展 >= 5.0
​
- Redis / PDO / MBstring PHP 扩展
​
- MySQL >= 8.0
​
- Redis >= 7.0
​
- Composer >= 2.0
 
安装步骤
 
1. 克隆项目
git clone https://github.com/your-username/hyperf-haoka.git
cd hyperf-haoka
2. 安装 PHP 依赖
composer install
3. 配置环境变量
cp .env.example .env
4. 初始化数据库
php bin/hyperf.php migrate
5. 启动服务
# 开发环境（热更新）
php bin/hyperf.php serve:watch

# 生产环境
php bin/hyperf.php start
默认服务端口： 9501 
后台管理地址： http://127.0.0.1:9501/admin 
默认超管账号： admin  /  123456 
 
前端启动
cd frontend
npm install
npm run dev
🧩 功能模块详解
模块名称核心功能设计参考来源号卡商品中心号池管理、靓号筛选、套餐配置、上下架管理hyperf-iot多级分销体系代理商等级、佣金规则、推广链接、专属小店、分销拓扑hyperf-iot + AntV G6订单生产系统下单、开卡、切单、渠道对接、状态同步hyperf-iot + Canal聚合支付中心多渠道支付、多商户隔离、分账提现、对账结算参考 IJPay 模块化架构实时通信中心订单推送、在线客服、系统预警通知参考 webim 长连接设计AI 运营助手智能客服、文案生成、异常诊断、规则解读DeepSeek + Dify数据可视化大屏分销拓扑、渠道链路、设备图谱、实时运营数据AntV G6 + Canal增量数据引擎Binlog 订阅、缓存刷新、全文检索、操作审计Canal合规风控中心敏感词过滤、内容审核、数据脱敏校验funNLP 中文词库设备运维模块物联网卡远程诊断、WebSSH 终端管理gliderlabs/ssh 设计思想系统管理后台权限管理、角色分配、操作日志、系统配置Ant Design Vue
🐳 Docker 一键部署
 
项目提供完整容器化部署方案，可一键启动全部服务：
cd docker
cp .env.example .env
docker compose up -d
默认包含服务：MySQL、Redis、RabbitMQ、Canal、Hyperf 后端、前端 Web 服务。
 
🤝 参与贡献
 
1. Fork 本仓库
​
2. 创建特性分支 ( git checkout -b feature/AmazingFeature )
​
3. 提交更改 ( git commit -m 'Add some AmazingFeature' )
​
4. 推送到分支 ( git push origin feature/AmazingFeature )
​
5. 提交 Pull Request
 
欢迎提交 Issue 反馈问题与建议。
 
📄 开源协议
 
本项目基于 Apache License 2.0 协议开源，可自由用于商业与非商业项目。
 
第三方依赖协议说明
 
- Ant Design Vue：MIT License
​
- AntV G6：MIT License
​
- Canal：Apache License 2.0
​
- funNLP：MIT License
​
- Hyperf：MIT License
 
⚠️ 免责声明：本项目仅用于技术学习与研究，实际运营需遵守国家相关法律法规与运营商合作规定。
 
📞 相关链接
 
- Hyperf 官方文档
​
- Ant Design Vue 文档
​
- AntV G6 文档
​
- Canal 官方仓库