---
title: Throttled Parallel ForEach
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6c8336060be48f55b974960e67ca1ebc57e76c63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="throttled-parallel-foreach"></a><span data-ttu-id="20057-102">Throttled Parallel ForEach</span><span class="sxs-lookup"><span data-stu-id="20057-102">Throttled Parallel ForEach</span></span>
<span data-ttu-id="20057-103">`ThrottleParallelForEach` 활동은 비슷합니다는 <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` 예외와 관련 된 활동 설정 하도록 허용 한다는 동시 비율 실행할 동시 분기 수를 제한 하려면.</span><span class="sxs-lookup"><span data-stu-id="20057-103">The `ThrottleParallelForEach` activity is similar to the <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span> <span data-ttu-id="20057-104">`ThrottleParallelForEach` 활동은 다른 활동(자식 활동)을 예약해야 하고 <xref:System.Activities.NativeActivity> 클래스를 통해서만 액세스 가능하기 때문에 <xref:System.Activities.NativeActivityContext>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="20057-104">The `ThrottleParallelForEach` activity derives from <xref:System.Activities.NativeActivity>, because it needs to schedule other activities (the child activities) and this is only accessible through the <xref:System.Activities.NativeActivityContext> class.</span></span>  
  
## <a name="projects"></a><span data-ttu-id="20057-105">프로젝트</span><span class="sxs-lookup"><span data-stu-id="20057-105">Projects</span></span>  
  
|<span data-ttu-id="20057-106">**ProjectName**</span><span class="sxs-lookup"><span data-stu-id="20057-106">**ProjectName**</span></span>|<span data-ttu-id="20057-107">**설명**</span><span class="sxs-lookup"><span data-stu-id="20057-107">**Description**</span></span>|<span data-ttu-id="20057-108">**기본 파일**</span><span class="sxs-lookup"><span data-stu-id="20057-108">**Main Files**</span></span>|  
|-|-|-|  
|<span data-ttu-id="20057-109">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="20057-109">ThrottledParallelForEach</span></span>|<span data-ttu-id="20057-110">`ThrottledParallelForEach` 활동과 이 활동의 디자이너가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20057-110">Contains `ThrottledParallelForEach` activity and its designer.</span></span>|<span data-ttu-id="20057-111">ThrottledParallelForEach.cs</span><span class="sxs-lookup"><span data-stu-id="20057-111">ThrottledParallelForEach.cs</span></span><br /><br /> <span data-ttu-id="20057-112">`ThrottledParallelForEach` 활동 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="20057-112">The `ThrottledParallelForEach` activity definition.</span></span>|  
|<span data-ttu-id="20057-113">CodeTestClient</span><span class="sxs-lookup"><span data-stu-id="20057-113">CodeTestClient</span></span>|<span data-ttu-id="20057-114">명령적 코드를 사용하여 `ThrottledParallelForEach`가 있는 워크플로를 구성 및 실행하는 샘플 클라이언트 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="20057-114">Sample client application that configures and runs a workflow with a `ThrottledParallelForEach` using imperative code.</span></span>|<span data-ttu-id="20057-115">Program.cs</span><span class="sxs-lookup"><span data-stu-id="20057-115">Program.cs</span></span><br /><br /> <span data-ttu-id="20057-116">샘플 워크플로의 인스턴스를 정의하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="20057-116">Defines and runs an instance of the sample workflow.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="20057-117">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="20057-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="20057-118">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 ThrottledParallelForEach.sln 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20057-118">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ThrottledParallelForEach.sln file.</span></span>  
  
2.  <span data-ttu-id="20057-119">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="20057-119">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="20057-120">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="20057-120">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="20057-121">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20057-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="20057-122">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="20057-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="20057-123">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="20057-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="20057-124">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20057-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`  
  
## <a name="see-also"></a><span data-ttu-id="20057-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20057-125">See Also</span></span>
