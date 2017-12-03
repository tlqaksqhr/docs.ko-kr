---
title: "오류 보내기 및 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 97a957932c04f52a4a77d7d636cda08a63121f2f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="sending-and-handling-faults"></a><span data-ttu-id="83870-102">오류 보내기 및 처리</span><span class="sxs-lookup"><span data-stu-id="83870-102">Sending and Handling Faults</span></span>
<span data-ttu-id="83870-103">이 샘플에서는 <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 메시징 활동을 사용하여 예상된 오류와 예기치 않은 오류를 주고받는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="83870-103">This sample demonstrates how to use the <xref:System.ServiceModel.Activities.SendReply> and <xref:System.ServiceModel.Activities.ReceiveReply> messaging activities to send and receive expected and unexpected faults.</span></span> <span data-ttu-id="83870-104">이 시나리오에서는 맨 처음 클라이언트 요청의 결과로 <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> 컬렉션에 포함되어 있는 예상된 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="83870-104">In this scenario, the first client request results in an expected fault that has been included in its <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> collection.</span></span> <span data-ttu-id="83870-105">그 이후 몇 번의 클라이언트 요청의 결과로 예기치 않은 오류가 발생한 다음 마지막 요청이 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="83870-105">The next few client requests result in receiving unexpected faults, before the final request succeeds.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="83870-106">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="83870-106">To use this sample</span></span>  
  
1.  <span data-ttu-id="83870-107">열기 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 마우스 오른쪽 단추로 클릭 하 여 승격 된 권한으로는 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 아이콘을 선택 하면 **관리자 권한으로 실행**합니다.</span><span class="sxs-lookup"><span data-stu-id="83870-107">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="83870-108">Faults.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="83870-108">Open the Faults.sln solution file.</span></span>  
  
3.  <span data-ttu-id="83870-109">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="83870-109">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="83870-110">서비스 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="83870-110">Run the service project.</span></span>  
  
    1.  <span data-ttu-id="83870-111">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 `FaultService` 프로젝트를 마우스 선택 **시작 프로젝트로 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="83870-111">In **Solution Explorer**, right-click the `FaultService` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="83870-112">Ctrl+F5를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="83870-112">Press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="83870-113">다른 복사본을 열고 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 마우스 오른쪽 단추로 클릭 하 여 승격 된 권한으로는 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 아이콘을 선택 하면 **관리자 권한으로 실행**합니다.</span><span class="sxs-lookup"><span data-stu-id="83870-113">Open another copy of [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
6.  <span data-ttu-id="83870-114">Faults.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="83870-114">Open the Faults.sln solution file.</span></span>  
  
7.  <span data-ttu-id="83870-115">클라이언트 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="83870-115">Run the client project.</span></span>  
  
    1.  <span data-ttu-id="83870-116">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 `FaultClient` 프로젝트를 마우스 선택 **시작 프로젝트로 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="83870-116">In **Solution Explorer**, right-click the `FaultClient` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="83870-117">Ctrl+F5를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="83870-117">Press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="83870-118">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83870-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="83870-119">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="83870-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="83870-120">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="83870-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="83870-121">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83870-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`