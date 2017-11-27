---
title: "진단 추적"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28e77a63-d20d-4b6a-9caf-ddad86550427
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 59e91b76245c7bdfd40f6fc449edbbcd47449f3f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="diagnostic-traces"></a><span data-ttu-id="54e46-102">진단 추적</span><span class="sxs-lookup"><span data-stu-id="54e46-102">Diagnostic Traces</span></span>
<span data-ttu-id="54e46-103">추적은 응용 프로그램 실행 중에 생성된 특정 메시지의 게시입니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-103">Traces are the publishing of specific messages that are generated during application execution.</span></span> <span data-ttu-id="54e46-104">추적을 사용하는 경우 전송된 메시지를 수집 및 기록하는 메커니즘이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-104">When using tracing, you must have a mechanism for collecting and recording the messages that are sent.</span></span> <span data-ttu-id="54e46-105">수신기가 추적 메시지를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-105">Trace messages are received by listeners.</span></span> <span data-ttu-id="54e46-106">수신기의 목적은 추적 메시지를 수집, 저장 및 라우팅하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-106">The purpose of a listener is to collect, store, and route tracing messages.</span></span> <span data-ttu-id="54e46-107">수신기는 추적 출력을 로그, 창 또는 텍스트 파일과 같은 적절한 대상에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-107">Listeners direct the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="54e46-108">추적을 사용하면 이러한 수신기 중 하나인 <xref:System.Diagnostics.DefaultTraceListener>가 자동으로 만들어지고 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-108">One such listener, the <xref:System.Diagnostics.DefaultTraceListener>, is automatically created and initialized when tracing is enabled.</span></span> <span data-ttu-id="54e46-109">추적 출력을 추가 소스에 보내려면 추가 추적 수신기를 만들고 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-109">If you want trace output to be directed to any additional sources, you must create and initialize additional trace listeners.</span></span> <span data-ttu-id="54e46-110">수신기를 만들 때는 개인이 필요로 하는 내용을 반영해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-110">The listeners you create should reflect your individual needs.</span></span> <span data-ttu-id="54e46-111">예를 들어, 모든 추적 출력의 텍스트 레코드를 필요로 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-111">For example, you might want a text record of all trace output.</span></span> <span data-ttu-id="54e46-112">이 경우에는 활성화되면 모든 출력을 새 텍스트 파일에 쓰는 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-112">In this case, you would create a listener that wrote all output to a new text file when enabled.</span></span> <span data-ttu-id="54e46-113">반면에 응용 프로그램이 실행되는 동안 출력을 보기만 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-113">On the other hand, you might only want to view output during application execution.</span></span> <span data-ttu-id="54e46-114">이 경우에는 모든 출력을 콘솔 창으로 보내는 수신기를 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-114">In that case, you might create a listener that directed all output to a console window.</span></span> <span data-ttu-id="54e46-115"><xref:System.Diagnostics.EventLogTraceListener>는 추적 출력을 이벤트 로그로 보낼 수 있고 <xref:System.Diagnostics.TextWriterTraceListener>는 추적 출력을 스트림에 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-115">The <xref:System.Diagnostics.EventLogTraceListener> can direct trace output to an event log, and the <xref:System.Diagnostics.TextWriterTraceListener> can write trace output to a stream.</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="54e46-116">추적 사용</span><span class="sxs-lookup"><span data-stu-id="54e46-116">Enabling Tracing</span></span>  
 <span data-ttu-id="54e46-117">트랜잭션 처리 중에 추적을 사용하려면 응용 프로그램의 구성 파일을 편집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-117">To enable traces during transaction processing, you should edit your application’s configuration file.</span></span> <span data-ttu-id="54e46-118">다음은 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-118">The following is an example.</span></span>  
  
