---
title: 동기 클라이언트 소켓 사용
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- synchronous client sockets
- Socket class, synchronous client sockets
- receiving data, sockets
- sockets, synchronous client sockets
- protocols, sockets
- Internet, sockets
- client sockets
ms.assetid: 945d00c6-7202-466c-9df9-140b84156d43
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c9101957c6c4b9961ca5985bda8b8f82d69b45d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397704"
---
# <a name="using-a-synchronous-client-socket"></a><span data-ttu-id="cc029-102">동기 클라이언트 소켓 사용</span><span class="sxs-lookup"><span data-stu-id="cc029-102">Using a Synchronous Client Socket</span></span>
<span data-ttu-id="cc029-103">동기 클라이언트 소켓은 네트워크 작업이 완료되는 동안 응용 프로그램을 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="cc029-103">A synchronous client socket suspends the application program while the network operation completes.</span></span> <span data-ttu-id="cc029-104">동기 소켓은 네트워크를 작업에 많이 사용하는 응용 프로그램에 적합하지 않지만 다른 응용 프로그램의 네트워크 서비스에 대한 간단한 액세스를 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc029-104">Synchronous sockets are not suitable for applications that make heavy use of the network for their operation, but they can enable simple access to network services for other applications.</span></span>  
  
 <span data-ttu-id="cc029-105">데이터를 보내려면 바이트 배열을 <xref:System.Net.Sockets.Socket> 클래스의 데이터 전송 메서드(<xref:System.Net.Sockets.Socket.Send%2A> 및 <xref:System.Net.Sockets.Socket.SendTo%2A>) 중 하나에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cc029-105">To send data, pass a byte array to one of the <xref:System.Net.Sockets.Socket> class's send-data methods (<xref:System.Net.Sockets.Socket.Send%2A> and <xref:System.Net.Sockets.Socket.SendTo%2A>).</span></span> <span data-ttu-id="cc029-106">다음 예제에서는 <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType> 속성을 사용하여 문자열을 바이트 배열 버퍼로 인코드한 다음 **Send** 메서드를 사용하여 버퍼를 네트워크 장치에 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="cc029-106">The following example encodes a string into a byte array buffer using the <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType> property and then transmits the buffer to the network device using the **Send** method.</span></span> <span data-ttu-id="cc029-107">**Send** 메서드는 네트워크 장치에 전송된 바이트 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cc029-107">The **Send** method returns the number of bytes sent to the network device.</span></span>  
  
```vb  
Dim msg As Byte() = _  
    System.Text.Encoding.ASCII.GetBytes("This is a test.")  
Dim bytesSent As Integer = s.Send(msg)  
```  
  
```csharp  
byte[] msg = System.Text.Encoding.ASCII.GetBytes("This is a test");  
int bytesSent = s.Send(msg);  
```  
  
 <span data-ttu-id="cc029-108">**Send** 메서드는 버퍼에서 바이트를 제거하고 네트워크 인터페이스를 사용하여 네트워크 장치에 전송되도록 큐에 대기시킵니다.</span><span class="sxs-lookup"><span data-stu-id="cc029-108">The **Send** method removes the bytes from the buffer and queues them with the network interface to be sent to the network device.</span></span> <span data-ttu-id="cc029-109">네트워크 인터페이스에서 데이터를 즉시 전송하지 않을 수도 있지만, 연결이 <xref:System.Net.Sockets.Socket.Shutdown%2A> 메서드를 사용하여 정상적으로 닫히기만 하면 결국 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="cc029-109">The network interface might not send the data immediately, but it will send it eventually, as long as the connection is closed normally with the <xref:System.Net.Sockets.Socket.Shutdown%2A> method.</span></span>  
  
 <span data-ttu-id="cc029-110">네트워크 장치에서 데이터를 수신하려면 버퍼를 **Socket** 클래스의 데이터 수신 메서드(<xref:System.Net.Sockets.Socket.Receive%2A> 및 <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>) 중 하나에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cc029-110">To receive data from a network device, pass a buffer to one of the **Socket** class's receive-data methods (<xref:System.Net.Sockets.Socket.Receive%2A> and <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>).</span></span> <span data-ttu-id="cc029-111">네트워크에서 바이트가 수신되거나 소켓이 닫힐 때까지 동기 소켓이 응용 프로그램을 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="cc029-111">Synchronous sockets will suspend the application until bytes are received from the network or until the socket is closed.</span></span> <span data-ttu-id="cc029-112">다음 예제에서는 네트워크에서 데이터를 수신한 후 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cc029-112">The following example receives data from the network and then displays it on the console.</span></span> <span data-ttu-id="cc029-113">이 예제에서는 네트워크에서 들어오는 데이터가 ASCII로 인코드된 텍스트라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="cc029-113">The example assumes that the data coming from the network is ASCII-encoded text.</span></span> <span data-ttu-id="cc029-114">**Receive** 메서드는 네트워크에서 받은 바이트 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cc029-114">The **Receive** method returns the number of bytes received from the network.</span></span>  
  
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
  
 <span data-ttu-id="cc029-115">소켓이 더 이상 필요하지 않은 경우 <xref:System.Net.Sockets.Socket.Shutdown%2A> 메서드를 호출한 다음 **Close** 메서드를 호출하여 소켓을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc029-115">When the socket is no longer needed, you need to release it by calling the <xref:System.Net.Sockets.Socket.Shutdown%2A> method and then calling the **Close** method.</span></span> <span data-ttu-id="cc029-116">다음 예제에서는 **Socket**을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="cc029-116">The following example releases a **Socket**.</span></span> <span data-ttu-id="cc029-117"><xref:System.Net.Sockets.SocketShutdown> 열거형은 전송, 수신 또는 둘 다를 위해 소켓을 닫아야 하는지 여부를 나타내는 상수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cc029-117">The <xref:System.Net.Sockets.SocketShutdown> enumeration defines constants that indicate whether the socket should be closed for sending, for receiving, or for both.</span></span>  
  
```vb  
s.Shutdown(SocketShutdown.Both)  
s.Close()  
```  
  
```csharp  
s.Shutdown(SocketShutdown.Both);  
s.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc029-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc029-118">See Also</span></span>  
 [<span data-ttu-id="cc029-119">비동기 클라이언트 소켓 사용</span><span class="sxs-lookup"><span data-stu-id="cc029-119">Using an Asynchronous Client Socket</span></span>](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)  
 [<span data-ttu-id="cc029-120">소켓으로 수신</span><span class="sxs-lookup"><span data-stu-id="cc029-120">Listening with Sockets</span></span>](../../../docs/framework/network-programming/listening-with-sockets.md)  
 [<span data-ttu-id="cc029-121">동기 클라이언트 소켓 예제</span><span class="sxs-lookup"><span data-stu-id="cc029-121">Synchronous Client Socket Example</span></span>](../../../docs/framework/network-programming/synchronous-client-socket-example.md)
