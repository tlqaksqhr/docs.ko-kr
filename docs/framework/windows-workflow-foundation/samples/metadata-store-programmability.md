---
title: "메타데이터 저장소 프로그래밍 기능"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b8bfce17169a1095d2d2817467fcc8f3366ead3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="metadata-store-programmability"></a><span data-ttu-id="069b4-102">메타데이터 저장소 프로그래밍 기능</span><span class="sxs-lookup"><span data-stu-id="069b4-102">Metadata Store Programmability</span></span>
<span data-ttu-id="069b4-103">메타데이터 저장소는 CLR 특성 형식의 임의의 메타데이터를 런타임에 형식에 연결할 수 있는 [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="069b4-103">The metadata store is a [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] feature that allows for the association of arbitrary metadata, in the form of CLR attributes, to types at runtime.</span></span> <span data-ttu-id="069b4-104">이를 통해 런타임 구성 요소와 해당 디자인 타임 구성 요소 간의 느슨한 결합이 가능할 뿐 아니라 런타임에 영향을 주지 않고 디자인 타임 구성 요소를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="069b4-104">This allows for a loose coupling between the run-time components and their design-time counterparts, as well as the ability to change the design-time components without affecting the runtime.</span></span> <span data-ttu-id="069b4-105">이 샘플에서는 제어 권한이 없는 소스인 런타임 형식에 특성을 적용하여 메타데이터 저장소를 기반으로 프로그래밍하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="069b4-105">The sample shows how to program against the metadata store by applying attributes to a run-time type, the source for which we have no control over.</span></span> <span data-ttu-id="069b4-106">즉, 호스팅 응용 프로그램이 형식 집합에 대한 메타데이터를 등록하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="069b4-106">The terminology typically used is that a hosting application registers the metadata for a set of types.</span></span>  
  
 <span data-ttu-id="069b4-107">출력에 예기치 않은 추가 특성인, 없는데 <!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`합니다.</span><span class="sxs-lookup"><span data-stu-id="069b4-107">Within the output, you may notice an additional, unexpected attribute, <!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`.</span></span> <span data-ttu-id="069b4-108">이 특성은 메타데이터 API를 사용할 때 추가되며 샘플 실행에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="069b4-108">This is added when using the Metadata API and has no impact on the running of the sample.</span></span>  
  
 <span data-ttu-id="069b4-109">이 샘플에서는 다음 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="069b4-109">This sample demonstrates:</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="069b4-110">세부 항목</span><span class="sxs-lookup"><span data-stu-id="069b4-110">Demonstrates</span></span>  
  
-   <span data-ttu-id="069b4-111">메타데이터 저장소 API를 사용하여 특성 삽입</span><span class="sxs-lookup"><span data-stu-id="069b4-111">Attribute injection using the metadata store API.</span></span>  
  
-   <span data-ttu-id="069b4-112">콜백 메커니즘을 사용하여 메타데이터 등록 지연</span><span class="sxs-lookup"><span data-stu-id="069b4-112">Using a callback mechanism to defer metadata registration.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="069b4-113">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="069b4-113">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="069b4-114">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 ProgrammingMetadataStore.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="069b4-114">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ProgrammingMetadataStore.sln solution file.</span></span>  
  
2.  <span data-ttu-id="069b4-115">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="069b4-115">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="069b4-116">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="069b4-116">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="069b4-117">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="069b4-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="069b4-118">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="069b4-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="069b4-119">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="069b4-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="069b4-120">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="069b4-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`