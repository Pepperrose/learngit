ͨ��Э��ֲ��˼�룺
	



IPЭ�飺��TCP/IP��⡷
	ip:�ṩ�˶�һ�޶���ip��ַ


TCPЭ���UDPЭ��
	TCP���ǿɿ��� �Ƚ������ӣ���绰 ��ι�� Ȼ����Ӧ��ģʽ��A������ȥ�Դ���Ϻ�� B:�õģ�

	UDP�����ɿ���  ���Ʒ��籨��û��Ӧ��

TCP Socket ͨ��ģ��

����EchoServer
	����������ͨ��һֱ�����˿ڣ������տͻ���������������ڷ����������У���Ҫ�ȴ���ServerSocket�����ڹ��췽����ָ�������Ķ˿ڣ�
		ServerSocket server = new ServerSocket(8000);//����8000�˿�

	ServerSocket�Ĺ��췽�������ڲ���ϵͳ�аѵ�ǰ����ע��Ϊ���������̣��������������������ServerSocke�����accept()�������÷���һֱ�����˿ڣ��ȴ��ͻ�����������������յ�һ����������accept()�����ͻ᷵��һ��Socket�������Socket������ͻ��˵�Socket�����γ�һ��ͨ����·��
		Socket socket = server.accept();//�ȴ��ͻ�����������


	Socket���ṩ��getInputStream()������getOutputStream()�������ֱ𷵻�������InputStream����������OutputStream���󡣳���ֻ���������д���ݣ�������Է��������ݣ�ֻ�����������ȡ���ݣ����ܽ������ԶԷ������ݡ�

	Socket���������������Ҳ�����ù�������װ�Ρ�
	��һ�´����У��Ȼ���������Ȼ����PrintWriterװ������PrintWriter��println()�����ܹ�дһ�����ݣ�
	һ�´�����Ż����������Ȼ����BufferedReaderװ������BufferedReader��readLine()�����ܹ���ȡһ������
		OutputStream socketOut = socket.getOutputStream();//����true��ʾûдһ�У�PrintWriter������Զ������������д��Ŀ�ĵ�
		PrintWriter pw = new PrintWriter(socketOut,true);
		InputStream socketIn = socket.getInputStream();
		BufferedReader br = new BufferedReader(new InputStreamReader(socketIn));

����EchoClient 
	��EchoClient�����У�Ϊ����EchoServerͨ�ţ���Ҫ�ȴ���һ��Socket����
		String host="localhost";
		String port=8000;
		Socket socket = new Socket(host,port);

	������host��ȡֵΪ"localost"����ʾEchoClient��EchoServer����������ͬ�ڸ������ϡ����Socket����ɹ��������ͱ�ʾ������EchoClient��EchoServer֮������ӡ���������EchoClient��Socket�����еõ����������������������EchoServer��������

Socket�÷�����
	1������Socket
	2����ȡSocket����Ϣ
	3���ر�Socket
	4����ر�Socket
	5������Socket��ѡ��
	6�������ʼ���SMTP�Ŀͻ�����




