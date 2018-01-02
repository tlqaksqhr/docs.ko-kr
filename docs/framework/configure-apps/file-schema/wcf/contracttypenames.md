---
title: '&lt;contractTypeNames&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5ac3a4af54d9f470a1cbd50096731b23d28b0c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcontracttypenamesgt"></a><span data-ttu-id="8e9e7-102">&lt;contractTypeNames&gt;</span><span class="sxs-lookup"><span data-stu-id="8e9e7-102">&lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="8e9e7-103">검색할 서비스의 계약 이름인 계약 형식 이름 목록 및 서비스를 검색할 때 일반적으로 사용되는 기준을 지정하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-103">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="8e9e7-104">둘 이상의 계약 이름이 지정되면 모든 계약과 일치하는 서비스 끝점만 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="8e9e7-105">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]에서는 하나의 끝점이 하나의 계약만 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-105">Note that in [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="8e9e7-106">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8e9e7-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="8e9e7-107">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="8e9e7-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e9e7-108">구문</span><span class="sxs-lookup"><span data-stu-id="8e9e7-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e9e7-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8e9e7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8e9e7-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e9e7-111">특성</span><span class="sxs-lookup"><span data-stu-id="8e9e7-111">Attributes</span></span>  
 <span data-ttu-id="8e9e7-112">없음</span><span class="sxs-lookup"><span data-stu-id="8e9e7-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8e9e7-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8e9e7-113">Child Elements</span></span>  
  
|<span data-ttu-id="8e9e7-114">요소</span><span class="sxs-lookup"><span data-stu-id="8e9e7-114">Element</span></span>|<span data-ttu-id="8e9e7-115">설명</span><span class="sxs-lookup"><span data-stu-id="8e9e7-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e9e7-116">\<add></span><span class="sxs-lookup"><span data-stu-id="8e9e7-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="8e9e7-117">계약 형식 이름은 서비스를 검색할 때 일반적으로 사용되는 조건 집합을 나타나는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-117">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8e9e7-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8e9e7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8e9e7-119">요소</span><span class="sxs-lookup"><span data-stu-id="8e9e7-119">Element</span></span>|<span data-ttu-id="8e9e7-120">설명</span><span class="sxs-lookup"><span data-stu-id="8e9e7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e9e7-121">\<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="8e9e7-121">\<findCriteria></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|<span data-ttu-id="8e9e7-122">클라이언트 응용 프로그램에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-122">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="8e9e7-123">기준을 검색 조건 (찾으려는 서비스 지정)으로 그룹화 할 수 및 찾기 종료 조건 (검색 지속 기간).</span><span class="sxs-lookup"><span data-stu-id="8e9e7-123">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e9e7-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e9e7-124">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
