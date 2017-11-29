---
title: "&lt;서비스&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: eb292a62c2b042c387799164ff4cec88bd2ca482
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltservicesgt"></a><span data-ttu-id="9c272-102">&lt;서비스&gt;</span><span class="sxs-lookup"><span data-stu-id="9c272-102">&lt;services&gt;</span></span>
<span data-ttu-id="9c272-103">서비스는 구성 파일의 `services` 섹션에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c272-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="9c272-104">서비스별로 해당 `service` 구성 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c272-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="9c272-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9c272-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c272-106">구문</span><span class="sxs-lookup"><span data-stu-id="9c272-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c272-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9c272-107">Attributes and Elements</span></span>  
 <span data-ttu-id="9c272-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9c272-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c272-109">특성</span><span class="sxs-lookup"><span data-stu-id="9c272-109">Attributes</span></span>  
 <span data-ttu-id="9c272-110">없음</span><span class="sxs-lookup"><span data-stu-id="9c272-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9c272-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9c272-111">Child Elements</span></span>  
  
|<span data-ttu-id="9c272-112">요소</span><span class="sxs-lookup"><span data-stu-id="9c272-112">Element</span></span>|<span data-ttu-id="9c272-113">설명</span><span class="sxs-lookup"><span data-stu-id="9c272-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c272-114">\<서비스 ></span><span class="sxs-lookup"><span data-stu-id="9c272-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="9c272-115">특정 서비스의 서비스 계약, 동작 및 끝점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9c272-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9c272-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9c272-116">Parent Elements</span></span>  
  
|<span data-ttu-id="9c272-117">요소</span><span class="sxs-lookup"><span data-stu-id="9c272-117">Element</span></span>|<span data-ttu-id="9c272-118">설명</span><span class="sxs-lookup"><span data-stu-id="9c272-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c272-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9c272-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="9c272-120">모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9c272-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c272-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c272-121">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServicesSection>
