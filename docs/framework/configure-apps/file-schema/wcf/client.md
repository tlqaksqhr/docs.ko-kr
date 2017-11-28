---
title: "&lt;클라이언트&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 67f91f4462fc8c11b1769d5805a4ad1407385a50
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientgt"></a><span data-ttu-id="e998a-102">&lt;클라이언트&gt;</span><span class="sxs-lookup"><span data-stu-id="e998a-102">&lt;client&gt;</span></span>
<span data-ttu-id="e998a-103">`client` 요소는 클라이언트가 연결할 수 있는 끝점 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e998a-103">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="e998a-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e998a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e998a-105">\<클라이언트 ></span><span class="sxs-lookup"><span data-stu-id="e998a-105">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e998a-106">구문</span><span class="sxs-lookup"><span data-stu-id="e998a-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <client>  
        <endpoint>  
        </endpoint>  
                <metadata>  
        </metadata>  
    </client>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e998a-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e998a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e998a-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e998a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e998a-109">특성</span><span class="sxs-lookup"><span data-stu-id="e998a-109">Attributes</span></span>  
 <span data-ttu-id="e998a-110">없음</span><span class="sxs-lookup"><span data-stu-id="e998a-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e998a-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e998a-111">Child Elements</span></span>  
  
|<span data-ttu-id="e998a-112">요소</span><span class="sxs-lookup"><span data-stu-id="e998a-112">Element</span></span>|<span data-ttu-id="e998a-113">설명</span><span class="sxs-lookup"><span data-stu-id="e998a-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e998a-114">\<끝점 ></span><span class="sxs-lookup"><span data-stu-id="e998a-114">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="e998a-115">이 클라이언트가 연결할 수 있는 끝점을 지정하는 끝점 요소 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e998a-115">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="e998a-116">\<메타 데이터 ></span><span class="sxs-lookup"><span data-stu-id="e998a-116">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="e998a-117">메타데이터 처리를 위한 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e998a-117">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e998a-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e998a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e998a-119">요소</span><span class="sxs-lookup"><span data-stu-id="e998a-119">Element</span></span>|<span data-ttu-id="e998a-120">설명</span><span class="sxs-lookup"><span data-stu-id="e998a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e998a-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e998a-121">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="e998a-122">모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e998a-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e998a-123">설명</span><span class="sxs-lookup"><span data-stu-id="e998a-123">Remarks</span></span>  
 <span data-ttu-id="e998a-124">`client` 섹션은 클라이언트가 연결할 수 있는 끝점 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e998a-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="e998a-125">클라이언트 섹션에 나열된 각 끝점은 자체의 바인딩, 동작 및 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e998a-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="e998a-126">각 끝점은 `name` 및 `contract` 특성 조합에 의해 고유하게 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="e998a-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="e998a-127">클라이언트 코드는 클라이언트가 구현하는 서비스에 대한 끝점에 연결하기 위한 `name`을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e998a-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="e998a-128">`name` 특성을 생략하면 끝점은 구현하는 계약에 대한 기본 끝점으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="e998a-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="e998a-129">또한 이 섹션에서는 메타데이터 처리를 위한 설정도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e998a-129">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e998a-130">예제</span><span class="sxs-lookup"><span data-stu-id="e998a-130">Example</span></span>  
  
```xml  
<client>  
    <endpoint address="/HelloWorld/"  
              bindingConfiguration="usingDefaults"  
              name="MyBinding"  
              binding="customBinding"  
              contract="HelloWorld">  
    <addressProperties actingAs="http://www.microsoft.com/TestActor"  
             identityData="BasicReadWrite" identityType="Spn" isAddressPrivate="false">  
    </endpoint>  
</client>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e998a-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e998a-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 [<span data-ttu-id="e998a-132">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="e998a-132">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="e998a-133">클라이언트</span><span class="sxs-lookup"><span data-stu-id="e998a-133">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
