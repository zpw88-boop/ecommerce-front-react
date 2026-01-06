# 中小型企业电商平台前端系统
这是一个基于 React 的中小型企业电商平台，前端应用，提供完整的购物流程和用户管理功能。

## 功能特性
- **商品浏览** - 商品列表、详情查看、搜索筛选
- **购物车管理** - 添加商品、数量管理、库存校验
- **订单系统** - 订单创建、订单列表、订单详情、状态管理
- **用户中心** - 个人信息管理、密码修改
- **用户认证** - JWT 登录/注册
- **响应式设计** - 支持桌面端和移动端

## 技术栈
- **React 19.2.3** - UI 框架
- **React Router DOM 7.11.0** - 路由管理
- **Ant Design 6.1.2** - UI 组件库
- **Axios 1.13.2** - HTTP 请求

## 项目结构
src/  
├── api/                    # API 接口层  
│   └── front/              # 前台业务接口  
│       ├── cartApi.js      # 购物车接口  
│       ├── orderApi.js     # 订单接口  
│       ├── productApi.js   # 商品接口  
│       └── userApi.js      # 用户接口  
├── components/             # 公共组件  
│   ├── Header.jsx          # 顶部导航栏  
│   ├── ProductCard.jsx     # 商品卡片组件  
│   └── ProductListCard.jsx # 商品列表卡片  
├── pages/                  # 页面组件  
│   ├── FrontHome.jsx       # 首页（商品列表）  
│   ├── ProductDetail.jsx   # 商品详情  
│   ├── Cart.jsx            # 购物车  
│   ├── Order.jsx           # 订单确认  
│   ├── OrderList.jsx       # 订单列表  
│   ├── OrderDetail.jsx     # 订单详情  
│   ├── UserProfile.jsx     # 个人中心  
│   ├── Login.jsx           # 登录  
│   └── Register.jsx        # 注册  
├── utils/                  # 工具函数  
│   ├── auth.js             # 认证工具（JWT处理）  
│   └── request.js          # HTTP 请求封装  
└── App.js                  # 应用入口和路由配置  

## 快速开始
### 环境要求
- Node.js >= 14.0.0
- npm >= 6.0.0

### 安装依赖
**npm install**

### 启动开发服务器
**npm start**  
应用将在 [http://localhost:3080](http://localhost:3080) 启动。

### 构建生产版本
**npm run build**  
构建文件将输出到 build/ 目录。

### 运行测试
**npm test**

## 主要页面
| 路由 | 页面 | 说明 |
|------|------|------|
| `/` | 首页 | 商品列表、搜索筛选 |
| `/products/:id` | 商品详情 | 商品详细信息、加入购物车 |
| `/cart` | 购物车 | 购物车管理、结算 |
| `/order` | 订单确认 | 订单信息确认、支付方式选择 |
| `/orders` | 订单列表 | 查看所有订单 |
| `/orders/:id` | 订单详情 | 订单详细信息、确认收货 |
| `/profile` | 个人中心 | 个人信息、密码修改 |
| `/login` | 登录 | 用户登录 |
| `/register` | 注册 | 用户注册 |

## 环境配置
### API 基础地址
默认后端 API 地址为 `http://localhost:8080`，可在 src/utils/request.js 中修改：  

**const request = axios.create({**  
    **baseURL: 'http://localhost:8080', // 修改为你的后端地址**  
    **timeout: 5000,**  
**});**

### 端口配置
默认开发端口为 3080，可在 package.json 中修改：  

**"scripts": {**  
  **"start": "PORT=3080 react-scripts start"**  
**}**

## 核心功能说明
### 用户认证
- 使用 JWT Token 进行身份认证
- Token 存储在 localStorage 中
- 请求自动携带 Token（通过 Axios 拦截器）

### 购物车
- 支持登录用户和未登录用户
- 未登录用户使用 localStorage 存储购物车
- 登录用户购物车数据存储在服务器
- 支持库存校验和数量限制

### 订单管理
- 订单状态：待发货、已发货、已完成、已取消
- 仅"待发货"状态可取消订单
- 已发货订单可确认收货
- 支持多种支付方式：支付宝、微信、银行卡、货到付款

### 响应式设计
- 自动检测屏幕宽度（断点：768px）
- 移动端优化布局和交互
- 移动端底部导航栏

## 开发说明
### 代码规范
- 使用函数式组件和 React Hooks
- 遵循 React 最佳实践
- 组件和函数使用清晰的命名

### 状态管理
- 使用 useState 管理组件级状态
- 使用 useEffect 处理副作用
- 使用自定义事件实现跨组件通信

### API 调用
所有 API 调用统一封装在 src/api/front/ 目录下，使用统一的请求工具 src/utils/request.js。

## 技术支持
如有问题或建议，请联系开发团队，邮箱：z_pw@163.com。

## License
MIT