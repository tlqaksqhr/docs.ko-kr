---
title: "전송"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfcfa36c-d3bb-44b4-aa15-1c922c6f73e6
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 83bb76cc46d72f3d368de20669391c3e7f24a0f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="transfer"></a><span data-ttu-id="735c1-102">전송</span><span class="sxs-lookup"><span data-stu-id="735c1-102">Transfer</span></span>
<span data-ttu-id="735c1-103">이 항목에서는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 동작 추적 모델의 전송에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-103">This topic describes transfer in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] activity tracing model.</span></span>  
  
## <a name="transfer-definition"></a><span data-ttu-id="735c1-104">전송 정의</span><span class="sxs-lookup"><span data-stu-id="735c1-104">Transfer Definition</span></span>  
 <span data-ttu-id="735c1-105">동작 간 전송은 끝점 내의 관련 동작에 있는 이벤트 간의 인과 관계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-105">Transfers between activities represent causal relationships between events in the related activities within endpoints.</span></span> <span data-ttu-id="735c1-106">두 가지 동작은 컨트롤이 이러한 동작 간에 이동할 때(예: 동작 경계를 넘나드는 메서드 호출) 전송과 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-106">Two activities are related with transfers when control flows between these activities, for example, a method call crossing activity boundaries.</span></span> <span data-ttu-id="735c1-107">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서는 서비스에서 바이트가 들어올 때 수신 대기 동작이 메시지 개체가 만들어지는 바이트 수신 동작으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-107">In [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], when bytes are incoming on the service, the Listen At activity is transferred to the Receive Bytes activity where the message object is created.</span></span> <span data-ttu-id="735c1-108">종단 간 추적 시나리오 및의 해당 활동 및 추적 디자인의 목록에 대 한 참조 [종단 간 추적 시나리오](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-108">For a list of end-to-end tracing scenarios, and their respective activity and tracing design, see [End-To-End Tracing Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md).</span></span>  
  
 <span data-ttu-id="735c1-109">Transfer 추적을 내보내려면 다음 구성 코드와 같이 추적 소스에 `ActivityTracing` 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-109">To emit transfer traces, use the `ActivityTracing` setting on the trace source as demonstrated by the following configuration code.</span></span>  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing">  
