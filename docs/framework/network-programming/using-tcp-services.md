---
title: "TCP 서비스 사용 | Microsoft Docs"
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
  - "인터넷에서 데이터 요청, TCP"
  - "데이터 받기, TCP"
  - "TcpClient 클래스, TcpClient 클래스 정보"
  - "데이터 요청, TCP"
  - "응용 프로그램 프로토콜, TCP"
  - "네트워크 리소스, TCP"
  - "데이터 보내기, TCP"
  - "TCP"
  - "프로토콜, TCP "
  - "인터넷, TCP"
ms.assetid: d2811830-3bcb-495c-b82d-cda9cf919aad
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# TCP 서비스 사용
<xref:System.Net.Sockets.TcpClient> 클래스는 TCP를 사용 하 여 인터넷 리소스에서 데이터를 요청 합니다.  메서드 및 속성의  **TcpClient** 만들기에 대 한 세부 정보를 추상화는 <xref:System.Net.Sockets.Socket> 요청 및 TCP를 사용 하 여 데이터를 수신 합니다.  원격 장치에 연결을 스트림으로 표시 되므로 데이터 읽기 및.NET Framework 스트림을 처리 하는 방법에 기록 합니다.  
  
 TCP 프로토콜은 원격 끝점과 연결 및 다음 해당 연결을 사용 하 여 데이터 패킷을 주고받을 수 있습니다.  TCP는 데이터 패킷을 끝점에 전송 되며 도착 하면 올바른 순서로 어셈블 할 책임입니다.  
  
 TCP 연결을 설정 하려면 필요한 서비스를 호스팅하는 네트워크 장치의 주소를 알고 있어야 하 고 통신 하는 서비스를 사용 하는 TCP 포트를 알아야 합니다.  인터넷 할당 번호 기관 \(Iana\) 공통 서비스 \(www.iana.org\/assignments\/port\-numbers 참조\)에 대 한 포트 번호를 정의 합니다.  Iana 목록에 없는 서비스 포트 번호는 1024에서 65535 범위에 있을 수 있습니다.  
  
 설정 하는 다음 예제를 보여 줍니다.를  **TcpClient** TCP 포트 13 시간 서버에 연결 합니다.  
  
```vb  
Imports System  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class TcpTimeClient  
    Private const portNum As Integer = 13  
    Private const hostName As String = "host.contoso.com"  
  
    ' Entry point  that delegates to C-style main Private Function.  
    Public Overloads Shared Sub Main()  
        System.Environment.ExitCode = _  
            Main(System.Environment.GetCommandLineArgs())  
    End Sub  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
        Try  
            Dim client As New TcpClient(hostName, portNum)  
  
            Dim ns As NetworkStream = client.GetStream()  
  
            Dim bytes(1024) As Byte  
            Dim bytesRead As Integer = ns.Read(bytes, 0, bytes.Length)  
  
            Console.WriteLine(Encoding.ASCII.GetString(bytes, 0, bytesRead))  
  
        Catch e As Exception  
            Console.WriteLine(e.ToString())  
        End Try  
  
        client.Close()  
  
        Return 0  
    End Function 'Main  
End Class 'TcpTimeClient  
  
```  
  
```csharp  
using System;  
using System.Net.Sockets;  
using System.Text;  
  
public class TcpTimeClient {  
    private const int portNum = 13;  
    private const string hostName = "host.contoso.com";  
  
    public static int Main(String[] args) {  
        try {  
            TcpClient client = new TcpClient(hostName, portNum);  
  
            NetworkStream ns = client.GetStream();  
  
            byte[] bytes = new byte[1024];  
            int bytesRead = ns.Read(bytes, 0, bytes.Length);  
  
            Console.WriteLine(Encoding.ASCII.GetString(bytes,0,bytesRead));  
  
            client.Close();  
  
        } catch (Exception e) {  
            Console.WriteLine(e.ToString());  
        }  
  
        return 0;  
    }  
}  
```  
  
 <xref:System.Net.Sockets.TcpListener>들어오는 요청에 대 한 TCP 포트를 모니터링 하 고 하나를 만드는 데는  **소켓** 또는  **TcpClient** 는 클라이언트 연결을 관리 합니다.  <xref:System.Net.Sockets.TcpListener.Start%2A> 메서드 있습니다 수신, 및 <xref:System.Net.Sockets.TcpListener.Stop%2A> 메서드를 사용 하지 않도록 설정 포트에서 수신 대기 합니다.  <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> 메서드는 들어오는 연결 요청을 받아 만듭니다는  **TcpClient** 요청을 처리 하 고 <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> 메서드는 들어오는 연결 요청을 받아 만듭니다는  **소켓** 요청을 처리할 수.  
  
 다음 예제에서는 사용 하 여 네트워크 시간 서버를 만드는 방법을 보여 줍니다.을  **TcpListener** TCP 포트 13을 모니터링 합니다.  들어오는 연결 요청을 수락할 때 시간 서버 호스트 서버에서 현재 날짜와 시간으로 응답 합니다.  
  
```vb  
Imports System  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class TcpTimeServer  
  
    Private const portNum As Integer = 13  
  
    ' Entry point that delegates to C-style main Private Function.  
    Public Overloads Shared Sub Main()  
        System.Environment.ExitCode = _  
            Main(System.Environment.GetCommandLineArgs())  
    End Sub  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
        Dim done As Boolean = False  
  
        Dim listener As New TcpListener(portNum)  
  
        listener.Start()  
  
        While Not done  
            Console.Write("Waiting for connection...")  
            Dim client As TcpClient = listener.AcceptTcpClient()  
  
            Console.WriteLine("Connection accepted.")  
            Dim ns As NetworkStream = client.GetStream()  
  
            Dim byteTime As Byte() = _  
                Encoding.ASCII.GetBytes(DateTime.Now.ToString())  
  
            Try  
                ns.Write(byteTime, 0, byteTime.Length)  
                ns.Close()  
                client.Close()  
            Catch e As Exception  
                Console.WriteLine(e.ToString())  
            End Try  
        End While  
  
        listener.Stop()  
  
        Return 0  
    End Function 'Main  
End Class 'TcpTimeServer  
```  
  
```csharp  
using System;  
using System.Net.Sockets;  
using System.Text;  
  
public class TcpTimeServer {  
  
    private const int portNum = 13;  
  
    public static int Main(String[] args) {  
        bool done = false;  
  
        TcpListener listener = new TcpListener(portNum);  
  
        listener.Start();  
  
        while (!done) {  
            Console.Write("Waiting for connection...");  
            TcpClient client = listener.AcceptTcpClient();  
  
            Console.WriteLine("Connection accepted.");  
            NetworkStream ns = client.GetStream();  
  
            byte[] byteTime = Encoding.ASCII.GetBytes(DateTime.Now.ToString());  
  
            try {  
                ns.Write(byteTime, 0, byteTime.Length);  
                ns.Close();  
                client.Close();  
            } catch (Exception e) {  
                Console.WriteLine(e.ToString());  
            }  
        }  
  
        listener.Stop();  
  
        return 0;  
    }  
  
}  
```  
  
## 참고 항목  
 [TCP\/UDP](../../../docs/framework/network-programming/tcp-udp.md)