---
title: '&lt;dynamicEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: 215bc9d8540b2d782a0c63f2f5be96f6fcde6812
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746763"
---
# <a name="ltdynamicendpointgt"></a><span data-ttu-id="03248-102">&lt;dynamicEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="03248-102">&lt;dynamicEndpoint&gt;</span></span>
<span data-ttu-id="03248-103">이 구성 요소는 응용 프로그램이 런타임에 끝점 주소를 동적으로 찾을 수 있는 클라이언트 프로그램으로 기능하도록 설정하기 위한 정보를 포함하는 표준 끝점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="03248-103">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="03248-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="03248-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="03248-105">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="03248-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03248-106">구문</span><span class="sxs-lookup"><span data-stu-id="03248-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03248-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="03248-107">Attributes and Elements</span></span>  
 <span data-ttu-id="03248-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="03248-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03248-109">특성</span><span class="sxs-lookup"><span data-stu-id="03248-109">Attributes</span></span>  
 <span data-ttu-id="03248-110">없음</span><span class="sxs-lookup"><span data-stu-id="03248-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="03248-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="03248-111">Child Elements</span></span>  
  
|<span data-ttu-id="03248-112">요소</span><span class="sxs-lookup"><span data-stu-id="03248-112">Element</span></span>|<span data-ttu-id="03248-113">설명</span><span class="sxs-lookup"><span data-stu-id="03248-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03248-114">\<discoveryClientSettings ></span><span class="sxs-lookup"><span data-stu-id="03248-114">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="03248-115">응용 프로그램에서 서비스 검색 프로세스에 클라이언트로 참여하기 위해 필요한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="03248-115">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03248-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="03248-116">Parent Elements</span></span>  
  
|<span data-ttu-id="03248-117">요소</span><span class="sxs-lookup"><span data-stu-id="03248-117">Element</span></span>|<span data-ttu-id="03248-118">설명</span><span class="sxs-lookup"><span data-stu-id="03248-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03248-119">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="03248-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="03248-120">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 끝점인 표준 끝점의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="03248-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03248-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03248-121">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
