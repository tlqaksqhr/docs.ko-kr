---
title: "ETW를 사용한 분석 추적"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a16f66ed8443749764e66d2616ae566ad788d571
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="f705e-102">ETW를 사용한 분석 추적</span><span class="sxs-lookup"><span data-stu-id="f705e-102">Analytic Tracing with ETW</span></span>
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="f705e-103"> 분석 추적을 사용하면 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스를 실행하는 동안 진단 정보를 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f705e-103"> analytic tracing offers a way to capture diagnostic information during the execution of a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="f705e-104">프로덕션 환경에서 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스 문제를 해결할 수 있도록 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 스택의 주요 시점에[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 분석 추적 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f705e-104">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analytic tracing events are emitted at key points in the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] stack to allow troubleshooting of [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services in a production environment.</span></span> <span data-ttu-id="f705e-105">분석 추적은 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스에 미치는 영향을 최소화는 프로덕션 서버의 성능에 호스팅하는 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 매우 효율적으로 내보내지므로 이벤트 추적에 대 한 ETW (Windows) 세션에 따라 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="f705e-105">Analytic tracing for [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f705e-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f705e-106">In This Section</span></span>  
 [<span data-ttu-id="f705e-107">분석 추적 개요</span><span class="sxs-lookup"><span data-stu-id="f705e-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="f705e-108">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] 분석 추적을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f705e-108">Discusses how [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="f705e-109">동적으로 분석 추적을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="f705e-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="f705e-110">ETW를 사용하여 추적을 동적으로 사용하거나 사용하지 않도록 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f705e-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="f705e-111">메시지 흐름 추적 구성</span><span class="sxs-lookup"><span data-stu-id="f705e-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="f705e-112">메시지 흐름 추적을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f705e-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="f705e-113">분석 추적 이벤트 참조</span><span class="sxs-lookup"><span data-stu-id="f705e-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="f705e-114">이벤트 ID와 함께 해당 이벤트 수준, 이벤트 메시지 및 키워드가 포함된 표를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f705e-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f705e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f705e-115">See Also</span></span>  
 [<span data-ttu-id="f705e-116">WCF 서비스 및 Windows용 이벤트 추적</span><span class="sxs-lookup"><span data-stu-id="f705e-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [<span data-ttu-id="f705e-117">Windows에서 이벤트 추적으로 이벤트 추적</span><span class="sxs-lookup"><span data-stu-id="f705e-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
