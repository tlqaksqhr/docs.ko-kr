---
title: UriTemplate 테이블 디스패처 샘플
ms.date: 03/30/2017
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
ms.openlocfilehash: 9075d779b2ca2360c5ad28c3872c54c64aa200b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33506018"
---
# <a name="uritemplate-table-dispatcher-sample"></a><span data-ttu-id="bbd54-102">UriTemplate 테이블 디스패처 샘플</span><span class="sxs-lookup"><span data-stu-id="bbd54-102">UriTemplate Table Dispatcher Sample</span></span>
<span data-ttu-id="bbd54-103"><xref:System.UriTemplateTable> 클래스는 <xref:System.UriTemplate> 인스턴스 집합으로 작업할 수 있도록 사전과 비슷한 연결 테이블 구조체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bbd54-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of <xref:System.UriTemplate> instances.</span></span> <span data-ttu-id="bbd54-104">이 샘플에서는 `UriTemplateTable`을 사용하여 빌드한 기본 디스패치 엔진을 보여 줍니다. `UriTemplateTable` 클래스의 일반적인 사용 시나리오에 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbd54-104">This sample demonstrates a basic dispatching engine built using `UriTemplateTable`, a common usage scenario for the `UriTemplateTable` class.</span></span>  
  
 <span data-ttu-id="bbd54-105">이 샘플에서는 `UriTemplateTable` 클래스의 다음 핵심 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bbd54-105">This sample demonstrates the following key concepts for the `UriTemplateTable` class:</span></span>  
  
-   <span data-ttu-id="bbd54-106">위임과 `UriTemplates`에 있는 `UriTemplateTable`의 연결</span><span class="sxs-lookup"><span data-stu-id="bbd54-106">Associating delegates with `UriTemplates` in a `UriTemplateTable`.</span></span>  
  
-   <span data-ttu-id="bbd54-107"><xref:System.UriTemplateTable.MatchSingle%2A>을 사용하여 특성 URI의 올바른 처리기 위임 가져오기.</span><span class="sxs-lookup"><span data-stu-id="bbd54-107">Using <xref:System.UriTemplateTable.MatchSingle%2A> to obtain the correct handler delegate for a particular URI.</span></span>  
  
-   <span data-ttu-id="bbd54-108">처리기 위임을 호출하여 요청 처리.</span><span class="sxs-lookup"><span data-stu-id="bbd54-108">Invoking the handler delegate to process the request.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bbd54-109">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="bbd54-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="bbd54-110">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bbd54-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="bbd54-111">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bbd54-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bbd54-112">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbd54-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bbd54-113">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bbd54-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bbd54-114">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="bbd54-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bbd54-115">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbd54-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a><span data-ttu-id="bbd54-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bbd54-116">See Also</span></span>  
 [<span data-ttu-id="bbd54-117">UriTemplate 테이블</span><span class="sxs-lookup"><span data-stu-id="bbd54-117">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [<span data-ttu-id="bbd54-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="bbd54-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
