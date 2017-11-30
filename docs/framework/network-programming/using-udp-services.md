---
title: "UDP 서비스 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- protocols, UDP
- network resources, UDP
- requesting data from Internet, UDP
- UDP
- receiving data, UDP
- Internet, UDP
- broadcasting messages to multiple addresses
- data requests, UDP
- UdpClient class, about UdpClient class
- sending data, UDP
- application protocols, UDP
ms.assetid: d5c3477a-e798-454c-a890-738ba14c5707
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c535710175423ebd0d163edc9bce78cfb2e18168
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-udp-services"></a>UDP 서비스 사용
<xref:System.Net.Sockets.UdpClient> 클래스는 UDP를 사용하여 네트워크 서비스와 통신합니다. <xref:System.Net.Sockets.UdpClient> 클래스의 속성 및 메서드는 UDP를 사용하여 데이터를 요청 및 수신하는 <xref:System.Net.Sockets.Socket>을 만들기 위한 세부 정보를 추상화합니다.  
  
 UDP(User Datagram Protocol)는 원격 호스트에 데이터를 전달하기 위해 최상의 노력을 하는 간단한 프로토콜입니다. 그러나 UDP 프로토콜은 연결 없는 프로토콜이기 때문에 원격 끝점에 전송된 UDP 데이터그램은 도착한다고 보장되지 않으며 전송된 동일한 순서로 도착한다고 보장되지도 않습니다. UDP를 사용하는 응용 프로그램은 누락, 중복 및 순서가 잘못된 데이터그램을 처리하도록 준비해야 합니다.  
  
 UDP를 사용하여 데이터그램을 보내려면 필요한 서비스를 호스트하는 네트워크 장치의 네트워크 주소와 서비스가 통신에 사용하는 UDP 포트 번호를 알고 있어야 합니다. Iana(Internet Assigned Numbers Authority)는 공통 서비스의 포트 번호를 정의합니다(www.iana.org/assignments/port-numbers 참조). Iana 목록에 없는 서비스에는 1,024~65,535 범위의 포트 번호를 사용할 수 있습니다.  
  
 특수 네트워크 주소는 IP 기반 네트워크에서 UDP 브로드캐스트 메시지를 지원하는 데 사용됩니다. 예를 들어 다음 설명에서는 인터넷에서 사용되는 IP 버전 4 주소 패밀리를 사용합니다.  
  
 IP 버전 4 주소는 32비트를 사용하여 네트워크 주소를 지정합니다. 네트워크 마스크 255.255.255.0을 사용하는 클래스 C 주소의 경우 이러한 비트가 4개의 8진수로 구분됩니다. 10진수로 표현된 경우 4개의 8진수는 192.168.100.2 같은 친숙한 점 표기법을 형성합니다. 처음 두 개의 8진수(이 예제의 192.168)는 네트워크 번호를 형성하고, 세 번째 8진수(100)는 서브넷을 정의하고, 최종 8진수(2)는 호스트 식별자입니다.  
  
 IP 주소의 모든 비트를 1 또는 255.255.255.255로 설정하면 제한된 브로드캐스트 주소가 형성됩니다. 이 주소에 UDP 데이터그램을 보내면 로컬 네트워크 세그먼트의 모든 호스트에 메시지가 배달됩니다. 라우터는 이 주소로 전송된 메시지를 전달하지 않으므로 네트워크 세그먼트의 호스트만 브로드캐스트 메시지를 받습니다.  
  
 호스트 식별자의 모든 비트를 설정하여 브로드캐스트를 네트워크의 특정 부분으로 리디렉션할 수 있습니다. 예를 들어 192.168.1로 시작하는 IP 주소로 식별되는 네트워크의 모든 호스트에 브로드캐스트를 보내려면 192.168.1.255 주소를 사용합니다.  
  
 다음 코드 예제에서는 <xref:System.Net.Sockets.UdpClient>를 사용하여 포트 11,000에서 리디렉션된 브로드캐스트 주소 192.168.1.255로 전송된 UDP 데이터그램을 수신 대기합니다. 클라이언트는 메시지 문자열을 수신하고 메시지를 콘솔에 씁니다.  
  
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
  
 다음 코드 예제에서는 <xref:System.Net.Sockets.UdpClient>를 사용하여 포트 11,000을 통해 리디렉션된 브로드캐스트 주소 192.168.1.255로 UDP 데이터그램을 전송합니다. 클라이언트는 명령줄에 지정된 메시지 문자열을 보냅니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Net.Sockets.UdpClient>  
 <xref:System.Net.IPAddress>  
 
