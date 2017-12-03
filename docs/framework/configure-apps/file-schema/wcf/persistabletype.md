---
title: '&lt;persistableType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 56443902885e191d93897096e55742f7665ba00a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltpersistabletypegt"></a><span data-ttu-id="d398e-102">&lt;persistableType&gt;</span><span class="sxs-lookup"><span data-stu-id="d398e-102">&lt;persistableType&gt;</span></span>
<span data-ttu-id="d398e-103">모든 지속 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d398e-103">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="d398e-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d398e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d398e-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="d398e-105">\<comContracts></span></span>  
<span data-ttu-id="d398e-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="d398e-106">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d398e-107">구문</span><span class="sxs-lookup"><span data-stu-id="d398e-107">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="type"></a><span data-ttu-id="d398e-108">형식</span><span class="sxs-lookup"><span data-stu-id="d398e-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d398e-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d398e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d398e-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d398e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d398e-111">특성</span><span class="sxs-lookup"><span data-stu-id="d398e-111">Attributes</span></span>  
  
|<span data-ttu-id="d398e-112">특성</span><span class="sxs-lookup"><span data-stu-id="d398e-112">Attribute</span></span>|<span data-ttu-id="d398e-113">설명</span><span class="sxs-lookup"><span data-stu-id="d398e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d398e-114">id</span><span class="sxs-lookup"><span data-stu-id="d398e-114">id</span></span>|<span data-ttu-id="d398e-115">지속 형식에 대한 고유 식별자를 지정하는 문자열이 포함된 필수적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d398e-115">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="d398e-116">name</span><span class="sxs-lookup"><span data-stu-id="d398e-116">name</span></span>|<span data-ttu-id="d398e-117">지속 형식의 이름을 지정하는 문자열이 포함된 선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d398e-117">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d398e-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d398e-118">Child Elements</span></span>  
 <span data-ttu-id="d398e-119">없음</span><span class="sxs-lookup"><span data-stu-id="d398e-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d398e-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d398e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d398e-121">요소</span><span class="sxs-lookup"><span data-stu-id="d398e-121">Element</span></span>|<span data-ttu-id="d398e-122">설명</span><span class="sxs-lookup"><span data-stu-id="d398e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d398e-123">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="d398e-123">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="d398e-124">`persistableType` 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d398e-124">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d398e-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d398e-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>  
 [<span data-ttu-id="d398e-126">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="d398e-126">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="d398e-127">COM + 응용 프로그램과 통합</span><span class="sxs-lookup"><span data-stu-id="d398e-127">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="d398e-128">방법: COM + 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="d398e-128">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
