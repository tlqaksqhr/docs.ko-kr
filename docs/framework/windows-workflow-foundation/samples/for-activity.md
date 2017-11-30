---
title: "For 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ea751b4-36f0-48aa-a115-70a2ab89f6d8
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e77800b21d671a0de0cab6f442919f50ce5ca51b
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="for-activity"></a><span data-ttu-id="6e547-102">For 활동</span><span class="sxs-lookup"><span data-stu-id="6e547-102">For Activity</span></span>
<span data-ttu-id="6e547-103">For 샘플에서는 <xref:System.Activities.NativeActivity>에서 상속되는 사용자 지정 활동을 빌드한 후 워크플로에서 해당 활동을 사용하여 실제 예제를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e547-103">The For sample demonstrates how to build a custom activity that inherits from <xref:System.Activities.NativeActivity>, and use it in a workflow to execute a real world example.</span></span> <span data-ttu-id="6e547-104">이 샘플에 포함된 사용자 지정 활동은 C# `for` 문처럼 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="6e547-104">The custom activity included in this sample functions like the C# `for` statement.</span></span> <span data-ttu-id="6e547-105">T</span><span class="sxs-lookup"><span data-stu-id="6e547-105">T</span></span>  
  
 <span data-ttu-id="6e547-106">`For` 사용자 지정 활동에는 각각 표준 C# `InitAction` 문의 초기화 문, 반복 문, 연속 조건 및 본문에 해당하는 `IterationAction`, `Condition`, `Body` 및 `For`라는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e547-106">The `For` custom activity has properties named `InitAction`, `IterationAction`, `Condition`, and `Body` that correspond to the initialization statement, iterative statement, continuation condition, and body statement respectively found in the standard C# `For` statement.</span></span>  
  
 <span data-ttu-id="6e547-107">다음 표에서는 샘플의 키 파일에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6e547-107">The following table describes the key files in the sample.</span></span>  
  
|<span data-ttu-id="6e547-108">파일</span><span class="sxs-lookup"><span data-stu-id="6e547-108">File</span></span>|<span data-ttu-id="6e547-109">설명</span><span class="sxs-lookup"><span data-stu-id="6e547-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="6e547-110">For.cs</span><span class="sxs-lookup"><span data-stu-id="6e547-110">For.cs</span></span>|<span data-ttu-id="6e547-111">`For` 클래스를 확장하여 C# <xref:System.Activities.NativeActivity> 문의 기능을 제공하는 `For` 사용자 지정 활동에 대한 클래스 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="6e547-111">Class definition for the `For` custom activity, which extends the <xref:System.Activities.NativeActivity> class to provide the functionality of the C# `For` statement.</span></span>|  
|<span data-ttu-id="6e547-112">Program.cs</span><span class="sxs-lookup"><span data-stu-id="6e547-112">Program.cs</span></span>|<span data-ttu-id="6e547-113">사용자 지정 `For` 활동을 사용하여 컬렉션에 대한 기본 반복 작업을 수행하는 클라이언트 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="6e547-113">A client application that performs basic iterative work on a collection using the custom `For` activity.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="6e547-114">`For` 사용자 지정 활동을 사용할 때는 `Condition` 속성이 설정되어 있는지 확인해야 합니다. 설정되어 있지 않으면 무한 루프가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e547-114">When using the `For` custom activity, ensure that the `Condition` property is set; otherwise an infinite loop could occur.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="6e547-115">세부 항목</span><span class="sxs-lookup"><span data-stu-id="6e547-115">Demonstrates</span></span>  
 <span data-ttu-id="6e547-116"><xref:System.Activities.NativeActivity>에서 상속되는 사용자 지정 활동을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e547-116">Create a custom activity that inherits from <xref:System.Activities.NativeActivity>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="6e547-117">토론</span><span class="sxs-lookup"><span data-stu-id="6e547-117">Discussion</span></span>  
 <span data-ttu-id="6e547-118">다음 표에서는 이 샘플에 포함된 활동의 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6e547-118">The following table describes the properties of the activity included in this sample.</span></span>  
  
 <span data-ttu-id="6e547-119">InitAction</span><span class="sxs-lookup"><span data-stu-id="6e547-119">InitAction</span></span>  
 <span data-ttu-id="6e547-120">초기화 문</span><span class="sxs-lookup"><span data-stu-id="6e547-120">Initialization statement</span></span>  
  
 <span data-ttu-id="6e547-121">IterationAction</span><span class="sxs-lookup"><span data-stu-id="6e547-121">IterationAction</span></span>  
 <span data-ttu-id="6e547-122">반복 문</span><span class="sxs-lookup"><span data-stu-id="6e547-122">Iterative statement</span></span>  
  
 <span data-ttu-id="6e547-123">조건</span><span class="sxs-lookup"><span data-stu-id="6e547-123">Condition</span></span>  
 <span data-ttu-id="6e547-124">연속 문</span><span class="sxs-lookup"><span data-stu-id="6e547-124">Continuation statement</span></span>  
  
 <span data-ttu-id="6e547-125">Body</span><span class="sxs-lookup"><span data-stu-id="6e547-125">Body</span></span>  
 <span data-ttu-id="6e547-126">본문</span><span class="sxs-lookup"><span data-stu-id="6e547-126">Body statement</span></span>  
  
 <span data-ttu-id="6e547-127">활동은 <xref:System.Activities.NativeActivity>에서 상속되어 `ScheduleActivity`의 <xref:System.Activities.NativeActivityContext> 메서드 중 하나를 사용하여 실행할 추가 활동 예약과 같은 런타임 기능에 대한 액세스 권한을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6e547-127">The activity inherits from <xref:System.Activities.NativeActivity> to gain access to runtime features such as scheduling additional activities to run, using one of the `ScheduleActivity` methods of <xref:System.Activities.NativeActivityContext>.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="6e547-128">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="6e547-128">To use this sample</span></span>  
  
1.  <span data-ttu-id="6e547-129">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 For.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6e547-129">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the For.sln solution file.</span></span>  
  
2.  <span data-ttu-id="6e547-130">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6e547-130">Build the solution, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="6e547-131">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6e547-131">Run the solution, by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6e547-132">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e547-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6e547-133">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="6e547-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6e547-134">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="6e547-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6e547-135">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e547-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\For`