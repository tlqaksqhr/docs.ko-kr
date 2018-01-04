---
title: "사용자 지정 활동 디자인 및 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d162635a82027d1aaa46545dabad3e103d0f339c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="designing-and-implementing-custom-activities"></a><span data-ttu-id="58c6c-102">사용자 지정 활동 디자인 및 구현</span><span class="sxs-lookup"><span data-stu-id="58c6c-102">Designing and Implementing Custom Activities</span></span>
<span data-ttu-id="58c6c-103">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]에서는 시스템 제공 활동을 복합 활동으로 어셈블하거나 <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> 또는 <xref:System.Activities.NativeActivity>에서 파생된 새 형식을 만들어 사용자 지정 활동을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="58c6c-103">Custom activities in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] are created by either assembling system-provided activities into composite activities or by creating new types that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="58c6c-104">이 단원에서는 이 메서드 중 하나를 사용하여 사용자 지정 활동을 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58c6c-104">This section describes how to create custom activities with either method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="58c6c-105">기본적으로 사용자 지정 활동은 Workflow Designer에 활동 이름과 함께 간단한 사각형으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="58c6c-105">Custom activities by default display within the workflow designer as a simple rectangle with the activity’s name.</span></span> <span data-ttu-id="58c6c-106">워크플로 디자이너에서 활동이 표시되는 모양을 사용자 지정하려면 사용자 지정 디자이너도 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58c6c-106">To provide a custom visual representation of your activity in the workflow designer you must also create a custom designer.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="58c6c-107">[사용자 지정 활동 디자이너와 템플릿을 사용 하 여](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="58c6c-107"> [Using Custom Activity Designers and Templates](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="58c6c-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="58c6c-108">In This Section</span></span>  
 [<span data-ttu-id="58c6c-109">활동 제작 옵션</span><span class="sxs-lookup"><span data-stu-id="58c6c-109">Activity Authoring Options</span></span>](../../../docs/framework/windows-workflow-foundation/activity-authoring-options-in-wf.md)  
 <span data-ttu-id="58c6c-110">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]에서 사용할 수 있는 제작 스타일에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58c6c-110">Discusses the authoring styles available in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="58c6c-111">사용자 지정 활동 사용</span><span class="sxs-lookup"><span data-stu-id="58c6c-111">Using a custom activity</span></span>](../../../docs/framework/windows-workflow-foundation/using-a-custom-activity.md)  
 <span data-ttu-id="58c6c-112">워크플로 프로젝트에 사용자 지정 활동을 추가하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58c6c-112">Describes how to add a custom activity to a workflow project.</span></span>  
  
  [<span data-ttu-id="58c6c-113">비동기 활동 만들기</span><span class="sxs-lookup"><span data-stu-id="58c6c-113">Creating Asynchronous Activities</span></span>](../../../docs/framework/windows-workflow-foundation/creating-asynchronous-activities-in-wf.md)  
 <span data-ttu-id="58c6c-114">비동기 활동을 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58c6c-114">Describes how to create asynchronous activities.</span></span>  
  
 [<span data-ttu-id="58c6c-115">활동 유효성 검사 구성</span><span class="sxs-lookup"><span data-stu-id="58c6c-115">Configuring Activity Validation</span></span>](../../../docs/framework/windows-workflow-foundation/configuring-activity-validation.md)  
 <span data-ttu-id="58c6c-116">활동을 실행하기 전에 활동 유효성 검사를 사용하여 활동 구성 오류를 식별하고 보고하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58c6c-116">Describes how activity validation can be used to identify and report errors in an activity’s configuration prior to its execution.</span></span>  
  
 [<span data-ttu-id="58c6c-117">런타임에 활동 만들기</span><span class="sxs-lookup"><span data-stu-id="58c6c-117">Creating an Activity at Runtime</span></span>](../../../docs/framework/windows-workflow-foundation/creating-an-activity-at-runtime-with-dynamicactivity.md)  
 <span data-ttu-id="58c6c-118">런타임에 <xref:System.Activities.DynamicActivity>를 사용하여 활동을 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58c6c-118">Discusses how to create activities at runtime using <xref:System.Activities.DynamicActivity>.</span></span>  
  
 [<span data-ttu-id="58c6c-119">워크플로 실행 속성</span><span class="sxs-lookup"><span data-stu-id="58c6c-119">Workflow Execution Properties</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-execution-properties.md)  
 <span data-ttu-id="58c6c-120">워크플로 실행 속성을 사용하여 활동 환경에 컨텍스트별 속성을 추가하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58c6c-120">Describes how to use workflow execution properties to add context specific properties to an activity’s environment</span></span>  
  
 [<span data-ttu-id="58c6c-121">활동 대리자 사용</span><span class="sxs-lookup"><span data-stu-id="58c6c-121">Using Activity Delegates</span></span>](../../../docs/framework/windows-workflow-foundation/using-activity-delegates.md)  
 <span data-ttu-id="58c6c-122">활동 대리자가 포함된 활동을 작성하고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58c6c-122">Discusses how to author and use activities that contain activity delegates.</span></span>  
  
 [<span data-ttu-id="58c6c-123">활동 지역화</span><span class="sxs-lookup"><span data-stu-id="58c6c-123">Activity Localization</span></span>](../../../docs/framework/windows-workflow-foundation/activity-localization.md)  
 <span data-ttu-id="58c6c-124">활동에서 문자열 리소스의 지역화를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58c6c-124">Describes how to use localization of string resources in activities.</span></span>  
  
 [<span data-ttu-id="58c6c-125">활동 확장명 사용</span><span class="sxs-lookup"><span data-stu-id="58c6c-125">Using Activity Extensions</span></span>](../../../docs/framework/windows-workflow-foundation/using-activity-extensions.md)  
 <span data-ttu-id="58c6c-126">활동 확장을 작성하고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58c6c-126">Describes how to author and use activity extensions.</span></span>  
  
 [<span data-ttu-id="58c6c-127">워크플로에서 OData 피드 사용</span><span class="sxs-lookup"><span data-stu-id="58c6c-127">Consuming OData Feeds from a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/consuming-odata-feeds-from-a-workflow.md)  
 <span data-ttu-id="58c6c-128">워크플로에서 WCF Data Service를 호출하는 여러 가지 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58c6c-128">Describes several methods for calling a WCF Data Service from a workflow.</span></span>  
  
 [<span data-ttu-id="58c6c-129">활동 정의 범위 지정 및 표시 유형</span><span class="sxs-lookup"><span data-stu-id="58c6c-129">Activity Definition Scoping and Visibility</span></span>](../../../docs/framework/windows-workflow-foundation/activity-definition-scoping-and-visibility.md)  
 <span data-ttu-id="58c6c-130">활동에 대한 데이터 범위와 멤버 표시 유형을 정의하는 옵션 및 규칙에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58c6c-130">Describes the options and rules for defining data scoping and member visibility for activities.</span></span>