```  
  
## <a name="using-transfer-to-correlate-activities-within-endpoints"></a><span data-ttu-id="735c1-110">끝점 내에서 동작을 상호 연결하기 위해 전송 사용</span><span class="sxs-lookup"><span data-stu-id="735c1-110">Using Transfer to Correlate Activities Within Endpoints</span></span>  
 <span data-ttu-id="735c1-111">동작 및 전송은 사용자가 오류의 근본 원인을 찾도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-111">Activities and transfers permit the user to probabilistically locate the root cause of an error.</span></span> <span data-ttu-id="735c1-112">예를 들어 동작 M과 N 간에 각각 구성 요소 M과 N에서 전송을 주고 받을 때 M으로 전송을 되돌린 직후에 N에서 충돌이 발생하면 M으로 보내는 N의 전달 데이터로 인해 오류가 발생했다고 결론을 내릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-112">For example, if we transfer back and forth between activities M and N respectively in components M and N, and a crash happens in N right after the transfer back to M, we can draw the conclusion that it is likely due to N’s passing data back to M.</span></span>  
  
 <span data-ttu-id="735c1-113">M과 N 간에 컨트롤의 흐름이 있을 때 Transfer 추적이 동작 M으로부터 동작 N으로 내보내집니다. 예를 들어 동작의 경계를 넘나드는 메서드 호출로 인해 N은 M에 대한 일부 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-113">A transfer trace is emitted from activity M to activity N when there is a flow of control between M and N. For example, N performs some work for M because of a method call crossing the activities’ boundaries.</span></span> <span data-ttu-id="735c1-114">N이 이미 존재하거나 만들어졌을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-114">N may already exist or has been created.</span></span> <span data-ttu-id="735c1-115">N이 M에 대한 일부 작업을 수행하는 새 동작일 경우 N이 M에 의해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-115">N is spawned by M when N is a new activity that performs some work for M.</span></span>  
  
 <span data-ttu-id="735c1-116">M으로부터 N으로 전송되더라도 다시 N으로부터 M으로의 전송이 발생하지 않을 수도 있습니다. 이는 M이 N에서의 일부 작업을 생성할 수 있으며 N이 해당 작업을 완료할 때 추적하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-116">A transfer from M to N may not be followed by a transfer back from N to M. This is because M can spawn some work in N and do not track when N completes that work.</span></span> <span data-ttu-id="735c1-117">실제로, M은 N이 해당 작업을 완료하기 전에 종료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-117">In fact, M can terminate before N completes its task.</span></span> <span data-ttu-id="735c1-118">이 수신기 동작 (N)를 생성 하 고 다음을 종료 하는 "Open ServiceHost" 동작 (M)에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-118">This happens in the "Open ServiceHost" activity (M) that spawns Listener activities (N) and then terminates.</span></span> <span data-ttu-id="735c1-119">N에서 M으로 다시 전송한다는 것은 N이 M과 관련된 작업을 완료했음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-119">A transfer back from N to M means that N completed the work related to M.</span></span>  
  
 <span data-ttu-id="735c1-120">N은 M과 연관되지 않은 다른 처리(예: 여러 로그인 동작으로부터 로그인 요청(M) 수신을 유지하는 기존 인증자 동작(N))를 계속 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-120">N can continue performing other processing unrelated to M, for example, an existing authenticator activity (N) that keeps receiving login requests (M) from different login activities.</span></span>  
  
 <span data-ttu-id="735c1-121">동작 M과 N 사이에 반드시 중첩된 관계가 존재하는 것은 아닙니다. 이는 두 가지 이유 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-121">A nesting relationship does not necessarily exist between activities M and N. This can happen due to two reasons.</span></span> <span data-ttu-id="735c1-122">첫 번째 이유는 동작 M이 N을 시작했더라도 M이 N에서 수행되는 실제 처리를 모니터링하지 않았기 때문이며, 두 번째 이유는 N이 이미 존재하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-122">First, when activity M does not monitor the actual processing performed in N although M initiated N. Second, when N already exists.</span></span>  
  
## <a name="example-of-transfers"></a><span data-ttu-id="735c1-123">전송 예제</span><span class="sxs-lookup"><span data-stu-id="735c1-123">Example of Transfers</span></span>  
 <span data-ttu-id="735c1-124">다음은 두 가지 전송 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-124">The following lists two transfer examples.</span></span>  
  
-   <span data-ttu-id="735c1-125">서비스 호스트를 만들 때 생성자가 호출 코드로부터 컨트롤을 얻거나 호출 코드가 생성자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-125">When you create a service host, the constructor gains control from the calling code, or the calling code transfers to the constructor.</span></span> <span data-ttu-id="735c1-126">생성자는 실행을 마치면 컨트롤을 호출 코드로 반환하거나 호출 코드로 다시 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-126">When the constructor has finished executing, it returns control to the calling code, or the constructor transfers back to the calling code.</span></span> <span data-ttu-id="735c1-127">이는 중첩된 관계의 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-127">This is the case of a nested relationship.</span></span>  
  
-   <span data-ttu-id="735c1-128">수신기가 전송 데이터 처리를 시작하면 새 스레드를 만들고, 처리를 위해 적절한 컨텍스트를 바이트 수신 동작(예: 컨트롤 및 데이터 전달)으로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-128">When a listener starts processing transport data, it creates a new thread and hands to the Receive Bytes activity the appropriate context for processing, passing control and data.</span></span> <span data-ttu-id="735c1-129">스레드가 요청 처리를 완료하면 바이트 수신 동작은 수신기로 아무 것도 전달하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-129">When that thread has finished processing the request, the Receive Bytes activity passes nothing back to the listener.</span></span> <span data-ttu-id="735c1-130">이 경우 새 스레드 동작 내에는 전송이 있지만 외부에는 전송이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-130">In this case, we have a transfer in but no transfer out of the new thread activity.</span></span> <span data-ttu-id="735c1-131">두 개의 동작은 연관되지만 중첩되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-131">The two activities are related but not nested.</span></span>  
  
## <a name="activity-transfer-sequence"></a><span data-ttu-id="735c1-132">동작 전송 시퀀스</span><span class="sxs-lookup"><span data-stu-id="735c1-132">Activity Transfer Sequence</span></span>  
 <span data-ttu-id="735c1-133">올바른 형식의 동작 전송 시퀀스에는 다음 단계가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-133">A well-formed activity transfer sequence includes the following steps.</span></span>  
  
1.  <span data-ttu-id="735c1-134">새 gAId 선택으로 구성된 새 동작 시작</span><span class="sxs-lookup"><span data-stu-id="735c1-134">Begin a new activity, which consists of selecting a new gAId.</span></span>  
  
2.  <span data-ttu-id="735c1-135">현재 동작 ID로부터 새 gAId에 대한 Transfer 추적 내보내기</span><span class="sxs-lookup"><span data-stu-id="735c1-135">Emit a transfer trace to that new gAId from the current activity ID</span></span>  
  
3.  <span data-ttu-id="735c1-136">TLS에서 새 ID 설정</span><span class="sxs-lookup"><span data-stu-id="735c1-136">Set the new ID in TLS</span></span>  
  
4.  <span data-ttu-id="735c1-137">새 동작의 시작을 나타내기 위해 Start 추적 내보내기</span><span class="sxs-lookup"><span data-stu-id="735c1-137">Emit a start trace to indicate the beginning of the new activity by.</span></span>  
  
5.  <span data-ttu-id="735c1-138">원래 동작으로 돌아가기는 다음으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-138">Return to the original activity consists of the following:</span></span>  
  
6.  <span data-ttu-id="735c1-139">원래 gAId로 Transfer 추적 내보내기</span><span class="sxs-lookup"><span data-stu-id="735c1-139">Emit a transfer trace to the original gAId</span></span>  
  
7.  <span data-ttu-id="735c1-140">새 동작의 종료를 나타내기 위해 Stop 추적 내보내기</span><span class="sxs-lookup"><span data-stu-id="735c1-140">Emit a Stop trace to indicate the end of the new activity</span></span>  
  
8.  <span data-ttu-id="735c1-141">이전 gAId로 TLS 설정</span><span class="sxs-lookup"><span data-stu-id="735c1-141">Set TLS to the old gAId.</span></span>  
  
 <span data-ttu-id="735c1-142">다음 코드 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-142">The following code example demonstrates how to do this.</span></span> <span data-ttu-id="735c1-143">이 샘플은 차단 호출이 새 동작으로 전송 중일 때 만들어지며, Suspend/Resume 추적을 포함한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="735c1-143">This sample assumes a blocking call is made when transferring to the new activity, and includes suspend/resume traces.</span></span>  
  
```  
// 0. Create a trace source  
TraceSource ts = new TraceSource("myTS");  
// 1. remember existing ("ambient") activity for clean up  
Guid oldGuid = Trace.CorrelationManager.ActivityId;  
// this will be our new activity  
Guid newGuid = Guid.NewGuid();   
// 2. call transfer, indicating that we are switching to the new AID  
ts.TraceTransfer(667, "Transferring.", newGuid);  
// 3. Suspend the current activity.  
ts.TraceEvent(TraceEventType.Suspend, 667, "Suspend: Activity " + i-1);  
// 4. set the new AID in TLS  
Trace.CorrelationManager.ActivityId = newGuid;  
// 5. Emit the start trace  
ts.TraceEvent(TraceEventType.Start, 667, "Boundary: Activity " + i);  
// trace something  
ts.TraceEvent(TraceEventType.Information, 667, "Hello from activity " + i);  
// Perform Work  
// some work.  
// Return  
ts.TraceEvent(TraceEventType.Information, 667, "Work complete on activity " + i);   
// 6. Emit the transfer returning to the original activity  
ts.TraceTransfer(667, "Transferring Back.", oldGuid);  
// 7. Emit the End trace  
ts.TraceEvent(TraceEventType.Stop, 667, "Boundary: Activity " + i);  
// 8. Change the tls variable to the original AID  
Trace.CorrelationManager.ActivityId = oldGuid;    
// 9. Resume the old activity  
ts.TraceEvent(TraceEventType.Resume, 667, "Resume: Activity " + i-1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="735c1-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="735c1-144">See Also</span></span>  
 [<span data-ttu-id="735c1-145">추적 구성</span><span class="sxs-lookup"><span data-stu-id="735c1-145">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
 [<span data-ttu-id="735c1-146">Service Trace Viewer를 사용하여 상호 관련된 추적 보기 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="735c1-146">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [<span data-ttu-id="735c1-147">종단 간 추적 시나리오</span><span class="sxs-lookup"><span data-stu-id="735c1-147">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 [<span data-ttu-id="735c1-148">Service Trace Viewer 도구(SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="735c1-148">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
