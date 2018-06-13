---
title: 내용 기반 상관 관계
ms.date: 03/30/2017
ms.assetid: 8638b5d6-1d59-456d-8acd-179a5b39b260
ms.openlocfilehash: b90d076d96e1bae5c44dc1c2b06f826d256f7463
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518834"
---
# <a name="content-based-correlation"></a><span data-ttu-id="7e8a2-102">내용 기반 상관 관계</span><span class="sxs-lookup"><span data-stu-id="7e8a2-102">Content-Based Correlation</span></span>
<span data-ttu-id="7e8a2-103">이 샘플에서는 여러 내용 기반 상관 관계와 내용 기반 상관 관계에 메시징 활동(<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply>)을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e8a2-103">This sample demonstrates how the messaging activities (<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>) can be used with multiple content-based correlations.and content-based correlation.</span></span> <span data-ttu-id="7e8a2-104">이 시나리오에서는 먼저 구매 주문 ID를 기반으로 상관 관계를 초기화한 다음, 나중에 고객 ID를 기반으로 다른 상관 관계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7e8a2-104">In this scenario, a correlation is first initialized based on a purchase order ID, and then another correlation is created later based on the customer ID.</span></span> <span data-ttu-id="7e8a2-105">여기에서는 <xref:System.ServiceModel.Activities.Receive> 활동이 기존 상관 관계를 따르고 들어오는 동일한 메시지를 기반으로 새 상관 관계를 초기화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e8a2-105">This shows how a <xref:System.ServiceModel.Activities.Receive> activity can both follow an existing correlation and initialize a new correlation based on the same incoming message.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="7e8a2-106">세부 항목</span><span class="sxs-lookup"><span data-stu-id="7e8a2-106">Demonstrates</span></span>  
 <span data-ttu-id="7e8a2-107">메시징 활동 및 내용 기반 상관 관계</span><span class="sxs-lookup"><span data-stu-id="7e8a2-107">Messaging activities and content-based correlation</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="7e8a2-108">토론</span><span class="sxs-lookup"><span data-stu-id="7e8a2-108">Discussion</span></span>  
 <span data-ttu-id="7e8a2-109">이 샘플에서는 여러 내용 기반 상관 관계를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e8a2-109">This sample shows how to use multiple content-based correlations.</span></span>  <span data-ttu-id="7e8a2-110">이 시나리오에서는 먼저 구매 주문 ID를 기반으로 상관 관계를 초기화한 다음, 나중에 고객 ID를 기반으로 다른 상관 관계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7e8a2-110">In this scenario, a correlation is first initialized based on a purchase order ID, and then another correlation is created later based on the customer ID.</span></span>  <span data-ttu-id="7e8a2-111">상관 관계는 기존 상관 관계(PurchaseOrderId)를 따르고 들어오는 동일한 메시지를 기반으로 새 상관 관계(CustomerId)를 초기화하는 <xref:System.ServiceModel.Activities.Receive> 활동을 사용하여 연계됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e8a2-111">The correlations are cascaded using a <xref:System.ServiceModel.Activities.Receive> activity that both follows an existing correlation (PurchaseOrderId) and initializes a new correlation (CustomerId) based on the same incoming message.</span></span>  <span data-ttu-id="7e8a2-112">이를 수행하기 위해 <xref:System.ServiceModel.Activities.Receive> 활동은 <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> 및 <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e8a2-112">To accomplish this, the <xref:System.ServiceModel.Activities.Receive> activity uses the <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> and <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> properties.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="7e8a2-113">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="7e8a2-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="7e8a2-114">열기 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 마우스 오른쪽 단추로 클릭 하 여 승격 된 권한으로는 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 아이콘을 선택 하면 **관리자 권한으로 실행**합니다.</span><span class="sxs-lookup"><span data-stu-id="7e8a2-114">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="7e8a2-115">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 CascadingCorrelation.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7e8a2-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CascadingCorrelation.sln solution file.</span></span>  
  
3.  <span data-ttu-id="7e8a2-116">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="7e8a2-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="7e8a2-117">F5 키를 눌러 서버를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7e8a2-117">To run the server, press F5.</span></span>  
  
5.  <span data-ttu-id="7e8a2-118">서버가 메시지를 수신할 준비가 되어 있으면 솔루션 탐색기에서 클라이언트 프로젝트를 마우스 오른쪽 단추로 클릭하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7e8a2-118">Once the service is ready and listening for messages, in Solution Explorer, right-click the Client project and run it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7e8a2-119">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e8a2-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7e8a2-120">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7e8a2-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7e8a2-121">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="7e8a2-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7e8a2-122">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e8a2-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ContentBasedCorrelation`