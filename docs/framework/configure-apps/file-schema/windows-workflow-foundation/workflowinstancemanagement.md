---
title: '&lt;workflowInstanceManagement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 28e0f2b0ed88ee73edb52a8c18346746beb34771
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="046ca-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="046ca-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="046ca-103">지속성 예외, 처리되지 않은 예외 동작 및 유휴 동작을 비롯하여 워크플로 인스턴스 실행 방법을 제어하는 설정을 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="046ca-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="046ca-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="046ca-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="046ca-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="046ca-105">\<behaviors></span></span>  
<span data-ttu-id="046ca-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="046ca-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="046ca-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="046ca-107">\<behavior></span></span>  
<span data-ttu-id="046ca-108">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="046ca-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="046ca-109">구문</span><span class="sxs-lookup"><span data-stu-id="046ca-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="046ca-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="046ca-110">Attributes and Elements</span></span>  
 <span data-ttu-id="046ca-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="046ca-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="046ca-112">특성</span><span class="sxs-lookup"><span data-stu-id="046ca-112">Attributes</span></span>  
  
|<span data-ttu-id="046ca-113">특성</span><span class="sxs-lookup"><span data-stu-id="046ca-113">Attribute</span></span>|<span data-ttu-id="046ca-114">설명</span><span class="sxs-lookup"><span data-stu-id="046ca-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="046ca-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="046ca-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="046ca-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="046ca-116">Child Elements</span></span>  
 <span data-ttu-id="046ca-117">없음</span><span class="sxs-lookup"><span data-stu-id="046ca-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="046ca-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="046ca-118">Parent Elements</span></span>  
  
|<span data-ttu-id="046ca-119">요소</span><span class="sxs-lookup"><span data-stu-id="046ca-119">Element</span></span>|<span data-ttu-id="046ca-120">설명</span><span class="sxs-lookup"><span data-stu-id="046ca-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="046ca-121">\<동작 >의 \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="046ca-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="046ca-122">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="046ca-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="046ca-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="046ca-123">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
