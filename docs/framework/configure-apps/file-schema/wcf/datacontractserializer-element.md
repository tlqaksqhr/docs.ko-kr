---
title: '&lt;dataContractSerializer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4ba6a70f6d618446ed3ffd446c06c8f3c88354ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltdatacontractserializergt"></a><span data-ttu-id="1736d-102">&lt;dataContractSerializer&gt;</span><span class="sxs-lookup"><span data-stu-id="1736d-102">&lt;dataContractSerializer&gt;</span></span>
<span data-ttu-id="1736d-103"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1736d-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="1736d-104">이 요소는 서로 다른 두 가지 계층 구조에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1736d-104">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="1736d-105">하나는 다음 스키마 계층 구조 부분에 나열되고 다른 하나는 설명 부분에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="1736d-105">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="1736d-106">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1736d-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="1736d-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="1736d-107">\<behaviors></span></span>  
<span data-ttu-id="1736d-108">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1736d-108">\<serviceBehaviors></span></span>  
<span data-ttu-id="1736d-109">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="1736d-109">\<behavior></span></span>  
<span data-ttu-id="1736d-110">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="1736d-110">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1736d-111">구문</span><span class="sxs-lookup"><span data-stu-id="1736d-111">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
   maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1736d-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1736d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1736d-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1736d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1736d-114">특성</span><span class="sxs-lookup"><span data-stu-id="1736d-114">Attributes</span></span>  
  
|<span data-ttu-id="1736d-115">요소</span><span class="sxs-lookup"><span data-stu-id="1736d-115">Element</span></span>|<span data-ttu-id="1736d-116">설명</span><span class="sxs-lookup"><span data-stu-id="1736d-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1736d-117">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="1736d-117">ignoreExtensionDataObject</span></span>|<span data-ttu-id="1736d-118">끝점이 serialize되거나 deserialize될 때 해당 끝점에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1736d-118">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="1736d-119">이 특성은 `<dataContractSerializer>` 요소의 `<behavior>`에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1736d-119">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="1736d-120">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="1736d-120">maxItemsInObjectGraph</span></span>|<span data-ttu-id="1736d-121">serialize 또는 deserialize할 항목의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="1736d-121">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="1736d-122">이 특성은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="1736d-122">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1736d-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1736d-123">Child Elements</span></span>  
 <span data-ttu-id="1736d-124">없음</span><span class="sxs-lookup"><span data-stu-id="1736d-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1736d-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1736d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="1736d-126">요소</span><span class="sxs-lookup"><span data-stu-id="1736d-126">Element</span></span>|<span data-ttu-id="1736d-127">설명</span><span class="sxs-lookup"><span data-stu-id="1736d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1736d-128">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="1736d-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="1736d-129">서비스의 동작에 대한 설정 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1736d-129">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="1736d-130">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="1736d-130">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="1736d-131"><xref:System.Runtime.Serialization> 네임스페이스 섹션의 루트 요소를 나타내며 <xref:System.Runtime.Serialization.DataContractSerializer>의 옵션을 설정하기 위한 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1736d-131">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1736d-132">설명</span><span class="sxs-lookup"><span data-stu-id="1736d-132">Remarks</span></span>  
 <span data-ttu-id="1736d-133">이는 두 번째 계층 구조는이 항목의 소개 부분에서 설명 했 듯이 \<X509Extension > 요소가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1736d-133">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="1736d-134">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="1736d-134">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="1736d-135">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="1736d-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="1736d-136">알려진 형식에 대한 자세한 내용은 <xref:System.Runtime.Serialization.DataContractSerializer>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1736d-136">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1736d-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1736d-137">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="1736d-138">데이터 계약 알려진된 형식</span><span class="sxs-lookup"><span data-stu-id="1736d-138">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="1736d-139">데이터 전송 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="1736d-139">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
