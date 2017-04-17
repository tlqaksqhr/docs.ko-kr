---
title: "동기 서버 소켓 사용 | Microsoft Docs"
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
  - "응용 프로그램 프로토콜, 소켓"
  - "동기 서버 소켓"
  - "데이터 보내기, 소켓"
  - "데이터 요청, 소켓"
  - "인터넷에서 데이터 요청, 소켓"
  - "서버 소켓"
  - "데이터 받기, 소켓"
  - "소켓 클래스, 동기 서버 소켓"
  - "프로토콜, 소켓"
  - "소켓, 동기 서버 소켓"
  - "인터넷, 소켓"
ms.assetid: d1ce882e-653e-41f5-9289-844ec855b804
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 동기 서버 소켓 사용
소켓에서 연결 요청을 받을 때까지 동기 서버 소켓 응용 프로그램의 실행을 일시 중단 합니다.  동기 서버 소켓 작업에 네트워크를 많이 사용 하는 응용 프로그램에 적합 하지만 간단한 네트워크 응용 프로그램에 적합 한 수 있습니다.  
  
 후는 <xref:System.Net.Sockets.Socket> 사용 하 여 끝점에서 수신 대기 하도록 설정 된 <xref:System.Net.Sockets.Socket.Bind%2A> 및 <xref:System.Net.Sockets.Socket.Listen%2A> 메서드는 들어오는 연결 요청을 사용 하 여 수락 준비가 되었습니다는 <xref:System.Net.Sockets.Socket.Accept%2A> 메서드.  연결 요청을 받을 때까지 응용 프로그램이 일시 중단 됩니다 때의  **수락** 메서드를 호출 합니다.  
  
 연결 요청을 받으면  **수락** 새 반환  **소켓** 연결 된 클라이언트와 연결 된 인스턴스.  다음 예제에서는 클라이언트에서 데이터를 읽고, 콘솔에 표시 됩니다 및 데이터를 다시 클라이언트에 에코.  **소켓** 메시지 데이터 끝 "\<EOF\>" 문자열을 표시 하도록 모든 메시징 프로토콜을 지정 하지 않습니다.  이 가정은  **소켓** 라는 `listener` 초기화 및 끝점에 연결.  
  
```vb  
Console.WriteLine("Waiting for a connection...")  
Dim handler As Socket = listener.Accept()  
Dim data As String = Nothing  
  
While True  
    bytes = New Byte(1024) {}  
    Dim bytesRec As Integer = handler.Receive(bytes)  
    data += Encoding.ASCII.GetString(bytes, 0, bytesRec)  
    If data.IndexOf("<EOF>") > - 1 Then  
        Exit While  
    End If  
End While  
  
Console.WriteLine("Text received : {0}", data)  
  
Dim msg As Byte() = Encoding.ASCII.GetBytes(data)  
handler.Send(msg)  
handler.Shutdown(SocketShutdown.Both)  
handler.Close()  
  
```  
  
```csharp  
Console.WriteLine("Waiting for a connection...");  
Socket handler = listener.Accept();  
String data = null;  
  
while (true) {  
    bytes = new byte[1024];  
    int bytesRec = handler.Receive(bytes);  
    data += Encoding.ASCII.GetString(bytes,0,bytesRec);  
    if (data.IndexOf("<EOF>") > -1) {  
        break;  
    }  
}  
  
Console.WriteLine( "Text received : {0}", data);  
  
byte[] msg = Encoding.ASCII.GetBytes(data);  
handler.Send(msg);  
handler.Shutdown(SocketShutdown.Both);  
handler.Close();  
```  
  
## 참고 항목  
 [비동기 서버 소켓 사용](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [동기 서버 소켓 예제](../../../docs/framework/network-programming/synchronous-server-socket-example.md)   
 [소켓으로 수신](../../../docs/framework/network-programming/listening-with-sockets.md)