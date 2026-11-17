# 苍穹外卖 · 管理端前端（Vue 2 + TypeScript）

「苍穹外卖」门店管理后台，对接 [sky-take-out](https://github.com/csbslh/sky-take-out) 后端。基于 Vue 2 + TypeScript + Element UI 构建，实现登录鉴权、菜品套餐管理、订单处理与营业数据可视化。

## 技术栈

| 分类 | 技术 |
|---|---|
| 框架 | Vue 2.6、TypeScript 4、Vue Router 3、Vuex |
| UI | Element UI、ECharts（统计图表） |
| 构建 | Vue CLI 5、Webpack |
| 请求 | Axios 封装（统一拦截器、token 处理） |
| 规范 | ESLint、Prettier |
| 测试 | Jest 单元测试、Cypress E2E |

## 功能

- 员工登录、退出、修改密码（JWT + 路由守卫）
- 工作台：今日营业额、订单、用户等核心指标
- 菜品管理：分类、菜品、口味、图片上传
- 套餐管理：套餐与菜品关联
- 订单管理：条件查询、接单/拒单/派送/完成、订单详情
- 数据统计：营业额、订单、用户、销量 Top10 折线柱状图
- 来单提醒（WebSocket 推送 + 语音播报）

## 目录结构

```
src/
├── api/         接口定义（按业务模块拆分）
├── components/  通用组件（面包屑、图表、上传等）
├── layout/      布局与侧边栏
├── router.ts    路由与权限控制
├── store/       Vuex 状态管理
├── styles/      全局样式
├── utils/       Axios 封装、Cookie、校验等
└── views/       页面（dashboard、dish、setmeal、orderDetails、statistics…）
```

## 快速开始

```bash
npm install          # 或 yarn
npm run serve        # 开发环境，默认 http://localhost:8888
npm run build        # 生产构建
npm run test:unit    # 单元测试
```

### 接口地址

环境变量位于 `.env.development` 等文件：

```bash
VUE_APP_BASE_API = '/api'                       # 走 devServer 代理
VUE_APP_URL = 'http://localhost:8080/admin'     # 后端地址
VUE_APP_SOCKET_URL = 'ws://localhost:8080/ws/'  # WebSocket 地址
```

使用前请先启动后端 `sky-take-out`（默认 8080 端口），并按需修改变量指向你的后端地址。

## 说明

- 登录账号来自后端员工表，默认账号见后端仓库的 `sky.sql`。
- 本项目在开源模板 [vue-typescript-admin](https://github.com/Armour/vue-typescript-admin-template)（MIT）基础上按苍穹外卖接口做了改造，保留原 LICENSE。
- 仓库不含任何密钥，接口地址通过 `.env` 环境变量配置。

## 作者

陈杉 · 武昌工学院 信息工程学院 软件工程
