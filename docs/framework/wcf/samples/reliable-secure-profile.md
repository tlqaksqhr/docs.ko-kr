---
title: "신뢰할 수 있는 보안 프로필"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 921edc41-e91b-40f9-bde9-b6148b633e61
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 89a6d5c2e485699a55c77797c34eaca2c9848c40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="reliable-secure-profile"></a><span data-ttu-id="6a2de-102">신뢰할 수 있는 보안 프로필</span><span class="sxs-lookup"><span data-stu-id="6a2de-102">Reliable Secure Profile</span></span>
<span data-ttu-id="6a2de-103">이 샘플에서는 구성 하는 방법을 보여 줍니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 [Reliable Secure Profile](http://go.microsoft.com/fwlink/?LinkId=178140) (RSP).</span><span class="sxs-lookup"><span data-stu-id="6a2de-103">This sample demonstrates how to compose [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and [Reliable Secure Profile](http://go.microsoft.com/fwlink/?LinkId=178140) (RSP).</span></span> <span data-ttu-id="6a2de-104">이 샘플의 구현을 설명는 [연결 만들기](http://go.microsoft.com/fwlink/?LinkId=178141) 함께 신뢰할 수 있는 메시징 및 선택적으로 구성 될 수 있는 채널에 보안 채널을 신뢰할 수 있는 보안 바인딩을 만드는 사양을 기반으로 rsp 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-104">This sample demonstrates the implementation of a [Make Connection](http://go.microsoft.com/fwlink/?LinkId=178141) channel which can be composed together with Reliable Messaging and optionally a secure channel to create a Reliable Secure Binding based on the RSP specification.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6a2de-105">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6a2de-106">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="6a2de-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6a2de-107">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="6a2de-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6a2de-108">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ReliableSecureProfile`  
  
## <a name="discussion"></a><span data-ttu-id="6a2de-109">토론</span><span class="sxs-lookup"><span data-stu-id="6a2de-109">Discussion</span></span>  
 <span data-ttu-id="6a2de-110">이 샘플에서는 신뢰할 수 있는 비동기 양방향 메시지 교환 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-110">This sample demonstrates a reliable asynchronous two-way message exchange scenario.</span></span> <span data-ttu-id="6a2de-111">서비스에는 이중 계약이 있으며 클라이언트에서는 이중 콜백 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-111">The service has a duplex contract and the client implements the duplex callback contract.</span></span> <span data-ttu-id="6a2de-112">클라이언트는 서비스에 대한 요청을 시작하며 해당 응답을 별도의 연결에서 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-112">The client initiates a request to a service, for which a response is expected on a separate connection.</span></span> <span data-ttu-id="6a2de-113">요청 메시지는 신뢰할 수 있는 상태로 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-113">The request message is sent reliably.</span></span> <span data-ttu-id="6a2de-114">그러나 클라이언트 쪽에서는 수신 대기 끝점을 열지 않으려고 하므로</span><span class="sxs-lookup"><span data-stu-id="6a2de-114">The client does not want to open a listening endpoint at its end.</span></span> <span data-ttu-id="6a2de-115">서비스에 대한 ‘Make Connection’ 요청으로 서비스를 폴링하여 이 ‘Make Connection’ 요청의 백 채널에서 응답을 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-115">Thus, it polls the service with ‘Make Connection’ requests for the service to send back the response on the back channel of this ‘Make Connection’ request.</span></span> <span data-ttu-id="6a2de-116">이 샘플에서는 클라이언트에서 수신 대기 끝점을 노출하지 않고 방화벽 예외도 생성하지 않으면서 HTTP를 통해 신뢰할 수 있는 이중 보안 통신을 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-116">This sample demonstrates how to have secure reliable duplex communication over HTTP without the client exposing a listening endpoint (and creating a firewall exception).</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6a2de-117">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="6a2de-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="6a2de-118">열기는 **ReliableSecureProfile** 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-118">Open the **ReliableSecureProfile** solution.</span></span>  
  
2.  <span data-ttu-id="6a2de-119">마우스 오른쪽 단추로 클릭는 **서비스** 프로젝트에서 **솔루션 탐색기**선택, **디버그**, **새 인스턴스 시작** 상황에 맞는 메뉴에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-119">Right click the **Service** project in **Solution Explorer**, select **Debug**, **Start new instance** from the context menu.</span></span> <span data-ttu-id="6a2de-120">그러면 서비스 호스트가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-120">This starts up the service host.</span></span>  
  
3.  <span data-ttu-id="6a2de-121">마우스 오른쪽 단추로 클릭는 **클라이언트** 프로젝트에서 **솔루션 탐색기**선택, **디버그**, **새 인스턴스 시작** 상황에 맞는 메뉴에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-121">Right click the **Client** project in **Solution Explorer**, select **Debug**, **Start new instance** from the context menu.</span></span> <span data-ttu-id="6a2de-122">그러면 클라이언트가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-122">This starts up the client.</span></span>  
  
4.  <span data-ttu-id="6a2de-123">클라이언트 콘솔 창의 프롬프트에 임의의 문자열을 입력하고 Enter 키를 클릭합니다. 그러면 입력 문자열이 이 문자열의 해시를 계산하는 서비스로 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-123">Type in any string in the prompt on the client console window and click ENTER.This sends the input string to the service, which computes a hash of this string.</span></span>  
  
5.  <span data-ttu-id="6a2de-124">서비스에서 이중 콜백 계약 작업을 콜백하여 클라이언트 콘솔 창에 결과가 표시되면 클라이언트 창에서 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-124">View the result on the client windows when the service calls back the duplex callback contract operation to display the result on the client console window.</span></span> <span data-ttu-id="6a2de-125">서비스에는 장시간 실행되는 데이터 처리 작업을 시뮬레이션하기 위한 의도적인 지연이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-125">There is an intentional delay on the service to simulate a long running operation of processing the data.</span></span>  
  
6.  <span data-ttu-id="6a2de-126">네트워크 모니터, Fiddler 등의 온라인 네트워크 모니터링 도구를 사용하여 HTTP 트래픽을 모니터링하면 클라이언트와 서비스 간의 통신 시퀀스가 Reliable Secure Profile에 규정된 대로 설정되어 있음을 알 수 있으며, 클라이언트에서 ‘Make Connection’ 요청을 사용하여 서비스를 폴링하는 방식도 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-126">Monitoring the HTTP traffic (by any of the online network monitoring tools like Network Monitor, Fiddler and so on) shows that a sequence for communication is established between the client and the service as laid down by the Reliable Secure Profile, and how the client polls the service with ‘Make Connection’ requests.</span></span> <span data-ttu-id="6a2de-127">서비스에서는 처리된 응답을 다시 보낼 수 있는 준비가 되면 마지막 ‘Make Connection’ 요청의 백 채널을 사용하여 결과를 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-127">When the service gets ready to send back the processed response, it uses the back channel of the last ‘Make Connection’ request to send back the results.</span></span>  
  
7.  <span data-ttu-id="6a2de-128">서비스 콘솔 창에서 Enter 키를 눌러 서비스를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-128">Press ENTER on the service console window to close the service.</span></span> <span data-ttu-id="6a2de-129">클라이언트 콘솔 창에서 Enter 키를 눌러 클라이언트를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="6a2de-129">Press ENTER on the client console window to close the client.</span></span>
