---
title: '&lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 31d661f39f9e3de0f7012c7fa52d4964e7ee4a69
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748882"
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="fc010-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="fc010-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="fc010-103">매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 요소 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fc010-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="fc010-104">**\<system.serviceModel >** </span><span class="sxs-lookup"><span data-stu-id="fc010-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="fc010-105">&nbsp;&nbsp;**\<라우팅 >** </span><span class="sxs-lookup"><span data-stu-id="fc010-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="fc010-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="fc010-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fc010-107">구문</span><span class="sxs-lookup"><span data-stu-id="fc010-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
``` 

## <a name="attributes-and-elements"></a><span data-ttu-id="fc010-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fc010-108">Attributes and elements</span></span>

<span data-ttu-id="fc010-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fc010-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="fc010-110">특성</span><span class="sxs-lookup"><span data-stu-id="fc010-110">Attributes</span></span>

<span data-ttu-id="fc010-111">없음</span><span class="sxs-lookup"><span data-stu-id="fc010-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="fc010-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fc010-112">Child elements</span></span>

|     | <span data-ttu-id="fc010-113">설명</span><span class="sxs-lookup"><span data-stu-id="fc010-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="fc010-114">**\<필터 >**</span><span class="sxs-lookup"><span data-stu-id="fc010-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="fc010-115">XPath 식에 사용되는 네임스페이스 접두사 매핑을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fc010-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="fc010-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fc010-116">Parent elements</span></span>

|     | <span data-ttu-id="fc010-117">설명</span><span class="sxs-lookup"><span data-stu-id="fc010-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="fc010-118">**\<라우팅 >**</span><span class="sxs-lookup"><span data-stu-id="fc010-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="fc010-119">Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다<xref:System.ServiceModel.Dispatcher.MessageFilter> 들어오는 메시지를 평가할 및 라우팅 테이블 대상 끝점을 정의 하는 경우에 사용 됩니다 필터가 일치할 때 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="fc010-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="fc010-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="fc010-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