```xml  
<configuration>  
<system.diagnostics>  
     <sources>  
          <source name="System.Transactions" switchValue="Warning">  
               <listeners>  
                    <add name="tx"   
                     type="System.Diagnostics.XmlWriterTraceListener"   
                     initializeData= "tx.log" />  
               </listeners>  
          </source>  
     </sources>  
</system.diagnostics>  
</configuration>  
```  
  
 <span data-ttu-id="54e46-119"><xref:System.Transactions> 추적은 "System.Transactions"라는 소스에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-119"><xref:System.Transactions> traces are written to the source named "System.Transactions".</span></span> <span data-ttu-id="54e46-120">`add`를 사용하여 사용할 추적 수신기의 이름과 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-120">You can use `add` to specify the name and type of the trace listener you want to use.</span></span> <span data-ttu-id="54e46-121">예제 구성에서는 수신기 이름을 "tx"로 지정하고 표준 .NET Framework 추적 수신기(<xref:System.Diagnostics.XmlWriterTraceListener>)를 사용할 형식으로 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-121">In our example configuration, we named the Listener "tx" and added the standard .NET Framework trace listener (<xref:System.Diagnostics.XmlWriterTraceListener>) as the type we want to use.</span></span> <span data-ttu-id="54e46-122">`initializeData`를 사용하여 해당 수신기의 로그 파일 이름을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-122">Use `initializeData` to set the name of the log file for that listener.</span></span> <span data-ttu-id="54e46-123">또한 단순한 파일 이름 대신 정규화된 경로를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-123">In addition, you can substitute a fully qualified path for a simple file name.</span></span>  
  
 <span data-ttu-id="54e46-124">각 추적 메시지 형식에 수준이 할당되어 중요도를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-124">Each trace message type is assigned a level to indicate its degree of importance.</span></span> <span data-ttu-id="54e46-125">app-domain의 추적 수준이 이벤트 형식의 수준보다 낮거나 같으면 해당 메시지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-125">If the app-domain’s trace level is equal or lower than the level of an event type, then that message is generated.</span></span> <span data-ttu-id="54e46-126">추적 수준은 구성 파일의 `switchValue` 설정에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-126">The tracing level is controlled by the `switchValue` setting in the configuration file.</span></span> <span data-ttu-id="54e46-127">진단 추적 메시지와 연결된 수준은 다음 표에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-127">The levels that are associated with diagnostic trace messages are defined in the following table.</span></span>  
  
