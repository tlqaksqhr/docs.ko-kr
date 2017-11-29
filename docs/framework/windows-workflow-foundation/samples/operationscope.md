---
title: OperationScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56206a21-1e63-422d-b92a-e5d8b713e707
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6d1e2738e8cdb546a1dcbb00689e5b4c360ddd04
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="operationscope"></a><span data-ttu-id="164d0-102">OperationScope</span><span class="sxs-lookup"><span data-stu-id="164d0-102">OperationScope</span></span>
<span data-ttu-id="164d0-103">이 샘플에서는 메시징 활동, <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply>를 사용하여 기존 사용자 지정 활동을 워크플로 서비스에 작업으로 노출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-103">This sample demonstrates how the messaging activities, <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> can be used to expose an existing custom activity as an operation in a workflow service.</span></span> <span data-ttu-id="164d0-104">이 샘플에는 `OperationScope`라는 새 사용자 지정 활동이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-104">This sample includes a new custom activity called an `OperationScope`.</span></span> <span data-ttu-id="164d0-105">이 활동을 사용하면 사용자가 작업 본문을 사용자 지정 활동과 별도로 작성한 다음 `OperationScope` 활동을 사용하여 해당 작업을 서비스 작업으로 쉽게 노출할 수 있도록 하여 워크플로 서비스를 쉽게 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-105">It is intended to ease the development of a workflow service by allowing users to author the body of their operations separately as custom activities and then easily exposing them as service operations using the `OperationScope` activity.</span></span> <span data-ttu-id="164d0-106">예를 들어 두 `Add` 인수를 사용하고 하나의 `in` 인수를 반환하는 사용자 지정 `out` 활동을 `Add`로 끌어 놓아 워크플로 서비스에 `OperationScope` 작업으로 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-106">For example, a custom `Add` activity that takes two `in` arguments and returns one `out` argument could be exposed as an `Add` operation on the workflow service by dropping it into an `OperationScope`.</span></span>  
  
 <span data-ttu-id="164d0-107">범위는 본문으로 제공된 활동을 검사하는 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-107">The scope works by inspecting the activity provided as its body.</span></span> <span data-ttu-id="164d0-108">바인딩되지 않은 `in` 인수는 모두 들어오는 메시지의 입력으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-108">Any unbound `in` arguments are assumed to be inputs from the incoming message.</span></span> <span data-ttu-id="164d0-109">모든 `out` 인수는 바인딩되어 있는지 여부에 관계없이 이후 회신 메시지의 출력으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-109">All `out` arguments, regardless of whether they are bound, are assumed to be outputs in the subsequent reply message.</span></span> <span data-ttu-id="164d0-110">노출된 작업의 이름은 `OperationScope` 활동의 표시 이름에서 가져온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-110">The exposed operation’s name is taken from the display name of the `OperationScope` activity.</span></span> <span data-ttu-id="164d0-111">본문 활동이 활동 인수에 바인딩된 메시지의 매개 변수를 사용하여 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply>에 래핑되는 것이 최종 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-111">The end result is that the body activity is wrapped in a <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> with the parameters from the messages bound to the arguments of the activity.</span></span>  
  
 <span data-ttu-id="164d0-112">이 샘플에서는 HTTP 끝점을 사용하여 워크플로 서비스를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-112">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="164d0-113">실행하려면 적절한 URL ACL을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-113">To run, proper URL ACLs must be added.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="164d0-114">[HTTP 및 HTTPS 구성](http://go.microsoft.com/fwlink/?LinkId=70353)합니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-114"> [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353).</span></span> <span data-ttu-id="164d0-115">프롬프트에서 다음 명령을 실행 하면 적절 한 Acl을 추가 (도메인과 사용자 이름을 % 도메인 %에 대 한 대체 확인\\% UserName %).</span><span class="sxs-lookup"><span data-stu-id="164d0-115">Executing the following command at an elevated prompt adds the appropriate ACLs (ensure that your Domain and Username are substituted for %DOMAIN%\\%UserName%).</span></span>  
  
 <span data-ttu-id="164d0-116">**netsh http urlacl url 추가 = http: / / +: 8000 / 사용자 = % 도메인 %\\% UserName %**</span><span class="sxs-lookup"><span data-stu-id="164d0-116">**netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\\%UserName%**</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="164d0-117">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="164d0-117">To run the sample</span></span>  
  
1.  <span data-ttu-id="164d0-118">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 OperationScope.sln 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-118">Open the OperationScope.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="164d0-119">솔루션 탐색기에서 솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 여러 시작 프로젝트 설정 **시작 프로젝트 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-119">Set multiple start-up projects by right-clicking the solution in Solution Explorer and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="164d0-120">Scenario와 Scenario_Client를 차례로 여러 시작 프로젝트로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-120">Add Scenario and Scenario_Client (in that order) as multiple start-up projects.</span></span>  
  
3.  <span data-ttu-id="164d0-121">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-121">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="164d0-122">이 단계는 사용자 지정 활동 `OperationScope`로 인해 BankService.xaml 워크플로를 보는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-122">This step is required to view the BankService.xaml workflow due to the custom activity `OperationScope`.</span></span>  
  
4.  <span data-ttu-id="164d0-123">Ctrl+F5를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-123">Press CTRL+F5 to run the application.</span></span> <span data-ttu-id="164d0-124">Scenario_Client 콘솔에서 입력하라는 메시지가 표시되고 해당 출력은 Scenario 콘솔에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-124">The Scenario_Client console prompts you for inputs and the corresponding output is seen in the Scenario console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="164d0-125">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="164d0-126">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="164d0-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="164d0-127">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="164d0-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="164d0-128">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164d0-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\OperationScope`  
  
## <a name="see-also"></a><span data-ttu-id="164d0-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="164d0-129">See Also</span></span>
