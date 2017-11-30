---
title: OverloadGroups
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1c866d337b6e02fa18241b6fafd9d4e5a397ef69
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="overloadgroups"></a><span data-ttu-id="97dfc-102">OverloadGroups</span><span class="sxs-lookup"><span data-stu-id="97dfc-102">OverloadGroups</span></span>
<span data-ttu-id="97dfc-103">이 샘플은 눈여겨 봐야 할 두 가지 특징을 지닌 활동(`CreateLocation`)으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97dfc-103">This sample consists of an activity (`CreateLocation`), which has two interesting characteristics:</span></span>  
  
1.  <span data-ttu-id="97dfc-104">이 활동에는 몇 가지 필수 인수와 몇 가지 선택적 인수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97dfc-104">It has some required arguments and some optional ones.</span></span>  
  
2.  <span data-ttu-id="97dfc-105">이 활동에서 서로 다른 두 가지 인수 집합 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97dfc-105">It allows the user to choose to provide one of two different sets of arguments.</span></span>  
  
 <span data-ttu-id="97dfc-106">이러한 동작을 수행하는 데는 다음과 같은 두 가지 기능이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="97dfc-106">These behaviors are accomplished by using these two features:</span></span>  
  
-   <span data-ttu-id="97dfc-107">`[isRequired]`는 특정 활동의 속성이 할당되었는지 여부를 검사하고, 속성이 할당되지 않았으면 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="97dfc-107">`[isRequired]` validates that a property of a specific activity is assign, and if not, it throws an exception.</span></span>  
  
-   <span data-ttu-id="97dfc-108">`[OverloadGroup]`은 인수 집합을 함께 묶어 활동 사용자가 특정 집합을 선택하여 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="97dfc-108">`[OverloadGroup]` puts together a set of arguments, so that the user of the activity can choose between using one set or another.</span></span> <span data-ttu-id="97dfc-109">동일한 인스턴스 내에서 다른 오버로드 그룹의 인수를 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97dfc-109">The user cannot use arguments from different Overload Groups in the same instance.</span></span>  
  
 <span data-ttu-id="97dfc-110">다른 워크플로를 설정하고 나면 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>의 <xref:System.Activities.Validation.ValidationResults> 컬렉션을 반환하는 <xref:System.Activities.Validation.Constraint>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="97dfc-110">After setting up different workflows, call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.Constraint>.</span></span> <span data-ttu-id="97dfc-111"><xref:System.Activities.Validation.Constraint> 개체를 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="97dfc-111">Print the <xref:System.Activities.Validation.Constraint> objects to the console.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="97dfc-112">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="97dfc-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="97dfc-113">열기는 **OverloadGroups.sln** 샘플 솔루션을 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="97dfc-113">Open the **OverloadGroups.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="97dfc-114">솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="97dfc-114">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="97dfc-115">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97dfc-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="97dfc-116">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="97dfc-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="97dfc-117">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="97dfc-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="97dfc-118">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97dfc-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`
