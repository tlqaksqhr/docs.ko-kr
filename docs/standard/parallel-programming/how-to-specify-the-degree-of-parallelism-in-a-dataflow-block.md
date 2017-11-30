---
title: "방법: 데이터 흐름 블록의 병렬 처리 수준 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow block, specifying parallelism in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, specifying parallelism
ms.assetid: e4088541-ee05-40db-95f5-147cfe62fde7
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c1ccd64a9acbc75a30984719671af2dc7dda6922
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-specify-the-degree-of-parallelism-in-a-dataflow-block"></a><span data-ttu-id="b3e67-102">방법: 데이터 흐름 블록의 병렬 처리 수준 지정</span><span class="sxs-lookup"><span data-stu-id="b3e67-102">How to: Specify the Degree of Parallelism in a Dataflow Block</span></span>
<span data-ttu-id="b3e67-103">이 문서에서는 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType> 속성을 설정하여 실행 데이터 흐름 블록이 한 번에 둘 이상의 메시지를 처리할 수 있도록 하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e67-103">This document describes how to set the <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType> property to enable an execution dataflow block to process more than one message at a time.</span></span> <span data-ttu-id="b3e67-104">이 방법은 오래 실행되는 계산을 수행하는 데이터 흐름 블록이 있고 메시지를 병렬로 처리하면 혜택을 얻을 수 있는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e67-104">Doing this is useful when you have a dataflow block that performs a long-running computation and can benefit from processing messages in parallel.</span></span> <span data-ttu-id="b3e67-105">이 예제에서는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType> 클래스를 사용하여 여러 데이터 흐름 작업을 동시에 수행합니다. 하지만 TPL 데이터 흐름 라이브러리에서 제공하는 미리 정의된 실행 블록 형식인 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>에서 최대 병렬 처리 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e67-105">This example uses the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType> class to perform multiple dataflow operations concurrently; however, you can specify the maximum degree of parallelism in any of the predefined execution block types that the TPL Dataflow Library provides, <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType>, and <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="b3e67-106">TPL 데이터 흐름 라이브러리(<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 네임스페이스)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]와 함께 배포되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e67-106">The TPL Dataflow Library (the <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="b3e67-107">설치 하는 <xref:System.Threading.Tasks.Dataflow> 네임 스페이스에서 프로젝트를 열고 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], 선택 **NuGet 패키지 관리** 프로젝트 메뉴에 대 한 온라인 검색에서는 `Microsoft.Tpl.Dataflow` 패키지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e67-107">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3e67-108">예제</span><span class="sxs-lookup"><span data-stu-id="b3e67-108">Example</span></span>  
 <span data-ttu-id="b3e67-109">다음 예제에서는 두 가지 데이터 흐름 계산을 수행하고 각 계산에 필요한 경과 시간을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e67-109">The following example performs two dataflow computations and prints the elapsed time that is required for each computation.</span></span> <span data-ttu-id="b3e67-110">첫 번째 계산에서는 최대 병렬 처리 수준을 기본값 1로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e67-110">The first computation specifies a maximum degree of parallelism of 1, which is the default.</span></span> <span data-ttu-id="b3e67-111">최대 병렬 처리 수준이 1이면 데이터 흐름 블록이 메시지를 연속적으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e67-111">A maximum degree of parallelism of 1 causes the dataflow block to process messages serially.</span></span> <span data-ttu-id="b3e67-112">두 번째 계산은 사용 가능한 프로세서 수와 동일한 최대 병렬 처리 수준을 지정하는 점을 제외하고 첫 번째 계산과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e67-112">The second computation resembles the first, except that it specifies a maximum degree of parallelism that is equal to the number of available processors.</span></span> <span data-ttu-id="b3e67-113">이러한 지정에 따라 데이터 흐름 블록이 여러 작업을 병렬로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e67-113">This enables the dataflow block to perform multiple operations in parallel.</span></span>  
  
 [!code-csharp[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_degreeofparallelism/cs/dataflowdegreeofparallelism.cs#1)]
 [!code-vb[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_degreeofparallelism/vb/dataflowdegreeofparallelism.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b3e67-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b3e67-114">Compiling the Code</span></span>  
 <span data-ttu-id="b3e67-115">예제 코드를 복사하여 Visual Studio 프로젝트에 붙여 넣거나, `DataflowDegreeOfParallelism.cs`([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]의 경우 `DataflowDegreeOfParallelism.vb`) 파일에 붙여 넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e67-115">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowDegreeOfParallelism.cs` (`DataflowDegreeOfParallelism.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="b3e67-116">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.cs**</span><span class="sxs-lookup"><span data-stu-id="b3e67-116">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="b3e67-117">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.vb**</span><span class="sxs-lookup"><span data-stu-id="b3e67-117">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b3e67-118">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b3e67-118">Robust Programming</span></span>  
 <span data-ttu-id="b3e67-119">기본적으로 미리 정의된 각각의 데이터 흐름 블록은 메시지를 받은 순서대로 메시지를 전파합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e67-119">By default, each predefined dataflow block propagates out messages in the order in which the messages are received.</span></span>  <span data-ttu-id="b3e67-120">1보다 큰 최대 병렬 처리 수준을 지정하는 경우 여러 메시지가 동시에 처리되지만 메시지는 수신된 순서대로 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3e67-120">Although multiple messages are processed simultaneously when you specify a maximum degree of parallelism that is greater than 1, they are still propagated out in the order in which they are received.</span></span>  
  
 <span data-ttu-id="b3e67-121"><xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> 속성이 최대 병렬 처리 수준을 나타내기 때문에 데이터 흐름 블록은 지정한 것보다 낮은 병렬 처리 수준으로 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e67-121">Because the <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> property represents the maximum degree of parallelism, the dataflow block might execute with a lesser degree of parallelism than you specify.</span></span> <span data-ttu-id="b3e67-122">데이터 흐름 블록은 기능적 요구 사항을 충족하기 위해서나 사용 가능한 시스템 리소스의 부족 때문에 낮은 병렬 처리 수준을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e67-122">The dataflow block can use a lesser degree of parallelism to meet its functional requirements or to account for a lack of available system resources.</span></span> <span data-ttu-id="b3e67-123">데이터 흐름 블록은 지정한 것보다 높은 병렬 처리 수준을 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e67-123">A dataflow block never chooses a greater degree of parallelism than you specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3e67-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3e67-124">See Also</span></span>  
 [<span data-ttu-id="b3e67-125">데이터 흐름</span><span class="sxs-lookup"><span data-stu-id="b3e67-125">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
