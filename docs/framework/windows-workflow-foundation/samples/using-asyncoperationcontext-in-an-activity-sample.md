---
title: Using AsyncOperationContext in an Activity 샘플
ms.date: 03/30/2017
ms.assetid: 0888a0bd-d227-4c00-ad6a-b654a01740e8
ms.openlocfilehash: da7b62ef9e29621d1e6ee1046afb5455af1164bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515499"
---
# <a name="using-asyncoperationcontext-in-an-activity-sample"></a><span data-ttu-id="f8898-102">Using AsyncOperationContext in an Activity 샘플</span><span class="sxs-lookup"><span data-stu-id="f8898-102">Using AsyncOperationContext in an Activity Sample</span></span>
<span data-ttu-id="f8898-103">이 샘플에서는 <xref:System.Activities.CodeActivity>를 사용하여 워크플로 외부에서 비동기적으로 작업을 수행하는 사용자 지정 <xref:System.Activities.AsyncCodeActivityContext>를 개발하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8898-103">This sample demonstrates how to develop a custom <xref:System.Activities.CodeActivity> that uses <xref:System.Activities.AsyncCodeActivityContext> to perform work asynchronously outside of the workflow.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="f8898-104">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="f8898-104">Sample Details</span></span>  
 <span data-ttu-id="f8898-105">샘플 활동에서는 <xref:System.IO.FileStream.BeginWrite%2A> 클래스의 <xref:System.IO.FileStream.EndWrite%2A> 및 <xref:System.IO.FileStream> 메서드를 사용하여 비동기적으로 파일에 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="f8898-105">The sample activity uses the <xref:System.IO.FileStream.BeginWrite%2A> and <xref:System.IO.FileStream.EndWrite%2A> methods on the <xref:System.IO.FileStream> class to asynchronously write data to a file.</span></span> <span data-ttu-id="f8898-106">여기에서 사용되는 패턴은 다른 비동기 메서드에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8898-106">The pattern introduced here can be adapted for use with other asynchronous methods.</span></span> <span data-ttu-id="f8898-107">비동기 작업이 실행 중일 때 워크플로의 다른 활동을 실행할 수는 있지만 워크플로를 유지할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8898-107">While the asynchronous operation is executing, other activities in the workflow can execute, but the workflow cannot be persisted.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f8898-108">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="f8898-108">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f8898-109">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 Async.sln 샘플 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f8898-109">Open the Async.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="f8898-110">솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8898-110">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f8898-111">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8898-111">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f8898-112">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="f8898-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f8898-113">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="f8898-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f8898-114">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8898-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\Async`