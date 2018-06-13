---
title: 소켓으로 수신
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- sockets, listening with sockets
- data requests, sockets
- requesting data from Internet, sockets
- receiving data, sockets
- protocols, sockets
- listening with sockets
- Internet, sockets
ms.assetid: 40e426cc-13db-4371-95eb-f7388bd23ebf
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f85b63b151bcc20db635f56ec1dfec8df6c92241
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395780"
---
# <a name="listening-with-sockets"></a><span data-ttu-id="4b613-102">소켓으로 수신</span><span class="sxs-lookup"><span data-stu-id="4b613-102">Listening with Sockets</span></span>
<span data-ttu-id="4b613-103">수신기 또는 서버 소켓에서 네트워크의 포트를 열고 클라이언트가 해당 포트에 연결할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="4b613-103">Listener or server sockets open a port on the network and then wait for a client to connect to that port.</span></span> <span data-ttu-id="4b613-104">다른 네트워크 주소 패밀리 및 프로토콜이 있어도 이 예제에서는 TCP/IP 네트워크에 대한 원격 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b613-104">Although other network address families and protocols exist, this example shows how to create remote service for a TCP/IP network.</span></span>  
  
 <span data-ttu-id="4b613-105">TCP/IP 서비스의 고유 주소는 서비스에 대한 끝점을 만드는 서비스의 포트 번호와 호스트의 IP 주소를 결합하여 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4b613-105">The unique address of a TCP/IP service is defined by combining the IP address of the host with the port number of the service to create an endpoint for the service.</span></span> <span data-ttu-id="4b613-106"><xref:System.Net.Dns> 클래스에서는 로컬 네트워크 장치에서 지원하는 네트워크 주소에 대한 정보를 반환하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4b613-106">The <xref:System.Net.Dns> class provides methods that return information about the network addresses supported by the local network device.</span></span> <span data-ttu-id="4b613-107">로컬 네트워크 장치에 두 개 이상의 네트워크 주소가 있거나 로컬 시스템에서 두 개 이상의 네트워크 장치를 지원하는 경우 **Dns** 클래스에서 모든 네트워크 주소에 대한 정보를 반환하고 응용 프로그램에서 서비스의 적절한 주소를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b613-107">When the local network device has more than one network address, or if the local system supports more than one network device, the **Dns** class returns information about all network addresses, and the application must choose the proper address for the service.</span></span> <span data-ttu-id="4b613-108">Iana(Internet Assigned Numbers Authority)는 공통 서비스의 포트 번호를 정의합니다(자세한 내용은 www.iana.org/assignments/port-numbers 참조).</span><span class="sxs-lookup"><span data-stu-id="4b613-108">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services (for more information, see www.iana.org/assignments/port-numbers).</span></span> <span data-ttu-id="4b613-109">다른 서비스에는 1,024 ~ 65,535 범위의 등록된 포트 번호가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b613-109">Other services can have registered port numbers in the range 1,024 to 65,535.</span></span>  
  
 <span data-ttu-id="4b613-110">다음 예에서는 등록된 포트 번호 범위에서 선택된 포트 번호를 사용하는 호스트 컴퓨터의 **Dns**에서 반환한 첫 번째 IP 주소를 결합하여 서버의 <xref:System.Net.IPEndPoint>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b613-110">The following example creates an <xref:System.Net.IPEndPoint> for a server by combining the first IP address returned by **Dns** for the host computer with a port number chosen from the registered port numbers range.</span></span>  
  
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
  
 <span data-ttu-id="4b613-111">로컬 끝점이 판별되고 나면 <xref:System.Net.Sockets.Socket.Bind%2A> 메서드를 사용하여 해당 끝점과 <xref:System.Net.Sockets.Socket>을 연결해야 하며, <xref:System.Net.Sockets.Socket.Listen%2A> 메서드를 사용하여 끝점에서 수신 대기하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b613-111">After the local endpoint is determined, the <xref:System.Net.Sockets.Socket> must be associated with that endpoint using the <xref:System.Net.Sockets.Socket.Bind%2A> method and set to listen on the endpoint using the <xref:System.Net.Sockets.Socket.Listen%2A> method.</span></span> <span data-ttu-id="4b613-112">특정 주소와 포트 조합이 이미 사용 중인 경우 **Bind**에서 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b613-112">**Bind** throws an exception if the specific address and port combination is already in use.</span></span> <span data-ttu-id="4b613-113">다음 예에서는 **Socket**과 **IPEndPoint**의 연결을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b613-113">The following example demonstrates associating a **Socket** with an **IPEndPoint**.</span></span>  
  
```vb  
Dim listener As New Socket(ipAddress.AddressFamily, _  
    SocketType.Stream, ProtocolType.Tcp) 
listener.Bind(localEndPoint)  
listener.Listen(100)  
```  
  
```csharp  
Socket listener = new Socket(ipAddress.AddressFamily,
    SocketType.Stream, ProtocolType.Tcp);
listener.Bind(localEndPoint);  
listener.Listen(100);  
```  
  
 <span data-ttu-id="4b613-114">**Listen** 메서드는 연결 중인 클라이언트에 서버 사용 중 오류가 반환되기 전에 **Socket**에 대해 허용되는 보류 연결 수를 지정하는 단일 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b613-114">The **Listen** method takes a single parameter that specifies how many pending connections to the **Socket** are allowed before a server busy error is returned to the connecting client.</span></span> <span data-ttu-id="4b613-115">이 경우 클라이언트 번호 101에 서버 사용 중 응답이 반환되기 전에 최대 100개의 클라이언트를 연결 큐에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="4b613-115">In this case, up to 100 clients are placed in the connection queue before a server busy response is returned to client number 101.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b613-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b613-116">See Also</span></span>  
 [<span data-ttu-id="4b613-117">동기 서버 소켓 사용</span><span class="sxs-lookup"><span data-stu-id="4b613-117">Using a Synchronous Server Socket</span></span>](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)  
 [<span data-ttu-id="4b613-118">비동기 서버 소켓 사용</span><span class="sxs-lookup"><span data-stu-id="4b613-118">Using an Asynchronous Server Socket</span></span>](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)  
 [<span data-ttu-id="4b613-119">클라이언트 소켓 사용</span><span class="sxs-lookup"><span data-stu-id="4b613-119">Using Client Sockets</span></span>](../../../docs/framework/network-programming/using-client-sockets.md)  
 [<span data-ttu-id="4b613-120">방법: 소켓 만들기</span><span class="sxs-lookup"><span data-stu-id="4b613-120">How to: Create a Socket</span></span>](../../../docs/framework/network-programming/how-to-create-a-socket.md)  
 [<span data-ttu-id="4b613-121">소켓</span><span class="sxs-lookup"><span data-stu-id="4b613-121">Sockets</span></span>](../../../docs/framework/network-programming/sockets.md)
