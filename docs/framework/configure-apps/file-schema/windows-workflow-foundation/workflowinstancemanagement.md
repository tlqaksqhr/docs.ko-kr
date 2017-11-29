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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9883cedbbe3657eb82c25abbad66487e39ce2579
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="741ed-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="741ed-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="741ed-103">지속성 예외, 처리되지 않은 예외 동작 및 유휴 동작을 비롯하여 워크플로 인스턴스 실행 방법을 제어하는 설정을 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="741ed-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="741ed-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="741ed-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="741ed-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="741ed-105">\<behaviors></span></span>  
<span data-ttu-id="741ed-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="741ed-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="741ed-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="741ed-107">\<behavior></span></span>  
<span data-ttu-id="741ed-108">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="741ed-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="741ed-109">구문</span><span class="sxs-lookup"><span data-stu-id="741ed-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="741ed-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="741ed-110">Attributes and Elements</span></span>  
 <span data-ttu-id="741ed-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="741ed-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="741ed-112">특성</span><span class="sxs-lookup"><span data-stu-id="741ed-112">Attributes</span></span>  
  
|<span data-ttu-id="741ed-113">특성</span><span class="sxs-lookup"><span data-stu-id="741ed-113">Attribute</span></span>|<span data-ttu-id="741ed-114">설명</span><span class="sxs-lookup"><span data-stu-id="741ed-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="741ed-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="741ed-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="741ed-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="741ed-116">Child Elements</span></span>  
 <span data-ttu-id="741ed-117">없음</span><span class="sxs-lookup"><span data-stu-id="741ed-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="741ed-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="741ed-118">Parent Elements</span></span>  
  
|<span data-ttu-id="741ed-119">요소</span><span class="sxs-lookup"><span data-stu-id="741ed-119">Element</span></span>|<span data-ttu-id="741ed-120">설명</span><span class="sxs-lookup"><span data-stu-id="741ed-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="741ed-121">\<동작 >의 \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="741ed-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="741ed-122">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="741ed-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="741ed-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="741ed-123">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
