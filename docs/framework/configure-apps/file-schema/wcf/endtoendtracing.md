---
title: '&lt;endToEndTracing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a43801f4c45d7ac518c3b24cadc58ffbec40adb4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltendtoendtracinggt"></a><span data-ttu-id="b9d22-102">&lt;endToEndTracing&gt;</span><span class="sxs-lookup"><span data-stu-id="b9d22-102">&lt;endToEndTracing&gt;</span></span>
<span data-ttu-id="b9d22-103">서비스 응용 프로그램 실행 중에 종단 간 추적의 다양한 측면을 사용하거나 사용하지 않도록 설정할 수 있는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b9d22-103">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="b9d22-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b9d22-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b9d22-105">\<진단 ></span><span class="sxs-lookup"><span data-stu-id="b9d22-105">\<diagnostic></span></span>  
<span data-ttu-id="b9d22-106">\<endToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="b9d22-106">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9d22-107">구문</span><span class="sxs-lookup"><span data-stu-id="b9d22-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
   <diagnostics>  
       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9d22-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b9d22-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b9d22-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b9d22-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9d22-110">특성</span><span class="sxs-lookup"><span data-stu-id="b9d22-110">Attributes</span></span>  
  
|<span data-ttu-id="b9d22-111">특성</span><span class="sxs-lookup"><span data-stu-id="b9d22-111">Attribute</span></span>|<span data-ttu-id="b9d22-112">설명</span><span class="sxs-lookup"><span data-stu-id="b9d22-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="b9d22-113">활동 추적 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b9d22-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="b9d22-114">메시지 흐름 추적 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b9d22-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="b9d22-115">propagate 특성을 true로 설정할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b9d22-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9d22-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b9d22-116">Child Elements</span></span>  
 <span data-ttu-id="b9d22-117">없음</span><span class="sxs-lookup"><span data-stu-id="b9d22-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b9d22-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b9d22-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b9d22-119">요소</span><span class="sxs-lookup"><span data-stu-id="b9d22-119">Element</span></span>|<span data-ttu-id="b9d22-120">설명</span><span class="sxs-lookup"><span data-stu-id="b9d22-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9d22-121">\<진단 ></span><span class="sxs-lookup"><span data-stu-id="b9d22-121">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="b9d22-122">관리자의 런타임 검사 및 제어를 위한 WCF 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b9d22-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b9d22-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9d22-123">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>  
 <xref:System.ServiceModel.Configuration.EndToEndTracingElement>  
 [<span data-ttu-id="b9d22-124">종단 간 추적</span><span class="sxs-lookup"><span data-stu-id="b9d22-124">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
