---
title: "동기 서버 소켓 사용"
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
- synchronous server sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- Socket class, synchronous server sockets
- protocols, sockets
- sockets, synchronous server sockets
- Internet, sockets
ms.assetid: d1ce882e-653e-41f5-9289-844ec855b804
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ce50fa5cf8664f93753312ee5f1db2b3058c3fd9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-a-synchronous-server-socket"></a><span data-ttu-id="aeb5d-102">동기 서버 소켓 사용</span><span class="sxs-lookup"><span data-stu-id="aeb5d-102">Using a Synchronous Server Socket</span></span>
<span data-ttu-id="aeb5d-103">동기 서버 소켓은 소켓에 연결 요청이 수신될 때까지 응용 프로그램 실행을 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-103">Synchronous server sockets suspend the execution of the application until a connection request is received on the socket.</span></span> <span data-ttu-id="aeb5d-104">동기 서버 소켓은 네트워크를 작업에 많이 사용하는 응용 프로그램에 적합하지 않지만 간단한 네트워크 응용 프로그램에는 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-104">Synchronous server sockets are not suitable for applications that make heavy use of the network in their operation, but they can be suitable for simple network applications.</span></span>  
  
 <span data-ttu-id="aeb5d-105"><xref:System.Net.Sockets.Socket>이 <xref:System.Net.Sockets.Socket.Bind%2A> 및 <xref:System.Net.Sockets.Socket.Listen%2A> 메서드를 사용하여 끝점에서 수신 대기하도록 설정되면 <xref:System.Net.Sockets.Socket.Accept%2A> 메서드를 사용하여 들어오는 연결 요청을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-105">After a <xref:System.Net.Sockets.Socket> is set to listen on an endpoint using the <xref:System.Net.Sockets.Socket.Bind%2A> and <xref:System.Net.Sockets.Socket.Listen%2A> methods, it is ready to accept incoming connection requests using the <xref:System.Net.Sockets.Socket.Accept%2A> method.</span></span> <span data-ttu-id="aeb5d-106">**Accept** 메서드를 호출하면 연결 요청이 수신될 때까지 응용 프로그램이 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-106">The application is suspended until a connection request is received when the **Accept** method is called.</span></span>  
  
 <span data-ttu-id="aeb5d-107">연결 요청이 수신되면 **Accept**는 연결 중인 클라이언트와 연결된 새 **Socket** 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-107">When a connection request is received, **Accept** returns a new **Socket** instance that is associated with the connecting client.</span></span> <span data-ttu-id="aeb5d-108">다음 예제에서는 클라이언트에서 데이터를 읽고 콘솔에 표시한 다음 데이터를 클라이언트에 다시 에코합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-108">The following example reads data from the client, displays it on the console, and echoes the data back to the client.</span></span> <span data-ttu-id="aeb5d-109">**Socket**은 메시징 프로토콜을 지정하지 않으므로 “\<EOF>” 문자열은 메시지 데이터의 끝을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-109">The **Socket** does not specify any messaging protocol, so the string "\<EOF>" marks the end of the message data.</span></span> <span data-ttu-id="aeb5d-110">`listener`라는 **Socket**이 초기화되었으며 끝점에 바인딩되었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-110">It assumes that a **Socket** named `listener` has been initialized and bound to an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aeb5d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aeb5d-111">See Also</span></span>  
 [<span data-ttu-id="aeb5d-112">비동기 서버 소켓 사용</span><span class="sxs-lookup"><span data-stu-id="aeb5d-112">Using an Asynchronous Server Socket</span></span>](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)  
 [<span data-ttu-id="aeb5d-113">동기 서버 소켓 예제</span><span class="sxs-lookup"><span data-stu-id="aeb5d-113">Synchronous Server Socket Example</span></span>](../../../docs/framework/network-programming/synchronous-server-socket-example.md)  
 [<span data-ttu-id="aeb5d-114">소켓으로 수신</span><span class="sxs-lookup"><span data-stu-id="aeb5d-114">Listening with Sockets</span></span>](../../../docs/framework/network-programming/listening-with-sockets.md)
