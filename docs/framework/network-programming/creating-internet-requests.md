---
title: "인터넷 요청 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WebRequest class, sending and receiving data
- Networking
- HttpWebResponse class, sending and receiving data
- requesting data from Internet, creating requests
- Network Resources
- Internet, requesting data
- data requests, creating requests
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 52f1fc2601aca9b4d823d42ed961fcf007e5e5ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="creating-internet-requests"></a><span data-ttu-id="45745-102">인터넷 요청 만들기</span><span class="sxs-lookup"><span data-stu-id="45745-102">Creating Internet Requests</span></span>
<span data-ttu-id="45745-103">응용 프로그램은 <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> 메서드를 통해 <xref:System.Net.WebRequest> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45745-103">Applications create <xref:System.Net.WebRequest> instances through the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="45745-104">이것은 전달된 URI 구성표에 따라 **WebRequest**에서 파생된 클래스를 만드는 정적 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="45745-104">This is a static method that creates a class derived from **WebRequest** based on the URI scheme passed to it.</span></span>  
  
## <a name="web-file-and-ftp-requests"></a><span data-ttu-id="45745-105">웹, 파일 및 FTP 요청</span><span class="sxs-lookup"><span data-stu-id="45745-105">Web, File and FTP Requests</span></span>  
 <span data-ttu-id="45745-106">.NET Framework는 HTTP 및 HTTPS 요청을 처리하기 위해 **WebRequest**에서 파생된 <xref:System.Net.HttpWebRequest> 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="45745-106">The .NET Framework provides the <xref:System.Net.HttpWebRequest> class, which is derived from **WebRequest**, to handle HTTP and HTTPS requests.</span></span> <span data-ttu-id="45745-107">대부분의 경우 **WebRequest** 클래스는 요청을 만드는 데 필요한 모든 속성을 제공합니다. 그러나 필요한 경우 **WebRequest.Create** 메서드를 통해 생성된 **WebRequest** 개체를 **HttpWebRequest** 형식에 캐스팅하여 요청의 HTTP 관련 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45745-107">In most cases, the **WebRequest** class provides all the properties you need to make a request; however, if necessary, you can cast **WebRequest** objects created by the **WebRequest.Create** method to the **HttpWebRequest** type to access the HTTP-specific properties of the request.</span></span> <span data-ttu-id="45745-108">마찬가지로 **HttpWebResponse** 개체는 HTTP 및 HTTPS 요청의 응답을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="45745-108">Similarly, the **HttpWebResponse** object handles the responses from HTTP and HTTPS requests.</span></span> <span data-ttu-id="45745-109">**HttpWebResponse** 개체의 HTTP 관련 속성에 액세스하려면 **WebResponse** 개체를 **HttpWebResponse** 형식에 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45745-109">To access the HTTP-specific properties of the **HttpWebResponse** object, you need to cast **WebResponse** objects to the **HttpWebResponse** type.</span></span>  
  
 <span data-ttu-id="45745-110">.NET Framework는 “file:” URI 구성표를 사용하는 리소스에 대한 요청을 처리하기 위해 <xref:System.Net.FileWebRequest> 및 <xref:System.Net.FileWebResponse> 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="45745-110">The .NET Framework also provides the <xref:System.Net.FileWebRequest> and <xref:System.Net.FileWebResponse> classes to handle requests for resources that use the "file:" URI scheme.</span></span> <span data-ttu-id="45745-111">마찬가지로 “ftp:” 구성표를 사용하는 리소스에 대한 요청을 처리하기 위해 <xref:System.Net.FtpWebRequest> 및 <xref:System.Net.FtpWebResponse> 클래스가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="45745-111">Likewise, the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes are provided to handle requests for resources that use the "ftp:" scheme.</span></span> <span data-ttu-id="45745-112">이러한 구성표를 사용하는 리소스에 대한 요청인 경우 **WebRequest.Create** 메서드를 사용하여 요청 생성에 사용할 개체를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45745-112">If your request is for a resource that uses any of these schemes, you can use the **WebRequest.Create** method to obtain an object with which to make your request.</span></span>  
  
 <span data-ttu-id="45745-113">다른 응용 프로그램 수준 프로토콜을 사용하는 요청을 처리하기 위해 **WebRequest** 및 **WebResponse**에서 파생된 프로토콜별 클래스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45745-113">To handle requests that use other application-level protocols, you need to implement protocol-specific classes derived from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="45745-114">자세한 내용은 [플러그형 프로토콜 프로그래밍](../../../docs/framework/network-programming/programming-pluggable-protocols.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45745-114">For more information, see [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45745-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45745-115">See Also</span></span>  
 [<span data-ttu-id="45745-116">방법: WebRequest 클래스를 사용하여 데이터 요청</span><span class="sxs-lookup"><span data-stu-id="45745-116">How to: Request Data Using the WebRequest Class</span></span>](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)  
 [<span data-ttu-id="45745-117">데이터 요청</span><span class="sxs-lookup"><span data-stu-id="45745-117">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
