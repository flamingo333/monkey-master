# monkey-master

黄皮衣，酥麻罪恶滔天，此项目诞生于抢购猴卡 RTX3080、RX6800XT.....。

### 安装

安装 deno:

Shell (Mac, Linux):

```bash
curl -fsSL https://deno.land/x/install/install.sh | sh
```

PowerShell (Windows):

```bash
iwr https://deno.land/x/install/install.ps1 -useb | iex
```

如果安装不成功可以看 deno 官网的更多安装方式
https://deno.land/#installation

安装依赖插件：

```bash

deno install -qAf --unstable https://deno.land/x/denon/denon.ts
```

### 启动

```bash
deno run --allow-env --allow-read --allow-write --allow-net --allow-run --allow-plugin --unstable --no-check index.js

or

denon start
```

### 配置参数说明

在 conf.json 文件中配置必要参数：

| 参数        | 说明                                                                   | 是否必须 | 数据类型 | 默认值    |
| ----------- | ---------------------------------------------------------------------- | -------- | -------- | --------- |
| timeout     | 请求超时时间 单位毫秒                                                  |          | Number   | 5000      |
| useRandomUA | 启动随机 user-agent                                                    |          | Boolean  | false     |
| userPath    | 用户信息暂存目录                                                       |          | string   | ./cookie/ |
| password    | 支付密码                                                               | required | string   |           |
| eid         | 设备 ID，部分系统可自动获取也可以手动配置                              |          | string   |           |
| fp          | fingerprint，部分系统可自动获取也可以手动配置                          |          | string   |           |
| sckey       | 用于下单成功的消息推送，这里借用第三方工具 http://sc.ftqq.com/ |          | string   |           |


### 最佳实践

- 操作之前删除购物车内的相关物品，因为JD的商品数据结构存在变化，依赖本公举可能会造成数量错误
- 只监控一个 ID 可加快下单速度/成功率
- 用 denon start 启动公举
- 增加京东金融分期接口，可从秒杀模式进入（听说这个方式节省步骤成功率较高)

### TODO

-   ~~auto get fingerprint (e.g. eid,fp).~~ windows 可以不配置
-   ~~seckill~~
-   GUI?
