# quartz

quartz 2.1 和 spring xml配置文件结合
这是一套quartz的整体框架，将trigger存储于Quartz的内存，同时在本地数据库中还会存储trigger的信息，用于用户修改。
这个框架可以用于公司每日大致的定时任务。
基本的业务逻辑都在service中。Controller可以根据service自己定义相关信息。

用户可以自定义任务的类型，为一个RcQuartzJob，以及该任务对应的相关触发器 RcQuartzTrigger

每个任务在执行时会触发trigger和job的相关listener，用于记录任务的执行情况RcQuartzExecution.

任务的执行在BaseJob和SerialJob，调用spring的反射进行处理。如果quartz和spring分开则需要调用dubbo接口或者http请求。

