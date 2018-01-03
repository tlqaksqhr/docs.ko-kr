---
title: "데이터 요청"
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
- sending data
- WebRequest class, sending and receiving data
- requesting data from Internet, about requesting data
- WebClient class, sending and receiving data
- network, requesting data
- receiving data
- sending data, about sending data
- response to Internet request, about responding to Internet requests
- data requests
- receiving data, about receiving data
- Internet, requesting data
ms.assetid: df6f1e1d-6f2a-45dd-8141-4a85c3dafe1d
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 76ea605444b5d1776c5a85891db4f3460e9df24b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="requesting-data"></a><span data-ttu-id="17b8c-102">데이터 요청</span><span class="sxs-lookup"><span data-stu-id="17b8c-102">Requesting Data</span></span>
<span data-ttu-id="17b8c-103">현재 인터넷의 분산된 운영 환경에서 실행되는 응용 프로그램을 개발하려면 모든 형식의 리소스에서 데이터를 검색하기 위한 효율적이고 사용하기 쉬운 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-103">Developing applications that run in the distributed operating environment of today's Internet requires an efficient, easy-to-use method for retrieving data from resources of all types.</span></span> <span data-ttu-id="17b8c-104">플러그형 프로토콜을 사용하면 단일 인터페이스를 사용하여 여러 인터넷 프로토콜에서 데이터를 검색하는 응용 프로그램을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-104">Pluggable protocols let you develop applications that use a single interface to retrieve data from multiple Internet protocols.</span></span>  
  
