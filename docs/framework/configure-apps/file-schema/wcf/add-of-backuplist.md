---
title: '&lt;backupList&gt;의 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 7e7361b24c0444b5f3d51a6f5bf079d5eb2dee18
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745554"
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="1d5e6-102">&lt;backupList&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="1d5e6-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="1d5e6-103">백업 끝점 요소를 정의하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d5e6-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="1d5e6-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1d5e6-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1d5e6-105">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="1d5e6-105">\<routing></span></span>  
<span data-ttu-id="1d5e6-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="1d5e6-106">\<backupLists></span></span>  
<span data-ttu-id="1d5e6-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="1d5e6-107">\<backupList></span></span>  
<span data-ttu-id="1d5e6-108">\<add></span><span class="sxs-lookup"><span data-stu-id="1d5e6-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d5e6-109">구문</span><span class="sxs-lookup"><span data-stu-id="1d5e6-109">Syntax</span></span>  
  
```xml  
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d5e6-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1d5e6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1d5e6-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d5e6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d5e6-112">특성</span><span class="sxs-lookup"><span data-stu-id="1d5e6-112">Attributes</span></span>  
  
|<span data-ttu-id="1d5e6-113">특성</span><span class="sxs-lookup"><span data-stu-id="1d5e6-113">Attribute</span></span>|<span data-ttu-id="1d5e6-114">설명</span><span class="sxs-lookup"><span data-stu-id="1d5e6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1d5e6-115">name</span><span class="sxs-lookup"><span data-stu-id="1d5e6-115">name</span></span>|<span data-ttu-id="1d5e6-116">백업 끝점의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1d5e6-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d5e6-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1d5e6-117">Child Elements</span></span>  
 <span data-ttu-id="1d5e6-118">없음</span><span class="sxs-lookup"><span data-stu-id="1d5e6-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1d5e6-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1d5e6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1d5e6-120">요소</span><span class="sxs-lookup"><span data-stu-id="1d5e6-120">Element</span></span>|<span data-ttu-id="1d5e6-121">설명</span><span class="sxs-lookup"><span data-stu-id="1d5e6-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d5e6-122">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="1d5e6-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="1d5e6-123">라우팅 서비스는 기본 끝점 도달할 수 없는 경우 사용 하도록 선택 하는 끝점의 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d5e6-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1d5e6-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d5e6-124">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType> 
