---
title: 오류 보내기 및 처리
ms.date: 03/30/2017
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
ms.openlocfilehash: 6796b4daccd88adc3bd006f454ce96ca155fbcb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516128"
---
# <a name="sending-and-handling-faults"></a><span data-ttu-id="ae67e-102">오류 보내기 및 처리</span><span class="sxs-lookup"><span data-stu-id="ae67e-102">Sending and Handling Faults</span></span>
<span data-ttu-id="ae67e-103">이 샘플에서는 <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 메시징 활동을 사용하여 예상된 오류와 예기치 않은 오류를 주고받는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae67e-103">This sample demonstrates how to use the <xref:System.ServiceModel.Activities.SendReply> and <xref:System.ServiceModel.Activities.ReceiveReply> messaging activities to send and receive expected and unexpected faults.</span></span> <span data-ttu-id="ae67e-104">이 시나리오에서는 맨 처음 클라이언트 요청의 결과로 <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> 컬렉션에 포함되어 있는 예상된 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ae67e-104">In this scenario, the first client request results in an expected fault that has been included in its <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> collection.</span></span> <span data-ttu-id="ae67e-105">그 이후 몇 번의 클라이언트 요청의 결과로 예기치 않은 오류가 발생한 다음 마지막 요청이 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="ae67e-105">The next few client requests result in receiving unexpected faults, before the final request succeeds.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="ae67e-106">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="ae67e-106">To use this sample</span></span>  
  
1.  <span data-ttu-id="ae67e-107">열기 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 마우스 오른쪽 단추로 클릭 하 여 승격 된 권한으로는 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 아이콘을 선택 하면 **관리자 권한으로 실행**합니다.</span><span class="sxs-lookup"><span data-stu-id="ae67e-107">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="ae67e-108">Faults.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ae67e-108">Open the Faults.sln solution file.</span></span>  
  
3.  <span data-ttu-id="ae67e-109">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="ae67e-109">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="ae67e-110">서비스 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ae67e-110">Run the service project.</span></span>  
  
    1.  <span data-ttu-id="ae67e-111">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 `FaultService` 프로젝트를 마우스 선택 **시작 프로젝트로 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="ae67e-111">In **Solution Explorer**, right-click the `FaultService` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="ae67e-112">Ctrl+F5를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ae67e-112">Press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="ae67e-113">다른 복사본을 열고 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 마우스 오른쪽 단추로 클릭 하 여 승격 된 권한으로는 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 아이콘을 선택 하면 **관리자 권한으로 실행**합니다.</span><span class="sxs-lookup"><span data-stu-id="ae67e-113">Open another copy of [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
6.  <span data-ttu-id="ae67e-114">Faults.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ae67e-114">Open the Faults.sln solution file.</span></span>  
  
7.  <span data-ttu-id="ae67e-115">클라이언트 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ae67e-115">Run the client project.</span></span>  
  
    1.  <span data-ttu-id="ae67e-116">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 `FaultClient` 프로젝트를 마우스 선택 **시작 프로젝트로 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="ae67e-116">In **Solution Explorer**, right-click the `FaultClient` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="ae67e-117">Ctrl+F5를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ae67e-117">Press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ae67e-118">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae67e-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ae67e-119">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ae67e-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ae67e-120">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="ae67e-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ae67e-121">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae67e-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`