## <a name="uploading-and-downloading-data-from-an-internet-server"></a><span data-ttu-id="17b8c-105">인터넷 서버에서 데이터를 다운로드 및 업로드</span><span class="sxs-lookup"><span data-stu-id="17b8c-105">Uploading and Downloading Data from an Internet Server</span></span>  
 <span data-ttu-id="17b8c-106">간단한 요청 및 응답 트랜잭션을 위해 <xref:System.Net.WebClient> 클래스에서는 인터넷에서 데이터를 다운로드하거나 업로드하는 가장 쉬운 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-106">For simple request and response transactions, the <xref:System.Net.WebClient> class provides the easiest method for uploading data to or downloading data from an Internet server.</span></span> <span data-ttu-id="17b8c-107">**WebClient**에서는 파일 업로드 및 다운로드, 스트림 전송 및 수신, 서버에 데이터 버퍼 전송 및 응답 수신하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-107">**WebClient** provides methods for uploading and downloading files, sending and receiving streams, and sending a data buffer to the server and receiving a response.</span></span> <span data-ttu-id="17b8c-108">**WebClient**에서는 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 클래스를 사용하여 인터넷 리소스에 실제로 연결하므로 등록된 플러그형 프로토콜을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-108">**WebClient** uses the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes to make the actual connections to the Internet resource, so any registered pluggable protocol is available for use.</span></span>  
  
 <span data-ttu-id="17b8c-109">더 복잡한 트랜잭션을 수행해야 하는 클라이언트 응용 프로그램에서는 **WebRequest** 클래스와 하위 항목을 사용하여 서버에서 데이터를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-109">Client applications that need to make more complex transactions request data from servers using the **WebRequest** class and its descendants.</span></span> <span data-ttu-id="17b8c-110">**WebRequest**를 통해 서버에 연결, 요청 전송 및 응답 수신에 관한 세부 정보를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-110">**WebRequest** encapsulates the details of connecting to the server, sending the request, and receiving the response.</span></span> <span data-ttu-id="17b8c-111">**WebRequest**는 플러그형 프로토콜을 사용하는 모든 응용 프로그램에서 사용할 수 있는 메서드와 속성 집합을 정의하는 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-111">**WebRequest** is an abstract class that defines a set of properties and methods that are available to all applications that use pluggable protocols.</span></span> <span data-ttu-id="17b8c-112">**WebRequest**의 하위 항목(예: <xref:System.Net.HttpWebRequest>)은 기본 프로토콜과 일치하는 방식으로 **WebRequest**를 통해 정의한 속성과 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-112">Descendants of **WebRequest**, such as <xref:System.Net.HttpWebRequest>, implement the properties and methods defined by **WebRequest** in a way that is consistent with the underlying protocol.</span></span>  
  
 <span data-ttu-id="17b8c-113">**WebRequest** 클래스에서는 만들 특정 파생 클래스 인스턴스를 판별하기 위해 <xref:System.Net.WebRequest.Create%2A> 메서드에 전달된 URI 값을 사용하여 **WebRequest** 하위 항목의 프로토콜별 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-113">The **WebRequest** class creates protocol-specific instances of **WebRequest** descendants, using the value of the URI passed to its <xref:System.Net.WebRequest.Create%2A> method to determine the specific derived-class instance to create.</span></span> <span data-ttu-id="17b8c-114">응용 프로그램에서 <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType> 메서드로 하위 항목의 생성자를 등록하여 요청을 처리하는 데 사용해야 하는 **WebRequest** 하위 항목을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-114">Applications indicate which **WebRequest** descendant should be used to handle a request by registering the descendant's constructor with the <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="17b8c-115">**WebRequest**에서 <xref:System.Net.WebRequest.GetResponse%2A> 메서드를 호출하여 인터넷 리소스를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-115">A request is made to the Internet resource by calling the <xref:System.Net.WebRequest.GetResponse%2A> method on the **WebRequest**.</span></span> <span data-ttu-id="17b8c-116">**GetResponse** 메서드를 통해 **WebRequest** 속성에서 프로토콜별 요청을 생성하고, TCP 또는 UDP 소켓으로 서버에 연결하며, 요청을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-116">The **GetResponse** method constructs the protocol-specific request from the properties of the **WebRequest**, makes the TCP or UDP socket connection to the server, and sends the request.</span></span> <span data-ttu-id="17b8c-117">HTTP **Post** 또는 FTP **Put** 요청과 같이 서버에 데이터를 전송하는 요청에서 <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=nameWithType> 메서드를 통해 데이터를 전송할 네트워크 스트림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-117">For requests that send data to the server, such as HTTP **Post** or FTP **Put** requests, the <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=nameWithType> method provides a network stream in which to send the data.</span></span>  
  
 <span data-ttu-id="17b8c-118">**GetResponse** 메서드에서는 **WebRequest**와 일치하는 프로토콜별 **WebResponse**를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-118">The **GetResponse** method returns a protocol-specific **WebResponse** that matches the **WebRequest.**</span></span>  
  
 <span data-ttu-id="17b8c-119">**WebResponse** 클래스도 플러그형 프로토콜을 사용하는 모든 응용 프로그램에서 사용할 수 있는 메서드와 속성을 정의하는 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-119">The **WebResponse** class is also an abstract class that defines properties and methods that are available to all applications that use pluggable protocols.</span></span> <span data-ttu-id="17b8c-120">**WebResponse** 후속 항목은 기본 프로토콜을 위해 이러한 속성과 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-120">**WebResponse** descendants implement these properties and methods for the underlying protocol.</span></span> <span data-ttu-id="17b8c-121">예를 들어 <xref:System.Net.HttpWebResponse> 클래스는 HTTP용 **WebResponse** 클래스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-121">The <xref:System.Net.HttpWebResponse> class, for example, implements the **WebResponse** class for HTTP.</span></span>  
  
 <span data-ttu-id="17b8c-122">서버에서 반환한 데이터는 <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> 메서드에서 반환한 스트림으로 응용 프로그램에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-122">The data returned by the server is presented to the application in the stream returned by the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="17b8c-123">다음 예제에 표시된 대로 다른 스트림과 마찬가지로 이 스트림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17b8c-123">You can use this stream like any other, as shown in the following example.</span></span>  
  
```csharp  
StreamReader sr =  
   new StreamReader(resp.GetResponseStream(), Encoding.ASCII);  
```  
  
```vb  
Dim sr As StreamReader  
sr = New StreamReader(resp.GetResponseStream(), Encoding.ASCII)  
```  
  
## <a name="see-also"></a><span data-ttu-id="17b8c-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17b8c-124">See Also</span></span>  
 [<span data-ttu-id="17b8c-125">.NET Framework의 네트워크 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="17b8c-125">Network Programming in the .NET Framework</span></span>](../../../docs/framework/network-programming/index.md)  
 [<span data-ttu-id="17b8c-126">방법: 웹 페이지 요청 및 결과를 스트림으로 검색</span><span class="sxs-lookup"><span data-stu-id="17b8c-126">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>](../../../docs/framework/network-programming/how-to-request-a-web-page-and-retrieve-the-results-as-a-stream.md)  
 [<span data-ttu-id="17b8c-127">방법: WebRequest와 일치하는 프로토콜 관련 WebResponse 검색</span><span class="sxs-lookup"><span data-stu-id="17b8c-127">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>](../../../docs/framework/network-programming/how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest.md)
