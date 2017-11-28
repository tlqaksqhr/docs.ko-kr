---
title: "네트워크에서 스트림 사용"
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
- requesting data from Internet, streams
- Networking
- response to Internet request, streams
- network resources, stream capabilities
- receiving data, stream capabilities
- Network Resources
- sending data, stream capabilities
- downloading Internet resources, streams
- streams, capabilities
- Internet, streams
- streams
ms.assetid: 02b05fba-7235-45ce-94e5-060436ee0875
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f9e011b304a7f6c7d0d07761677c0368efcfcf4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-streams-on-the-network"></a><span data-ttu-id="da02b-102">네트워크에서 스트림 사용</span><span class="sxs-lookup"><span data-stu-id="da02b-102">Using Streams on the Network</span></span>
<span data-ttu-id="da02b-103">네트워크 리소스는 .NET Framework에서 스트림으로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-103">Network resources are represented in the .NET Framework as streams.</span></span> <span data-ttu-id="da02b-104">스트림을 일반적으로 처리하여 .NET Framework는 다음과 같은 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-104">By treating streams generically, the .NET Framework offers the following capabilities:</span></span>  
  
-   <span data-ttu-id="da02b-105">웹 데이터를 송수신하는 일반적인 방법.</span><span class="sxs-lookup"><span data-stu-id="da02b-105">A common way to send and receive Web data.</span></span> <span data-ttu-id="da02b-106">파일의 실제 내용에 관계없이(HTML, XML 또는 기타 모든 항목) 응용 프로그램은 <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType> 및 <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType>를 사용하여 데이터를 주고받습니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-106">Whatever the actual contents of the file — HTML, XML, or anything else — your application will use <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType> and <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType> to send and receive data.</span></span>  
  
-   <span data-ttu-id="da02b-107">.NET Framework 전체에서 스트림과 호환성.</span><span class="sxs-lookup"><span data-stu-id="da02b-107">Compatibility with streams across the .NET Framework.</span></span> <span data-ttu-id="da02b-108">스트림은 처리를 위한 풍부한 인프라가 있는 .NET Framework 전체에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-108">Streams are used throughout the .NET Framework, which has a rich infrastructure for handling them.</span></span> <span data-ttu-id="da02b-109">예를 들어 스트림을 초기화하는 코드 몇 줄만 변경하여 <xref:System.IO.FileStream>에서 XML 데이터를 읽는 응용 프로그램을 <xref:System.Net.Sockets.NetworkStream>에서 데이터를 읽도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-109">For example, you can modify an application that reads XML data from a <xref:System.IO.FileStream> to read data from a <xref:System.Net.Sockets.NetworkStream> instead by changing only the few lines of code that initialize the stream.</span></span> <span data-ttu-id="da02b-110">**NetworkStream** 클래스와 다른 스트림 간의 주요 차이점은 **NetworkStream**은 검색할 수 없고, <xref:System.Net.Sockets.NetworkStream.CanSeek%2A> 속성은 항상 **false**를 반환하고, <xref:System.Net.Sockets.NetworkStream.Seek%2A> 및 <xref:System.Net.Sockets.NetworkStream.Position%2A> 메서드는 <xref:System.NotSupportedException>을 throw한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-110">The major differences between the **NetworkStream** class and other streams are that **NetworkStream** is not seekable, the <xref:System.Net.Sockets.NetworkStream.CanSeek%2A> property always returns **false**, and the <xref:System.Net.Sockets.NetworkStream.Seek%2A> and <xref:System.Net.Sockets.NetworkStream.Position%2A> methods throw a <xref:System.NotSupportedException>.</span></span>  
  
