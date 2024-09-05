## UDP서버

UDP서버는 네트워크 상에서 데이터그램을 송수신하는데 사용됩니다. TCP와 달리 연결지향적이지 않고 데이터 전송을 위해 미리 연결을 설정하지 않고 수신자에게 바로 데이터를 전송할 수 있는 방식으로 비연결형 프로토콜을 사용합니다.<br>

-비연결형 프로토콜 : UDP는 송신자와 수신자 간의 연결을 설정하지 않고 송신자가 데이터를 보내고 수신자는 수신하면 끝입니다. 따라서 연결 설정 및 종료 과정이 필요 없으므로 지연 시간이 적고 속도가 빠릅니다.<br>

-데이터그램 단위 전송 : UDP는 데이터를 패킷단위로 보내는데 각 패킷은 독립적으로 전송되고 네트워크 상에서 순서 상관없이 전달될 수 있습니다. 이러한 이유로 패킷이 유실되거나 순서가 바뀔 가능성이 있지만 응용프로그램에서 이를 처리하는 속도가 빨라집니다.<br>

-신뢰성 부족 : UDP는 패킷이 도착했는지 확인하지 않고 손실된 패킷을 재전송하지 않아서 신뢰성이 필요한 응용 프로그램에는 적합하지 않지만 실시간 데이터 전송(스트리밍,온라인게임)에는 유리합니다.<br>

-------------------------------------------------------------------------

## MyUDPServer

이 클래스는 특정 포트에서 데이터를 받고 출력하여 나오게해주는 프로그램입니다.<br>
DatagramSocket은 UDP기반의 네트워크 통신을 처리하는 소캣 클래스입니다.<br>
DatagramPacket은 수신한 데이터를 담아두는 컨테이너 역할로 수신된 데이터를 배열에 저장하여 이후 데이터를 읽을때 이용되는 역할을 합니다.<br>
```catch (Exception e){ System.out.println(e.getMessage());```에서 예외가 발생할 경우 예외 메세지를 출력하여 서버의 안정성을 높이고 서버 실행중 발생할 수 있는 오류를 파악할 수 있으며 예외를 처리할 수 있습니다.<br>
이 서버는 무한 루프를 사용해 계속하여 클라이언트로부터 데이터를 수신합니다.

------------------------------------------------------------------------------

## MyUDPClient

이 클라이언트 프로그램은 UDP 기반의 네트워크 통신에서 데이터 전송을 수행하는 기본적인 예제입니다.<br>
사용자 입력을 받아 지정된 IP 주소와 포트 번호로 메시지를 전송합니다.<br>
간단한 프로그램으로 UDP 통신의 기본적인 개념을 반영하고 서버와 클라이언트 간의 데이터 송수신이 어떻게 이루어지는지 이해하기 유용한 예제입니다.

---------------------------------------------------

## MySerialClient

이 프로그램은 현재 PC에 연결되어있는 포트의 순서를 알려주는 프로그램입니다.<br>
위에서부터 아래로 0부터 카운트됩니다.<br>
연결된 포트넘버는 시작버튼 우클릭후 장치관리자의 포트에서 확인가능합니다.

------------------------------------------------------------------

## MySerialClient2
이 클래스는 시리얼 포트를 통해 아두이노와의 데이터를 송수신할 수 있는 프로그램입니다.<br>

------------------------------------------------------------------------------

## MySerialClientUDPServer
이 클래스는 위의 코드를 종합하여 클라이언트로부터 받은 명령 커맨드를 IP서버를 통해 아두이노에 전달하여 지정된 커맨드를 수행할 수 있도록 연결해주는 방법을 구현하였습니다.<br>
예로는 카메라의 움직임, 조명 제어 등등 아두이노를 통한 제어가 가능합니다.<br>
여기서는 아두이노와 안드로이드 스튜디오를 연결해주는 역할로 사용되었습니다.<br>
![image](https://github.com/user-attachments/assets/350b5ffc-8041-4001-88c9-0254718f4c52)<br>
위의 사진처럼 어플리케이션에서 버튼 클릭시 송신IP와 지정된 커맨드가 출력되는걸 확인할 수 있습니다.


