---
title: "&lt;routing&gt;의 &lt;filters&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2687101aa868ae77ce0ae818afd9df906f8525c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltersgt-of-ltroutinggt"></a><span data-ttu-id="b1f2b-102">&lt;routing&gt;의 &lt;filters&gt;</span><span class="sxs-lookup"><span data-stu-id="b1f2b-102">&lt;filters&gt; of &lt;routing&gt;</span></span>

<span data-ttu-id="b1f2b-103">들어오는 메시지를 평가할 때 사용되는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> 형식을 결정하는 라우팅 필터 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-103">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="b1f2b-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="b1f2b-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="b1f2b-105">&nbsp;&nbsp;[**\<라우팅 >**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="b1f2b-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="b1f2b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<필터 >**</span><span class="sxs-lookup"><span data-stu-id="b1f2b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b1f2b-107">구문</span><span class="sxs-lookup"><span data-stu-id="b1f2b-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String" 
              filterData="String" 
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
              name="String" />
    </filters>
  </routing>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b1f2b-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b1f2b-108">Attributes and elements</span></span>

<span data-ttu-id="b1f2b-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b1f2b-110">특성</span><span class="sxs-lookup"><span data-stu-id="b1f2b-110">Attributes</span></span>

<span data-ttu-id="b1f2b-111">없음</span><span class="sxs-lookup"><span data-stu-id="b1f2b-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="b1f2b-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b1f2b-112">Child elements</span></span>

|     | <span data-ttu-id="b1f2b-113">설명</span><span class="sxs-lookup"><span data-stu-id="b1f2b-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b1f2b-114">**\<필터 >**</span><span class="sxs-lookup"><span data-stu-id="b1f2b-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="b1f2b-115">들어오는 메시지를 평가할 때 사용될 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> 형식을 결정하는 라우팅 필터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-115">Contains a routing filter that determines the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="b1f2b-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b1f2b-116">Parent elements</span></span>

|     | <span data-ttu-id="b1f2b-117">설명</span><span class="sxs-lookup"><span data-stu-id="b1f2b-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b1f2b-118">**\<라우팅 >**</span><span class="sxs-lookup"><span data-stu-id="b1f2b-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="b1f2b-119">들어오는 메시지 및 필터가 일치할 때 메시지를 보낼 대상 끝점을 정의하는 라우팅 테이블을 평가할 때 사용되는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> 형식을 결정하는 라우팅 필터 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-119">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="b1f2b-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1f2b-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
