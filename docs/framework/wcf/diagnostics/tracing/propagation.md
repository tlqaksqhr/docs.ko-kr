---
title: "전파"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8181e75-d693-48d1-b333-a776ad3b382a
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bfe861d6b535c7158ae930d4f31ac0ad4bae6721
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="propagation"></a><span data-ttu-id="899ff-102">전파</span><span class="sxs-lookup"><span data-stu-id="899ff-102">Propagation</span></span>
<span data-ttu-id="899ff-103">이 항목에서는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 추적 모델의 동작 전파에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-103">This topic describes activity propagation in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model.</span></span>  
  
## <a name="using-propagation-to-correlate-activities-across-endpoints"></a><span data-ttu-id="899ff-104">전파를 통해 끝점 내의 동작 상호 연결</span><span class="sxs-lookup"><span data-stu-id="899ff-104">Using Propagation to Correlate Activities Across Endpoints</span></span>  
 <span data-ttu-id="899ff-105">전파는 사용자에게 응용 프로그램 끝점을 통해 동일한 처리 단위(예: 요청)에 대한 오류 추적의 직접적인 상관 관계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-105">Propagation provides the user with direct correlation of error traces for the same unit of processing across application endpoints, for example, a request.</span></span> <span data-ttu-id="899ff-106">동일한 처리 단위에 대해 다른 끝점에서 내보내진 오류는 응용 프로그램 도메인에서도 동일한 동작에서 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-106">Errors emitted at different endpoints for the same unit of processing are grouped in the same activity, even across application domains.</span></span> <span data-ttu-id="899ff-107">이는 메시지 헤더에서 동작 ID의 전파를 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-107">This is done through propagation of the activity ID in the message headers.</span></span> <span data-ttu-id="899ff-108">그러므로 서버의 내부 오류로 인해 클라이언트의 시간이 초과되면 두 오류 모두 직접 상관 관계에 대해 동일한 동작에서 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-108">Therefore, if a client times out because of an internal error in the server, both errors appear in the same activity for direct correlation.</span></span>  
  
 <span data-ttu-id="899ff-109">이 작업을 수행하려면 앞의 예제에서 설명한 대로 `ActivityTracing` 설정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="899ff-109">To do this, use the `ActivityTracing` setting as demonstrated in the previous example.</span></span> <span data-ttu-id="899ff-110">또한 모든 끝점에서 `propagateActivity` 추적 소스에 대해 `System.ServiceModel` 특성을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="899ff-110">In addition, set the `propagateActivity` attribute for the `System.ServiceModel` trace source at all endpoints.</span></span>  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing" propagateActivity="true" >  
```  
  
 <span data-ttu-id="899ff-111">동작 전파는 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]가 TLS에 동작 ID를 포함한 아웃바운드 메시지에 헤더를 추가하도록 구성할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-111">Activity propagation is a configurable capability that causes [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] to add a header to outbound messages, which includes the activity ID on the TLS.</span></span> <span data-ttu-id="899ff-112">서버측에서 이후의 추적에 이를 포함함으로써 클라이언트 및 서버 동작을 상호 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-112">By including this on subsequent traces on the server side, we can correlate client and server activities.</span></span>  
  
## <a name="propagation-definition"></a><span data-ttu-id="899ff-113">전파 정의</span><span class="sxs-lookup"><span data-stu-id="899ff-113">Propagation Definition</span></span>  
 <span data-ttu-id="899ff-114">다음 조건이 모두 충족되면 동작 M의 gAId가 동작 N에 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-114">Activity M’s gAId is propagated to activity N if all of the following conditions apply.</span></span>  
  
-   <span data-ttu-id="899ff-115">N은 M으로 인해 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-115">N is created because of M</span></span>  
  
-   <span data-ttu-id="899ff-116">M의 gAId가 N에 알려집니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-116">M’s gAId is known to N</span></span>  
  
-   <span data-ttu-id="899ff-117">N의 gAId가 M의 gAId와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-117">N's gAId is equal to M’s gAId.</span></span>  
  
 <span data-ttu-id="899ff-118">다음 XML 스키마에 설명된 것처럼 gAId는 ActivityId 메시지 헤더를 통해 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-118">The gAId is propagated through the ActivityId message header, as illustrated in the following XML schema.</span></span>  
  
```xml  
<xsd:element name="ActivityId" type="integer" minOccurs="0">  
  <xsd:attribute name="CorrelationId" type="integer" minOccurs="0"/>  
