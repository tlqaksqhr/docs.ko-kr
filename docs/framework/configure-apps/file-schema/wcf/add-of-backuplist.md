---
title: "&lt;backupList&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b93b442d21d34eea5031cea565bdcf62139abc81
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="84992-102">&lt;backupList&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="84992-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="84992-103">백업 끝점 요소를 정의하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84992-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="84992-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="84992-104">\<system.serviceModel></span></span>  
<span data-ttu-id="84992-105">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="84992-105">\<routing></span></span>  
<span data-ttu-id="84992-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="84992-106">\<backupLists></span></span>  
<span data-ttu-id="84992-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="84992-107">\<backupList></span></span>  
<span data-ttu-id="84992-108">\<add></span><span class="sxs-lookup"><span data-stu-id="84992-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84992-109">구문</span><span class="sxs-lookup"><span data-stu-id="84992-109">Syntax</span></span>  
  
```xml  
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84992-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="84992-110">Attributes and Elements</span></span>  
 <span data-ttu-id="84992-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84992-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84992-112">특성</span><span class="sxs-lookup"><span data-stu-id="84992-112">Attributes</span></span>  
  
|<span data-ttu-id="84992-113">특성</span><span class="sxs-lookup"><span data-stu-id="84992-113">Attribute</span></span>|<span data-ttu-id="84992-114">설명</span><span class="sxs-lookup"><span data-stu-id="84992-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="84992-115">name</span><span class="sxs-lookup"><span data-stu-id="84992-115">name</span></span>|<span data-ttu-id="84992-116">백업 끝점의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="84992-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84992-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="84992-117">Child Elements</span></span>  
 <span data-ttu-id="84992-118">없음</span><span class="sxs-lookup"><span data-stu-id="84992-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="84992-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="84992-119">Parent Elements</span></span>  
  
|<span data-ttu-id="84992-120">요소</span><span class="sxs-lookup"><span data-stu-id="84992-120">Element</span></span>|<span data-ttu-id="84992-121">설명</span><span class="sxs-lookup"><span data-stu-id="84992-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84992-122">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="84992-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="84992-123">라우팅 서비스는 기본 끝점 도달할 수 없는 경우 사용 하도록 선택 하는 끝점의 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="84992-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84992-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84992-124">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType> 
