---
title: "UriTemplate 테이블 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5dd1d38f-1989-4c64-820d-821f5a02216a
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c4561590228531066014e69c03fcef0a6142cd70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="uritemplate-table-sample"></a><span data-ttu-id="5e9d3-102">UriTemplate 테이블 샘플</span><span class="sxs-lookup"><span data-stu-id="5e9d3-102">UriTemplate Table Sample</span></span>
<span data-ttu-id="5e9d3-103"><xref:System.UriTemplateTable> 클래스는 `UriTemplate` 인스턴스 집합으로 작업할 수 있도록 사전과 비슷한 연결 테이블 구조체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5e9d3-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of `UriTemplate` instances.</span></span> <span data-ttu-id="5e9d3-104">특정 URI(Uniform Resource Identifier)를 테이블의 모든 템플릿에 대해 효율적으로 일치시킬 수 있으며 일치한 템플릿과 연결된 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e9d3-104">Specific Uniform Resource Identifiers (URIs) can be matched efficiently against all templates in the table, and data associated with the matched template can be retrieved.</span></span>  
  
 <span data-ttu-id="5e9d3-105">이 샘플에서는 `UriTemplateTable` 클래스와 관련된 다음 주요 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5e9d3-105">This sample demonstrates the following key concepts related to the `UriTemplateTable` class:</span></span>  
  
-   <span data-ttu-id="5e9d3-106">`UriTemplateTable`을 인스턴스화하는 구문</span><span class="sxs-lookup"><span data-stu-id="5e9d3-106">Syntax for instantiating a `UriTemplateTable`.</span></span>  
  
-   <span data-ttu-id="5e9d3-107">`UriTemplateTable`을 키/값 쌍의 집합으로 채우기</span><span class="sxs-lookup"><span data-stu-id="5e9d3-107">Populating a `UriTemplateTable` with a set of key/value pairs.</span></span>  
  
-   <span data-ttu-id="5e9d3-108"><xref:System.UriTemplateTable.MatchSingle%2A>을 사용하여 후보 URI를 테이블과 일치시키기</span><span class="sxs-lookup"><span data-stu-id="5e9d3-108">Matching a candidate URI against the table using <xref:System.UriTemplateTable.MatchSingle%2A>.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5e9d3-109">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="5e9d3-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="5e9d3-110">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="5e9d3-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="5e9d3-111">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5e9d3-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5e9d3-112">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e9d3-112">The samples may already be installed on your computer.</span></span> <span data-ttu-id="5e9d3-113">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5e9d3-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5e9d3-114">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="5e9d3-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5e9d3-115">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e9d3-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateTable`  
  
## <a name="see-also"></a><span data-ttu-id="5e9d3-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e9d3-116">See Also</span></span>  
 [<span data-ttu-id="5e9d3-117">UriTemplate 테이블 디스패처 샘플</span><span class="sxs-lookup"><span data-stu-id="5e9d3-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)  
 [<span data-ttu-id="5e9d3-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="5e9d3-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
