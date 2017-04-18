---
title: "UDP 서비스 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "프로토콜, UDP"
  - "네트워크 리소스, UDP"
  - "인터넷에서 데이터 요청, UDP"
  - "UDP"
  - "데이터 받기, UDP"
  - "인터넷, UDP"
  - "여러 주소에 메시지 브로드캐스트"
  - "데이터 요청, UDP"
  - "UdpClient 클래스, UdpClient 클래스 정보"
  - "데이터 보내기, UDP"
  - "응용 프로그램 프로토콜, UDP"
ms.assetid: d5c3477a-e798-454c-a890-738ba14c5707
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# UDP 서비스 사용
<xref:System.Net.Sockets.UdpClient> 클래스에 UDP를 사용 하 여 네트워크 서비스와 통신 합니다.  메서드와 속성은 <xref:System.Net.Sockets.UdpClient> 자세히 만드는 추상 클래스는 <xref:System.Net.Sockets.Socket> 요청 및 UDP를 사용 하 여 데이터를 수신.  
  
 사용자 데이터 그램 프로토콜 \(UDP\) 원격 호스트에 데이터를 전달 하는 최선의 노력을 하는 단순한 프로토콜입니다.  그러나 UDP 프로토콜은 연결 없는 프로토콜 이기 때문에 원격 끝점으로 보낸 UDP 데이터 그램은 도착 하지 않을 없으며 도착 한 순서 대로 전송 됩니다 보장할 수 없습니다.  UDP를 사용 하는 응용 프로그램 누락, 중복, 및 시퀀스의 출력 데이터 그램을 처리 하도록 준비 해야 합니다.  
  
 UDP를 사용 하 여 데이터 그램을 보내기 위해 필요한 서비스와 통신 하는 서비스를 사용 하 여 UDP 포트 번호를 호스팅하는 네트워크 장치의 네트워크 주소를 알고 있어야 합니다.  인터넷 할당 번호 기관 \(Iana\) 공통 서비스 \(www.iana.org\/assignments\/port\-numbers 참조\)에 대 한 포트 번호를 정의 합니다.  Iana 목록에 없는 서비스 포트 번호는 1024에서 65535 범위에 있을 수 있습니다.  
  
 특수 네트워크 주소는 IP 기반 네트워크에서 UDP 브로드캐스트 메시지를 지원 하도록 사용 됩니다.  다음 토론 인터넷에서 예로 사용 되는 IP 버전 4 주소 패밀리를 사용 합니다.  
  
 32 비트 IP 버전 4 주소를 사용 하 여 네트워크 주소를 지정 합니다.  클래스 C 주소는 네트워크 마스크 255.255.255.0을 사용 하 여 4 개의 8 진수에 이러한 비트 구분 됩니다.  십진수에서 표현 하면 192.168.100.2 처럼 익숙한 4 점 표기법을 4 개의 8 진수를 형성 합니다.  네트워크 번호 \(192.168\)이이 예제에서는 처음 두 옥텟 형성, 세 번째 옥텟 \(100\) 서브넷, 정의 및 마지막 옥텟 \(2\) 호스트 식별자입니다.  
  
 IP 주소의 모든 비트를 1 또는 255.255.255.255 설정 제한 된 브로드캐스트 주소를 구성 합니다.  UDP 데이터 그램을이 주소로 보내는 모든 호스트의 로컬 네트워크 세그먼트에 메시지를 배달 합니다.  라우터는이 주소로 보낸 메시지를 전달 하기 때문에 호스트는 네트워크 세그먼트에 브로드캐스트 메시지를 받습니다.  
  
 호스트 식별자의 모든 비트를 설정 하 여 브로드캐스트는 네트워크의 특정 부분에 보낼 수 있습니다.  예를 들어, 192.168.1로 시작 하는 IP 주소에 의해 식별 되는 네트워크의 모든 호스트로 브로드캐스트를 보내려면 192.168.1.255 주소를 사용 합니다.  
  
 다음 코드 예제에서는 사용 하는 <xref:System.Net.Sockets.UdpClient> 직접된 브로드캐스트 주소 192.168.1.255 11,000 포트에서 보낸 UDP 데이터 그램을 수신 합니다.  클라이언트가 메시지 문자열을 받고 메시지를 콘솔에 씁니다.  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class UDPListener  
   Private Const listenPort As Integer = 11000  
  
   Private Shared Sub StartListener()  
      Dim done As Boolean = False  
      Dim listener As New UdpClient(listenPort)  
      Dim groupEP As New IPEndPoint(IPAddress.Any, listenPort)  
      Try  
         While Not done  
            Console.WriteLine("Waiting for broadcast")  
            Dim bytes As Byte() = listener.Receive(groupEP)  
            Console.WriteLine("Received broadcast from {0} :", _  
                groupEP.ToString())   
            Console.WriteLine( _  
                Encoding.ASCII.GetString(bytes, 0, bytes.Length))  
            Console.WriteLine()  
         End While  
      Catch e As Exception  
         Console.WriteLine(e.ToString())  
      Finally  
         listener.Close()  
      End Try  
   End Sub 'StartListener  
  
   Public Shared Function Main() As Integer  
      StartListener()  
      Return 0  
   End Function 'Main  
