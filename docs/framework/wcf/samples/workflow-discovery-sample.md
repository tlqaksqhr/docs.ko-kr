---
title: "Workflow Discovery 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f778fead0e09be36ca2a829dde9cf906f4fcaa9f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-discovery-sample"></a><span data-ttu-id="a5d4d-102">Workflow Discovery 샘플</span><span class="sxs-lookup"><span data-stu-id="a5d4d-102">Workflow Discovery Sample</span></span>
<span data-ttu-id="a5d4d-103">이 샘플에서는 워크플로 서비스를 검색 가능하게 만드는 방법과 특정 서비스를 검색하는 사용자 지정 코드 활동을 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-103">This sample demonstrates how to make a workflow service discoverable and how to author a custom code activity that searches for a particular service.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="a5d4d-104">세부 항목</span><span class="sxs-lookup"><span data-stu-id="a5d4d-104">Demonstrates</span></span>  
 <span data-ttu-id="a5d4d-105">찾기 활동 및 워크플로 사용</span><span class="sxs-lookup"><span data-stu-id="a5d4d-105">Discovery Find Activity and Workflow Usage</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="a5d4d-106">토론</span><span class="sxs-lookup"><span data-stu-id="a5d4d-106">Discussion</span></span>  
 <span data-ttu-id="a5d4d-107">샘플의 첫 번째 부분에서는 구성을 사용하여 워크플로 서비스를 검색 가능하게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-107">In the first part of the sample, a workflow service is made discoverable using configuration.</span></span> <span data-ttu-id="a5d4d-108">또한 구성을 사용하여 범위와 같은 사용자 지정 메타데이터로 서비스를 적절하게 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-108">Configuration can also be used to apply the service appropriately with custom metadata (such as scopes).</span></span> <span data-ttu-id="a5d4d-109">클라이언트에서 이 샘플은 검색을 사용하여 특정 계약과 일치하는 서비스를 검색하는 사용자 지정 코드 활동을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-109">On the client, the sample uses a custom code activity, which uses Discovery to search for a service matching a particular contract.</span></span> <span data-ttu-id="a5d4d-110">코드 활동은 URI를 출력하며 이 URI는 나중에 보내기 활동에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-110">The code activity outputs a URI, which is later used by a send activity.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a5d4d-111">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="a5d4d-111">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a5d4d-112">이 샘플은 실행 하려면 적절 한 URL Acl을 가져야 하는 HTTP 끝점 사용 (참조 [HTTP 및 HTTPS 구성](http://go.microsoft.com/fwlink/?LinkId=70353) 세부 정보에 대 한).</span><span class="sxs-lookup"><span data-stu-id="a5d4d-112">This sample uses HTTP endpoints, which must have proper URL ACLs to run (see [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) for details).</span></span> <span data-ttu-id="a5d4d-113">권한이 높은 명령 프롬프트에서 다음 명령을 실행하면 적절한 ACL이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-113">Executing the following command at an elevated command prompt should add the appropriate ACLs.</span></span> <span data-ttu-id="a5d4d-114">셸에서 변수 형식을 인식하지 못하는 경우 다음 인수 대신 도메인과 사용자 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-114">Substitute your Domain and Username for the following arguments if your shell does not understand the variable format.</span></span>  
  
     <span data-ttu-id="a5d4d-115">**netsh http urlacl url 추가 = http: / / +: 8000 / 사용자 = % 도메인 %\\% UserName %**</span><span class="sxs-lookup"><span data-stu-id="a5d4d-115">**netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\\%UserName%**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a5d4d-116">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a5d4d-117">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-117">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a5d4d-118">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a5d4d-119">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-119">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`
