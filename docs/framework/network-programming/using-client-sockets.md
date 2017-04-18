---
title: "클라이언트 소켓 사용 | Microsoft Docs"
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
  - "데이터 받기, 소켓"
  - "소켓 클래스, 클라이언트 소켓"
  - "프로토콜, 소켓"
  - "인터넷, 소켓"
  - "소켓, 클라이언트 소켓"
  - "클라이언트 소켓"
ms.assetid: 81de9f59-8177-4d98-b25d-43fc32a98383
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# 클라이언트 소켓 사용
대화를 통해 시작할 수 있습니다 전에 <xref:System.Net.Sockets.Socket>, 응용 프로그램과 원격 장치 사이 데이터 파이프를 만들어야 합니다.  다른 네트워크 주소 패밀리 및 프로토콜이 있지만이 예제에서는 원격 서비스에 TCP\/IP 연결을 만드는 방법을 보여 줍니다.  
  
 서비스를 고유 하 게 식별 하는 네트워크 주소와 서비스 포트 번호를 TCP\/IP를 사용 합니다.  네트워크 주소는 네트워크에서 특정 장치를 나타냅니다. 포트 번호는 연결할 해당 장치에서 특정 서비스를 식별 합니다.  네트워크 주소와 서비스 포트의 조합이 끝점에는.NET Framework 표시 되며, 호출 되는 <xref:System.Net.EndPoint> 클래스입니다.  하위 항목의  **끝점** 정의 각 지원 되는 주소 패밀리입니다. IP 주소 패밀리에 대 한 클래스인 <xref:System.Net.IPEndPoint>.  
  
 <xref:System.Net.Dns> 클래스는 TCP\/IP 인터넷 서비스를 사용 하는 응용 프로그램 도메인 이름 서비스를 제공 합니다.  <xref:System.Net.Dns.Resolve%2A> 메서드 숫자로 된 인터넷 주소 \(예: 192.168.1.1\)에 친숙 한 도메인 이름 \(예: "나타내기"\)에 매핑하는 DNS 서버를 쿼리 합니다.  **해결** 반환은  [IPHostEnty](frlrfsystemnetiphostentryclasstopic) 요청 된 이름에 대 한 별칭 및 주소 목록을 포함 합니다.  대부분의 경우 첫 번째 반환 주소 수를 <xref:System.Net.IPHostEntry.AddressList%2A> 배열.  다음 코드를 가져옵니다는 <xref:System.Net.IPAddress> 서버 나타내기에 대 한 IP 주소를 포함 합니다.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve("host.contoso.com")  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve("host.contoso.com");  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
```  
  
 인터넷 할당 번호 기관 \(Iana\) 공통 서비스 \(자세한 내용은 www.iana.org\/assignments\/port\-numbers 참조\)에 대 한 포트 번호를 정의합니다.  다른 서비스 포트 번호는 1024에서 65535 범위에서 등록 수 있습니다.  다음 코드 원격 끝점과 연결을 만들 수 있는 포트 번호와 IP 주소를 나타내기를 결합 합니다.  
  
```vb  
Dim ipe As New IPEndPoint(ipAddress, 11000)  
  
```  
  
```csharp  
IPEndPoint ipe = new IPEndPoint(ipAddress,11000);  
```  
  
 원격 장치의 주소를 결정 하는 연결에 사용할 포트를 선택 후 응용 프로그램 원격 장치에 연결을 시도할 수 있습니다.  다음 예제에서는 기존에 사용 하 여  **IPEndPoint** 원격 장치에 연결 하려면 throw 되는 예외를 catch 하 고.  
  
```vb  
Try  
    s.Connect(ipe)  
Catch ae As ArgumentNullException  
    Console.WriteLine("ArgumentNullException : {0}", _  
        ae.ToString())  
Catch se As SocketException  
    Console.WriteLine("SocketException : {0}", se.ToString())  
Catch e As Exception  
    Console.WriteLine("Unexpected exception : {0}", e.ToString())  
End Try  
  
```  
  
```csharp  
try {  
    s.Connect(ipe);  
} catch(ArgumentNullException ae) {  
    Console.WriteLine("ArgumentNullException : {0}", ae.ToString());  
} catch(SocketException se) {  
    Console.WriteLine("SocketException : {0}", se.ToString());  
} catch(Exception e) {  
    Console.WriteLine("Unexpected exception : {0}", e.ToString());  
}  
```  
  
## 참고 항목  
 [동기 클라이언트 소켓 사용](../../../docs/framework/network-programming/using-a-synchronous-client-socket.md)   
 [비동기 클라이언트 소켓 사용](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)   
 [방법: 소켓 만들기](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [소켓](../../../docs/framework/network-programming/sockets.md)