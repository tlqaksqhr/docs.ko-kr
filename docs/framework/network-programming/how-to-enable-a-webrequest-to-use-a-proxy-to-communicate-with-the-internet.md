---
title: "방법: 프록시를 사용하여 인터넷과 통신하도록 WebRequest 설정"
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
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 68871505e735485dd73d219b4144d56eabe21e43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="7efff-102">방법: 프록시를 사용하여 인터넷과 통신하도록 WebRequest 설정</span><span class="sxs-lookup"><span data-stu-id="7efff-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>
<span data-ttu-id="7efff-103">이 예제에서는 인터넷과 통신하는 데 프록시를 사용하기 위해 <xref:System.Net.WebRequest>를 사용하도록 설정할 전역 프록시 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7efff-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="7efff-104">예제에서는 프록시 서버의 이름이 `webproxy`이고 표준 HTTP 포트인 포트 80에서 통신한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7efff-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7efff-105">예</span><span class="sxs-lookup"><span data-stu-id="7efff-105">Example</span></span>  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7efff-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7efff-106">Compiling the Code</span></span>  
 <span data-ttu-id="7efff-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7efff-107">This example requires:</span></span>  
  
-   <span data-ttu-id="7efff-108">**System.Net** 네임스페이스에 대한 참조.</span><span class="sxs-lookup"><span data-stu-id="7efff-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7efff-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7efff-109">See Also</span></span>  
 [<span data-ttu-id="7efff-110">응용 프로그램 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="7efff-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="7efff-111">프록시를 통해 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="7efff-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
