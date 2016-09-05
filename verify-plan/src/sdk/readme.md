#sdk工程

* 本工程负责提供javascript版本的sdk
    * 业务界面负责使用该sdk,创建一个弹出的iframe
    * 该iframe的url指向验证码服务server
    * iframe会把验证结果的access token,通知给业务web(parent iframe)
    * 业务web使用该token,通过web后台调用验证码服务的消费接口,验证token的有效性(该token只能使用一次)
