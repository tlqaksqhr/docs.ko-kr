---
title: Asynchronous Communication
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9cf1cc88f2b9dda0b0f6e155a5d6a465552d6267
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="asynchronous-communication"></a><span data-ttu-id="2b902-102">Asynchronous Communication</span><span class="sxs-lookup"><span data-stu-id="2b902-102">Asynchronous Communication</span></span>
<span data-ttu-id="2b902-103">이 샘플에서는 두 개의 Windows WF (Workflow Foundation) 서비스 간의 통신은 기본적으로 비동기적으로 수행 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b902-103">This sample demonstrates how the communication between two different Windows Workflow Foundation (WF) services is done asynchronously by default.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="2b902-104">세부 항목</span><span class="sxs-lookup"><span data-stu-id="2b902-104">Demonstrates</span></span>  
 <span data-ttu-id="2b902-105">[!INCLUDE[wf1](../../../../includes/wf1-md.md)] 서비스 간의 비동기 통신</span><span class="sxs-lookup"><span data-stu-id="2b902-105">Asynchronous communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] services.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="2b902-106">토론</span><span class="sxs-lookup"><span data-stu-id="2b902-106">Discussion</span></span>  
 <span data-ttu-id="2b902-107">이 샘플에서는 .NET Framework에서 제공되는 메시징 활동을 통해 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 응용 프로그램 간의 통신이 비동기적으로 이루어지는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b902-107">This sample shows how the communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] applications is done asynchronously by using the messaging activities provided by .NET Framework.</span></span>  
  
 <span data-ttu-id="2b902-108">이 샘플은 다음 세 개의 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b902-108">This sample consists of the following three projects.</span></span>  
  
 <span data-ttu-id="2b902-109">CreditCheckService</span><span class="sxs-lookup"><span data-stu-id="2b902-109">CreditCheckService</span></span>  
 <span data-ttu-id="2b902-110">이 서비스는 특정 개인의 신용 점수나 승인할 품목의 가치를 받은 다음 해당 개인에게 신용을 부여할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b902-110">This service receives the credit score of a particular person or the value of the item to acquire, and then decides whether the credit is given to the person.</span></span>  
  
 <span data-ttu-id="2b902-111">RentalApprovalService</span><span class="sxs-lookup"><span data-stu-id="2b902-111">RentalApprovalService</span></span>  
 <span data-ttu-id="2b902-112">이 서비스는 신용 거래를 필요로 하는 개인으로부터 신청을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2b902-112">This service receives an application from a person who is in need of some credit.</span></span> <span data-ttu-id="2b902-113">이 서비스는 `CreditCheckService`와 비동기적으로 통신하여 신용 거래 신청이 유효한지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b902-113">This service communicates asynchronously with the `CreditCheckService` to decide whether the credit application is valid.</span></span>  
  
 <span data-ttu-id="2b902-114">클라이언트</span><span class="sxs-lookup"><span data-stu-id="2b902-114">Client</span></span>  
 <span data-ttu-id="2b902-115">클라이언트는 `RentalApprovalService`와 동기적으로 통신하여 신용 거래가 승인되었는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2b902-115">The client communicates synchronously with the `RentalApprovalService` to know whether the credit is approved.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2b902-116">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="2b902-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2b902-117">마우스 오른쪽 단추로 클릭는 **AsynchronousCommunication** 솔루션과 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="2b902-117">Right-click the **AsynchronousCommunication** solution and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="2b902-118">**공용 속성**선택, **시작 프로젝트**를 선택 하 고 **여러 개의 시작 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="2b902-118">In **Common Properties**, select **Startup Project**, and select **Multiple Startup Projects**.</span></span>  
  
3.  <span data-ttu-id="2b902-119">이동 **RentalApprovalService** 하려면 목록에서 첫 번째 위치 뒤 **CreditCheckService**옵니다 **클라이언트**합니다.</span><span class="sxs-lookup"><span data-stu-id="2b902-119">Move **RentalApprovalService** to the first position in the list, followed by **CreditCheckService**, followed by **Client**.</span></span> <span data-ttu-id="2b902-120">설정의 **시작** 세 프로젝트 모두에서 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b902-120">Set the **Start** action on all three projects.</span></span>  
  
4.  <span data-ttu-id="2b902-121">클릭 **확인**, 샘플을 실행 하려면 F5 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2b902-121">Click **OK**, and press F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2b902-122">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b902-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2b902-123">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2b902-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2b902-124">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="2b902-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2b902-125">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b902-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
