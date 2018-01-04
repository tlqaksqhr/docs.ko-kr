---
title: "LINQ 메시지 쿼리 상관 관계"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1207f371da5b447903e2846229860fd8c214a46e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="linq-message-query-correlation"></a><span data-ttu-id="2ba8e-102">LINQ 메시지 쿼리 상관 관계</span><span class="sxs-lookup"><span data-stu-id="2ba8e-102">LINQ Message Query Correlation</span></span>
<span data-ttu-id="2ba8e-103">이 샘플에서는 시스템에서 제공하는 <xref:System.ServiceModel.Dispatcher.MessageQuery> 대신 사용자 지정 <xref:System.ServiceModel.XPathMessageQuery> 구현을 사용하여 내용 기반 상관 관계를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-103">This sample demonstrates how to do content-based correlation using a custom <xref:System.ServiceModel.Dispatcher.MessageQuery> implementation as opposed to the system-provided <xref:System.ServiceModel.XPathMessageQuery>.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="2ba8e-104">세부 항목</span><span class="sxs-lookup"><span data-stu-id="2ba8e-104">Demonstrates</span></span>  
 <span data-ttu-id="2ba8e-105">사용자 지정 <xref:System.ServiceModel.Dispatcher.MessageQuery>, 내용 기반 상관 관계</span><span class="sxs-lookup"><span data-stu-id="2ba8e-105">Custom <xref:System.ServiceModel.Dispatcher.MessageQuery>, Content-Based Correlation.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="2ba8e-106">토론</span><span class="sxs-lookup"><span data-stu-id="2ba8e-106">Discussion</span></span>  
 <span data-ttu-id="2ba8e-107">이 샘플에서는 상관 관계를 만들기 위해 <xref:System.ServiceModel.Dispatcher.MessageQuery> 기본 클래스를 확장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-107">This sample shows how to extend from the <xref:System.ServiceModel.Dispatcher.MessageQuery> base class for the purposes of correlation.</span></span> <span data-ttu-id="2ba8e-108">사용자 지정 `LinqMessageQuery`를 구현하면 XLinq를 사용하여 메시지 내에서 XName을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-108">The custom implementation, `LinqMessageQuery`, allows users to provide an XName to find within the message using XLinq.</span></span> <span data-ttu-id="2ba8e-109">쿼리를 통해 검색한 데이터는 메시지를 적절한 워크플로 인스턴스로 디스패치하기 위한 상관 관계 키를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-109">The data retrieved by the query is used to form the correlation key to dispatch messages to the appropriate workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2ba8e-110">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="2ba8e-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2ba8e-111">이 샘플에서는 HTTP 끝점을 사용하여 워크플로 서비스를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-111">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="2ba8e-112">이 샘플을 적절 한 URL Acl을 실행 하려면 추가 해야 합니다 (참조 [HTTP 및 HTTPS 구성](http://go.microsoft.com/fwlink/?LinkId=70353) 세부 정보에 대 한), 관리자 권한으로 Visual Studio를 실행 하거나 적절 한 Acl을 추가 하려면 프롬프트에서 다음 명령을 실행 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-112">To run this sample, proper URL ACLs must be added (see [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) for details), either by running Visual Studio as Administrator or by executing the following command at an elevated prompt to add the appropriate ACLs.</span></span> <span data-ttu-id="2ba8e-113">도메인과 사용자 이름이 대체되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-113">Ensure that your Domain and Username are substituted.</span></span>  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  <span data-ttu-id="2ba8e-114">URL ACL이 추가되었으면 다음 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-114">Once the URL ACLs are added, use the following steps.</span></span>  
  
    1.  <span data-ttu-id="2ba8e-115">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-115">Build the solution.</span></span>  
  
    2.  <span data-ttu-id="2ba8e-116">솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 여러 시작 프로젝트 설정 **시작 프로젝트 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-116">Set multiple start-up projects by right-clicking the solution and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="2ba8e-117">추가 **서비스** 및 **클라이언트** 순서 대로) (에 여러 시작 프로젝트로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-117">Add **Service** and **Client** (in that order) as multiple start-up projects.</span></span>  
  
    3.  <span data-ttu-id="2ba8e-118">응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-118">Run the application.</span></span> <span data-ttu-id="2ba8e-119">주문서를 보내고 구매 주문서 ID를 받은 다음 주문을 확인하는 워크플로가 클라이언트 콘솔에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-119">The client console shows a workflow  sending an order and receiving the purchase order id and then subsequently confirming the order.</span></span> <span data-ttu-id="2ba8e-120">처리 중인 요청이 서비스 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-120">The Service window will show the requests being processed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2ba8e-121">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2ba8e-122">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2ba8e-123">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2ba8e-124">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ba8e-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
