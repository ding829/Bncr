常见问题Q&A：
## 一、拉不了镜像？
* 镜像已经推了大概一周左右，如果拉不到就是你网络问题，或者是镜像服务器问题，请换回官方docker Hub源

## 二、为什么不回复消息 没反应？
* 检查管理员是否设置，
    * set 平台名 admin xxx  
    * 平台名有(wxQianxun/wxKeAImao/wxXyo/qq/tgBot/HumanTG)
    * 你问我平台名为什么那么杂？因为设计了多账户对接，比如qianxun+xyo双框架对接，so..
* 官方命令作为演示插件 * @platform 只填了部分的，检查页眉这个值是否有你准备触发消息的平台名. 可以直接删掉这一行，表示接受所有平台的消息匹配该插件

## 三、鉴权问题
* 每个token对应一个机器码，初次鉴权的时候会绑定机器码，一台机器上重建docker 机器码不会变。 需要换机器码请在群里发/清空机器码

## 四、反馈问题？
* 请带上报错截图，以及说明发了什么命令触发的

## 五 、关于安装npm包！
* 安装npm失败?
    * 基本都是你网络环境问题,换网重试!
* 开发者在容器内部安装npm包时，尽量在BncrData下执行npm i 命令 ,否则在更新镜像时、重建docker时 会丢失安装过的npm包
* 正确示例：
```
docker exec -it bncr /bin/sh
cd BncrData
npm i xxxx
```
* 或者在宿主机cd到容器映射目录 （需要宿主机安装过node 且npm版本 不低于 9.5.0，使用npm -v 查看版本）
npm i xxxx