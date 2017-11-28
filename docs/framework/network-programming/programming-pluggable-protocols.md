---
title: "플러그형 프로토콜 프로그래밍"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- downloading Internet resources, pluggable protocols
- WebRequest class, pluggable protocols
- response to Internet request, pluggable protocols
- WebResponse class, pluggable protocols
- sending data, pluggable protocols
- network resources, pluggable protocols
- Internet, pluggable protocols
- programming pluggable protocols
- pluggable protocols, programming
- requesting data from Internet, pluggable protocols
- receiving data, pluggable protocols
- protocols, pluggable
ms.assetid: 66ef8456-7576-4e97-8956-959b216373db
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 51d9b6e444cfa49bfbf7854ee7f33f5a45d80e31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="programming-pluggable-protocols"></a><span data-ttu-id="d8e84-102">플러그형 프로토콜 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="d8e84-102">Programming Pluggable Protocols</span></span>
<span data-ttu-id="d8e84-103">추상 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 클래스에서 플러그형 프로토콜의 기초를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d8e84-103">The abstract <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide the base for pluggable protocols.</span></span> <span data-ttu-id="d8e84-104"><xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse>에서 프로토콜별 클래스를 파생시키면, 응용 프로그램에서 사용할 프로토콜을 지정하지 않아도 인터넷 리소스에서 데이터를 요청하고 응답을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8e84-104">By deriving protocol-specific classes from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>, an application can request data from an Internet resource and read the response without specifying the protocol being used.</span></span>  
  
 <span data-ttu-id="d8e84-105">Create 메서드를 등록해야 프로토콜별 <xref:System.Net.WebRequest>를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8e84-105">Before you can create a protocol-specific <xref:System.Net.WebRequest>, you must register its Create method.</span></span> <span data-ttu-id="d8e84-106">특정 인터넷 구성표, 구성표와 서버 또는 구성표, 서버 및 경로에 대한 요청 집합을 처리하려면 <xref:System.Net.WebRequest>의 정적 <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> 메서드를 사용하여 <xref:System.Net.WebRequest> 하위 항목을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d8e84-106">Use the static <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> method of <xref:System.Net.WebRequest> to register a <xref:System.Net.WebRequest> descendant to handle a set of requests to a particular Internet scheme, to a scheme and server, or to a scheme, server, and path.</span></span>  
  
 <span data-ttu-id="d8e84-107">대부분의 경우 <xref:System.Net.WebRequest> 클래스의 속성과 메서드를 사용하여 데이터를 보내고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8e84-107">In most cases you will be able to send and receive data using the methods and properties of the <xref:System.Net.WebRequest> class.</span></span> <span data-ttu-id="d8e84-108">그러나 프로토콜별 속성에 액세스해야 하는 경우 <xref:System.Net.WebRequest>를 특정 파생 클래스 인스턴스로 형식 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8e84-108">However, if you need to access protocol-specific properties, you can typecast a <xref:System.Net.WebRequest> to a specific derived-class instance.</span></span>  
  
 <span data-ttu-id="d8e84-109">플러그형 프로토콜을 이용하려면 <xref:System.Net.WebRequest> 하위 항목에서 프로토콜별 속성을 설정하지 않아도 되는 기본 요청 및 응답 트랜잭션을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8e84-109">To take advantage of pluggable protocols, your <xref:System.Net.WebRequest> descendants must provide a default request-and-response transaction that does not require protocol-specific properties to be set.</span></span> <span data-ttu-id="d8e84-110">예를 들어 HTTP의 <xref:System.Net.WebRequest> 클래스를 구현하는 <xref:System.Net.HttpWebRequest> 클래스에서 기본적으로 `GET` 요청을 제공하고 웹 서버에서 반환된 스트림을 포함하는 <xref:System.Net.HttpWebResponse>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8e84-110">For example, the <xref:System.Net.HttpWebRequest> class, which implements the <xref:System.Net.WebRequest> class for HTTP, provides a `GET` request by default and returns an <xref:System.Net.HttpWebResponse> that contains the stream returned from the Web server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8e84-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8e84-111">See Also</span></span>  
 [<span data-ttu-id="d8e84-112">WebRequest에서 파생</span><span class="sxs-lookup"><span data-stu-id="d8e84-112">Deriving from WebRequest</span></span>](../../../docs/framework/network-programming/deriving-from-webrequest.md)  
 [<span data-ttu-id="d8e84-113">WebResponse에서 파생</span><span class="sxs-lookup"><span data-stu-id="d8e84-113">Deriving from WebResponse</span></span>](../../../docs/framework/network-programming/deriving-from-webresponse.md)  
 [<span data-ttu-id="d8e84-114">.NET Framework의 네트워크 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="d8e84-114">Network Programming in the .NET Framework</span></span>](../../../docs/framework/network-programming/index.md)  
 [<span data-ttu-id="d8e84-115">방법: 프로토콜 관련 속성에 액세스하기 위해 WebRequest 형식 캐스팅</span><span class="sxs-lookup"><span data-stu-id="d8e84-115">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>](../../../docs/framework/network-programming/how-to-typecast-a-webrequest-to-access-protocol-specific-properties.md)
