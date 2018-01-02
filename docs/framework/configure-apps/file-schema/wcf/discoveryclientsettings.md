---
title: '&lt;discoveryClientSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0bcd70df9809288987636f7766d6d4887dec84d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltdiscoveryclientsettingsgt"></a><span data-ttu-id="5b5e9-102">&lt;discoveryClientSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="5b5e9-102">&lt;discoveryClientSettings&gt;</span></span>
<span data-ttu-id="5b5e9-103">응용 프로그램에서 서비스 검색 프로세스에 클라이언트로 참여하기 위해 필요한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b5e9-103">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="5b5e9-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5b5e9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5b5e9-105">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="5b5e9-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b5e9-106">구문</span><span class="sxs-lookup"><span data-stu-id="5b5e9-106">Syntax</span></span>  
  
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
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b5e9-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5b5e9-107">Attributes and Elements</span></span>  
 <span data-ttu-id="5b5e9-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5b5e9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b5e9-109">특성</span><span class="sxs-lookup"><span data-stu-id="5b5e9-109">Attributes</span></span>  
  
|<span data-ttu-id="5b5e9-110">특성</span><span class="sxs-lookup"><span data-stu-id="5b5e9-110">Attribute</span></span>|<span data-ttu-id="5b5e9-111">설명</span><span class="sxs-lookup"><span data-stu-id="5b5e9-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5b5e9-112">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="5b5e9-112">discoveryEndpoint</span></span>|<span data-ttu-id="5b5e9-113">클라이언트 응용 프로그램에서 런타임에 검색 가능한 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 검색 끝점의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5b5e9-113">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b5e9-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5b5e9-114">Child Elements</span></span>  
  
|<span data-ttu-id="5b5e9-115">요소</span><span class="sxs-lookup"><span data-stu-id="5b5e9-115">Element</span></span>|<span data-ttu-id="5b5e9-116">설명</span><span class="sxs-lookup"><span data-stu-id="5b5e9-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b5e9-117">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="5b5e9-117">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="5b5e9-118">클라이언트 응용 프로그램에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5b5e9-118">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="5b5e9-119">기준을 검색 조건 (찾으려는 서비스 지정)으로 그룹화 할 수 및 찾기 종료 조건 (검색 지속 기간).</span><span class="sxs-lookup"><span data-stu-id="5b5e9-119">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5b5e9-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5b5e9-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5b5e9-121">요소</span><span class="sxs-lookup"><span data-stu-id="5b5e9-121">Element</span></span>|<span data-ttu-id="5b5e9-122">설명</span><span class="sxs-lookup"><span data-stu-id="5b5e9-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b5e9-123">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="5b5e9-123">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="5b5e9-124">응용 프로그램이 런타임에 끝점 주소를 동적으로 찾을 수 있는 클라이언트 프로그램으로 기능하도록 설정하기 위한 정보를 포함하는 표준 끝점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5b5e9-124">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b5e9-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b5e9-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
