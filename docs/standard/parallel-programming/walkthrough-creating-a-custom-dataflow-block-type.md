---
title: "연습: 사용자 지정 데이터 흐름 블록 형식 만들기"
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
- Task Parallel Library, dataflows
- TPL dataflow library, creating custom dataflow blocks
- dataflow blocks, creating custom in TPL
ms.assetid: a6147146-0a6a-4d9b-ab0f-237b3c1ac691
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 809b21fa6e1470890011604792d849998dd03ede
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-creating-a-custom-dataflow-block-type"></a><span data-ttu-id="fee8c-102">연습: 사용자 지정 데이터 흐름 블록 형식 만들기</span><span class="sxs-lookup"><span data-stu-id="fee8c-102">Walkthrough: Creating a Custom Dataflow Block Type</span></span>
<span data-ttu-id="fee8c-103">TPL 데이터 흐름 라이브러리는 다양 한 기능을 사용할 수 있는 몇 가지 데이터 흐름 블록 형식은 제공 하지만 사용자 지정 블록 형식을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-103">Although the TPL Dataflow Library provides several dataflow block types that enable a variety of functionality, you can also create custom block types.</span></span> <span data-ttu-id="fee8c-104">이 문서에는 사용자 지정 동작을 구현 하는 데이터 흐름 블록 형식을 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-104">This document describes how to create a dataflow block type that implements custom behavior.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fee8c-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fee8c-105">Prerequisites</span></span>  
 <span data-ttu-id="fee8c-106">읽기 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) 이 문서를 읽기 전에 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-106">Read [Dataflow](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) before you read this document.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="fee8c-107">TPL 데이터 흐름 라이브러리(<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 네임스페이스)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]와 함께 배포되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-107">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="fee8c-108">설치 하는 <xref:System.Threading.Tasks.Dataflow> 네임 스페이스에서 프로젝트를 열고 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], 선택 **NuGet 패키지 관리** 프로젝트 메뉴에 대 한 온라인 검색에서는 `Microsoft.Tpl.Dataflow` 패키지 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-108">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
## <a name="defining-the-sliding-window-dataflow-block"></a><span data-ttu-id="fee8c-109">슬라이딩 창 데이터 흐름 블록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-109">Defining the Sliding Window Dataflow Block</span></span>  
 <span data-ttu-id="fee8c-110">입력된 값 버퍼링 되 고 다음 슬라이딩 윈도우 방식으로 출력 필요로 하는 데이터 흐름 응용 프로그램을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-110">Consider a dataflow application that requires that input values be buffered and then output in a sliding window manner.</span></span> <span data-ttu-id="fee8c-111">예를 들어 입력된 값 {0, 1, 2, 3, 4, 5} 및 3의 창 크기에 대 한 슬라이딩 창 데이터 흐름 블록을 생성 출력 배열의 {0, 1, 2} {1, 2, 3} {2, 3, 4}와 {3, 4, 5}.</span><span class="sxs-lookup"><span data-stu-id="fee8c-111">For example, for the input values {0, 1, 2, 3, 4, 5} and a window size of three, a sliding window dataflow block produces the output arrays {0, 1, 2}, {1, 2, 3}, {2, 3, 4}, and {3, 4, 5}.</span></span> <span data-ttu-id="fee8c-112">다음 섹션에서는이 사용자 지정 동작을 구현 하는 데이터 흐름 블록 형식을 만드는 두 가지 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-112">The following sections describe two ways to create a dataflow block type that implements this custom behavior.</span></span> <span data-ttu-id="fee8c-113">첫 번째 방법을 사용 하 여는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> 의 기능을 결합 하는 메서드는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 개체 및 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 하나의 전파자 블록에는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-113">The first technique uses the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> method to combine the functionality of an <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> object and an <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> object into one propagator block.</span></span> <span data-ttu-id="fee8c-114">파생 되는 클래스를 정의 하는 두 번째 기술은 <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> 하 고 사용자 지정 동작을 수행 하는 기존 기능을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-114">The second technique defines a class that derives from <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> and combines existing functionality to perform custom behavior.</span></span>  
  
## <a name="using-the-encapsulate-method-to-define-the-sliding-window-dataflow-block"></a><span data-ttu-id="fee8c-115">사용 하 여 슬라이딩 창 데이터 흐름 블록을 정의 하는 메서드를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-115">Using the Encapsulate Method to Define the Sliding Window Dataflow Block</span></span>  
 <span data-ttu-id="fee8c-116">다음 예제에서는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> 대상과 원본이에서 전파자 블록을 만드는 메서드를 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-116">The following example uses the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> method to create a propagator block from a target and a source.</span></span> <span data-ttu-id="fee8c-117">전파자 블록은 소스 블록과 대상 블록 역할 수신기 및 데이터의 보낸 사람을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-117">A propagator block enables a source block and a target block to act as a receiver and sender of data.</span></span>  
  
 <span data-ttu-id="fee8c-118">이 방법은 사용자 지정 데이터 흐름 기능이 필요 하지만 추가 메서드, 속성 또는 필드를 제공 하는 형식 필요 하지 않은 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-118">This technique is useful when you require custom dataflow functionality, but you do not require a type that provides additional methods, properties, or fields.</span></span>  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#1)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#1)]  
  
