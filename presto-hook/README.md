开发说明
```
1.需要手动实现三个Interface：EventListener、EventListenerFactory、Plugin
2.需要在resources目录下创建META-INF/services文件夹
  在该目录新建com.facebook.presto.spi.Plugin文件，文件内容为Plugin实现类的全类名
3.打包
```
部署说明（coordinator结点）
```
1.在<presto根目录>/etc/目录添加event-listener.properties配置文件，添加配置：
  event-listener.name=<EventListenerFactory实现类getName()方法返回值>
2.创建<presto根目录>/plugin/<event-listener.name的值>/文件夹，并放入jar包
3.重启presto集群
```