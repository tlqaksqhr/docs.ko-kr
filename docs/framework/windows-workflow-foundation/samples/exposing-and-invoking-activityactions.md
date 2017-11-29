---
title: "ActivityAction 노출 및 호출"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8a87e4463689e9301045a55b16af46cb037c1fa5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="exposing-and-invoking-activityactions"></a><span data-ttu-id="dc7f7-102">ActivityAction 노출 및 호출</span><span class="sxs-lookup"><span data-stu-id="dc7f7-102">Exposing and Invoking ActivityActions</span></span>
<span data-ttu-id="dc7f7-103">이 샘플에서는 <xref:System.Activities.ActivityAction>이 있는 사용자 지정 활동을 개발하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc7f7-103">This sample demonstrates how to develop a custom activity that has an <xref:System.Activities.ActivityAction>.</span></span> <span data-ttu-id="dc7f7-104">또한 <xref:System.Activities.ActivityAction>의 구현을 제공하여 이 활동을 사용하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc7f7-104">It also demonstrates how to use this activity by providing an implementation of the <xref:System.Activities.ActivityAction>.</span></span>  
  
 <span data-ttu-id="dc7f7-105"><xref:System.Activities.ActivityAction> 통해 활동 작성자는 "허점"을 노출할 특정 서명이 있는 활동 사용자는 사용자 지정 동작을 연결할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc7f7-105">An <xref:System.Activities.ActivityAction> allows an activity author to expose "holes" with specific signatures where the activity user can plug in a custom behavior.</span></span> <span data-ttu-id="dc7f7-106">예를 들어는 <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` 활동 (작동 하 항목의 컬렉션을 통해)는 <xref:System.Activities.ActivityAction> 활동 사용자가 현재 반복 항목에 작동 하는 동작을 플러그 인할에서 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc7f7-106">For example, the <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` activity, (which operates over a collection of items), has an <xref:System.Activities.ActivityAction> that allows the activity user to plug in behavior that operates on the current iteration item.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dc7f7-107">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="dc7f7-107">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="dc7f7-108">열기는 **ActivityAction.sln** 샘플 솔루션을 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="dc7f7-108">Open the **ActivityAction.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="dc7f7-109">솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dc7f7-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dc7f7-110">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc7f7-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dc7f7-111">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="dc7f7-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dc7f7-112">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="dc7f7-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dc7f7-113">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc7f7-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`  
  
## <a name="see-also"></a><span data-ttu-id="dc7f7-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc7f7-114">See Also</span></span>
