---
title: "종단 간 추적 시나리오"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f83b7d53-6061-4362-a9a3-ee1daf6542be
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d37f752e0a36835f91e01b7c092b654eeba2b8ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="end-to-end-tracing-scenarios"></a><span data-ttu-id="c666a-102">종단 간 추적 시나리오</span><span class="sxs-lookup"><span data-stu-id="c666a-102">End-To-End Tracing Scenarios</span></span>
<span data-ttu-id="c666a-103">이 단원에는 추적에 사용하는 다양한 시나리오를 설명하는 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c666a-103">This section contains topics that describe different scenarios for using tracing.</span></span>  
  
 <span data-ttu-id="c666a-104">다음을 사용하여 회신/응답, 단방향 및 이중 시나리오에 대한 활동 추적을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c666a-104">Activity Tracing is implemented for Reply/Response, OneWay and Duplex scenarios using the following</span></span>  
  
-   <span data-ttu-id="c666a-105">동기 또는 비동기</span><span class="sxs-lookup"><span data-stu-id="c666a-105">Synchronous or Asynchronous</span></span>  
  
-   <span data-ttu-id="c666a-106">BasicHttpBinding, netNamedPipeBinding, netTcpBinding, wsHttpBinding 또는 netMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="c666a-106">BasicHttpBinding, netNamedPipeBinding, netTcpBinding, wsHttpBinding or netMsmqBinding</span></span>  
  
-   <span data-ttu-id="c666a-107">COM 서비스</span><span class="sxs-lookup"><span data-stu-id="c666a-107">COM Service</span></span>  
  
-   <span data-ttu-id="c666a-108">사용자 활동 ID 전파</span><span class="sxs-lookup"><span data-stu-id="c666a-108">User activity id propagation</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c666a-109">단원 내용</span><span class="sxs-lookup"><span data-stu-id="c666a-109">In This Section</span></span>  
  
-   [<span data-ttu-id="c666a-110">작업 목록</span><span class="sxs-lookup"><span data-stu-id="c666a-110">Activity List</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/activity-list.md)  
  
-   [<span data-ttu-id="c666a-111">동작 ID 전파</span><span class="sxs-lookup"><span data-stu-id="c666a-111">Activity ID Propagation</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/activity-id-propagation.md)  
  
-   [<span data-ttu-id="c666a-112">HTTP, TCP 또는 명명 된 파이프를 사용 하는 동기 시나리오</span><span class="sxs-lookup"><span data-stu-id="c666a-112">Synchronous Scenarios using HTTP, TCP or Named-Pipe</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/synchronous-scenarios-using-http-tcp-or-named-pipe.md)  
  
-   [<span data-ttu-id="c666a-113">HTTP, TCP 또는 명명 된 파이프를 사용 하는 비동기 시나리오</span><span class="sxs-lookup"><span data-stu-id="c666a-113">Asynchronous Scenarios using HTTP, TCP, or Named-Pipe</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/asynchronous-scenarios-using-http-tcp-or-named-pipe.md)  
  
-   [<span data-ttu-id="c666a-114">메시지 보안의 동작 추적</span><span class="sxs-lookup"><span data-stu-id="c666a-114">Activity Tracing in Message Security</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/activity-tracing-in-message-security.md)  
  
-   [<span data-ttu-id="c666a-115">MSMQ</span><span class="sxs-lookup"><span data-stu-id="c666a-115">MSMQ</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/msmq.md)  
  
-   [<span data-ttu-id="c666a-116">COM +</span><span class="sxs-lookup"><span data-stu-id="c666a-116">COM+</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/com.md)  
  
## <a name="see-also"></a><span data-ttu-id="c666a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c666a-117">See Also</span></span>  
 [<span data-ttu-id="c666a-118">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="c666a-118">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="c666a-119">종단 간 추적</span><span class="sxs-lookup"><span data-stu-id="c666a-119">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
