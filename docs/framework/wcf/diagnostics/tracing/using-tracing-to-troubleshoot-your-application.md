---
title: "추적을 사용하여 응용 프로그램 문제 해결"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7676b9bb-cbd1-41fd-9a93-cc615af6e2d0
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c04817d5a13c85f739f17fe25dd3c48ec9941a79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-tracing-to-troubleshoot-your-application"></a><span data-ttu-id="e0ecb-102">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e0ecb-102">Using Tracing to Troubleshoot Your Application</span></span>
<span data-ttu-id="e0ecb-103">이 단원에는 추적을 사용하여 응용 프로그램 문제를 해결할 수 있는 방법에 대해 설명하는 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0ecb-103">This section contains various topics that describe how you can use tracing to troubleshoot your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e0ecb-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="e0ecb-104">In This Section</span></span>  
 [<span data-ttu-id="e0ecb-105">추적 및 메시지 로깅에 대 한 권장된 설정</span><span class="sxs-lookup"><span data-stu-id="e0ecb-105">Recommended Settings for Tracing and Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/recommended-settings-for-tracing-and-message-logging.md)  
 <span data-ttu-id="e0ecb-106">프로덕션 환경 및 디버깅 환경의 제안된 설정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e0ecb-106">Describes suggested settings for production and debugging environments.</span></span>  
  
 [<span data-ttu-id="e0ecb-107">Service Trace Viewer를 사용하여 상호 관련된 추적 보기 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e0ecb-107">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 <span data-ttu-id="e0ecb-108">Service Trace Viewer 도구를 사용하여 추적 데이터를 보고, 상호 연결하고 분석하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e0ecb-108">Describes how you can use the Service Trace Viewer tool to view, correlate and analyze trace data.</span></span>  
  
 [<span data-ttu-id="e0ecb-109">중요 한 추적</span><span class="sxs-lookup"><span data-stu-id="e0ecb-109">Significant Traces</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/significant-traces.md)  
 <span data-ttu-id="e0ecb-110">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서 내보낸 주요 추적을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="e0ecb-110">A list of major traces emitted by [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="e0ecb-111">클라이언트에서의 디버깅</span><span class="sxs-lookup"><span data-stu-id="e0ecb-111">Debugging on the Client</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/debugging-on-the-client.md)  
 <span data-ttu-id="e0ecb-112">클라이언트가 응용 프로그램을 디버깅할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0ecb-112">Enables clients to debug your application.</span></span>  
  
 [<span data-ttu-id="e0ecb-113">종단 간 추적 시나리오</span><span class="sxs-lookup"><span data-stu-id="e0ecb-113">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 <span data-ttu-id="e0ecb-114">동기 wsHttp 요청-회신, 비동기 TCP 단방향 요청 등의 E2E [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 시나리오에 사용하는 추적에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e0ecb-114">Describes traces used for E2E [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] scenarios, for example, synchronous wsHttp request-replies, and asynchronous TCP one-way requests.</span></span>  
  
 [<span data-ttu-id="e0ecb-115">사용자 코드 추적 내보내기</span><span class="sxs-lookup"><span data-stu-id="e0ecb-115">Emitting User-Code Traces</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md)  
 <span data-ttu-id="e0ecb-116">사용자 코드에서 프로그래밍 방식으로 추적을 내보내는 방법에 대해 설명합니다. 이 방법을 통해 나중에 진단을 위해 사용하거나 WCF 추적과 상호 연결하여 사용할 계측 데이터를 사전에 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0ecb-116">Describes how to emit traces programmatically in user code, so that you can proactively create instrumentation data to be used later for diagnostic purpose, and in correlation with WCF traces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ecb-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0ecb-117">See Also</span></span>  
 [<span data-ttu-id="e0ecb-118">Service Trace Viewer 도구(SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="e0ecb-118">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [<span data-ttu-id="e0ecb-119">추적</span><span class="sxs-lookup"><span data-stu-id="e0ecb-119">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="e0ecb-120">종단 간 추적</span><span class="sxs-lookup"><span data-stu-id="e0ecb-120">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
