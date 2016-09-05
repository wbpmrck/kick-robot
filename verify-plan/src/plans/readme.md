#说明

* 这里存放所有的验证策略(plan)
* 每一个验证策略,都单独存放在以策略名命名的文件夹里
    * xxx
        * client:存放在客户端的逻辑
        * server:存放在服务器端的操作逻辑
            * 要实现的接口:
                * generateNew($context,options) => settingJSON
                    * 生成一个给client使用的配置数据项
                    * 这个配置数据要能够驱动client进行所有的工作
                * update($context,options)
                    * 某些情况下,如果client在用户操作过程中会上报一些过程数据,会触发这个方法调用
                * verify($context,token,settingJSON,answerJSON) => success
                    * 最后结束验证的时候,client给出answerJSON
                    * 这个方法要给出是否验证成功