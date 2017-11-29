---
title: HttpListener
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ca0a22ff1d06485658da75a46bd408a12a3a964c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="httplistener"></a><span data-ttu-id="448cc-102">HttpListener</span><span class="sxs-lookup"><span data-stu-id="448cc-102">HttpListener</span></span>
<span data-ttu-id="448cc-103"><xref:System.Net.HttpListener> 클래스는 프로그래밍 방식으로 제어되는 HTTP 프로토콜 수신기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-103">The <xref:System.Net.HttpListener> class provides a programmatically controlled HTTP protocol listener.</span></span> <span data-ttu-id="448cc-104">수신기는 <xref:System.Net.HttpListener> 개체의 수명 동안 활성화되며 응용 프로그램 내에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-104">The listener is active for the lifetime of the <xref:System.Net.HttpListener> object and runs within your application.</span></span>  
  
## <a name="httpsys"></a><span data-ttu-id="448cc-105">HTTP.SYS</span><span class="sxs-lookup"><span data-stu-id="448cc-105">HTTP.SYS</span></span>  
 <span data-ttu-id="448cc-106"><xref:System.Net.HttpListener> 클래스는 Windows에 대한 모든 HTTP 트래픽을 처리하는 커널 모드 수신기인 HTTP.sys를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-106">The <xref:System.Net.HttpListener> class is built on top of HTTP.sys, which is the kernel mode listener that handles all HTTP traffic for Windows.</span></span> <span data-ttu-id="448cc-107">HTTP.sys는 연결 관리, 대역폭 제한 및 웹 서버 로깅 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-107">HTTP.sys provides connection management, bandwidth throttling, and Web server logging.</span></span> <span data-ttu-id="448cc-108">`HttpCfg.exe` 도구를 사용하여 SSL 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-108">Use the `HttpCfg.exe` tool to add SSL certificates.</span></span> <span data-ttu-id="448cc-109">자세한 내용은 [서버](http://go.microsoft.com/fwlink/?LinkID=178285) 설명서의 [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) 도구에 대한 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="448cc-109">For more information, see the documentation on the [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) tool in the [Server](http://go.microsoft.com/fwlink/?LinkID=178285) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="448cc-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="448cc-110">See Also</span></span>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [<span data-ttu-id="448cc-111">HTTP 서버</span><span class="sxs-lookup"><span data-stu-id="448cc-111">HTTP Server</span></span>](http://go.microsoft.com/fwlink/?LinkID=178285)  
 [<span data-ttu-id="448cc-112">인터넷 정보에서 향상 된 보안 기능</span><span class="sxs-lookup"><span data-stu-id="448cc-112">Security Enhancements in Internet Information</span></span>](http://go.microsoft.com/fwlink/?LinkID=178286)  
 [<span data-ttu-id="448cc-113">HttpListener ASPX 호스트 응용 프로그램 샘플</span><span class="sxs-lookup"><span data-stu-id="448cc-113">HttpListener ASPX Host Application Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179560)  
 [<span data-ttu-id="448cc-114">HttpListener 기술 샘플</span><span class="sxs-lookup"><span data-stu-id="448cc-114">HttpListener Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179558)  
 [<span data-ttu-id="448cc-115">네트워크 프로그래밍 샘플</span><span class="sxs-lookup"><span data-stu-id="448cc-115">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)
