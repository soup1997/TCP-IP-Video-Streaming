# TCP_IP
라즈베리파이와 PC간의 실시간 영상전송을 할 수 있으며 Client는 라즈베리파이, Server는 PC이다.
라즈베리파이에 웹캠을 연결하여 Server인 PC로 웹캠 영상을 전송한다.
TCP/IP 통신을 위해서는 server와 client간의 연결할 Ip주소와 포트번호를 알아야 한다.

TCP/IP의 개요는 다음아래의 사진과 같다.

![image](https://user-images.githubusercontent.com/86957779/129339184-3b005504-496a-4cd8-b11f-b3c839fab65c.png)

가장먼저 server와 client로 구분되며 둘 모두 socket을 먼저 생성한다. 그 다음 server에서 만들어진 소켓을 호스트이름과 포트번호로 binding하고 소켓을 통해 들어오는 연결을 듣는다. accept()를 통해 다른 컴퓨터에서 해당 컴퓨터로 연결할 때 연결을 받아들인다. 마지막으로 write(): client에서 server로 데이터를 전송, read(): client에서 보낸 데이터를 buffer로 읽어들이는 과정을 통해 데이터를 송수신한다. 다음은 라즈베리파이와 pc간의 TCP/IP통신과정이다.

1. Windows PC를 기준으로 windows + R을 눌러 CMD를 입력한다.

2. CMD에서 ipconfig 명령어를 입력한다.
![image](https://user-images.githubusercontent.com/86957779/129338302-f979fc9f-bea1-4bfe-98f9-89774d6b17c4.png)

3.연결할 ip주소를 확인한다
![image](https://user-images.githubusercontent.com/86957779/129339081-6b423738-c927-4ead-b1da-36e2b7064448.png)

4. CMD에서 netstat -a를 입력한다.

5. Listening 상태의 TCP프로토콜을 선택하고, 포트번호를 확인한다.
 
6. Server.py를 먼저 실행시켜 서버소켓을 create->bind->listen과정을 진행한다.

7. Client.py를 실행시켜 마찬가지로 클라이언트소켓을 create->bind->connect과정을 진행하게 된다.

8. 출력결과는 다음과 같다.
![image](https://user-images.githubusercontent.com/86957779/125408022-6bccab00-e3f5-11eb-8826-6de8980a3e2b.png)
