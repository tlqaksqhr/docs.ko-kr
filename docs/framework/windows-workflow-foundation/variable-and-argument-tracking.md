---
title: "변수 및 인수 추적"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f3d9d30-d899-49aa-b7ce-a8d0d32c4ff0
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 76a9d169b7b8b551685f67288667036ad7b4c87b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="variable-and-argument-tracking"></a><span data-ttu-id="dbe7f-102">변수 및 인수 추적</span><span class="sxs-lookup"><span data-stu-id="dbe7f-102">Variable and Argument Tracking</span></span>
<span data-ttu-id="dbe7f-103">워크플로 실행을 추적할 때 데이터를 추출하는 것이 유용할 때가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-103">When tracking the execution of a workflow, it is often useful to extract data.</span></span> <span data-ttu-id="dbe7f-104">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-104">This provides additional context when accessing a tracking record post execution.</span></span> <span data-ttu-id="dbe7f-105">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]에서는 추적을 통해 워크플로의 활동 범위 내에서 표시 변수 또는 인수를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-105">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], you can extract any visible variable or argument within the scope of any activity in a workflow using tracking.</span></span> <span data-ttu-id="dbe7f-106">추적 프로필을 사용하여 데이터를 쉽게 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-106">Tracking profiles make it easy to extract data.</span></span>  
  
## <a name="variables-and-arguments"></a><span data-ttu-id="dbe7f-107">변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="dbe7f-107">Variables and Arguments</span></span>  
 <span data-ttu-id="dbe7f-108">변수 및 인수는 활동에서 ActivityStateRecord를 내보낼 때 추출됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-108">Variables and arguments are extracted when an activity emits an ActivityStateRecord.</span></span>  <span data-ttu-id="dbe7f-109">변수는 활동 범위 내에 있는 경우에만 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-109">A variable is available for extraction only if it is within the scope of the activity.</span></span> <span data-ttu-id="dbe7f-110">활동 내에서 추출할 변수는 다음과 같은 방식으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-110">A variable to be extracted within an activity is specified in the following manner:</span></span>  
  
-   <span data-ttu-id="dbe7f-111">변수 이름으로 변수를 지정할 경우 추적을 실행하면 추적 중인 현재 활동과 부모 활동에서 변수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-111">If a variable is specified by the variable name, then tracking looks for the variable within the current activity being tracked and in parent activities.</span></span> <span data-ttu-id="dbe7f-112">즉, 현재 활동 범위와 부모 범위에서 변수를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-112">The variable is searched in current activity scope and in parent scope.</span></span>  
  
-   <span data-ttu-id="dbe7f-113">이름을 사용 하 여 추출할 변수를 지정 된 경우 = "*", 추적 되는 현재 활동 내의 모든 변수가 추출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-113">If variables to be extracted are specified by using name="*", then all variables within the current activity being tracked are extracted.</span></span> <span data-ttu-id="dbe7f-114">이 경우 범위 내에 있지만 부모 활동에 정의된 변수는 추출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-114">In this case variables that are in scope but defined in parent activities are not extracted.</span></span>  
  
 <span data-ttu-id="dbe7f-115">인수를 추출할 경우 추출되는 인수는 활동의 상태에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-115">When extracting arguments, the arguments extracted depend on the state of the activity.</span></span> <span data-ttu-id="dbe7f-116">활동 상태가 Executing인 경우 `InArguments`만 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-116">When the state of an activity is Executing, then only the `InArguments` are available for extraction.</span></span> <span data-ttu-id="dbe7f-117">다른 활동 상태(Closed, Faulted, Canceled)인 경우 모든 인수, InArguments 및 OutArguments를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-117">For any other activity state (Closed, Faulted, Canceled), all arguments, both InArguments and OutArguments, are available for extraction.</span></span>  
  
 <span data-ttu-id="dbe7f-118">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-118">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="dbe7f-119">변수 및 인수는 <xref:System.Activities.Tracking.ActivityStateRecord>를 통해서만 추출할 수 있으므로 <xref:System.Activities.Tracking.ActivityStateQuery>를 사용하여 추적 프로필 내에서 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-119">Variables and arguments can be extracted only with an <xref:System.Activities.Tracking.ActivityStateRecord> and thus are subscribed to within a tracking profile using <xref:System.Activities.Tracking.ActivityStateQuery>.</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="protecting-information-stored-within-variables-and-arguments"></a><span data-ttu-id="dbe7f-120">변수 및 인수에 저장된 정보 보호</span><span class="sxs-lookup"><span data-stu-id="dbe7f-120">Protecting Information Stored Within Variables and Arguments</span></span>  
 <span data-ttu-id="dbe7f-121">추적된 변수 또는 인수는 기본적으로 WF 런타임에 의해 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-121">A tracked variable or argument is by default made visible by the WF runtime.</span></span> <span data-ttu-id="dbe7f-122">워크플로 개발자는 다음 단계를 수행하여 해당 변수 또는 인수에 액세스하지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-122">A workflow developer can protect it from being accessed by taking the following steps:</span></span>  
  
1.  <span data-ttu-id="dbe7f-123">변수 값을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-123">Encrypt the value of a variable.</span></span>  
  
2.  <span data-ttu-id="dbe7f-124">추적 프로필 작성을 제어하여 변수 또는 인수 추출을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-124">Control the authoring of a tracking profile to prevent the extraction of a variable or argument.</span></span>  
  
3.  <span data-ttu-id="dbe7f-125">사용자 지정 추적 참가자는 변수 또는 인수에 저장된 중요한 정보가 WF 코드를 통해 공개되지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-125">For custom tracking participants ensure that the WF code does not disclose sensitive information that is stored in variables or arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe7f-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dbe7f-126">See Also</span></span>  
 [<span data-ttu-id="dbe7f-127">Windows Server App Fabric 모니터링</span><span class="sxs-lookup"><span data-stu-id="dbe7f-127">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="dbe7f-128">App Fabric로 응용 프로그램 모니터링</span><span class="sxs-lookup"><span data-stu-id="dbe7f-128">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