-   <span data-ttu-id="da02b-111">데이터 도착 시 처리.</span><span class="sxs-lookup"><span data-stu-id="da02b-111">Processing of data as it arrives.</span></span> <span data-ttu-id="da02b-112">스트림은 전체 데이터 집합이 다운로드될 때까지 응용 프로그램을 강제로 대기시키는 대신 네트워크에서 도착하는 대로 데이터에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-112">Streams provide access to data as it arrives from the network, rather than forcing your application to wait for an entire data set to be downloaded.</span></span>  
  
 <span data-ttu-id="da02b-113"><xref:System.Net.Sockets> 네임스페이스에는 네트워크 리소스에 사용할 수 있도록 특별히 고안된 <xref:System.IO.Stream> 클래스를 구현하는 **NetworkStream** 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-113">The <xref:System.Net.Sockets> namespace contains a **NetworkStream** class that implements the <xref:System.IO.Stream> class specifically for use with network resources.</span></span> <span data-ttu-id="da02b-114"><xref:System.Net.Sockets> 네임스페이스에 있는 클래스는 **NetworkStream** 클래스를 사용하여 스트림을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-114">Classes in the <xref:System.Net.Sockets> namespace use the **NetworkStream** class to represent streams.</span></span>  
  
 <span data-ttu-id="da02b-115">반환된 스트림을 사용하여 데이터를 네트워크에 보내려면 <xref:System.Net.WebRequest>에서 <xref:System.Net.WebRequest.GetRequestStream%2A>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-115">To send data to the network using the returned stream, call <xref:System.Net.WebRequest.GetRequestStream%2A> on your <xref:System.Net.WebRequest>.</span></span> <span data-ttu-id="da02b-116">**WebRequest**는 요청 헤더를 서버에 보냅니다. 그러면 반환된 스트림에서 <xref:System.IO.Stream.BeginWrite%2A>, <xref:System.IO.Stream.EndWrite%2A> 또는 <xref:System.IO.Stream.Write%2A> 메서드를 호출하여 데이터를 네트워크 리소스에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-116">The **WebRequest** will send request headers to the server; then you can send data to the network resource by calling the <xref:System.IO.Stream.BeginWrite%2A>, <xref:System.IO.Stream.EndWrite%2A>, or <xref:System.IO.Stream.Write%2A> method on the returned stream.</span></span> <span data-ttu-id="da02b-117">HTTP와 같은 일부 프로토콜의 경우 데이터를 보내기 전에 프로토콜 관련 속성을 설정해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-117">Some protocols, such as HTTP, may require you to set protocol-specific properties before sending data.</span></span> <span data-ttu-id="da02b-118">다음 코드 예제에서는 데이터 전송을 위한 HTTP 관련 속성을 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-118">The following code example shows how to set HTTP-specific properties for sending data.</span></span> <span data-ttu-id="da02b-119">`sendData` 변수에 보낼 데이터가 들어 있고 `sendLength` 변수는 보낼 데이터의 바이트 수라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-119">It assumes that the variable `sendData` contains the data to send and that the variable `sendLength` is the number of bytes of data to send.</span></span>  
  
```csharp  
HttpWebRequest request =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
request.Method = "POST";  
request.ContentLength = sendLength;  
try  
{  
   Stream sendStream = request.GetRequestStream();  
   sendStream.Write(sendData,0,sendLength);  
   sendStream.Close();  
}  
catch  
{  
   // Handle errors . . .  
}  
```  
  
```vb  
Dim request As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
request.Method = "POST"  
request.ContentLength = sendLength  
Try  
   Dim sendStream As Stream = request.GetRequestStream()  
   sendStream.Write(sendData, 0, sendLength)  
   sendStream.Close()  
Catch  
   ' Handle errors . . .  
End Try  
```  
  
 <span data-ttu-id="da02b-120">네트워크에서 데이터를 수신하려면 <xref:System.Net.WebResponse>에서 <xref:System.Net.WebResponse.GetResponseStream%2A>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-120">To receive data from the network, call <xref:System.Net.WebResponse.GetResponseStream%2A> on your <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="da02b-121">반환된 스트림에서 <xref:System.IO.Stream.BeginRead%2A>, <xref:System.IO.Stream.EndRead%2A> 또는 <xref:System.IO.Stream.Read%2A> 메서드를 호출하여 네트워크 리소스에서 데이터를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-121">You can then read data from the network resource by calling the <xref:System.IO.Stream.BeginRead%2A>, <xref:System.IO.Stream.EndRead%2A>, or <xref:System.IO.Stream.Read%2A> method on the returned stream.</span></span>  
  
 <span data-ttu-id="da02b-122">네트워크 리소스의 스트림을 사용하는 경우 다음 사항에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="da02b-122">When using streams from network resources, keep in mind the following points:</span></span>  
  
