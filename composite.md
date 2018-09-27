## 通用图片生成服务

### 产生背景
- 多个业务场景需要用到图片生成
   - 易吸粉邀请卡（门店，员工，粉丝）
   - 商城拼团二维码
   - 支付台卡
- 以前的做法
  
  node.js项目上安装sharp, canvas等模块, 直接代码画图.
  存在的问题：
  - 安装慢: 需要编译安装依赖库和模块本身，过程慢，增加镜像体积
  - 性能低: 图片操作涉及较多CPU计算，会降低node.js api服务响应能力
  - 不通用: 针对不同图片生成需求，需求重写一套画图流程，代码冗余


### 系统需求
- 业务无关的独立服务
- 处理通用的图片合成逻辑
- 低延时

### 通用处理流程
- 