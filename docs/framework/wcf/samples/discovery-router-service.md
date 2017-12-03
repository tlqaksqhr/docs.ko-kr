---
title: "검색 라우터 서비스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 66ff9d760ee59ef7a08f38826437b29077bc68d5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="discovery-router-service"></a><span data-ttu-id="0507f-102">검색 라우터 서비스</span><span class="sxs-lookup"><span data-stu-id="0507f-102">Discovery Router Service</span></span>
<span data-ttu-id="0507f-103">이 샘플에서는 검색 메시지를 다른 끝점에 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0507f-103">This sample demonstrates how to forward discovery messages to another endpoint.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="0507f-104">세부 항목</span><span class="sxs-lookup"><span data-stu-id="0507f-104">Demonstrates</span></span>  
 <span data-ttu-id="0507f-105">검색 라우팅</span><span class="sxs-lookup"><span data-stu-id="0507f-105">Discovery Routing</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="0507f-106">토론</span><span class="sxs-lookup"><span data-stu-id="0507f-106">Discussion</span></span>  
 <span data-ttu-id="0507f-107">클라이언트에서 프록시를 사용하여 서비스를 찾으려고 하며 프록시에서는 이러한 서비스를 인식하지 못하지만 다른 프록시는 인식하는 경우에 검색 라우팅이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0507f-107">Discovery routing is useful in a scenario in which a client is looking for a service using a proxy and the proxy is unaware of such a service, but knows of another proxy.</span></span> <span data-ttu-id="0507f-108">이 프록시에서는 이 클라이언트의 검색 패킷을 두 번째 프록시에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0507f-108">This proxy can forward the discovery packet from this client to the second proxy.</span></span> <span data-ttu-id="0507f-109">두 번째 프록시에서는 서비스를 찾고 원래 클라이언트에 응답을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0507f-109">The second proxy can look for the service and return the responses to the original client.</span></span>  
  
 <span data-ttu-id="0507f-110">이 샘플의 클라이언트에서는 검색 라우팅 구성 요소에 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="0507f-110">In this sample, a client sends a message to a discovery routing component.</span></span> <span data-ttu-id="0507f-111">이 메시지는 검색 라우터의 특정 끝점에 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="0507f-111">This message is sent to a specific endpoint on the discovery router.</span></span> <span data-ttu-id="0507f-112">그런 다음 라우터에서 해당 메시지를 UDP 멀티캐스트 끝점에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="0507f-112">The router then forwards the message to a UDP multicast endpoint.</span></span> <span data-ttu-id="0507f-113">프로브 메시지는 멀티캐스트 끝점으로 이동하며 UDP 멀티캐스트 주소에서 수신 대기하는 서비스는 해당 검색 라우터에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="0507f-113">The probe message goes out to the multicast endpoint and a service listening on a UDP multicast address responds to that discovery router.</span></span> <span data-ttu-id="0507f-114">검색 라우터에서는 응답을 수집하여 클라이언트로 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="0507f-114">The discovery router collects the responses and sends them back to the client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0507f-115">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="0507f-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0507f-116">샘플을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0507f-116">Build the sample.</span></span>  
  
2.  <span data-ttu-id="0507f-117">DiscoveryRouter 실행 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0507f-117">Run the DiscoveryRouter executable.</span></span>  
  
3.  <span data-ttu-id="0507f-118">빌드 디렉터리에서 서비스 실행 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0507f-118">Run the service executable from the build directory.</span></span>  
  
4.  <span data-ttu-id="0507f-119">클라이언트 실행 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0507f-119">Run the client executable.</span></span> <span data-ttu-id="0507f-120">그러면 클라이언트에서는 서비스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0507f-120">Note that the client locates the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0507f-121">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0507f-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0507f-122">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0507f-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0507f-123">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="0507f-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0507f-124">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0507f-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`
