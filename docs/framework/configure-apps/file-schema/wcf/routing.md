---
title: '&lt;라우팅&gt;'
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 1771d8a2603a8f61af6ba6e2acf6243d2fd073f7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltroutinggt"></a><span data-ttu-id="48305-102">&lt;라우팅&gt;</span><span class="sxs-lookup"><span data-stu-id="48305-102">&lt;routing&gt;</span></span>

<span data-ttu-id="48305-103">Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다 <xref:System.ServiceModel.Dispatcher.MessageFilter> 들어오는 메시지를 평가할 및 라우팅 테이블 대상 끝점을 정의 하는 경우에 사용 됩니다 필터가 일치할 때 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="48305-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="48305-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="48305-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="48305-105">&nbsp;&nbsp;**\<라우팅 >**</span><span class="sxs-lookup"><span data-stu-id="48305-105">&nbsp;&nbsp;**\<routing>**</span></span>

## <a name="syntax"></a><span data-ttu-id="48305-106">구문</span><span class="sxs-lookup"><span data-stu-id="48305-106">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String" 
              filterData="String" 
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
              name="String" />
    </filters>
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String" 
               filterName="String" 
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
  </routing>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="48305-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="48305-107">Attributes and elements</span></span>

<span data-ttu-id="48305-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="48305-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="48305-109">특성</span><span class="sxs-lookup"><span data-stu-id="48305-109">Attributes</span></span>

<span data-ttu-id="48305-110">없음</span><span class="sxs-lookup"><span data-stu-id="48305-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="48305-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="48305-111">Child elements</span></span>

|     | <span data-ttu-id="48305-112">설명</span><span class="sxs-lookup"><span data-stu-id="48305-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="48305-113">**\<필터 >**</span><span class="sxs-lookup"><span data-stu-id="48305-113">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="48305-114">Windows Communication Foundation (WCF) MessageFilter 유형의 들어오는 메시지를 평가할 때 사용될지를 결정 하는 라우팅 필터 집합을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="48305-114">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="48305-115">**\<filterTables >**</span><span class="sxs-lookup"><span data-stu-id="48305-115">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="48305-116">필터가 일치할 때 사용할 끝점을 지정하기 위한 라우팅 필터와 대상 끝점 간의 매핑을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="48305-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="48305-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="48305-117">Parent elements</span></span>

|     | <span data-ttu-id="48305-118">설명</span><span class="sxs-lookup"><span data-stu-id="48305-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="48305-119">**\<시스템입니다. ServiceModel >**</span><span class="sxs-lookup"><span data-stu-id="48305-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="48305-120">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="48305-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="48305-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="48305-121">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
