---
title: '&lt;dynamicEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e24d340364f126d9cf33295d6d36d1b686065a76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltdynamicendpointgt"></a><span data-ttu-id="6be29-102">&lt;dynamicEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="6be29-102">&lt;dynamicEndpoint&gt;</span></span>
<span data-ttu-id="6be29-103">이 구성 요소는 응용 프로그램이 런타임에 끝점 주소를 동적으로 찾을 수 있는 클라이언트 프로그램으로 기능하도록 설정하기 위한 정보를 포함하는 표준 끝점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6be29-103">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="6be29-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6be29-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6be29-105">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="6be29-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6be29-106">구문</span><span class="sxs-lookup"><span data-stu-id="6be29-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
      <discoveryClientSettings discoveryEndpoint="String">
        <findCriteria duration="TimeSpan" 
                      maxResults="Integer" 
                      scopeMatchBy="Uri">
          <contractTypeNames>
            <add name="String" namespace="String" />
          <contractTypeNames>
          <extensions />
          <scopes>
            <add scope="URI" />
          </scopes>
        </findCriteria>
      </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6be29-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6be29-107">Attributes and Elements</span></span>  
 <span data-ttu-id="6be29-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6be29-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6be29-109">특성</span><span class="sxs-lookup"><span data-stu-id="6be29-109">Attributes</span></span>  
 <span data-ttu-id="6be29-110">없음</span><span class="sxs-lookup"><span data-stu-id="6be29-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6be29-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6be29-111">Child Elements</span></span>  
  
|<span data-ttu-id="6be29-112">요소</span><span class="sxs-lookup"><span data-stu-id="6be29-112">Element</span></span>|<span data-ttu-id="6be29-113">설명</span><span class="sxs-lookup"><span data-stu-id="6be29-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6be29-114">\<discoveryClientSettings ></span><span class="sxs-lookup"><span data-stu-id="6be29-114">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="6be29-115">응용 프로그램에서 서비스 검색 프로세스에 클라이언트로 참여하기 위해 필요한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6be29-115">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6be29-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6be29-116">Parent Elements</span></span>  
  
|<span data-ttu-id="6be29-117">요소</span><span class="sxs-lookup"><span data-stu-id="6be29-117">Element</span></span>|<span data-ttu-id="6be29-118">설명</span><span class="sxs-lookup"><span data-stu-id="6be29-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6be29-119">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="6be29-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="6be29-120">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 끝점인 표준 끝점의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="6be29-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6be29-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6be29-121">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
