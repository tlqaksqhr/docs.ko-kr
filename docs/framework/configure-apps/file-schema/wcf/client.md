---
title: '&lt;클라이언트&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: b8a006d3dee4149569b3f5b573d9d765504b0d65
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltclientgt"></a><span data-ttu-id="8d87d-102">&lt;클라이언트&gt;</span><span class="sxs-lookup"><span data-stu-id="8d87d-102">&lt;client&gt;</span></span>
<span data-ttu-id="8d87d-103">`client` 요소는 클라이언트가 연결할 수 있는 끝점 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8d87d-103">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="8d87d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8d87d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8d87d-105">\<client></span><span class="sxs-lookup"><span data-stu-id="8d87d-105">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d87d-106">구문</span><span class="sxs-lookup"><span data-stu-id="8d87d-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d87d-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8d87d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8d87d-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d87d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d87d-109">특성</span><span class="sxs-lookup"><span data-stu-id="8d87d-109">Attributes</span></span>  
 <span data-ttu-id="8d87d-110">없음</span><span class="sxs-lookup"><span data-stu-id="8d87d-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8d87d-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8d87d-111">Child Elements</span></span>  
  
|<span data-ttu-id="8d87d-112">요소</span><span class="sxs-lookup"><span data-stu-id="8d87d-112">Element</span></span>|<span data-ttu-id="8d87d-113">설명</span><span class="sxs-lookup"><span data-stu-id="8d87d-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d87d-114">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="8d87d-114">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="8d87d-115">이 클라이언트가 연결할 수 있는 끝점을 지정하는 끝점 요소 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8d87d-115">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="8d87d-116">\<메타 데이터 ></span><span class="sxs-lookup"><span data-stu-id="8d87d-116">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="8d87d-117">메타데이터 처리를 위한 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8d87d-117">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8d87d-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8d87d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8d87d-119">요소</span><span class="sxs-lookup"><span data-stu-id="8d87d-119">Element</span></span>|<span data-ttu-id="8d87d-120">설명</span><span class="sxs-lookup"><span data-stu-id="8d87d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d87d-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8d87d-121">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="8d87d-122">모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8d87d-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d87d-123">설명</span><span class="sxs-lookup"><span data-stu-id="8d87d-123">Remarks</span></span>  
 <span data-ttu-id="8d87d-124">`client` 섹션은 클라이언트가 연결할 수 있는 끝점 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8d87d-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="8d87d-125">클라이언트 섹션에 나열된 각 끝점은 자체의 바인딩, 동작 및 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8d87d-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="8d87d-126">각 끝점은 `name` 및 `contract` 특성 조합에 의해 고유하게 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d87d-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="8d87d-127">클라이언트 코드는 클라이언트가 구현하는 서비스에 대한 끝점에 연결하기 위한 `name`을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d87d-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="8d87d-128">`name` 특성을 생략하면 끝점은 구현하는 계약에 대한 기본 끝점으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="8d87d-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="8d87d-129">또한 이 섹션에서는 메타데이터 처리를 위한 설정도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d87d-129">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d87d-130">예제</span><span class="sxs-lookup"><span data-stu-id="8d87d-130">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8d87d-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d87d-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 [<span data-ttu-id="8d87d-132">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="8d87d-132">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="8d87d-133">클라이언트</span><span class="sxs-lookup"><span data-stu-id="8d87d-133">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