|<span data-ttu-id="54e46-128">추적 수준</span><span class="sxs-lookup"><span data-stu-id="54e46-128">Trace Level</span></span>|<span data-ttu-id="54e46-129">설명</span><span class="sxs-lookup"><span data-stu-id="54e46-129">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="54e46-130">중요</span><span class="sxs-lookup"><span data-stu-id="54e46-130">Critical</span></span>|<span data-ttu-id="54e46-131">다음과 같은 심각한 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-131">Serious failures, such as the following, have occurred:</span></span><br /><br /> <span data-ttu-id="54e46-132">-사용자 기능에는 즉시 손실을 발생 시킬 수 있는 오류.</span><span class="sxs-lookup"><span data-stu-id="54e46-132">-   An error that can cause an immediate loss in user functionality.</span></span><br /><span data-ttu-id="54e46-133">-관리자 기능이 손실 되지 않도록 조치를 취해야 해야 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-133">-   An event that requires an administrator to take action to avoid loss of functionality.</span></span><br /><span data-ttu-id="54e46-134">코드 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-134">-   Code hangs.</span></span><br /><span data-ttu-id="54e46-135">-이 추적 수준이 다른 중요 한 추적을 해석 하기 위한 충분 한 컨텍스트를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-135">-   This tracing level can also provide sufficient context for interpreting other critical traces.</span></span> <span data-ttu-id="54e46-136">이를 통해 심각한 오류를 발생시키는 작업 시퀀스를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-136">This can help to identify the sequence of operations leading to a serious failure.</span></span>|  
|<span data-ttu-id="54e46-137">오류</span><span class="sxs-lookup"><span data-stu-id="54e46-137">Error</span></span>|<span data-ttu-id="54e46-138">사용자 기능이 손실될 수 있는 오류(예: 잘못된 구성 또는 네트워크 동작)가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-138">An error (for example, invalid configuration or network behavior) has occurred that can result in a loss of user functionality.</span></span>|  
|<span data-ttu-id="54e46-139">경고</span><span class="sxs-lookup"><span data-stu-id="54e46-139">Warning</span></span>|<span data-ttu-id="54e46-140">이후에 오류 또는 치명적인 오류를 발생시킬 수 있는 조건이 있습니다(예: 할당 실패 또는 한도 접근).</span><span class="sxs-lookup"><span data-stu-id="54e46-140">A condition exists that can subsequently result in an error or critical failure (for example, allocation failing or approaching a limit).</span></span> <span data-ttu-id="54e46-141">사용자 코드 오류(예: 트랜잭션 중단, 시간 초과, 인증 실패)의 정상적인 처리 중에 경고가 생성될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-141">Normal processing of errors from user code (for example, transaction aborted, timeouts, authentication failed) can also generate a warning.</span></span>|  
|<span data-ttu-id="54e46-142">정보</span><span class="sxs-lookup"><span data-stu-id="54e46-142">Information</span></span>|<span data-ttu-id="54e46-143">시스템 상태 모니터링 및 진단, 성능 측정 또는 프로파일링에 유용한 메시지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-143">Messages helpful for monitoring and diagnosing system status, measuring performance, or profiling are generated.</span></span> <span data-ttu-id="54e46-144">여기에는 만들어지거나 커밋되는 트랜잭션, 중요한 경계 초과 또는 중요한 리소스 할당 같은 트랜잭션 및 인리스트먼트 수명 이벤트가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-144">These can include transaction and enlistment lifetime events, such as a transaction being created or committed, the crossing of a significant boundary, or the allocation of significant resources.</span></span> <span data-ttu-id="54e46-145">개발자는 용량 계획 및 성능 관리에 이러한 정보를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-145">A developer can then utilize such information for capacity planning and performance management.</span></span>|  
  
## <a name="trace-codes"></a><span data-ttu-id="54e46-146">추적 코드</span><span class="sxs-lookup"><span data-stu-id="54e46-146">Trace Codes</span></span>  
 <span data-ttu-id="54e46-147">다음 표에서는 <xref:System.Transactions> 인프라에서 생성되는 추적 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-147">The following table lists the trace codes that are generated by the <xref:System.Transactions> infrastructure.</span></span> <span data-ttu-id="54e46-148">추적 코드 식별자에는 테이블에 포함 되어는 <xref:System.Diagnostics.EventTypeFilter.EventType%2A> 추적 및에 포함 된 추가 데이터에 대 한 열거형 수준을 **TraceRecord** 추적에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-148">Included in the table are the trace code identifier, the <xref:System.Diagnostics.EventTypeFilter.EventType%2A> enumeration level for the trace, and the extra data contained in the **TraceRecord** for the trace.</span></span> <span data-ttu-id="54e46-149">추적의 해당 하는 추적 수준에도 저장은 또한는 **TraceRecord**합니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-149">In addition, the corresponding trace level of the trace is also stored in the **TraceRecord**.</span></span>  
  