End Class 'UDPListener  
```  
  
```csharp  
using System;  
using System.Net;  
using System.Net.Sockets;  
using System.Text;  
  
public class UDPListener   
{  
    private const int listenPort = 11000;  
  
    private static void StartListener()   
    {  
        bool done = false;  
  
        UdpClient listener = new UdpClient(listenPort);  
        IPEndPoint groupEP = new IPEndPoint(IPAddress.Any,listenPort);  
  
        try   
        {  
            while (!done)   
            {  
                Console.WriteLine("Waiting for broadcast");  
                byte[] bytes = listener.Receive( ref groupEP);  
  
                Console.WriteLine("Received broadcast from {0} :\n {1}\n",  
                    groupEP.ToString(),  
                    Encoding.ASCII.GetString(bytes,0,bytes.Length));  
            }  
  
        }   
        catch (Exception e)   
        {  
            Console.WriteLine(e.ToString());  
        }  
        finally  
        {  
            listener.Close();  
        }  
    }  
  
    public static int Main()   
    {  
        StartListener();  
  
        return 0;  
    }  
}  
```  
  
 다음 코드 예제에서는 사용 하는 <xref:System.Net.Sockets.UdpClient> 11,000 포트를 사용 하 여 직접된 브로드캐스트 주소에 192.168.1.255, UDP 데이터 그램을 보낼 수 있습니다.  클라이언트는 명령줄에 지정 된 메시지 문자열을 보냅니다.  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class Program  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
      Dim s As New Socket(AddressFamily.InterNetwork, SocketType.Dgram,  
          ProtocolType.Udp)  
      Dim broadcast As IPAddress = IPAddress.Parse("192.168.1.255")  
      Dim sendbuf As Byte() = Encoding.ASCII.GetBytes(args(0))  
      Dim ep As New IPEndPoint(broadcast, 11000)  
      s.SendTo(sendbuf, ep)  
      Console.WriteLine("Message sent to the broadcast address")  
   End Function 'Main  
End Class   
```  
  
```csharp  
using System;  
using System.Net;  
using System.Net.Sockets;  
using System.Text;  
  
class Program   
{  
    static void Main(string[] args)   
    {  
        Socket s = new Socket(AddressFamily.InterNetwork, SocketType.Dgram,  
            ProtocolType.Udp);  
  
        IPAddress broadcast = IPAddress.Parse("192.168.1.255");  
  
        byte[] sendbuf = Encoding.ASCII.GetBytes(args[0]);  
        IPEndPoint ep = new IPEndPoint(broadcast, 11000);  
  
        s.SendTo(sendbuf, ep);  
  
        Console.WriteLine("Message sent to the broadcast address");  
    }  
}  
```  
  
## 참고 항목  
 <xref:System.Net.Sockets.UdpClient>   
 <xref:System.Net.IPAddress>   
 [TCP\/UDP](../../../docs/framework/network-programming/tcp-udp.md)