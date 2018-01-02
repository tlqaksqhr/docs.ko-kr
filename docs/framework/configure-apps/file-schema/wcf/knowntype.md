---
title: '&lt;knownType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 439d241d73df4db2820eac72c5e88e7d9023c6a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltknowntypegt"></a><span data-ttu-id="59ba5-102">&lt;knownType&gt;</span><span class="sxs-lookup"><span data-stu-id="59ba5-102">&lt;knownType&gt;</span></span>
<span data-ttu-id="59ba5-103">deserialization을 수행하는 동안 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba5-103">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="59ba5-104">요소는 "선언된 형식"의 필드 또는 속성에서 반환하는 "알려진 형식"을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba5-104">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="59ba5-105">자세한 내용은 참조 [데이터 계약 알려진 형식을](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba5-105">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="59ba5-106">\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="59ba5-106">\<system.runtime.serialization></span></span>  
<span data-ttu-id="59ba5-107">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="59ba5-107">\<dataContractSerializer></span></span>  
<span data-ttu-id="59ba5-108">\<declaredTypes > 요소</span><span class="sxs-lookup"><span data-stu-id="59ba5-108">\<declaredTypes> Element</span></span>  
<span data-ttu-id="59ba5-109">\<추가 >의 \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="59ba5-109">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="59ba5-110">\<knownType > 요소</span><span class="sxs-lookup"><span data-stu-id="59ba5-110">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59ba5-111">구문</span><span class="sxs-lookup"><span data-stu-id="59ba5-111">Syntax</span></span>  
  
```xml  
<knownType type="String">  
     <parameter index="Integer"  
                type="String" />  
</knownType>  
```  
  
## <a name="type"></a><span data-ttu-id="59ba5-112">형식</span><span class="sxs-lookup"><span data-stu-id="59ba5-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59ba5-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="59ba5-113">Attributes and Elements</span></span>  
 <span data-ttu-id="59ba5-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba5-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59ba5-115">특성</span><span class="sxs-lookup"><span data-stu-id="59ba5-115">Attributes</span></span>  
  
|<span data-ttu-id="59ba5-116">특성</span><span class="sxs-lookup"><span data-stu-id="59ba5-116">Attribute</span></span>|<span data-ttu-id="59ba5-117">설명</span><span class="sxs-lookup"><span data-stu-id="59ba5-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59ba5-118">형식</span><span class="sxs-lookup"><span data-stu-id="59ba5-118">type</span></span>|<span data-ttu-id="59ba5-119">형식(네임스페이스 포함), 어셈블리 이름, 버전, 문화권 및 공개 키 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba5-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59ba5-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="59ba5-120">Child Elements</span></span>  
  
|<span data-ttu-id="59ba5-121">요소</span><span class="sxs-lookup"><span data-stu-id="59ba5-121">Element</span></span>|<span data-ttu-id="59ba5-122">설명</span><span class="sxs-lookup"><span data-stu-id="59ba5-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59ba5-123">\<매개 변수 ></span><span class="sxs-lookup"><span data-stu-id="59ba5-123">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="59ba5-124">선언된 형식이 제네릭 형식이면 매개 변수 인덱스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba5-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59ba5-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="59ba5-125">Parent Elements</span></span>  
  
|<span data-ttu-id="59ba5-126">요소</span><span class="sxs-lookup"><span data-stu-id="59ba5-126">Element</span></span>|<span data-ttu-id="59ba5-127">설명</span><span class="sxs-lookup"><span data-stu-id="59ba5-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59ba5-128">\<add></span><span class="sxs-lookup"><span data-stu-id="59ba5-128">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="59ba5-129">선언된 형식을 선언된 형식의 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba5-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59ba5-130">설명</span><span class="sxs-lookup"><span data-stu-id="59ba5-130">Remarks</span></span>  
 <span data-ttu-id="59ba5-131">알려진된 형식에 대 한 자세한 내용은 참조 [데이터 계약 알려진 형식을](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) 및 <xref:System.Runtime.Serialization.DataContractSerializer>합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba5-131">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="59ba5-132">참조는 [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) 이 요소를 사용 하는 예제에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba5-132">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59ba5-133">예</span><span class="sxs-lookup"><span data-stu-id="59ba5-133">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,   
           MyAssembly, Version=2.0.0.0, Culture=neutral,  
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">  
           <knownType type="MyCompany.Library.Circle,   
                      MyAssembly, Version=2.0.0.0, Culture=neutral,  
                      PublicKeyToken=XXXXXX,  
                      processorArchitecture=MSIL"/>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="59ba5-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59ba5-134">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="59ba5-135">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="59ba5-135">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="59ba5-136">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="59ba5-136">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="59ba5-137">\<add></span><span class="sxs-lookup"><span data-stu-id="59ba5-137">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
