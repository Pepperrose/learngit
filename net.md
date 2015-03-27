通信协议分层的思想：
	



IP协议：《TCP/IP详解》
	ip:提供了独一无二的ip地址


TCP协议和UDP协议
	TCP：是可靠的 先建立连接（打电话 ：喂） 然后是应答模式（A：我们去吃大龙虾吧 B:好的）

	UDP：不可靠的  类似发电报，没有应答

TCP Socket 通信模型

创建EchoServer
	服务器程序通过一直监听端口，来接收客户程序的连接请求。在服务器程序中，需要先创建ServerSocket对象，在构造方法中指定监听的端口：
		ServerSocket server = new ServerSocket(8000);//监听8000端口

	ServerSocket的构造方法负责在操作系统中把当前进程注册为服务器进程，服务器程序接下来调用ServerSocke对象的accept()方法，该方法一直监听端口，等待客户的连接请求，如果接收到一个连接请求，accept()犯法就会返回一个Socket对象，这个Socket对象与客户端的Socket对象形成一条通信线路。
		Socket socket = server.accept();//等待客户的连接请求


	Socket类提供了getInputStream()方法和getOutputStream()方法，分别返回输入流InputStream对象和输出流OutputStream对象。程序只需向输出流写数据，就能向对方发送数据；只需从输入流读取数据，就能接受来自对方的数据。

	Socket的输入流和输出流也可以用过滤流来装饰。
	在一下代码中，先获得输出流，然后用PrintWriter装饰它，PrintWriter的println()方法能够写一行数据；
	一下代码接着获得输入流，然后用BufferedReader装饰它，BufferedReader的readLine()方法能够读取一行数据
		OutputStream socketOut = socket.getOutputStream();//参数true表示没写一行，PrintWriter缓存就自动溢出，把数据写到目的地
		PrintWriter pw = new PrintWriter(socketOut,true);
		InputStream socketIn = socket.getInputStream();
		BufferedReader br = new BufferedReader(new InputStreamReader(socketIn));

创建EchoClient 
	在EchoClient程序中，为了与EchoServer通信，需要先创建一个Socket对象：
		String host="localhost";
		String port=8000;
		Socket socket = new Socket(host,port);

	当参数host的取值为"localost"，表示EchoClient与EchoServer进程运行在同于个主机上。如果Socket对象成功创建，就表示建立了EchoClient与EchoServer之间的连接。接下来，EchoClient从Socket对象中得到输入流和输出流，就能与EchoServer交换数据

Socket用法详情
	1、构造Socket
	2、获取Socket的信息
	3、关闭Socket
	4、半关闭Socket
	5、设置Socket的选项
	6、发送邮件的SMTP的客户程序




