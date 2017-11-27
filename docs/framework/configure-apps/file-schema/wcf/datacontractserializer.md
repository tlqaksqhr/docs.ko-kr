---
title: dataContractSerializer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4044e81b7c33c7a755678e79586dd4f37cf54ed5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="datacontractserializer"></a><span data-ttu-id="d3ff4-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="d3ff4-102">dataContractSerializer</span></span>
<span data-ttu-id="d3ff4-103"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ff4-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="d3ff4-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d3ff4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d3ff4-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d3ff4-105">\<behaviors></span></span>  
<span data-ttu-id="d3ff4-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d3ff4-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="d3ff4-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d3ff4-107">\<behavior></span></span>  
<span data-ttu-id="d3ff4-108">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="d3ff4-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3ff4-109">구문</span><span class="sxs-lookup"><span data-stu-id="d3ff4-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3ff4-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d3ff4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d3ff4-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ff4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3ff4-112">특성</span><span class="sxs-lookup"><span data-stu-id="d3ff4-112">Attributes</span></span>  
  
|<span data-ttu-id="d3ff4-113">요소</span><span class="sxs-lookup"><span data-stu-id="d3ff4-113">Element</span></span>|<span data-ttu-id="d3ff4-114">설명</span><span class="sxs-lookup"><span data-stu-id="d3ff4-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d3ff4-115">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="d3ff4-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="d3ff4-116">끝점이 serialize되거나 deserialize될 때 해당 끝점에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ff4-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="d3ff4-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="d3ff4-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="d3ff4-118">serialize 또는 deserialize할 항목의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ff4-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3ff4-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d3ff4-119">Child Elements</span></span>  
 <span data-ttu-id="d3ff4-120">없음</span><span class="sxs-lookup"><span data-stu-id="d3ff4-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d3ff4-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d3ff4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d3ff4-122">요소</span><span class="sxs-lookup"><span data-stu-id="d3ff4-122">Element</span></span>|<span data-ttu-id="d3ff4-123">설명</span><span class="sxs-lookup"><span data-stu-id="d3ff4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3ff4-124">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d3ff4-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d3ff4-125">끝점 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ff4-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3ff4-126">설명</span><span class="sxs-lookup"><span data-stu-id="d3ff4-126">Remarks</span></span>  
 <span data-ttu-id="d3ff4-127">알려진 형식에 대한 자세한 내용은 <xref:System.Runtime.Serialization.DataContractSerializer> 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3ff4-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="d3ff4-128">`<dataContractSerializer>` 동작 요소(있는 경우)는 항상 구성 파일에서 `<enableWebScript>` 동작 요소 앞에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ff4-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="d3ff4-129">그렇지 않으면 결과 동작이 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ff4-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ff4-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3ff4-130">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="d3ff4-131">데이터 계약 알려진된 형식</span><span class="sxs-lookup"><span data-stu-id="d3ff4-131">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="d3ff4-132">데이터 전송 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="d3ff4-132">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
