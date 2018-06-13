---
title: Send를 사용한 채널 캐싱
ms.date: 03/30/2017
ms.assetid: e69a2502-25cb-43bf-b8d2-95fbdecb41cb
ms.openlocfilehash: c26d81b9cd85ba75189fafddd82c3fb4673c7fae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514041"
---
# <a name="channel-caching-with-send"></a><span data-ttu-id="59e51-102">Send를 사용한 채널 캐싱</span><span class="sxs-lookup"><span data-stu-id="59e51-102">Channel Caching with Send</span></span>
<span data-ttu-id="59e51-103"><xref:System.ServiceModel.Activities.SendMessageChannelCache>를 사용하면 <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.SendParametersContent> 활동에 각기 다른 채널 캐싱 수준을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-103">The <xref:System.ServiceModel.Activities.SendMessageChannelCache> enables users to have different levels of channel caching with <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.SendParametersContent> activities.</span></span> <span data-ttu-id="59e51-104">기본적으로 인스턴스 수준 캐싱이 사용됩니다. 이 샘플에서는 다음과 같은 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-104">Instance-level caching is enabled by default and this sample demonstrates the following features:</span></span>  
  
1.  <span data-ttu-id="59e51-105">응용 프로그램 도메인에 걸친 <xref:System.ServiceModel.Activities.SendMessageChannelCache> 공유</span><span class="sxs-lookup"><span data-stu-id="59e51-105">Share a <xref:System.ServiceModel.Activities.SendMessageChannelCache> across an application domain.</span></span>  
  
2.  <span data-ttu-id="59e51-106">채널 캐싱 비활성화</span><span class="sxs-lookup"><span data-stu-id="59e51-106">Disable channel caching.</span></span>  
  
3.  <span data-ttu-id="59e51-107"><xref:System.ServiceModel.Activities.SendMessageChannelCache>에서 워크플로 인스턴스 사이에 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 공유</span><span class="sxs-lookup"><span data-stu-id="59e51-107">Share a <xref:System.ServiceModel.Activities.SendMessageChannelCache> among workflow instances in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="59e51-108">세부 항목</span><span class="sxs-lookup"><span data-stu-id="59e51-108">Demonstrates</span></span>  
 <span data-ttu-id="59e51-109"><xref:System.ServiceModel.Activities.SendMessageChannelCache> 확장, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.ReceiveContent> 및 <xref:System.ServiceModel.Activities.SendReply> 활동</span><span class="sxs-lookup"><span data-stu-id="59e51-109"><xref:System.ServiceModel.Activities.SendMessageChannelCache> extension, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.ReceiveContent> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="59e51-110">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="59e51-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="59e51-111">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에 프로젝트 솔루션을 로드하고 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="59e51-112">\EchoWorkflowService\bin\debug에 생성된 EchoWorkflowService 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-112">Run the EchoWorkflowService application generated in \EchoWorkflowService\bin\debug.</span></span>  
  
3.  <span data-ttu-id="59e51-113">.\EchoWorkflowClient\bin\debug에 생성된 EchoWorkflowClient 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-113">Run the EchoWorkflowClient application generated in .\EchoWorkflowClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="59e51-114">클라이언트에서 서비스에 대한 Echo 작업을 호출하고 결과를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-114">The client calls the Echo operation on the service and prints the results.</span></span> <span data-ttu-id="59e51-115">결과가 출력되면 Enter 키를 눌러 클라이언트와 서비스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-115">When the results have been printed, press ENTER to exit the client and the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="59e51-116">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="59e51-117">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="59e51-117">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="59e51-118">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="59e51-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="59e51-119">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-119">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ChannelCache`
