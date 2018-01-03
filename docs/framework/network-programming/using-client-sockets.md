---
title: "클라이언트 소켓 사용"
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
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- receiving data, sockets
- Socket class, client sockets
- protocols, sockets
- Internet, sockets
- sockets, client sockets
- client sockets
ms.assetid: 81de9f59-8177-4d98-b25d-43fc32a98383
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 25c033ae46abc65040c00b6beb105c8ebb6b1d90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="using-client-sockets"></a>클라이언트 소켓 사용
<xref:System.Net.Sockets.Socket>을 통해 대화를 시작하려면 먼저 응용 프로그램과 원격 장치 간에 데이터 파이프를 만들어야 합니다. 다른 네트워크 주소 패밀리 및 프로토콜이 있어도 이 예제에서는 원격 서비스에 대한 TCP/IP 연결을 만드는 방법을 보여 줍니다.  
  
 TCP/IP는 네트워크 주소와 서비스 포트 번호를 사용하여 서비스를 고유하게 식별합니다. 네트워크 주소는 네트워크에서 특정 장치를 식별하고, 포트 번호는 연결할 해당 장치의 특정 서비스를 식별합니다. 네트워크 주소와 서비스 포트의 조합을 끝점이라고 하며, .NET Framework에서는 <xref:System.Net.EndPoint> 클래스로 표현됩니다. **EndPoint**의 하위 항목이 지원되는 각 주소 패밀리에 대해 정의되고, IP 주소 패밀리에 대한 클래스는 <xref:System.Net.IPEndPoint>입니다.  
  
 <xref:System.Net.Dns> 클래스는 TCP/IP 인터넷 서비스를 사용하는 응용 프로그램에 도메인 이름 서비스를 제공합니다. <xref:System.Net.Dns.Resolve%2A> 메서드는 DNS 서버를 쿼리하여 친숙한 도메인 이름(예: “host.contoso.com”)을 숫자 인터넷 주소(예: 192.168.1.1)에 매핑합니다. **Resolve**는 요청된 이름에 대한 주소 및 별칭 목록이 들어 있는 <xref:System.Net.IPHostEntry>를 반환합니다. 대부분의 경우 <xref:System.Net.IPHostEntry.AddressList%2A> 배열에 반환된 첫 번째 주소를 사용할 수 있습니다. 다음 코드에서는 host.contoso.com 서버의 IP 주소가 포함된 <xref:System.Net.IPAddress>를 가져옵니다.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve("host.contoso.com")  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve("host.contoso.com");  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
```  
  
 Iana(Internet Assigned Numbers Authority)는 공통 서비스의 포트 번호를 정의합니다(자세한 내용은 www.iana.org/assignments/port-numbers 참조). 다른 서비스에는 1,024 ~ 65,535 범위의 등록된 포트 번호가 있을 수 있습니다. 다음 코드에서는 host.contoso.com의 IP 주소를 포트 번호와 결합하여 연결에 대한 원격 끝점을 만듭니다.  
  
```vb  
Dim ipe As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPEndPoint ipe = new IPEndPoint(ipAddress,11000);  
```  
  
 원격 장치의 주소를 결정하고 연결에 사용할 포트를 선택하면 응용 프로그램이 원격 장치에 대한 연결을 시도할 수 있습니다. 다음 예제에서는 기존 **IPEndPoint**를 사용하여 원격 장치에 연결하고 throw되는 예외를 catch합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [동기 클라이언트 소켓 사용](../../../docs/framework/network-programming/using-a-synchronous-client-socket.md)  
 [비동기 클라이언트 소켓 사용](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)  
 [방법: 소켓 만들기](../../../docs/framework/network-programming/how-to-create-a-socket.md)  
 [소켓](../../../docs/framework/network-programming/sockets.md)
