---
title: "&lt;baseAddresses&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9e941b63e42af9237388df6be8223acbad8db745
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a><span data-ttu-id="8e315-102">&lt;baseAddresses&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="8e315-102">&lt;add&gt; of &lt;baseAddresses&gt;</span></span>
<span data-ttu-id="8e315-103">서비스 호스트에서 사용하는 기본 주소를 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8e315-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="8e315-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8e315-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8e315-105">\<클라이언트 ></span><span class="sxs-lookup"><span data-stu-id="8e315-105">\<client></span></span>  
<span data-ttu-id="8e315-106">\<끝점 ></span><span class="sxs-lookup"><span data-stu-id="8e315-106">\<endpoint></span></span>  
<span data-ttu-id="8e315-107">\<호스트 ></span><span class="sxs-lookup"><span data-stu-id="8e315-107">\<host></span></span>  
<span data-ttu-id="8e315-108">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="8e315-108">\<baseAddresses></span></span>  
<span data-ttu-id="8e315-109">\<baseAddress ></span><span class="sxs-lookup"><span data-stu-id="8e315-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e315-110">구문</span><span class="sxs-lookup"><span data-stu-id="8e315-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />  
```  
  
## <a name="type"></a><span data-ttu-id="8e315-111">형식</span><span class="sxs-lookup"><span data-stu-id="8e315-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e315-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8e315-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8e315-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8e315-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e315-114">특성</span><span class="sxs-lookup"><span data-stu-id="8e315-114">Attributes</span></span>  
  
|<span data-ttu-id="8e315-115">특성</span><span class="sxs-lookup"><span data-stu-id="8e315-115">Attribute</span></span>|<span data-ttu-id="8e315-116">설명</span><span class="sxs-lookup"><span data-stu-id="8e315-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="8e315-117">서비스 호스트에서 사용하는 기본 주소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8e315-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e315-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8e315-118">Child Elements</span></span>  
 <span data-ttu-id="8e315-119">없음</span><span class="sxs-lookup"><span data-stu-id="8e315-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e315-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8e315-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8e315-121">요소</span><span class="sxs-lookup"><span data-stu-id="8e315-121">Element</span></span>|<span data-ttu-id="8e315-122">설명</span><span class="sxs-lookup"><span data-stu-id="8e315-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e315-123">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="8e315-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="8e315-124">`baseAddress` 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8e315-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e315-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e315-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="8e315-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="8e315-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
