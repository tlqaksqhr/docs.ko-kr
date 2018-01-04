---
title: "비동기 찾기 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a713a25-c1f4-42e1-8c4a-93d64ca45a3b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4b0b21e9d75c0145c9bd3fa5edf13913cf43f461
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="asynchronous-find-sample"></a><span data-ttu-id="11044-102">비동기 찾기 샘플</span><span class="sxs-lookup"><span data-stu-id="11044-102">Asynchronous Find Sample</span></span>
<span data-ttu-id="11044-103">이 샘플에서는 클라이언트 응용 프로그램에서 비동기 찾기 작업을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11044-103">This sample shows how to use the asynchronous find operation from a client application.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="11044-104">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="11044-104">Sample Details</span></span>  
 <span data-ttu-id="11044-105">이 디자인 패턴을 따르면 클라이언트가 찾기 요청의 결과로 찾은 끝점에 대한 알림을 비동기적으로 받을 수 있다는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11044-105">The benefit of following this design pattern is that the client is notified asynchronously of the endpoints located as a result of the find request.</span></span> <span data-ttu-id="11044-106">이 샘플이 작동하는 방식을 보려면 Client.cs 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="11044-106">To see how this works, open the Client.cs file.</span></span> <span data-ttu-id="11044-107"><xref:System.ServiceModel.Discovery.DiscoveryClient> 개체의 이벤트 처리기에는 두 개의 대리자가 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11044-107">Note the <xref:System.ServiceModel.Discovery.DiscoveryClient> object has two delegates attached to its event handlers.</span></span> <span data-ttu-id="11044-108">하나는 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> 이벤트가 발생할 때 호출되고 다른 하나는 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> 이벤트가 발생할 때마다 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="11044-108">One delegate is called when a <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> event is raised and another is called each time a <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> event is raised.</span></span> <span data-ttu-id="11044-109">이 샘플에서는 응용 프로그램에 이 패턴을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11044-109">The sample shows how you can utilize this pattern in your application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11044-110">이 샘플에서는 HTTP 끝점을 사용하며 이 샘플을 실행하려면 적절한 URL ACL을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11044-110">This sample uses HTTP endpoints and to run, proper URL ACLs must be added.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="11044-111">[HTTP 및 HTTPS 구성](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11044-111"> [Configuring HTTP and HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="11044-112">높은 권한으로 다음 명령을 실행하면 적절한 ACL이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="11044-112">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="11044-113">명령이 지정한 대로 작동하지 않는 경우 다음 인수의 도메인과 사용자 이름을 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11044-113">You may want to substitute your domain and username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="11044-114">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="11044-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="11044-115">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 AsyncFind.sln을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="11044-115">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the AsyncFind.sln.</span></span>  
  
2.  <span data-ttu-id="11044-116">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="11044-116">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="11044-117">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트를 열고 \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug 또는 \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug 디렉터리로 이동한 다음 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="11044-117">Open a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt and navigate to the \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug or \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug directory and run Service.exe.</span></span>  
  
4.  <span data-ttu-id="11044-118">서비스가 시작된 후 \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug 또는 WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug 디렉터리로 이동하여 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="11044-118">After the service has started, navigate to the \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug or WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug directory and run Client.exe.</span></span>  
  
5.  <span data-ttu-id="11044-119">클라이언트에서 서비스를 찾아 호출할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="11044-119">Observe the client is able to locate and call the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="11044-120">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11044-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="11044-121">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="11044-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="11044-122">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="11044-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="11044-123">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11044-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\AsyncFind`  
  
## <a name="see-also"></a><span data-ttu-id="11044-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11044-124">See Also</span></span>
