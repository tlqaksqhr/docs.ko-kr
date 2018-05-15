---
title: '&lt;routing&gt;의 &lt;filters&gt;'
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 9f0fa9bf51d264346738172f57a8efca7950fdb7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltfiltersgt-of-ltroutinggt"></a><span data-ttu-id="3f35a-102">&lt;routing&gt;의 &lt;filters&gt;</span><span class="sxs-lookup"><span data-stu-id="3f35a-102">&lt;filters&gt; of &lt;routing&gt;</span></span>

<span data-ttu-id="3f35a-103">Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다 <xref:System.ServiceModel.Dispatcher.MessageFilter> 들어오는 메시지를 평가할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f35a-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="3f35a-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="3f35a-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="3f35a-105">&nbsp;&nbsp;[**\<라우팅 >**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="3f35a-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="3f35a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<필터 >**</span><span class="sxs-lookup"><span data-stu-id="3f35a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3f35a-107">구문</span><span class="sxs-lookup"><span data-stu-id="3f35a-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="3f35a-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3f35a-108">Attributes and elements</span></span>

<span data-ttu-id="3f35a-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3f35a-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3f35a-110">특성</span><span class="sxs-lookup"><span data-stu-id="3f35a-110">Attributes</span></span>

<span data-ttu-id="3f35a-111">없음</span><span class="sxs-lookup"><span data-stu-id="3f35a-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="3f35a-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3f35a-112">Child elements</span></span>

|     | <span data-ttu-id="3f35a-113">설명</span><span class="sxs-lookup"><span data-stu-id="3f35a-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="3f35a-114">**\<필터 >**</span><span class="sxs-lookup"><span data-stu-id="3f35a-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="3f35a-115">Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터를 포함<xref:System.ServiceModel.Dispatcher.MessageFilter> 들어오는 메시지를 평가할 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f35a-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="3f35a-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3f35a-116">Parent elements</span></span>

|     | <span data-ttu-id="3f35a-117">설명</span><span class="sxs-lookup"><span data-stu-id="3f35a-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="3f35a-118">**\<라우팅 >**</span><span class="sxs-lookup"><span data-stu-id="3f35a-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="3f35a-119">Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다<xref:System.ServiceModel.Dispatcher.MessageFilter> 들어오는 메시지를 평가할 및 라우팅 테이블 대상 끝점을 정의 하는 경우에 사용 됩니다 필터가 일치할 때 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3f35a-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3f35a-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="3f35a-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
