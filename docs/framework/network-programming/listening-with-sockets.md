---
title: "소켓으로 수신 | Microsoft Docs"
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
  - "소켓, 소켓으로 수신"
  - "데이터 요청, 소켓"
  - "인터넷에서 데이터 요청, 소켓"
  - "데이터 받기, 소켓"
  - "프로토콜, 소켓"
  - "소켓으로 수신"
  - "인터넷, 소켓"
ms.assetid: 40e426cc-13db-4371-95eb-f7388bd23ebf
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# 소켓으로 수신
수신기 또는 서버 소켓은 네트워크에서 포트를 열 및 해당 포트에 연결할 클라이언트를 기다립니다.  다른 네트워크 주소 패밀리 및 프로토콜이 있지만이 예제에서는 TCP\/IP 네트워크에 대 한 원격 서비스를 만드는 방법을 보여 줍니다.  
  
 TCP\/IP 서비스의 고유 주소는 호스트의 IP 주소는 서비스 끝점을 만드는 데 서비스의 포트 번호를 조합 하 여 정의 됩니다.  <xref:System.Net.Dns> 클래스는 로컬 네트워크 장치에서 지 원하는 네트워크 주소에 대 한 정보를 반환 하는 메서드를 제공 합니다.  로컬 네트워크 장치에서 두 개 이상의 네트워크 주소가 있을 때 또는 로컬 시스템 두 개 이상의 네트워크 장치를 지 원하는 경우는  **Dns** 클래스는 모든 네트워크 주소에 대 한 정보를 반환 하 고 응용 프로그램 서비스에 대 한 적절 한 주소를 선택 해야 합니다.  인터넷 할당 번호 기관 \(Iana\) 공통 서비스 \(자세한 내용은 www.iana.org\/assignments\/port\-numbers 참조\)에 대 한 포트 번호를 정의합니다.  다른 서비스 포트 번호는 1024에서 65535 범위에서 등록 수 있습니다.  
  
 다음 예제는 <xref:System.Net.IPEndPoint> 서버에서 반환 된 첫 번째 IP 주소를 결합 하 여  **Dns** 등록 된 포트 번호 범위에서 선택한 포트 번호와 호스트 컴퓨터.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
Dim localEndPoint As New IPEndPoint(ipAddress, 11000)  
  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
IPEndPoint localEndPoint = new IPEndPoint(ipAddress, 11000);  
```  
  
 로컬 끝점이 결정 되 면은 <xref:System.Net.Sockets.Socket> 해당 끝점을 사용 하 여 연결 해야는 <xref:System.Net.Sockets.Socket.Bind%2A> 메서드 및 집합을 사용 하 여 끝점에서 수신 대기 하는 <xref:System.Net.Sockets.Socket.Listen%2A> 메서드.  **바인딩할** 경우 예외가 throw 된 이미 사용 중인 주소 및 포트 조합입니다.  다음 예제 연결에  **소켓** 에  **IPEndPoint**.  
  
```vb  
listener.Bind(localEndPoint)  
listener.Listen(100)  
```  
  
```csharp  
listener.Bind(localEndPoint);  
listener.Listen(100);  
```  
  
 **수신** 메서드는 보류 중인 연결 개수를 지정 하는 단일 매개 변수를 사용을  **소켓** 연결 클라이언트에 서버 작업 중 오류가 반환 하기 전에 허용 되는.  이 경우 서버가 사용 중인 응답 101 클라이언트 번호를 반환 하기 전에 최대 100 명의 클라이언트 연결 큐에 배치 됩니다.  
  
## 참고 항목  
 [동기 서버 소켓 사용](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)   
 [비동기 서버 소켓 사용](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [클라이언트 소켓 사용](../../../docs/framework/network-programming/using-client-sockets.md)   
 [방법: 소켓 만들기](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [소켓](../../../docs/framework/network-programming/sockets.md)