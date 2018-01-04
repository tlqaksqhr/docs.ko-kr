---
title: "워크플로 관리 끝점 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ac6e08f-c43d-4bb7-83c3-e3890a4dac03
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e516d41a9f9736877fb3974774ddaf4b3bddb198
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-management-endpoint-sample"></a><span data-ttu-id="5f169-102">워크플로 관리 끝점 샘플</span><span class="sxs-lookup"><span data-stu-id="5f169-102">Workflow Management Endpoint Sample</span></span>
<span data-ttu-id="5f169-103">이 샘플에서는 워크플로 제어 끝점을 사용하여 로컬 및 원격으로 워크플로를 만들고 실행하는 방법과</span><span class="sxs-lookup"><span data-stu-id="5f169-103">This sample shows how a workflow control endpoint can be used to create and run workflows both locally and remotely.</span></span> <span data-ttu-id="5f169-104">제어 끝점을 호스트하고 제어 끝점을 호출하여 워크플로 인스턴스를 만들고 실행하는 클라이언트를 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f169-104">The sample demonstrates how to host a control endpoint and write clients that call the control endpoint to create and run the instance of a workflow.</span></span> <span data-ttu-id="5f169-105">워크플로는 서비스가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5f169-105">The workflow is not a service.</span></span>  
  
 <span data-ttu-id="5f169-106">샘플의 서비스 쪽에서 워크플로가 WorkflowServiceHost로 호스트되고 WorkflowControlEndpoint가 추가되므로 클라이언트는 일시 중단, 시작 등의 제어 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f169-106">On the service side of the sample a workflow is hosted with WorkflowServiceHost and a WorkflowControlEndpoint is added so that clients can perform control operations (Suspend, Start, etc).</span></span> <span data-ttu-id="5f169-107">사용자 정의 CreationEndpoint도 추가되어 워크플로를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f169-107">A user-defined CreationEndpoint is also added to allow the workflow to be created.</span></span> <span data-ttu-id="5f169-108">그런 다음 서비스는 이러한 끝점을 사용하여 일시 중단 상태의 워크플로를 시작한 후 워크플로를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5f169-108">The service then uses these endpoints to start the workflow in a suspended state and then resume the workflow.</span></span> <span data-ttu-id="5f169-109">클라이언트는 동일한 작업을 클라이언트 코드에서 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5f169-109">The client performs the same operations but from the client code.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5f169-110">이러한 인터페이스 참조 [워크플로 제어 끝점](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) 및 [하는 방법: IIS에서 서비스가 아닌 워크플로 호스팅](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)</span><span class="sxs-lookup"><span data-stu-id="5f169-110"> these interfaces see, [Workflow Control Endpoint](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) and [How to: Host a non-service workflow in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="5f169-111">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="5f169-111">To run the sample</span></span>  
  
1.  <span data-ttu-id="5f169-112">관리자 권한으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5f169-112">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="5f169-113">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 ManagementEndpoint.sln 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5f169-113">Open the ManagementEndpoint.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="5f169-114">솔루션을 빌드하려면 CTRL + SHIFT + B 키를 누르거나 선택 **솔루션 빌드** 에서 **빌드** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="5f169-114">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
4.  <span data-ttu-id="5f169-115">ManagementEndpoint.exe 응용 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5f169-115">Start the ManagementEndpoint.exe application.</span></span>  
  
5.  <span data-ttu-id="5f169-116">Client.exe 응용 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5f169-116">Start the Client.exe application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5f169-117">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f169-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="5f169-118">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5f169-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5f169-119">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="5f169-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5f169-120">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f169-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ManagementEndpoint`