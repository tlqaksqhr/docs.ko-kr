---
title: "워크플로 서비스에 보안 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53f84ad5-1ed1-4114-8d0d-b12e8a021c6e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ba98ac3e64d7dcbf52ed6363d44487af54128437
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="securing-workflow-services"></a><span data-ttu-id="36df1-102">워크플로 서비스에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="36df1-102">Securing Workflow Services</span></span>
<span data-ttu-id="36df1-103">보안 워크플로 서비스 샘플에서는 다음 절차를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-103">The Secured Workflow Service sample shows the following procedures:</span></span>  
  
-   <span data-ttu-id="36df1-104"><xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 활동을 사용하여 기본 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="36df1-104">Creating a basic workflow service using the <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>  
  
-   <span data-ttu-id="36df1-105">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 구성을 사용하여 워크플로 서비스에서 사용할 보안 끝점 정의</span><span class="sxs-lookup"><span data-stu-id="36df1-105">Using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] configuration to define secure endpoints for use by the workflow service.</span></span>  
  
-   <span data-ttu-id="36df1-106">사용자 지정 정책 내부에 클레임을 만들고 <xref:System.ServiceModel.ServiceAuthorizationManager>를 사용하여 클레임의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="36df1-106">Creating claims inside a custom policy and using the <xref:System.ServiceModel.ServiceAuthorizationManager> to validate claims.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="36df1-107">세부 항목</span><span class="sxs-lookup"><span data-stu-id="36df1-107">Demonstrates</span></span>  
 <span data-ttu-id="36df1-108">WCF 보안(클레임 기반 권한 부여)을 사용하여 클라이언트와 워크플로 서비스 간 통신에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="36df1-108">Using WCF security to secure communication between client and Workflow service, Claims based authorization</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="36df1-109">토론</span><span class="sxs-lookup"><span data-stu-id="36df1-109">Discussion</span></span>  
 <span data-ttu-id="36df1-110">이 샘플에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 인프라를 사용하여 일반 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서와 동일하게 워크플로 서비스에 보안을 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-110">This sample demonstrates the use of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security infrastructure to secure a workflow service just like you would with a normal [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="36df1-111">특히 여기에서는 권한 부여에 사용자 지정 클레임을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-111">Specifically, it uses a custom claim for authorization.</span></span> <span data-ttu-id="36df1-112">이 경우 Windows 자격 증명에 <xref:System.ServiceModel.WSHttpBinding> 및 메시지 모드 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-112">In this case, it uses <xref:System.ServiceModel.WSHttpBinding> and message mode security with Windows credentials.</span></span>  
  
 <span data-ttu-id="36df1-113">사용자 지정 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>(`CustomNameCheckerPolicy`)는 클라이언트의 Windows 사용자 이름에 특정 문자가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-113">The custom <xref:System.IdentityModel.Policy.IAuthorizationPolicy> (`CustomNameCheckerPolicy`) checks the client's Windows username and for a specific character.</span></span> <span data-ttu-id="36df1-114">해당 문자가 있으면 클레임을 만들어 <xref:System.IdentityModel.Policy.EvaluationContext>에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-114">If that character is present, it creates and adds the claim to the <xref:System.IdentityModel.Policy.EvaluationContext>.</span></span> <span data-ttu-id="36df1-115">이렇게 하여 사용자 지정 정책이 클라이언트의 사용자 이름에 이 문자가 있음을 나타내는 문을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-115">By doing this, the custom policy is making the statement that the client has this character in the username.</span></span> <span data-ttu-id="36df1-116">호출의 수명 주기 전체에 걸쳐 이 클레임을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-116">This claim can be queried throughout the lifetime of the call.</span></span> <span data-ttu-id="36df1-117">`Constants.cs`에서 해당 문자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-117">You can find that character in `Constants.cs`.</span></span>  
  
 <span data-ttu-id="36df1-118">권한 부여 정책은 `SecureWorkFlowAuthZManager` 내부에서 클레임을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-118">The authorization policy looks for the claim inside the `SecureWorkFlowAuthZManager`.</span></span> <span data-ttu-id="36df1-119">클레임을 찾으면 `true`를 반환하고 워크플로가 계속되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-119">If it finds it, it returns `true` and allow the workflow to proceed.</span></span> <span data-ttu-id="36df1-120">그렇지 않으면 `false`를 반환합니다. 그러면 클라이언트에 '액세스 거부' 메시지가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-120">Otherwise, it returns `false`, which causes an 'Access Denied' message to be returned to the client.</span></span> <span data-ttu-id="36df1-121">다른 클레임은 컨텍스트에 있으며 이 클레임도 `SecureWorkFlowAuthZManager` 내부에서 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-121">Other claims are present in the context and can be examined as well inside the `SecureWorkFlowAuthZManager`.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="36df1-122">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="36df1-122">To run this sample</span></span>  
  
1.  <span data-ttu-id="36df1-123">관리자 권한으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-123">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="36df1-124">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 SecuringWorkflowServices.sln을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-124">Load SecuringWorkflowServices.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="36df1-125">Ctrl+Shift+B를 눌러 솔루션을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-125">Press CTRL+SHIFT+B to compile the solution.</span></span>  
  
4.  <span data-ttu-id="36df1-126">서비스 프로젝트를 솔루션의 시작 프로젝트로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-126">Set the Service project as the start-up project for the solution.</span></span>  
  
5.  <span data-ttu-id="36df1-127">Ctrl+F5를 눌러 디버깅 없이 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-127">Press CTRL+F5 to start the service without debugging.</span></span>  
  
6.  <span data-ttu-id="36df1-128">클라이언트 프로젝트를 솔루션의 시작 프로젝트로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-128">Set the Client project as the start-up project for the solution.</span></span>  
  
7.  <span data-ttu-id="36df1-129">Ctrl+F5를 눌러 디버깅 없이 클라이언트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-129">Press CTRL+F5 to start the client without debugging.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="36df1-130">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="36df1-131">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="36df1-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="36df1-132">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="36df1-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="36df1-133">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36df1-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\SecuringWorkflowServices`
