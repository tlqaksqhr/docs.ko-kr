---
title: "UriTemplate 테이블 디스패처 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3d2332e5f23c46454d1a876c3e21c5a575d10bf5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="uritemplate-table-dispatcher-sample"></a><span data-ttu-id="cda48-102">UriTemplate 테이블 디스패처 샘플</span><span class="sxs-lookup"><span data-stu-id="cda48-102">UriTemplate Table Dispatcher Sample</span></span>
<span data-ttu-id="cda48-103"><xref:System.UriTemplateTable> 클래스는 <xref:System.UriTemplate> 인스턴스 집합으로 작업할 수 있도록 사전과 비슷한 연결 테이블 구조체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cda48-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of <xref:System.UriTemplate> instances.</span></span> <span data-ttu-id="cda48-104">이 샘플에서는 `UriTemplateTable`을 사용하여 빌드한 기본 디스패치 엔진을 보여 줍니다. `UriTemplateTable` 클래스의 일반적인 사용 시나리오에 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="cda48-104">This sample demonstrates a basic dispatching engine built using `UriTemplateTable`, a common usage scenario for the `UriTemplateTable` class.</span></span>  
  
 <span data-ttu-id="cda48-105">이 샘플에서는 `UriTemplateTable` 클래스의 다음 핵심 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cda48-105">This sample demonstrates the following key concepts for the `UriTemplateTable` class:</span></span>  
  
-   <span data-ttu-id="cda48-106">위임과 `UriTemplates`에 있는 `UriTemplateTable`의 연결</span><span class="sxs-lookup"><span data-stu-id="cda48-106">Associating delegates with `UriTemplates` in a `UriTemplateTable`.</span></span>  
  
-   <span data-ttu-id="cda48-107"><xref:System.UriTemplateTable.MatchSingle%2A>을 사용하여 특성 URI의 올바른 처리기 위임 가져오기.</span><span class="sxs-lookup"><span data-stu-id="cda48-107">Using <xref:System.UriTemplateTable.MatchSingle%2A> to obtain the correct handler delegate for a particular URI.</span></span>  
  
-   <span data-ttu-id="cda48-108">처리기 위임을 호출하여 요청 처리.</span><span class="sxs-lookup"><span data-stu-id="cda48-108">Invoking the handler delegate to process the request.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cda48-109">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="cda48-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="cda48-110">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="cda48-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="cda48-111">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cda48-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cda48-112">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cda48-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cda48-113">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="cda48-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cda48-114">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="cda48-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cda48-115">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cda48-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a><span data-ttu-id="cda48-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cda48-116">See Also</span></span>  
 [<span data-ttu-id="cda48-117">UriTemplate 테이블</span><span class="sxs-lookup"><span data-stu-id="cda48-117">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [<span data-ttu-id="cda48-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="cda48-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
