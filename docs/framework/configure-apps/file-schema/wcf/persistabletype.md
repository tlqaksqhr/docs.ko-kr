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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c77bdf8ef02edf682ded95ab16b4d56dbf60b4ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltpersistabletypegt"></a><span data-ttu-id="15f5b-102">&lt;persistableType&gt;</span><span class="sxs-lookup"><span data-stu-id="15f5b-102">&lt;persistableType&gt;</span></span>
<span data-ttu-id="15f5b-103">모든 지속 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-103">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="15f5b-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="15f5b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="15f5b-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="15f5b-105">\<comContracts></span></span>  
<span data-ttu-id="15f5b-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="15f5b-106">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15f5b-107">구문</span><span class="sxs-lookup"><span data-stu-id="15f5b-107">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="15f5b-108">형식</span><span class="sxs-lookup"><span data-stu-id="15f5b-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15f5b-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="15f5b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="15f5b-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15f5b-111">특성</span><span class="sxs-lookup"><span data-stu-id="15f5b-111">Attributes</span></span>  
  
|<span data-ttu-id="15f5b-112">특성</span><span class="sxs-lookup"><span data-stu-id="15f5b-112">Attribute</span></span>|<span data-ttu-id="15f5b-113">설명</span><span class="sxs-lookup"><span data-stu-id="15f5b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15f5b-114">id</span><span class="sxs-lookup"><span data-stu-id="15f5b-114">id</span></span>|<span data-ttu-id="15f5b-115">지속 형식에 대한 고유 식별자를 지정하는 문자열이 포함된 필수적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-115">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="15f5b-116">name</span><span class="sxs-lookup"><span data-stu-id="15f5b-116">name</span></span>|<span data-ttu-id="15f5b-117">지속 형식의 이름을 지정하는 문자열이 포함된 선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-117">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15f5b-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="15f5b-118">Child Elements</span></span>  
 <span data-ttu-id="15f5b-119">없음</span><span class="sxs-lookup"><span data-stu-id="15f5b-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15f5b-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="15f5b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="15f5b-121">요소</span><span class="sxs-lookup"><span data-stu-id="15f5b-121">Element</span></span>|<span data-ttu-id="15f5b-122">설명</span><span class="sxs-lookup"><span data-stu-id="15f5b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15f5b-123">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="15f5b-123">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="15f5b-124">`persistableType` 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-124">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15f5b-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15f5b-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>  
 [<span data-ttu-id="15f5b-126">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="15f5b-126">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="15f5b-127">COM + 응용 프로그램과 통합</span><span class="sxs-lookup"><span data-stu-id="15f5b-127">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="15f5b-128">방법: COM + 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="15f5b-128">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
