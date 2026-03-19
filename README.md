# Net_AISec_hunter

基于 Wails + cursor-cli 的红队自动化 .NET 白盒漏洞挖掘工具

> 面向授权测试场景，“白盒漏洞挖掘 + 红队打点 + 审计结果验证”

![image-20260319173534814](https://photoscloud.oss-cn-shanghai.aliyuncs.com/image-20260319173534814.png)

## 解压密码

私信发送`Net_AISec_hunter`获取解压密码

## 快速开始

### cursor cli安装 ###

https://cursor.com/cn/docs/cli/installation

```
irm 'https://cursor.com/install?win32=true' | iex
```

Windows 默认情况下禁止运行未签名的脚本

![image-20260316170151228](https://photoscloud.oss-cn-shanghai.aliyuncs.com/image-20260316170151228.png)

如果希望以后直接运行 `cursor-agent` 命令不用每次加 `-ExecutionPolicy Bypass`，可以把当前用户策略改为 `RemoteSigned`：

```
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

然后确认：

```
Get-ExecutionPolicy -Scope CurrentUser
```

![image-20260316170304365](https://photoscloud.oss-cn-shanghai.aliyuncs.com/image-20260316170304365.png)

### 为什么选择cursor ###

在安全代码审计场景中，Cursor 将大模型能力嵌入 IDE，可直接基于本地完整代码仓库进行多文件关联分析，自动定位调用链、数据流及潜在漏洞点，避免了在 Claude 中手动拆分代码、拼接上下文所带来的信息丢失问题

按次数收费 20美刀=500次调用（某海鲜平台购买更加便宜），相比于claude、GPT按token计费有着更友好的价格

### 创建key ###

https://cursor.com/cn/dashboard/cloud-agents

![image-20260316170615080](https://photoscloud.oss-cn-shanghai.aliyuncs.com/image-20260316170615080.png)

调用命令验证

```
cursor-agent --model "Claude 4.6 Opus max" -p "你的具体AI模型型号是什么？" --api-key "key_95f42902ff9fxxx25541ceaa" --trust
```

![image-20260316170700058](https://photoscloud.oss-cn-shanghai.aliyuncs.com/image-20260316170700058.png)

## 使用流程

选择目标扫描仓库目录 

![image-20260319103939059](https://photoscloud.oss-cn-shanghai.aliyuncs.com/image-20260319103939059.png)

配置 API Key / AI 模型，验证key有效性

![image-20260318180722235](https://photoscloud.oss-cn-shanghai.aliyuncs.com/image-20260318180722235.png)

按需勾选：去混淆、反编译，如果已经反编译好则不需要勾选，然后开始扫描（阶段化执行）  

导入报告，在 Repeater 中导入报告数据包并做二次验证

![image-20260319173704701](https://photoscloud.oss-cn-shanghai.aliyuncs.com/image-20260319173704701.png)

## 合规声明

本项目仅用于合法授权的安全测试与研究，适用于：授权渗透测试、内部安全审计、攻防演练

使用者需自行确保测试对象和行为符合当地法律法规及组织规范。
