---
title: "동기 클라이언트 소켓 사용 | Microsoft Docs"
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
  - "데이터 보내기, 소켓"
  - "데이터 요청, 소켓"
  - "인터넷에서 데이터 요청, 소켓"
  - "동기 클라이언트 소켓"
  - "소켓 클래스, 동기 클라이언트 소켓"
  - "데이터 받기, 소켓"
  - "소켓, 동기 클라이언트 소켓"
  - "프로토콜, 소켓"
  - "인터넷, 소켓"
  - "클라이언트 소켓"
ms.assetid: 945d00c6-7202-466c-9df9-140b84156d43
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# 동기 클라이언트 소켓 사용
동기 클라이언트 소켓 네트워크 작업이 완료 될 때 응용 프로그램을 중단 합니다.  동기 소켓 해당 작업에 대 한 네트워크를 많이 사용 하는 응용 프로그램에 적합 하지만 네트워크 서비스를 다른 응용 프로그램에 대 한 간단한 액세스는 사용할 수 있습니다.  
  
 보낼 데이터를 바이트 배열 중 하나에 전달 된 <xref:System.Net.Sockets.Socket> 클래스의 데이터 전송 방법 \(<xref:System.Net.Sockets.Socket.Send%2A> 및 <xref:System.Net.Sockets.Socket.SendTo%2A>\).  다음 예제에서는 바이트 배열 버퍼 사용 하 여에 문자열을 인코딩합니다.는 <xref:System.Text.Encoding.ASCII%2A?displayProperty=fullName> 속성 다음 버퍼를 사용 하 여 네트워크 장치에 전송 하 고는  **보내기** 메서드.  **보내기** 메서드는 네트워크 장치에 보내진 바이트 수를 반환 합니다.  
  
```vb  
Dim msg As Byte() = _  
    System.Text.Encoding.ASCII.GetBytes("This is a test.")  
Dim bytesSent As Integer = s.Send(msg)  
  
```  
  
```csharp  
byte[] msg = System.Text.Encoding.ASCII.GetBytes("This is a test");  
int bytesSent = s.Send(msg);  
```  
  
 **보내기** 메서드는 버퍼에서 바이트를 제거 및 해당 네트워크 인터페이스를 네트워크 장치에 보낼 수 있는 큐입니다.  네트워크 인터페이스 데이터를 즉시 보낼 수 있습니다 있지만 연결으로 폐쇄로 결국 보낼 됩니다는 <xref:System.Net.Sockets.Socket.Shutdown%2A> 메서드.  
  
 네트워크 장치에서 데이터를 수신 하는 버퍼 중 하나에 전달 된  **소켓** 수신 데이터 클래스의 메서드 \(<xref:System.Net.Sockets.Socket.Receive%2A> 및 <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>\).  소켓을 닫을 때까지 또는 네트워크에서 받은 바이트까지 동기 소켓 응용 프로그램을 일시 중단 합니다.  다음 예제에서는 네트워크에서 데이터를 수신 및 다음 콘솔에 표시 합니다.  네트워크에서 들어오는 데이터가 ASCII로 인코딩된 텍스트 임을 전제로 합니다.  **수신** 메서드는 네트워크에서 받은 바이트 수를 반환 합니다.  
  
```vb  
Dim bytes(1024) As Byte  
Dim bytesRec = s.Receive(bytes)  
Console.WriteLine("Echoed text = {0}", _  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec))  
  
```  
  
```csharp  
byte[] bytes = new byte[1024];  
int bytesRec = s.Receive(bytes);  
Console.WriteLine("Echoed text = {0}",  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec));  
```  
  
 소켓이 더 이상 필요 없는 경우 호출 하 여 해제 해야 합니다의 <xref:System.Net.Sockets.Socket.Shutdown%2A> 메서드 및 호출을 다음의  **닫기** 메서드.  다음 예제에서는 해제는  **소켓**.  <xref:System.Net.Sockets.SocketShutdown> 열거형 보내기, 받기, 또는 모두에 대해 소켓을 닫아야 하는지 여부를 나타내는 상수를 정의 합니다.  
  
```vb  
s.Shutdown(SocketShutdown.Both)  
s.Close()  
```  
  
```csharp  
s.Shutdown(SocketShutdown.Both);  
s.Close();  
```  
  
## 참고 항목  
 [비동기 클라이언트 소켓 사용](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)   
 [소켓으로 수신](../../../docs/framework/network-programming/listening-with-sockets.md)   
 [동기 클라이언트 소켓 예제](../../../docs/framework/network-programming/synchronous-client-socket-example.md)