-   <span data-ttu-id="da02b-123">**NetworkStream** 클래스가 스트림 내의 위치를 변경할 수 없기 때문에 **CanSeek** 속성은 항상 **false**를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-123">The **CanSeek** property always returns **false** since the **NetworkStream** class cannot change position in the stream.</span></span> <span data-ttu-id="da02b-124">**Seek** 및 **Position** 메서드는 **NotSupportedException**을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-124">The **Seek** and **Position** methods throw a **NotSupportedException**.</span></span>  
  
-   <span data-ttu-id="da02b-125">**WebRequest** 및 **WebResponse**를 사용하는 경우 **GetResponseStream**을 호출하여 만든 스트림 인스턴스는 읽기 전용이고 **GetRequestStream**을 호출하여 만든 스트림 인스턴스는 쓰기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-125">When you use **WebRequest** and **WebResponse**, stream instances created by calling **GetResponseStream** are read-only and stream instances created by calling **GetRequestStream** are write-only.</span></span>  
  
-   <span data-ttu-id="da02b-126"><xref:System.IO.StreamReader> 클래스를 사용하여 인코딩을 용이하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-126">Use the <xref:System.IO.StreamReader> class to make encoding easier.</span></span> <span data-ttu-id="da02b-127">다음 코드 예제에서는 **StreamReader**를 사용하여 **WebResponse**에서 ASCII로 인코드된 스트림을 읽습니다(예제에는 요청을 만드는 방법이 포함되지 않음).</span><span class="sxs-lookup"><span data-stu-id="da02b-127">The following code example uses a **StreamReader** to read an ASCII-encoded stream from a **WebResponse** (the example does not show creating the request).</span></span>  
  
-   <span data-ttu-id="da02b-128">네트워크 리소스를 사용할 수 없는 경우 **GetResponse** 호출이 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-128">The call to **GetResponse** can block if network resources are not available.</span></span> <span data-ttu-id="da02b-129"><xref:System.Net.WebRequest.BeginGetResponse%2A> 및 <xref:System.Net.WebRequest.EndGetResponse%2A> 메서드와 함께 비동기 요청을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-129">You should consider using an asynchronous request with the <xref:System.Net.WebRequest.BeginGetResponse%2A> and <xref:System.Net.WebRequest.EndGetResponse%2A> methods.</span></span>  
  
-   <span data-ttu-id="da02b-130">서버에 연결하는 동안 **GetRequestStream** 호출이 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-130">The call to **GetRequestStream** can block while the connection to the server is created.</span></span> <span data-ttu-id="da02b-131"><xref:System.Net.WebRequest.BeginGetRequestStream%2A> 및 <xref:System.Net.WebRequest.EndGetRequestStream%2A> 메서드와 함께 스트림에 대한 비동기 요청을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="da02b-131">You should consider using an asynchronous request for the stream with the <xref:System.Net.WebRequest.BeginGetRequestStream%2A> and <xref:System.Net.WebRequest.EndGetRequestStream%2A> methods.</span></span>  
  
```csharp  
// Create a response object.  
WebResponse response = request.GetResponse();  
// Get a readable stream from the server.  
StreamReader sr =   
   new StreamReader(response.GetResponseStream(), Encoding.ASCII);  
// Use the stream. Remember when you are through with the stream to close it.  
sr.Close();  
```  
  
```vb  
' Create a response object.  
Dim response As WebResponse = request.GetResponse()  
' Get a readable stream from the server.  
Dim sr As _   
   New StreamReader(response.GetResponseStream(), Encoding.ASCII)  
' Use the stream. Remember when you are through with the stream to close it.  
sr.Close()  
```  
  
## <a name="see-also"></a><span data-ttu-id="da02b-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da02b-132">See Also</span></span>  
 [<span data-ttu-id="da02b-133">방법: WebRequest 클래스를 사용하여 데이터 요청</span><span class="sxs-lookup"><span data-stu-id="da02b-133">How to: Request Data Using the WebRequest Class</span></span>](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)  
 [<span data-ttu-id="da02b-134">데이터 요청</span><span class="sxs-lookup"><span data-stu-id="da02b-134">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
