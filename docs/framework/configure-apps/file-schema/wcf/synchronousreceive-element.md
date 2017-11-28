---
title: "&lt;synchronousReceive&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b630f5ad2fbf5e3f20667e0bd1b7ae711992dc18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltsynchronousreceivegt-element"></a><span data-ttu-id="d407b-102">&lt;synchronousReceive&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="d407b-102">&lt;synchronousReceive&gt; element</span></span>
<span data-ttu-id="d407b-103">이 구성 요소는 서비스 또는 클라이언트 응용 프로그램에서 메시지 수신을 위한 런타임 동작을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d407b-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="d407b-104">이 구성 요소에는 특성이나 자식 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d407b-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="d407b-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d407b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d407b-106">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d407b-106">\<behaviors></span></span>  
<span data-ttu-id="d407b-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d407b-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="d407b-108">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d407b-108">\<behavior></span></span>  
<span data-ttu-id="d407b-109">\<synchronousReceive ></span><span class="sxs-lookup"><span data-stu-id="d407b-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d407b-110">구문</span><span class="sxs-lookup"><span data-stu-id="d407b-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d407b-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d407b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d407b-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d407b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d407b-113">특성</span><span class="sxs-lookup"><span data-stu-id="d407b-113">Attributes</span></span>  
 <span data-ttu-id="d407b-114">없음</span><span class="sxs-lookup"><span data-stu-id="d407b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d407b-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d407b-115">Child Elements</span></span>  
 <span data-ttu-id="d407b-116">없음</span><span class="sxs-lookup"><span data-stu-id="d407b-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d407b-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d407b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d407b-118">요소</span><span class="sxs-lookup"><span data-stu-id="d407b-118">Element</span></span>|<span data-ttu-id="d407b-119">설명</span><span class="sxs-lookup"><span data-stu-id="d407b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d407b-120">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d407b-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d407b-121">끝점 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d407b-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d407b-122">설명</span><span class="sxs-lookup"><span data-stu-id="d407b-122">Remarks</span></span>  
 <span data-ttu-id="d407b-123">채널 수신기에 기본값(비동기) 대신 동기 수신을 사용하도록 지시하려면 이 동작을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d407b-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="d407b-124">는 수락된 각 채널에 대해 공급할 새 스레드를 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="d407b-124"> issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="d407b-125">채널이 많은 경우 스레드가 부족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d407b-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d407b-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d407b-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