|<span data-ttu-id="54e46-150">TraceCode</span><span class="sxs-lookup"><span data-stu-id="54e46-150">TraceCode</span></span>|<span data-ttu-id="54e46-151">EventType</span><span class="sxs-lookup"><span data-stu-id="54e46-151">EventType</span></span>|<span data-ttu-id="54e46-152">TraceRecord의 추가 데이터</span><span class="sxs-lookup"><span data-stu-id="54e46-152">Extra data in TraceRecord</span></span>|  
|---------------|---------------|-------------------------------|  
|<span data-ttu-id="54e46-153">TransactionCreated</span><span class="sxs-lookup"><span data-stu-id="54e46-153">TransactionCreated</span></span>|<span data-ttu-id="54e46-154">Info</span><span class="sxs-lookup"><span data-stu-id="54e46-154">Info</span></span>|<span data-ttu-id="54e46-155">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="54e46-155">TransactionTraceId</span></span>|  
|<span data-ttu-id="54e46-156">TransactionPromoted</span><span class="sxs-lookup"><span data-stu-id="54e46-156">TransactionPromoted</span></span>|<span data-ttu-id="54e46-157">Info</span><span class="sxs-lookup"><span data-stu-id="54e46-157">Info</span></span>|<span data-ttu-id="54e46-158">로컬 TransactionTraceId, 분산 TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="54e46-158">Local TransactionTraceId, Distributed TransactionTraceId</span></span>|  
|<span data-ttu-id="54e46-159">EnlistmentCreated</span><span class="sxs-lookup"><span data-stu-id="54e46-159">EnlistmentCreated</span></span>|<span data-ttu-id="54e46-160">Info</span><span class="sxs-lookup"><span data-stu-id="54e46-160">Info</span></span>|<span data-ttu-id="54e46-161">TransactionTraceId, EnlistmentTraceId, EnlistmentType(durable/volatile), EnlistmentOptions</span><span class="sxs-lookup"><span data-stu-id="54e46-161">TransactionTraceId, EnlistmentTraceId, EnlistmentType (durable/volatile), EnlistmentOptions</span></span>|  
|<span data-ttu-id="54e46-162">EnlistmentCallbackNegative</span><span class="sxs-lookup"><span data-stu-id="54e46-162">EnlistmentCallbackNegative</span></span>|<span data-ttu-id="54e46-163">경고</span><span class="sxs-lookup"><span data-stu-id="54e46-163">Warning</span></span>|<span data-ttu-id="54e46-164">TransactionTraceId, EnlistmentTraceId,</span><span class="sxs-lookup"><span data-stu-id="54e46-164">TransactionTraceId, EnlistmentTraceId,</span></span><br /><br /> <span data-ttu-id="54e46-165">Callback(forcerollback/aborted/indoubt)</span><span class="sxs-lookup"><span data-stu-id="54e46-165">Callback (forcerollback/aborted/indoubt)</span></span>|  
|<span data-ttu-id="54e46-166">TransactionRollbackCalled</span><span class="sxs-lookup"><span data-stu-id="54e46-166">TransactionRollbackCalled</span></span>|<span data-ttu-id="54e46-167">경고</span><span class="sxs-lookup"><span data-stu-id="54e46-167">Warning</span></span>|<span data-ttu-id="54e46-168">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="54e46-168">TransactionTraceId</span></span>|  
|<span data-ttu-id="54e46-169">TransactionAborted</span><span class="sxs-lookup"><span data-stu-id="54e46-169">TransactionAborted</span></span>|<span data-ttu-id="54e46-170">경고</span><span class="sxs-lookup"><span data-stu-id="54e46-170">Warning</span></span>|<span data-ttu-id="54e46-171">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="54e46-171">TransactionTraceId</span></span>|  
|<span data-ttu-id="54e46-172">TransactionInDoubt</span><span class="sxs-lookup"><span data-stu-id="54e46-172">TransactionInDoubt</span></span>|<span data-ttu-id="54e46-173">경고</span><span class="sxs-lookup"><span data-stu-id="54e46-173">Warning</span></span>|<span data-ttu-id="54e46-174">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="54e46-174">TransactionTraceId</span></span>|  
|<span data-ttu-id="54e46-175">TransactionScopeCreated</span><span class="sxs-lookup"><span data-stu-id="54e46-175">TransactionScopeCreated</span></span>|<span data-ttu-id="54e46-176">Info</span><span class="sxs-lookup"><span data-stu-id="54e46-176">Info</span></span>|<span data-ttu-id="54e46-177">TransactionScopeResult. 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-177">TransactionScopeResult, which can be the following:</span></span><br /><br /> <span data-ttu-id="54e46-178">-새 트랜잭션입니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-178">-   New transaction.</span></span><br /><span data-ttu-id="54e46-179">트랜잭션 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-179">-   Transaction passed.</span></span><br /><span data-ttu-id="54e46-180">-종속 트랜잭션을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-180">-   Dependent transaction passed.</span></span><br /><span data-ttu-id="54e46-181">-현재 트랜잭션을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-181">-   Using current transaction.</span></span><br /><span data-ttu-id="54e46-182">-트랜잭션입니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-182">-   No transaction.</span></span><br /><br /> <span data-ttu-id="54e46-183">새 현재 TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="54e46-183">new current TransactionTraceId</span></span>|  
|<span data-ttu-id="54e46-184">TransactionScopeDisposed</span><span class="sxs-lookup"><span data-stu-id="54e46-184">TransactionScopeDisposed</span></span>|<span data-ttu-id="54e46-185">Info</span><span class="sxs-lookup"><span data-stu-id="54e46-185">Info</span></span>|<span data-ttu-id="54e46-186">범위의 TransactionTraceId "예상" 현재 트랜잭션이 합니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-186">TransactionTraceId of the scope’s "expected" current transaction.</span></span>|  
|<span data-ttu-id="54e46-187">TransactionScopeIncomplete</span><span class="sxs-lookup"><span data-stu-id="54e46-187">TransactionScopeIncomplete</span></span>|<span data-ttu-id="54e46-188">경고</span><span class="sxs-lookup"><span data-stu-id="54e46-188">Warning</span></span>|<span data-ttu-id="54e46-189">범위의 TransactionTraceId "예상" 현재 트랜잭션이 합니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-189">TransactionTraceId of the scope’s "expected" current transaction.</span></span>|  
|<span data-ttu-id="54e46-190">TransactionScopeNestedIncorrectly</span><span class="sxs-lookup"><span data-stu-id="54e46-190">TransactionScopeNestedIncorrectly</span></span>|<span data-ttu-id="54e46-191">경고</span><span class="sxs-lookup"><span data-stu-id="54e46-191">Warning</span></span>|<span data-ttu-id="54e46-192">범위의 TransactionTraceId "예상" 현재 트랜잭션이 합니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-192">TransactionTraceId of the scope’s "expected" current transaction.</span></span>|  
|<span data-ttu-id="54e46-193">TransactionScopeCurrentTransactionChanged</span><span class="sxs-lookup"><span data-stu-id="54e46-193">TransactionScopeCurrentTransactionChanged</span></span>|<span data-ttu-id="54e46-194">경고</span><span class="sxs-lookup"><span data-stu-id="54e46-194">Warning</span></span>|<span data-ttu-id="54e46-195">이전의 현재 TransactionTraceId, 기타 TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="54e46-195">Old current TransactionTraceId, other TransactionTraceId</span></span>|  
|<span data-ttu-id="54e46-196">TransactionScopeTimeout</span><span class="sxs-lookup"><span data-stu-id="54e46-196">TransactionScopeTimeout</span></span>|<span data-ttu-id="54e46-197">경고</span><span class="sxs-lookup"><span data-stu-id="54e46-197">Warning</span></span>|<span data-ttu-id="54e46-198">범위의 TransactionTraceId "예상" 현재 트랜잭션이 합니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-198">TransactionTraceId of the scope’s "expected" current transaction.</span></span>|  
|<span data-ttu-id="54e46-199">DependentCloneCreated</span><span class="sxs-lookup"><span data-stu-id="54e46-199">DependentCloneCreated</span></span>|<span data-ttu-id="54e46-200">Info</span><span class="sxs-lookup"><span data-stu-id="54e46-200">Info</span></span>|<span data-ttu-id="54e46-201">TransactionTraceId, 만들어지는 종속 트랜잭션의 형식(RollbackIfNotComplete/BlockCommitUntilComplete)</span><span class="sxs-lookup"><span data-stu-id="54e46-201">TransactionTraceId, type of dependent transaction created (RollbackIfNotComplete/BlockCommitUntilComplete)</span></span>|  
|<span data-ttu-id="54e46-202">DependentCloneComplete</span><span class="sxs-lookup"><span data-stu-id="54e46-202">DependentCloneComplete</span></span>|<span data-ttu-id="54e46-203">Info</span><span class="sxs-lookup"><span data-stu-id="54e46-203">Info</span></span>|<span data-ttu-id="54e46-204">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="54e46-204">TransactionTraceId</span></span>|  
|<span data-ttu-id="54e46-205">RecoveryComplete</span><span class="sxs-lookup"><span data-stu-id="54e46-205">RecoveryComplete</span></span>|<span data-ttu-id="54e46-206">Info</span><span class="sxs-lookup"><span data-stu-id="54e46-206">Info</span></span>|<span data-ttu-id="54e46-207">리소스 관리자 GUID(기본 클래스로부터)</span><span class="sxs-lookup"><span data-stu-id="54e46-207">Resource Manager GUID (from base)</span></span>|  
|<span data-ttu-id="54e46-208">Reenlist</span><span class="sxs-lookup"><span data-stu-id="54e46-208">Reenlist</span></span>|<span data-ttu-id="54e46-209">Info</span><span class="sxs-lookup"><span data-stu-id="54e46-209">Info</span></span>|<span data-ttu-id="54e46-210">리소스 관리자 GUID(기본 클래스로부터)</span><span class="sxs-lookup"><span data-stu-id="54e46-210">Resource Manager GUID (from base)</span></span>|  
|<span data-ttu-id="54e46-211">TransactionSerialized</span><span class="sxs-lookup"><span data-stu-id="54e46-211">TransactionSerialized</span></span>|<span data-ttu-id="54e46-212">Info</span><span class="sxs-lookup"><span data-stu-id="54e46-212">Info</span></span>|<span data-ttu-id="54e46-213">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="54e46-213">TransactionTraceId.</span></span>|  
|<span data-ttu-id="54e46-214">TransactionException</span><span class="sxs-lookup"><span data-stu-id="54e46-214">TransactionException</span></span>|<span data-ttu-id="54e46-215">오류</span><span class="sxs-lookup"><span data-stu-id="54e46-215">Error</span></span>|<span data-ttu-id="54e46-216">예외 메시지</span><span class="sxs-lookup"><span data-stu-id="54e46-216">Exception message</span></span>|  
|<span data-ttu-id="54e46-217">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="54e46-217">InvalidOperationException</span></span>|<span data-ttu-id="54e46-218">오류</span><span class="sxs-lookup"><span data-stu-id="54e46-218">Error</span></span>|<span data-ttu-id="54e46-219">예외 메시지</span><span class="sxs-lookup"><span data-stu-id="54e46-219">Exception message</span></span>|  
|<span data-ttu-id="54e46-220">InternalError</span><span class="sxs-lookup"><span data-stu-id="54e46-220">InternalError</span></span>|<span data-ttu-id="54e46-221">중요</span><span class="sxs-lookup"><span data-stu-id="54e46-221">Critical</span></span>|<span data-ttu-id="54e46-222">예외 메시지</span><span class="sxs-lookup"><span data-stu-id="54e46-222">Exception message</span></span>|  
|<span data-ttu-id="54e46-223">TransferEvent</span><span class="sxs-lookup"><span data-stu-id="54e46-223">TransferEvent</span></span>||<span data-ttu-id="54e46-224">트랜잭션을 deserialize하거나 <xref:System.Transactions> 트랜잭션에서 분산 트랜잭션으로 승격하는 경우 ExecutionContext의 현재 ActivityID 및 분산 트랜잭션 ID가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-224">When a transaction is deserialized, or promoted from a <xref:System.Transactions> transaction to a distributed one, the current ActivityID from the ExecutionContext and the distributed transaction ID are written.</span></span><br /><br /> <span data-ttu-id="54e46-225">DTC가 관리되는 코드로 콜백되는 경우 분산 트랜잭션 ID는 콜백 기간 동안 ExecutionContext에 ActivityID로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-225">When the DTC calls back into managed code, the distributed transaction ID is set as the ActivityID in the ExecutionContext for the duration of the callback.</span></span>|  
|<span data-ttu-id="54e46-226">ConfiguredDefaultTimeoutAdjusted</span><span class="sxs-lookup"><span data-stu-id="54e46-226">ConfiguredDefaultTimeoutAdjusted</span></span>|<span data-ttu-id="54e46-227">경고</span><span class="sxs-lookup"><span data-stu-id="54e46-227">Warning</span></span>|<span data-ttu-id="54e46-228">추가 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-228">No extra data</span></span>|  
|<span data-ttu-id="54e46-229">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="54e46-229">TransactionTimeout</span></span>|<span data-ttu-id="54e46-230">경고</span><span class="sxs-lookup"><span data-stu-id="54e46-230">Warning</span></span>|<span data-ttu-id="54e46-231">시간 초과되는 트랜잭션의 TransactionTraceId입니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-231">The TransactionTraceId of the transaction being timed out.</span></span>|  
  
 <span data-ttu-id="54e46-232">앞의 각 추가 데이터 항목에 대한 XML 스키마에는 다음 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-232">The XML schema for each of the preceding extra data items has the following format.</span></span>  
  
