---
title: '&lt;transactedBatching&gt;'
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: f0cf0b78ddcbd3214e30a36ce7641d115275a265
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="lttransactedbatchinggt"></a><span data-ttu-id="5d108-102">&lt;transactedBatching&gt;</span><span class="sxs-lookup"><span data-stu-id="5d108-102">&lt;transactedBatching&gt;</span></span>
<span data-ttu-id="5d108-103">받기 작업에 트랜잭션 일괄 처리가 지원되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d108-103">Specifies whether transaction batching is supported for receive operations.</span></span>  
  
 <span data-ttu-id="5d108-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5d108-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5d108-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="5d108-105">\<behaviors></span></span>  
<span data-ttu-id="5d108-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="5d108-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="5d108-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="5d108-107">\<behavior></span></span>  
<span data-ttu-id="5d108-108">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="5d108-108">\<transactedBatching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d108-109">구문</span><span class="sxs-lookup"><span data-stu-id="5d108-109">Syntax</span></span>  
  
```xml  
<transactedBatching maxBatchSize="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d108-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5d108-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5d108-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5d108-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d108-112">특성</span><span class="sxs-lookup"><span data-stu-id="5d108-112">Attributes</span></span>  
  
|<span data-ttu-id="5d108-113">특성</span><span class="sxs-lookup"><span data-stu-id="5d108-113">Attribute</span></span>|<span data-ttu-id="5d108-114">설명</span><span class="sxs-lookup"><span data-stu-id="5d108-114">Description</span></span>|  
|---------------|-----------------|  
|`maxBatchSize`|<span data-ttu-id="5d108-115">트랜잭션 한 번으로 일괄 처리할 수 있는 받기 작업의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d108-115">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="5d108-116">기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="5d108-116">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d108-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5d108-117">Child Elements</span></span>  
 <span data-ttu-id="5d108-118">없음</span><span class="sxs-lookup"><span data-stu-id="5d108-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d108-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5d108-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5d108-120">요소</span><span class="sxs-lookup"><span data-stu-id="5d108-120">Element</span></span>|<span data-ttu-id="5d108-121">설명</span><span class="sxs-lookup"><span data-stu-id="5d108-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d108-122">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="5d108-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="5d108-123">끝점 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d108-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d108-124">설명</span><span class="sxs-lookup"><span data-stu-id="5d108-124">Remarks</span></span>  
 <span data-ttu-id="5d108-125">트랜잭션 일괄 처리로 구성된 전송에서 여러 개의 받기 작업을 한 번의 트랜잭션으로 일괄 처리하도록 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="5d108-125">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="5d108-126">이렇게 하면 모든 받기 작업에서 트랜잭션을 만들고 이를 커밋하는 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d108-126">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d108-127">예제</span><span class="sxs-lookup"><span data-stu-id="5d108-127">Example</span></span>  
 <span data-ttu-id="5d108-128">다음 예제에서는 구성 파일에서 트랜잭션된 일괄 처리 동작을 서비스에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d108-128">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <host>  
        <baseAddresses>  
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
        </baseAddresses>  
      </host>  
  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamples"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IQueueCalculator" />  
  
      <!-- the mex endpoint is explosed at http://localhost:8000/ServiceModelSamples/service/mex -->  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange" />  
    </service>  
  </services>  
  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="endpointBehavior">  
        <transactedBatching maxBatchSize="10" />  
      </behavior>  
    </endpointBehaviors>  
    <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
        <serviceMetadata httpGetEnabled="true" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d108-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d108-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactedBatchingElement>  
 <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