## <a name="deriving-from-ipropagatorblock-to-define-the-sliding-window-dataflow-block"></a><span data-ttu-id="fee8c-119">슬라이딩 창 데이터 흐름 블록을 정의 하려면 IPropagatorBlock에서 파생</span><span class="sxs-lookup"><span data-stu-id="fee8c-119">Deriving from IPropagatorBlock to Define the Sliding Window Dataflow Block</span></span>  
 <span data-ttu-id="fee8c-120">다음 예제와 `SlidingWindowBlock` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-120">The following example shows the `SlidingWindowBlock` class.</span></span> <span data-ttu-id="fee8c-121">이 클래스에서 파생 <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> 는 소스와 데이터의 대상으로 작동할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-121">This class derives from <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> so that it can act as both a source and a target of data.</span></span> <span data-ttu-id="fee8c-122">위의 예와 `SlidingWindowBlock` 클래스는 기존 데이터 흐름 블록 형식을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-122">As in the previous example, the `SlidingWindowBlock` class is built on existing dataflow block types.</span></span> <span data-ttu-id="fee8c-123">그러나는 `SlidingWindowBlock` 클래스 구현에 필요한 메서드는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, 및 <xref:System.Threading.Tasks.Dataflow.IDataflowBlock> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-123">However, the `SlidingWindowBlock` class also implements the methods that are required by the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, and <xref:System.Threading.Tasks.Dataflow.IDataflowBlock> interfaces.</span></span> <span data-ttu-id="fee8c-124">이러한 메서드를 앞으로 모든 미리 정의 된 데이터 흐름 블록 형식 멤버에 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-124">These methods all forward work to the predefined dataflow block type members.</span></span> <span data-ttu-id="fee8c-125">예를 들어는 `Post` 에 작업을 지연 하는 메서드는 `m_target` 이기도 데이터 멤버는 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-125">For example, the `Post` method defers work to the `m_target` data member, which is also an <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> object.</span></span>  
  
 <span data-ttu-id="fee8c-126">이 방법은 사용자 지정 데이터 흐름 기능을 필요로 하 고 추가 메서드, 속성 또는 필드를 제공 하는 형식에 있어야 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-126">This technique is useful when you require custom dataflow functionality, and also require a type that provides additional methods, properties, or fields.</span></span> <span data-ttu-id="fee8c-127">예를 들어는 `SlidingWindowBlock` 클래스에서 파생 되기도 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601> 제공할 수 있도록는 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 및 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="fee8c-127">For example, the `SlidingWindowBlock` class also derives from <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601> so that it can provide the <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> and <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A> methods.</span></span> <span data-ttu-id="fee8c-128">`SlidingWindowBlock` 클래스에서는 확장성을 제공 하 여는 `WindowSize` 슬라이딩 윈도우에 있는 요소의 수를 검색 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-128">The `SlidingWindowBlock` class also demonstrates extensibility by providing the `WindowSize` property, which retrieves the number of elements in the sliding window.</span></span>  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#2)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#2)]  
  
## <a name="the-complete-example"></a><span data-ttu-id="fee8c-129">전체 예제</span><span class="sxs-lookup"><span data-stu-id="fee8c-129">The Complete Example</span></span>  
 <span data-ttu-id="fee8c-130">다음 예제에서는 이 연습의 전체 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-130">The following example shows the complete code for this walkthrough.</span></span> <span data-ttu-id="fee8c-131">또한 블록, 여기에서 읽고 쓰고 콘솔에 결과 출력 하는 메서드에서 두 슬라이딩 창 블록을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-131">It also demonstrates how to use the both sliding window blocks in a method that writes to the block, reads from it, and prints the results to the console.</span></span>  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#100)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fee8c-132">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="fee8c-132">Compiling the Code</span></span>  
 <span data-ttu-id="fee8c-133">예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `SlidingWindowBlock.cs` (`SlidingWindowBlock.vb` 에 대 한 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 및 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee8c-133">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `SlidingWindowBlock.cs` (`SlidingWindowBlock.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="fee8c-134">**csc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**</span><span class="sxs-lookup"><span data-stu-id="fee8c-134">**csc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="fee8c-135">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**</span><span class="sxs-lookup"><span data-stu-id="fee8c-135">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fee8c-136">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fee8c-136">Next Steps</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fee8c-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fee8c-137">See Also</span></span>  
 [<span data-ttu-id="fee8c-138">데이터 흐름</span><span class="sxs-lookup"><span data-stu-id="fee8c-138">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