### <a name="transactiontraceidentifier"></a><span data-ttu-id="54e46-233">TransactionTraceIdentifier</span><span class="sxs-lookup"><span data-stu-id="54e46-233">TransactionTraceIdentifier</span></span>  
 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `< CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `</TransactionTraceIdentifier>`  
  
### <a name="enlistmenttraceidentifier"></a><span data-ttu-id="54e46-234">EnlistmentTraceIdentifier</span><span class="sxs-lookup"><span data-stu-id="54e46-234">EnlistmentTraceIdentifier</span></span>  
 `<EnlistmentTraceIdentifier>`  
  
 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `<CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `<TransactionTraceIdentifier>`  
  
 `<EnlistmentIdentifier>`  
  
 `the enlistment id number`  
  
 `</EnlistmentIdentifier>`  
  
 `</EnlistmentTraceIdentifier>`  
  
### <a name="resource-manager-identifier"></a><span data-ttu-id="54e46-235">리소스 관리자 식별자</span><span class="sxs-lookup"><span data-stu-id="54e46-235">Resource Manager Identifier</span></span>  
 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
## <a name="security-issues-for-tracing"></a><span data-ttu-id="54e46-236">추적과 관련된 보안 문제</span><span class="sxs-lookup"><span data-stu-id="54e46-236">Security Issues For Tracing</span></span>  
 <span data-ttu-id="54e46-237">관리자 권한으로 추적을 설정한 경우 기본적으로 공개적으로 볼 수 있는 추적 로그에 중요 한 정보에 기록 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-237">When you as an administrator turn on tracing, sensitive information might be written to a trace log that is publicly viewable by default.</span></span> <span data-ttu-id="54e46-238">모든 가능한 보안 위협을 완화 하기 위해 추적 로그 공유 및 파일 시스템 액세스 권한에 의해 제어 되는 안전한 위치에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54e46-238">To mitigate any possible security threat, you should consider storing the trace log in a secure location controlled by share and file system access permissions.</span></span>
