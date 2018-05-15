---
title: '&lt;bufferReceive&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 07d5b66b14d9495808f972734cdce4476efaefde
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltbufferreceivegt"></a><span data-ttu-id="684e1-102">&lt;bufferReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="684e1-102">&lt;bufferReceive&gt;</span></span>
<span data-ttu-id="684e1-103">서비스에서 버퍼링되는 수신 처리를 사용할 수 있도록 하는 서비스 동작입니다. 이를 통해 워크플로 서비스가 순서가 맞지 않는 메시지를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="684e1-103">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="684e1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="684e1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="684e1-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="684e1-105">\<behaviors></span></span>  
<span data-ttu-id="684e1-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="684e1-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="684e1-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="684e1-107">\<behavior></span></span>  
<span data-ttu-id="684e1-108">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="684e1-108">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="684e1-109">구문</span><span class="sxs-lookup"><span data-stu-id="684e1-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="684e1-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="684e1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="684e1-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="684e1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="684e1-112">특성</span><span class="sxs-lookup"><span data-stu-id="684e1-112">Attributes</span></span>  
  
|<span data-ttu-id="684e1-113">특성</span><span class="sxs-lookup"><span data-stu-id="684e1-113">Attribute</span></span>|<span data-ttu-id="684e1-114">설명</span><span class="sxs-lookup"><span data-stu-id="684e1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="684e1-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="684e1-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="684e1-116">각 채널에 허용되는 최대 보류 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="684e1-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="684e1-117">기본값은 512입니다.</span><span class="sxs-lookup"><span data-stu-id="684e1-117">The default value is 512.</span></span> <span data-ttu-id="684e1-118">이 속성은 워크플로 서비스가 수신할 수 있는 순서가 맞지 않는 메시지의 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="684e1-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="684e1-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="684e1-119">Child Elements</span></span>  
 <span data-ttu-id="684e1-120">없음</span><span class="sxs-lookup"><span data-stu-id="684e1-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="684e1-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="684e1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="684e1-122">요소</span><span class="sxs-lookup"><span data-stu-id="684e1-122">Element</span></span>|<span data-ttu-id="684e1-123">설명</span><span class="sxs-lookup"><span data-stu-id="684e1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="684e1-124">\<동작 >의 \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="684e1-124">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="684e1-125">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="684e1-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="684e1-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="684e1-126">See Also</span></span>  
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
 <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
