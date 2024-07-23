## 插件说明

## 一个基于[ChatGPT-on-Wechat](https://github.com/zhayujie/chatgpt-on-wechat)项目的简单插件，
由于[原插件](https://github.com/lanvent/plugin_summary)安装始终失败，故在此基础上进行了改写。

该插件也是用户根据需求开发自定义插件的示例插件，参考[插件开发说明](https://github.com/zhayujie/chatgpt-on-wechat/tree/master/plugins)

## 插件配置

将 `plugins/plugin_summary` 目录下的 `config.json.template` 配置模板复制为最终生效的 `config.json`。 (如果未配置则会默认使用`config.json.template`模板中配置)。


以下是插件配置项说明：

```bash
{
 "rate_limit_summary":60, # 总结间隔时间(单位分钟)，防止同一时间多次触发总结，浪费token
 "save_time":  1440 # 聊天记录保存时间(单位分钟)，默认保留12小时，凌晨12点将过去12小时之前的记录清楚.-1表示永久保留
}

```

## 指令参考
- $总结 999
- $总结 3 小时内消息
- $总结 开启
- $总结 关闭


注意：
 - 总结默认针对所有群开放，关闭请在对应群发送关闭指令 
 - 实际 `config.json` 配置中应保证json格式，不应携带 '#' 及后面的注释
 - 如果是`docker`部署，可通过映射 `plugins/config.json` 到容器中来完成插件配置，参考[文档](https://github.com/zhayujie/chatgpt-on-wechat#3-%E6%8F%92%E4%BB%B6%E4%BD%BF%E7%94%A8)



