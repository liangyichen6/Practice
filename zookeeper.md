#Zeekeeper 需要知道的东西
##Command
    ./zkServer.sh status 查看zookeeper server 的状态，可以知道该server是leader还是follower  
    ./zkServer.sh start  start server  
    ./zkServer.sh stop   stop server
    ./zkCli.sh -server ip:port  连接进入zookeeper
    create -s path data acl 建立永久有序node
    create -e path data acl 创建临时的node
	create path data acl  创建永远有效的node
	get path 获得 node 的信息


##config
    基础配置
    tickTime = 2000    每次心跳的间隔时间  milionseconds
	syncLimit = 5      leader 和 follower 之间互相通信的最长容忍时间  5 次心跳间隔时间
	initLimit = 10     zookeeper接受客户端建立连接的最长容忍时间 10 次心跳间隔的时间
    dataDir = 数据目录
    dataLogDir = 数据日志目录
    clientPort = client 用来连接zookeeper的端口，zookeeper会监听这个端口，接受客户端用户的请求
    
    集群模式：
    server.A:B:ip C:D port     A表示这是第几台服务器   B:zookeeper server的地址  C端口 用来与集群中的leader交互信息的端口， D端口是用来选举leader的端口号
    example: server.1 = localhost:2187:2887

        


