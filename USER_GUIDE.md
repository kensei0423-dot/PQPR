# PQPR — 用户使用指南

> PayPal QR 扫码收款 · Android 商户端

---

## 目录

1. [快速开始](#1-快速开始)
2. [登录](#2-登录)
3. [收款（主页面）](#3-收款主页面)
4. [支付结果](#4-支付结果)
5. [设置](#5-设置)
6. [门店管理 BOPIS](#6-门店管理-bopis)
7. [商品管理](#7-商品管理)
8. [数据看板](#8-数据看板)
9. [交易历史](#9-交易历史)
10. [订单查询](#10-订单查询)
11. [退款](#11-退款)
12. [打印机配置](#12-打印机配置)

---

## 1. 快速开始

### 首次使用步骤

```
① 打开 App → 初始化配置页面
② 填写 PayPal Client ID & Secret
③ 选择环境（Sandbox 测试 / Production 生产）
④ 点击「Verify & Save」验证凭据
⑤ 完成登录（邮箱 OTP 验证）
⑥ 进入收款主页面
```

### 凭据获取方式
- 登录 [developer.paypal.com](https://developer.paypal.com)
- Apps & Credentials → 创建或选择应用
- 复制 Client ID 和 Secret

---

## 2. 登录

邮箱 + 一次性验证码（OTP）两步登录：

| 步骤 | 操作 |
|------|------|
| 1 | 输入邮箱地址 → 点击「Send Code」|
| 2 | 收到 6 位验证码 → 输入 → 「Verify & Login」|

- **Resend**：重新发送验证码
- **Change Email**：返回修改邮箱

---

## 3. 收款（主页面）

### 基础收款流程

```
① 输入金额（自由模式）或直接使用固定金额
② 可选：输入备注描述
③ 点击「Generate QR Code」生成二维码
④ 展示二维码给买家扫码（PayPal App 或浏览器）
⑤ 等待买家支付（最长 60 秒自动轮询）
⑥ 支付完成 → 跳转支付结果页
```

### 快捷商品选择
- 若已配置商品，主页面顶部显示快捷按钮
- 点击商品按钮自动填入金额

### 注意事项

| 情况 | 提示 |
|------|------|
| 有待支付 QR 订单时点「History」或「Settings」| 弹出确认框，选择 Leave（放弃订单）或 Stay |
| 点击「Cancel」取消当前 QR | 同样弹出确认框 |
| 60 秒内未支付 | 自动转为 TIMEOUT，可手动 Retry |

### 支付状态流转
```
IDLE → CREATING → WAITING → CAPTURING → COMPLETED / FAILED
```

---

## 4. 支付结果

### COMPLETED（成功）
- ✅ 绿色勾图标
- 显示：金额、Order ID、Capture ID
- **取货码**（大字体显示，4 位）
- 点击取货码 → 标记为「已取货」（需确认）
- 打印收据按钮（需连接打印机）

### 其他状态

| 状态 | 图标 | 操作 |
|------|------|------|
| PENDING | 🟠 时钟 | Retry Capture |
| TIMEOUT | 🟠 时钟 | Retry Capture |
| FAILED | 🔴 X | Retry Capture |

> Retry 会先查询订单状态，再尝试 Capture

---

## 5. 设置

进入路径：主页面右上角 ⚙️ 图标

### Authorization（凭据）
- 修改 Client ID / Secret
- 切换 Sandbox ↔ Production
- 「Verify & Save」重新验证
- 「Clear」清除凭据

### Payment Mode（收款模式）
- **Free Amount**：收款时手动输入金额
- **Fixed Amount**：预设固定金额，收款时直接使用

### Currency（货币）
支持 26 种货币，包括：USD、EUR、GBP、JPY、AUD、CAD、CNY、HKD、TWD 等

### Business Tools（商业工具）
| 工具 | 功能 |
|------|------|
| Dashboard | 查看销售数据 |
| Products | 管理快捷商品 |
| Order Lookup | 查询订单 |
| Refund | 处理退款 |
| QR Logo | 设置 QR 码中心 Logo |

### Notifications（通知）
- **Voice Announcement**：支付完成时语音播报金额
- 「Test Voice」试听

### Printer（打印机）
- 开关自动打印收据
- 「Set Up Printer」配置蓝牙打印机

### Admin PIN
- 设置管理员 PIN 码保护退出登录

### Logout
- 如已设置 PIN，需验证后退出

---

## 6. 门店管理 BOPIS

> 配置自提门店地址，支付时自动使用 `PICKUP_IN_STORE` 类型，获得 PayPal 卖家保护。

### 添加门店
设置 → Store Locations → **Add Store**

填写字段：
| 字段 | 说明 |
|------|------|
| Display Name | 门店显示名称 |
| Address Line 1 | 街道地址 |
| Address Line 2 | 补充地址（可选）|
| City | 城市 |
| State | 州/省（可选）|
| Postal Code | 邮编 |
| Country | 国家代码（如 GB、US）|
| Opening Hours | 营业时间（可选）|

### 选择当前门店
- 下拉菜单选择门店
- 选中后显示蓝色详情卡片（名称、地址、营业时间）

### 编辑 / 删除门店
- **Edit**：修改门店信息
- **Remove**：删除选中门店

> 配置门店后，每笔订单自动带入门店地址，买家在 PayPal 看到的是自提地址。

---

## 7. 商品管理

设置 → Business Tools → **Products**

- 最多添加 **2 个**商品
- 每个商品：名称 + 价格
- 商品在收款主页面以快捷按钮形式显示
- 删除需二次确认
- 商品数据仅本地存储，退出登录后清空

---

## 8. 数据看板

设置 → Business Tools → **Dashboard**

### 显示内容
| 区域 | 数据 |
|------|------|
| 今日 | 收款金额、交易笔数 |
| 本周 | 收款金额、交易笔数 |
| 本月 | 收款金额、交易笔数、平均单价 |
| 图表 | 7 天 / 30 天收款趋势 |

### 操作
- 🔄 刷新数据
- 切换图表周期：7D / 30D
- **Export CSV**：导出全部交易记录（含日期、金额、状态、取货码等）

---

## 9. 交易历史

主页面右上角 📋 图标

### 筛选
- **All**：全部交易
- **Completed**：仅已完成

### 交易卡片信息
- 金额 & 货币
- 状态（颜色区分：绿=完成、橙=处理中、红=失败）
- Order ID
- 买家邮箱
- 取货码（完成订单）
- 时间

### 操作
| 操作 | 条件 |
|------|------|
| 标记取货 | 状态 COMPLETED |
| 打印收据 | 状态 COMPLETED + 已连接打印机 |
| Retry Capture | 状态 TIMEOUT / FAILED |
| Load More | 滚动到底部加载更多（每页 10 条）|

---

## 10. 订单查询

设置 → Business Tools → **Order Lookup**

### 查询规则
| 输入内容 | 查询方式 |
|---------|---------|
| ≤ 4 个字符 | 按取货码查询（Supabase）|
| > 4 个字符 | 按 Order ID 查询（PayPal API）|

### 结果显示
- 状态、金额、Order ID、Capture ID
- 取货码（已完成订单）
- 买家邮箱

---

## 11. 退款

设置 → Business Tools → **Refund**

### 全额退款
1. 输入 Capture ID
2. 选择「Full Refund」
3. 点击「Process Refund」

### 部分退款
1. 输入 Capture ID
2. 选择「Partial Refund」
3. 输入退款金额
4. 点击「Process Refund」

> Capture ID 可在交易历史或结果页查看

---

## 12. 打印机配置

设置 → Printer → **Set Up Printer**

### 连接流程
```
① 手机蓝牙已开启并已配对打印机
② 进入打印机配置页面
③ 已配对设备列表中点击对应打印机
④ 连接成功后显示绿色状态
⑤ 点击「Test Print」验证打印
```

### 说明
- 需要 Android 蓝牙权限（首次使用时授权）
- 支持标准蓝牙热敏打印机
- 收据内容：商户名、金额、订单号、时间

---

## 附录：状态说明

| 状态 | 含义 |
|------|------|
| COMPLETED | 支付成功，已 Capture |
| PENDING | 买家已审批，等待 Capture |
| TIMEOUT | 60 秒内未支付，自动超时 |
| FAILED | Capture 失败 |
| DECLINED | 支付被拒绝 |
| AUTHORIZED | 已授权，未 Capture |

---

## 附录：环境说明

| 环境 | API 地址 | 说明 |
|------|---------|------|
| Sandbox | api-m.sandbox.paypal.com | 测试环境，不产生真实扣款 |
| Production | api-m.paypal.com | 生产环境，真实交易 |

> ⚠️ 上线前务必切换为 Production 并更换生产环境凭据
