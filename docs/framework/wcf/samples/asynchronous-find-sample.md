---
title: 비동기 찾기 샘플
ms.date: 03/30/2017
ms.assetid: 7a713a25-c1f4-42e1-8c4a-93d64ca45a3b
ms.openlocfilehash: ed900ba3cd1b55f4e35ec0d2b92ef6b7283b498e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33500300"
---
# <a name="asynchronous-find-sample"></a><span data-ttu-id="cf223-102">비동기 찾기 샘플</span><span class="sxs-lookup"><span data-stu-id="cf223-102">Asynchronous Find Sample</span></span>
<span data-ttu-id="cf223-103">이 샘플에서는 클라이언트 응용 프로그램에서 비동기 찾기 작업을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-103">This sample shows how to use the asynchronous find operation from a client application.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="cf223-104">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="cf223-104">Sample Details</span></span>  
 <span data-ttu-id="cf223-105">이 디자인 패턴을 따르면 클라이언트가 찾기 요청의 결과로 찾은 끝점에 대한 알림을 비동기적으로 받을 수 있다는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-105">The benefit of following this design pattern is that the client is notified asynchronously of the endpoints located as a result of the find request.</span></span> <span data-ttu-id="cf223-106">이 샘플이 작동하는 방식을 보려면 Client.cs 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-106">To see how this works, open the Client.cs file.</span></span> <span data-ttu-id="cf223-107"><xref:System.ServiceModel.Discovery.DiscoveryClient> 개체의 이벤트 처리기에는 두 개의 대리자가 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-107">Note the <xref:System.ServiceModel.Discovery.DiscoveryClient> object has two delegates attached to its event handlers.</span></span> <span data-ttu-id="cf223-108">하나는 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> 이벤트가 발생할 때 호출되고 다른 하나는 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> 이벤트가 발생할 때마다 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-108">One delegate is called when a <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> event is raised and another is called each time a <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> event is raised.</span></span> <span data-ttu-id="cf223-109">이 샘플에서는 응용 프로그램에 이 패턴을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-109">The sample shows how you can utilize this pattern in your application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf223-110">이 샘플에서는 HTTP 끝점을 사용하며 이 샘플을 실행하려면 적절한 URL ACL을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-110">This sample uses HTTP endpoints and to run, proper URL ACLs must be added.</span></span> <span data-ttu-id="cf223-111">자세한 내용은 참조 [HTTP 및 HTTPS 구성](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-111">For more information, see [Configuring HTTP and HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="cf223-112">높은 권한으로 다음 명령을 실행하면 적절한 ACL이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-112">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="cf223-113">명령이 지정한 대로 작동하지 않는 경우 다음 인수의 도메인과 사용자 이름을 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-113">You may want to substitute your domain and username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cf223-114">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="cf223-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="cf223-115">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 AsyncFind.sln을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-115">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the AsyncFind.sln.</span></span>  
  
2.  <span data-ttu-id="cf223-116">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-116">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="cf223-117">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트를 열고 \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug 또는 \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug 디렉터리로 이동한 다음 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-117">Open a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt and navigate to the \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug or \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug directory and run Service.exe.</span></span>  
  
4.  <span data-ttu-id="cf223-118">서비스가 시작된 후 \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug 또는 WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug 디렉터리로 이동하여 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-118">After the service has started, navigate to the \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug or WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug directory and run Client.exe.</span></span>  
  
5.  <span data-ttu-id="cf223-119">클라이언트에서 서비스를 찾아 호출할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-119">Observe the client is able to locate and call the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf223-120">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cf223-121">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="cf223-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cf223-122">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="cf223-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cf223-123">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf223-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\AsyncFind`  
  
## <a name="see-also"></a><span data-ttu-id="cf223-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf223-124">See Also</span></span>
