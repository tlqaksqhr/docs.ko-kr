---
title: ETW를 사용한 분석 추적
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: 210418b8a8765a1fc59658e9df57c92ce087c95f
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="bcc91-102">ETW를 사용한 분석 추적</span><span class="sxs-lookup"><span data-stu-id="bcc91-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="bcc91-103">Windows Communication Foundation (WCF) 분석 추적에서는 WCF 서비스를 실행 하는 동안 진단 정보를 캡처하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc91-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="bcc91-104">프로덕션 환경에서 WCF 서비스의 문제 해결을 허용 하기 위해 WCF 스택의 주요 시점 WCF 분석 추적 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bcc91-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="bcc91-105">WCF 서비스에 대 한 분석 추적의 영향이 최소화는 프로덕션 서버의 성능에 호스팅하는 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] 매우 효율적으로 내보내지므로 이벤트 추적에 대 한 ETW (Windows) 세션에 따라 WCF 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc91-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bcc91-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="bcc91-106">In This Section</span></span>  
 [<span data-ttu-id="bcc91-107">분석 추적 개요</span><span class="sxs-lookup"><span data-stu-id="bcc91-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="bcc91-108">WCF 분석 추적에서 작동 하는 방법을 설명 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc91-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="bcc91-109">동적으로 분석 추적을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="bcc91-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="bcc91-110">ETW를 사용하여 추적을 동적으로 사용하거나 사용하지 않도록 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc91-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="bcc91-111">메시지 흐름 추적 구성</span><span class="sxs-lookup"><span data-stu-id="bcc91-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="bcc91-112">메시지 흐름 추적을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc91-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="bcc91-113">분석 추적 이벤트 참조</span><span class="sxs-lookup"><span data-stu-id="bcc91-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="bcc91-114">이벤트 ID와 함께 해당 이벤트 수준, 이벤트 메시지 및 키워드가 포함된 표를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bcc91-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcc91-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcc91-115">See Also</span></span>  
 [<span data-ttu-id="bcc91-116">WCF 서비스 및 Windows용 이벤트 추적</span><span class="sxs-lookup"><span data-stu-id="bcc91-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [<span data-ttu-id="bcc91-117">Windows에서 이벤트 추적으로 이벤트 추적</span><span class="sxs-lookup"><span data-stu-id="bcc91-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
