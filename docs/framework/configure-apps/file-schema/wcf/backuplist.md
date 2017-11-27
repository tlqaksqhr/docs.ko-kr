---
title: '&lt;backupList&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e9f8138f2a2448293e1f26da5f7d0562b1338b7d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltbackuplistgt"></a><span data-ttu-id="ed064-102">&lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="ed064-102">&lt;backupList&gt;</span></span>
<span data-ttu-id="ed064-103">라우팅 서비스는 기본 끝점 도달할 수 없는 경우 사용 하도록 할 끝점 집합을 열거 하는 백업 목록을 정의 하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ed064-103">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="ed064-104">목록의 첫 번째 끝점이 다운되는 경우 라우팅 서비스는 자동으로 목록의 다음 끝점으로 장애 조치(failover)됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed064-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="ed064-105">따라서 복잡한 패턴을 처리하는 방법이나 모든 서비스가 배포되는 위치를 클라이언트 응용 프로그램에 지정할 필요 없이 응용 프로그램의 안정성을 빠르게 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed064-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="ed064-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="ed064-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ed064-107">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="ed064-107">\<routing></span></span>  
<span data-ttu-id="ed064-108">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="ed064-108">\<backupLists></span></span>  
<span data-ttu-id="ed064-109">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="ed064-109">\<backupList></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed064-110">구문</span><span class="sxs-lookup"><span data-stu-id="ed064-110">Syntax</span></span>  
  
```xml 
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ed064-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ed064-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ed064-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed064-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed064-113">특성</span><span class="sxs-lookup"><span data-stu-id="ed064-113">Attributes</span></span>  
  
|<span data-ttu-id="ed064-114">특성</span><span class="sxs-lookup"><span data-stu-id="ed064-114">Attribute</span></span>|<span data-ttu-id="ed064-115">설명</span><span class="sxs-lookup"><span data-stu-id="ed064-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ed064-116">name</span><span class="sxs-lookup"><span data-stu-id="ed064-116">name</span></span>|<span data-ttu-id="ed064-117">이 끝점 목록을 식별하는 데 사용되는 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ed064-117">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ed064-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ed064-118">Child Elements</span></span>  
  
|<span data-ttu-id="ed064-119">요소</span><span class="sxs-lookup"><span data-stu-id="ed064-119">Element</span></span>|<span data-ttu-id="ed064-120">설명</span><span class="sxs-lookup"><span data-stu-id="ed064-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed064-121">\<filter></span><span class="sxs-lookup"><span data-stu-id="ed064-121">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="ed064-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ed064-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ed064-123">요소</span><span class="sxs-lookup"><span data-stu-id="ed064-123">Element</span></span>|<span data-ttu-id="ed064-124">설명</span><span class="sxs-lookup"><span data-stu-id="ed064-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed064-125">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="ed064-125">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="ed064-126">백업 끝점의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ed064-126">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed064-127">설명</span><span class="sxs-lookup"><span data-stu-id="ed064-127">Remarks</span></span>  
 <span data-ttu-id="ed064-128">이 섹션에는 기본 끝점으로 메시지를 보낼 때 통신 예외가 발생하면 이 메시지를 전송할 끝점의 정렬된 컬렉션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed064-128">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="ed064-129">에 나열 된 기본 끝점에 전달 하는 경우는 `endpointName` 특성 [ \<추가 >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) 라우팅 서비스는이 첫 번째 끝점에 메시지를 보내려고 시도 실패 통신 예외가 발생 하 고, 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="ed064-129">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="ed064-130">이것도 통신 예외가 발생하여 실패하는 경우 라우팅 서비스는 보내기가 성공할 때까지, 통신 예외가 아닌 다른 원인으로 보내기가 실패할 때까지 또는 컬렉션의 모든 끝점에 대한 보내기가 실패할 때까지 이 섹션에 포함된 다음 끝점으로 메시지를 보내려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="ed064-130">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="ed064-131">다음 예제에서는 "Destination" 이라는 기본 끝점으로 보내기 통신 예외가 반환 하는 경우 서비스를 "alternateservicequeue"로 메시지를 보내려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed064-131">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="ed064-132">이 시도에 대해서도 통신 예외가 반환되면 라우팅 서비스는 컬렉션의 다음 끝점으로 메시지를 보내려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="ed064-132">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="MatchAllFilter1" endpointName="Destination" backupList="backupEndpointList"/>  
     </filterTable>  
</filterTables>  
<backupLists>  
     <backupList name="backupEndpointList">  
          <add endpointName="backupServiceQueue" />  
          <add endpointName="alternateServiceQueue" />  
     </backupList>  
</backupLists>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed064-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed064-133">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
