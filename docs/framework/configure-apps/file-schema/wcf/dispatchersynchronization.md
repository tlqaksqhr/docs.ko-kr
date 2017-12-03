---
title: '&lt;dispatcherSynchronization&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c0a6349f50c8810d834d7887daecb6ac9cffb2e9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="8b2a0-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="8b2a0-102">&lt;dispatcherSynchronization&gt;</span></span>

<span data-ttu-id="8b2a0-103">서비스에서 응답을 비동기적으로 보낼 수 있도록 하는 끝점 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8b2a0-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>

<span data-ttu-id="8b2a0-104">\<system.serviceModel > \<동작 > \<endpointBehaviors > \<동작 ></span><span class="sxs-lookup"><span data-stu-id="8b2a0-104">\<system.serviceModel> \<behaviors> \<endpointBehaviors> \<behavior></span></span>

## <a name="syntax"></a><span data-ttu-id="8b2a0-105">구문</span><span class="sxs-lookup"><span data-stu-id="8b2a0-105">Syntax</span></span>

```xml
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean" 
                                   maxPendingReceives="Integer" />
```

## <a name="type"></a><span data-ttu-id="8b2a0-106">형식</span><span class="sxs-lookup"><span data-stu-id="8b2a0-106">Type</span></span>

`Type`

## <a name="attributes-and-elements"></a><span data-ttu-id="8b2a0-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8b2a0-107">Attributes and elements</span></span>

<span data-ttu-id="8b2a0-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8b2a0-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8b2a0-109">특성</span><span class="sxs-lookup"><span data-stu-id="8b2a0-109">Attributes</span></span>

| <span data-ttu-id="8b2a0-110">특성</span><span class="sxs-lookup"><span data-stu-id="8b2a0-110">Attribute</span></span>               | <span data-ttu-id="8b2a0-111">설명</span><span class="sxs-lookup"><span data-stu-id="8b2a0-111">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="8b2a0-112">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="8b2a0-112">asynchronousSendEnabled</span></span> | <span data-ttu-id="8b2a0-113">비동기 보내기 동작 사용 여부를 나타내는 부울입니다.</span><span class="sxs-lookup"><span data-stu-id="8b2a0-113">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="8b2a0-114">채널에서 발급할 수 있는 동시 수신의 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b2a0-114">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="8b2a0-115">이 값은 서비스 스로틀 동작을 제대로 구성한 후에 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b2a0-115">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="8b2a0-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8b2a0-116">Child elements</span></span>

<span data-ttu-id="8b2a0-117">없음</span><span class="sxs-lookup"><span data-stu-id="8b2a0-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8b2a0-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8b2a0-118">Parent elements</span></span>

| <span data-ttu-id="8b2a0-119">요소</span><span class="sxs-lookup"><span data-stu-id="8b2a0-119">Element</span></span> | <span data-ttu-id="8b2a0-120">설명</span><span class="sxs-lookup"><span data-stu-id="8b2a0-120">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="8b2a0-121">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="8b2a0-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="8b2a0-122">끝점 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8b2a0-122">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="8b2a0-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b2a0-123">See also</span></span>

 <span data-ttu-id="8b2a0-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span><span class="sxs-lookup"><span data-stu-id="8b2a0-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span></span>