</xsd:element>  
```  
  
 <span data-ttu-id="899ff-119">다음은 메시지 헤더의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-119">The following is an example of the message header.</span></span>  
  
```xml  
<MessageLogTraceRecord>  
  <s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope"     
                      xmlns:a="http://www.w3.org/2005/08/addressing">  
    <s:Header>  
      <a:Action s:mustUnderstand="1">http://Microsoft.ServiceModel.Samples/ICalculator/Subtract  
      </a:Action>  
      <a:MessageID>urn:uuid:f0091eae-d339-4c7e-9408-ece34602f1ce  
      </a:MessageID>  
      <ActivityId CorrelationId="f94c6af1-7d5d-4295-b693-4670a8a0ce34"   
  
               xmlns="http://schemas.microsoft.com/2004/09/ServiceModel/Diagnostics">  
        17f59a29-b435-4a15-bf7b-642ffc40eac8  
      </ActivityId>  
      <a:ReplyTo>  
          <a:Address>http://www.w3.org/2005/08/addressing/anonymous  
          </a:Address>  
      </a:ReplyTo>  
      <a:To s:mustUnderstand="1">net.tcp://localhost/servicemodelsamples/service</a:To>  
   </s:Header>  
   <s:Body>  
     <Subtract xmlns="http://Microsoft.ServiceModel.Samples">  
       <n1>145</n1>  
       <n2>76.54</n2>  
     </Subtract>  
   </s:Body>  
  </s:Envelope>  
</MessageLogTraceRecord>  
```  
  
## <a name="propagation-and-activity-boundaries"></a><span data-ttu-id="899ff-120">전파 및 동작 경계</span><span class="sxs-lookup"><span data-stu-id="899ff-120">Propagation and Activity Boundaries</span></span>  
 <span data-ttu-id="899ff-121">동작 ID가 끝점을 통해 전파되는 경우 메시지 수신자는 해당(전파된) 동작 ID를 사용하여 Start 및 Stop 추적을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-121">When the activity ID is propagated across endpoints, the message receiver emits a Start and Stop traces with that (propagated) activity ID.</span></span> <span data-ttu-id="899ff-122">따라서 각 추적 소스의 해당 gAId를 가진 Start 및 Stop 추적이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-122">Therefore, there is a Start and Stop trace with that gAId from each trace source.</span></span> <span data-ttu-id="899ff-123">끝점이 동일한 프로세스에 있고 동일한 추적 소스 이름을 사용하는 경우 동일한 lAId(동일한 gAId, 동일한 추적 소스, 동일한 프로세스)를 가진 여러 Start 및 Stop 추적이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-123">If the endpoints are in the same process and use the same trace source name, multiple Start and Stop with the same lAId (same gAId, same trace source, same process) are created.</span></span>  
  
## <a name="synchronization"></a><span data-ttu-id="899ff-124">동기화</span><span class="sxs-lookup"><span data-stu-id="899ff-124">Synchronization</span></span>  
 <span data-ttu-id="899ff-125">서로 다른 컴퓨터에서 실행되는 끝점에서 이벤트를 동기화하기 위해 CorrelationId가 메시지에 전파되는 ActivityId 헤더에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-125">To synchronize events across endpoints that run on different machines, a CorrelationId is added to the ActivityId header that is propagated in messages.</span></span> <span data-ttu-id="899ff-126">도구에서 이 ID를 사용하여 클럭이 일치하지 않는 시스템 간의 이벤트를 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-126">Tools can use this ID to synchronize events across machines with clock discrepancy.</span></span> <span data-ttu-id="899ff-127">특히 Service Trace Viewer 도구는 이 ID를 사용하여 끝점 간의 메시지 흐름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="899ff-127">Specifically, the Service Trace Viewer tool uses this ID for showing message flows between endpoints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="899ff-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="899ff-128">See Also</span></span>  
 [<span data-ttu-id="899ff-129">추적 구성</span><span class="sxs-lookup"><span data-stu-id="899ff-129">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
 [<span data-ttu-id="899ff-130">Service Trace Viewer를 사용하여 상호 관련된 추적 보기 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="899ff-130">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [<span data-ttu-id="899ff-131">종단 간 추적 시나리오</span><span class="sxs-lookup"><span data-stu-id="899ff-131">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 [<span data-ttu-id="899ff-132">Service Trace Viewer 도구(SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="899ff-132">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
