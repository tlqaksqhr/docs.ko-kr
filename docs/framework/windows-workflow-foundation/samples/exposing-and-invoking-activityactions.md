---
title: ActivityAction 노출 및 호출
ms.date: 03/30/2017
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
ms.openlocfilehash: 2d369ec4b028b047ce02016dd511c1c088b46a91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513154"
---
# <a name="exposing-and-invoking-activityactions"></a><span data-ttu-id="f7ce9-102">ActivityAction 노출 및 호출</span><span class="sxs-lookup"><span data-stu-id="f7ce9-102">Exposing and Invoking ActivityActions</span></span>
<span data-ttu-id="f7ce9-103">이 샘플에서는 <xref:System.Activities.ActivityAction>이 있는 사용자 지정 활동을 개발하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f7ce9-103">This sample demonstrates how to develop a custom activity that has an <xref:System.Activities.ActivityAction>.</span></span> <span data-ttu-id="f7ce9-104">또한 <xref:System.Activities.ActivityAction>의 구현을 제공하여 이 활동을 사용하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f7ce9-104">It also demonstrates how to use this activity by providing an implementation of the <xref:System.Activities.ActivityAction>.</span></span>  
  
 <span data-ttu-id="f7ce9-105"><xref:System.Activities.ActivityAction> 통해 활동 작성자는 "허점"을 노출할 특정 서명이 있는 활동 사용자는 사용자 지정 동작을 연결할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ce9-105">An <xref:System.Activities.ActivityAction> allows an activity author to expose "holes" with specific signatures where the activity user can plug in a custom behavior.</span></span> <span data-ttu-id="f7ce9-106">예를 들어는 <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` 활동 (작동 하 항목의 컬렉션을 통해)는 <xref:System.Activities.ActivityAction> 활동 사용자가 현재 반복 항목에 작동 하는 동작을 플러그 인할에서 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ce9-106">For example, the <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` activity, (which operates over a collection of items), has an <xref:System.Activities.ActivityAction> that allows the activity user to plug in behavior that operates on the current iteration item.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f7ce9-107">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="f7ce9-107">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f7ce9-108">열기는 **ActivityAction.sln** 샘플 솔루션을 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ce9-108">Open the **ActivityAction.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="f7ce9-109">솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ce9-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7ce9-110">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7ce9-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f7ce9-111">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="f7ce9-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f7ce9-112">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="f7ce9-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f7ce9-113">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7ce9-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`