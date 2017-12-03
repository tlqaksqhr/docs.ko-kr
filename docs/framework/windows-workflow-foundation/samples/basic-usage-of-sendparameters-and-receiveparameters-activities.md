---
title: "SendParameters 및 ReceiveParameters 활동의 기본 사용법"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 501aead51a96d483a55602c737613e1d9066b74c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a><span data-ttu-id="d3d49-102">SendParameters 및 ReceiveParameters 활동의 기본 사용법</span><span class="sxs-lookup"><span data-stu-id="d3d49-102">Basic Usage of SendParameters and ReceiveParameters Activities</span></span>
<span data-ttu-id="d3d49-103">이 샘플에서는 <xref:System.ServiceModel.Activities.SendParametersContent> 및 <xref:System.ServiceModel.Activities.ReceiveParametersContent> 활동의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3d49-103">This sample shows the use of <xref:System.ServiceModel.Activities.SendParametersContent> and <xref:System.ServiceModel.Activities.ReceiveParametersContent> activities.</span></span> <span data-ttu-id="d3d49-104">서비스에서는 문자열 인수를 받는 하나의 작업을 노출하고 해당 입력을 클라이언트에 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3d49-104">The service exposes one operation that takes a string argument and echoes the input back to the client.</span></span> <span data-ttu-id="d3d49-105">이 샘플에서는 이러한 메시징 활동의 매개 변수를 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3d49-105">The sample shows how to set up the parameters for these messaging activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d3d49-106">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3d49-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d3d49-107">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d3d49-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d3d49-108">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="d3d49-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d3d49-109">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3d49-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a><span data-ttu-id="d3d49-110">이 샘플의 사용법</span><span class="sxs-lookup"><span data-stu-id="d3d49-110">Using this sample</span></span>  
  
1.  <span data-ttu-id="d3d49-111">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에 프로젝트 솔루션을 로드하고 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d49-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="d3d49-112">먼저 [solution base directory]\EchoWorkflowService\bin\debug에 생성된 EchoWorkflowService 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d49-112">First run the EchoWorkflowService application generated in [solution base directory]\EchoWorkflowService\bin\debug.</span></span>  
  
3.  <span data-ttu-id="d3d49-113">그 다음 [solution base directory]\EchoWorkflowClient\bin\debug에 생성된 EchoWorkflowClient 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d49-113">Second, run the EchoWorkflowClient application generated in [solution base directory]\EchoWorkflowClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="d3d49-114">클라이언트에서 서비스에 대한 Echo 작업을 호출하고 결과를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d49-114">The client calls Echo operation on the service and prints the results.</span></span> <span data-ttu-id="d3d49-115">완료되면 Enter 키를 눌러 클라이언트와 서비스를 차례로 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="d3d49-115">When complete, press ENTER to exit the client and then the service.</span></span>