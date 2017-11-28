---
title: "실행 속성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5a394ff136464dd2e69f8c38f07b1b2542bf4a87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="execution-properties"></a><span data-ttu-id="ed188-102">실행 속성</span><span class="sxs-lookup"><span data-stu-id="ed188-102">Execution Properties</span></span>
<span data-ttu-id="ed188-103">이 샘플에서는 사용자 지정 활동에 실행 속성을 정의하고 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed188-103">This sample shows how to define and use an execution property in a custom activity.</span></span> <span data-ttu-id="ed188-104">이 예제에서는 실행 속성에 따라 콘솔의 전경색이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed188-104">In this example, the execution property determines the console's foreground color.</span></span> <span data-ttu-id="ed188-105">예제 워크플로는 실행의 논리 경로(<xref:System.Activities.Statements.Parallel> 활동의 분기)가 달라지는 경우 <xref:System.Activities.Statements.Parallel> 활동의 분기 전반에서 활동이 인터리브 방식으로 실행되더라도 다른 콘솔 색이 유지되는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed188-105">An example workflow shows how different logical paths of execution (branches of a <xref:System.Activities.Statements.Parallel> activity) can maintain different console colors despite interleaved execution of activities (across the branches of the <xref:System.Activities.Statements.Parallel> activity).</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ed188-106">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="ed188-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ed188-107">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 ExecutionProperties.sln 샘플 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ed188-107">Open the ExecutionProperties.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ed188-108">솔루션을 빌드하기 전에 ThreeColors.xaml을 보면 오류가 표시됩니다. 사용하는 사용자 지정 활동은 솔루션과 동시에 빌드되어야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ed188-108">Viewing ThreeColors.xaml before building the solution displays an error, because the custom activities used must be built at the same time as the solution.</span></span>  
  
2.  <span data-ttu-id="ed188-109">솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed188-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ed188-110">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed188-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ed188-111">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ed188-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ed188-112">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="ed188-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ed188-113">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed188-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`  
  
## <a name="see-also"></a><span data-ttu-id="ed188-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed188-114">See Also</span></span>
