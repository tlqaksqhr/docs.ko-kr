---
title: '&lt;bufferReceive&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 623ff924e171282c399bddcdc212a0606a3416d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltbufferreceivegt"></a><span data-ttu-id="b3af0-102">&lt;bufferReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="b3af0-102">&lt;bufferReceive&gt;</span></span>
<span data-ttu-id="b3af0-103">서비스에서 버퍼링되는 수신 처리를 사용할 수 있도록 하는 서비스 동작입니다. 이를 통해 워크플로 서비스가 순서가 맞지 않는 메시지를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3af0-103">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="b3af0-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b3af0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b3af0-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="b3af0-105">\<behaviors></span></span>  
<span data-ttu-id="b3af0-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="b3af0-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="b3af0-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="b3af0-107">\<behavior></span></span>  
<span data-ttu-id="b3af0-108">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="b3af0-108">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3af0-109">구문</span><span class="sxs-lookup"><span data-stu-id="b3af0-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3af0-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b3af0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b3af0-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b3af0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3af0-112">특성</span><span class="sxs-lookup"><span data-stu-id="b3af0-112">Attributes</span></span>  
  
|<span data-ttu-id="b3af0-113">특성</span><span class="sxs-lookup"><span data-stu-id="b3af0-113">Attribute</span></span>|<span data-ttu-id="b3af0-114">설명</span><span class="sxs-lookup"><span data-stu-id="b3af0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b3af0-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="b3af0-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="b3af0-116">각 채널에 허용되는 최대 보류 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="b3af0-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="b3af0-117">기본값은 512입니다.</span><span class="sxs-lookup"><span data-stu-id="b3af0-117">The default value is 512.</span></span> <span data-ttu-id="b3af0-118">이 속성은 워크플로 서비스가 수신할 수 있는 순서가 맞지 않는 메시지의 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="b3af0-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3af0-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b3af0-119">Child Elements</span></span>  
 <span data-ttu-id="b3af0-120">없음</span><span class="sxs-lookup"><span data-stu-id="b3af0-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b3af0-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b3af0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b3af0-122">요소</span><span class="sxs-lookup"><span data-stu-id="b3af0-122">Element</span></span>|<span data-ttu-id="b3af0-123">설명</span><span class="sxs-lookup"><span data-stu-id="b3af0-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3af0-124">\<동작 >의 \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="b3af0-124">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="b3af0-125">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b3af0-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3af0-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3af0-126">See Also</span></span>  
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
 <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
