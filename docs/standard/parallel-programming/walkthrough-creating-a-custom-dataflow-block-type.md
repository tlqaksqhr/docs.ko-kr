---
title: '연습: 사용자 지정 데이터 흐름 블록 형식 만들기'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, creating custom dataflow blocks
- dataflow blocks, creating custom in TPL
ms.assetid: a6147146-0a6a-4d9b-ab0f-237b3c1ac691
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fbc81729e8280f3a062cfa8290b102349e80e7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-creating-a-custom-dataflow-block-type"></a><span data-ttu-id="e0653-102">연습: 사용자 지정 데이터 흐름 블록 형식 만들기</span><span class="sxs-lookup"><span data-stu-id="e0653-102">Walkthrough: Creating a Custom Dataflow Block Type</span></span>
<span data-ttu-id="e0653-103">TPL 데이터 흐름 라이브러리는 다양한 기능을 구현하는 여러 데이터 흐름 블록 형식을 제공하지만 사용자 지정 블록 형식을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-103">Although the TPL Dataflow Library provides several dataflow block types that enable a variety of functionality, you can also create custom block types.</span></span> <span data-ttu-id="e0653-104">이 문서에서는 사용자 지정 동작을 구현하는 데이터 흐름 블록 형식을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-104">This document describes how to create a dataflow block type that implements custom behavior.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e0653-105">전제 조건</span><span class="sxs-lookup"><span data-stu-id="e0653-105">Prerequisites</span></span>  
 <span data-ttu-id="e0653-106">이 문서를 읽기 전에 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)을 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="e0653-106">Read [Dataflow](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) before you read this document.</span></span>  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="defining-the-sliding-window-dataflow-block"></a><span data-ttu-id="e0653-107">슬라이딩 윈도우 데이터 흐름 블록 정의</span><span class="sxs-lookup"><span data-stu-id="e0653-107">Defining the Sliding Window Dataflow Block</span></span>  
 <span data-ttu-id="e0653-108">입력 값을 버퍼링한 다음, 슬라이딩 윈도우 방식으로 출력해야 하는 데이터 흐름 응용 프로그램을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-108">Consider a dataflow application that requires that input values be buffered and then output in a sliding window manner.</span></span> <span data-ttu-id="e0653-109">예를 들어 입력 값 {0, 1, 2, 3, 4, 5} 및 윈도우 크기가 3인 경우 슬라이딩 윈도우 데이터 흐름 블록은 출력 배열 {0, 1, 2}, {1, 2, 3}, {2, 3, 4}, {3, 4, 5}를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-109">For example, for the input values {0, 1, 2, 3, 4, 5} and a window size of three, a sliding window dataflow block produces the output arrays {0, 1, 2}, {1, 2, 3}, {2, 3, 4}, and {3, 4, 5}.</span></span> <span data-ttu-id="e0653-110">다음 섹션에서는 이 사용자 지정 동작을 구현하는 데이터 흐름 블록 형식을 만드는 두 가지 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-110">The following sections describe two ways to create a dataflow block type that implements this custom behavior.</span></span> <span data-ttu-id="e0653-111">첫 번째 방법은 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> 메서드를 사용하여 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 개체와 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 개체의 기능을 하나의 전파자 블록으로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-111">The first technique uses the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> method to combine the functionality of an <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> object and an <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> object into one propagator block.</span></span> <span data-ttu-id="e0653-112">두 번째 방법은 <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602>에서 파생되는 클래스를 정의하고 기존 기능을 결합하여 사용자 지정 동작을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-112">The second technique defines a class that derives from <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> and combines existing functionality to perform custom behavior.</span></span>  
  
## <a name="using-the-encapsulate-method-to-define-the-sliding-window-dataflow-block"></a><span data-ttu-id="e0653-113">Encapsulate 메서드를 사용하여 슬라이딩 윈도우 데이터 흐름 블록 정의</span><span class="sxs-lookup"><span data-stu-id="e0653-113">Using the Encapsulate Method to Define the Sliding Window Dataflow Block</span></span>  
 <span data-ttu-id="e0653-114">다음 예제에서는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> 메서드를 사용하여 대상과 소스에서 전파자 블록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-114">The following example uses the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> method to create a propagator block from a target and a source.</span></span> <span data-ttu-id="e0653-115">전파자 블록을 사용하면 소스 블록과 대상 블록이 데이터 수신자 및 송신자 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-115">A propagator block enables a source block and a target block to act as a receiver and sender of data.</span></span>  
  
 <span data-ttu-id="e0653-116">이 방법은 사용자 지정 데이터 흐름 기능이 필요하지만 추가 메서드, 속성 또는 필드를 제공하는 형식이 필요하지 않은 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-116">This technique is useful when you require custom dataflow functionality, but you do not require a type that provides additional methods, properties, or fields.</span></span>  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#1)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#1)]  
  
## <a name="deriving-from-ipropagatorblock-to-define-the-sliding-window-dataflow-block"></a><span data-ttu-id="e0653-117">IPropagatorBlock에서 파생시켜 슬라이딩 윈도우 데이터 흐름 블록 정의</span><span class="sxs-lookup"><span data-stu-id="e0653-117">Deriving from IPropagatorBlock to Define the Sliding Window Dataflow Block</span></span>  
 <span data-ttu-id="e0653-118">다음 예제에서는 `SlidingWindowBlock` 클래스를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-118">The following example shows the `SlidingWindowBlock` class.</span></span> <span data-ttu-id="e0653-119">이 클래스는 <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602>에서 파생되므로 데이터의 소스 및 대상 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-119">This class derives from <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> so that it can act as both a source and a target of data.</span></span> <span data-ttu-id="e0653-120">이전 예제와 같이 `SlidingWindowBlock` 클래스는 기존 데이터 흐름 블록 형식에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-120">As in the previous example, the `SlidingWindowBlock` class is built on existing dataflow block types.</span></span> <span data-ttu-id="e0653-121">그러나 `SlidingWindowBlock` 클래스는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 및 <xref:System.Threading.Tasks.Dataflow.IDataflowBlock> 인터페이스에 필요한 메서드도 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-121">However, the `SlidingWindowBlock` class also implements the methods that are required by the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, and <xref:System.Threading.Tasks.Dataflow.IDataflowBlock> interfaces.</span></span> <span data-ttu-id="e0653-122">이러한 메서드는 모두 미리 정의된 데이터 흐름 블록 형식 멤버에 대한 작업을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-122">These methods all forward work to the predefined dataflow block type members.</span></span> <span data-ttu-id="e0653-123">예를 들어 `Post` 메서드는 작업을 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 개체이기도 한 `m_target` 데이터 멤버로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-123">For example, the `Post` method defers work to the `m_target` data member, which is also an <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> object.</span></span>  
  
 <span data-ttu-id="e0653-124">이 방법은 사용자 지정 데이터 흐름 기능이 필요하고 추가 메서드, 속성 또는 필드를 제공하는 형식도 필요한 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-124">This technique is useful when you require custom dataflow functionality, and also require a type that provides additional methods, properties, or fields.</span></span> <span data-ttu-id="e0653-125">예를 들어 `SlidingWindowBlock` 클래스는 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601>에서 파생되므로 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 및 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A> 메서드를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-125">For example, the `SlidingWindowBlock` class also derives from <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601> so that it can provide the <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> and <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A> methods.</span></span> <span data-ttu-id="e0653-126">또한 `SlidingWindowBlock` 클래스는 슬라이딩 윈도우에서 요소 수를 검색하는 `WindowSize` 속성을 제공하여 확장성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-126">The `SlidingWindowBlock` class also demonstrates extensibility by providing the `WindowSize` property, which retrieves the number of elements in the sliding window.</span></span>  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#2)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#2)]  
  
## <a name="the-complete-example"></a><span data-ttu-id="e0653-127">전체 예제</span><span class="sxs-lookup"><span data-stu-id="e0653-127">The Complete Example</span></span>  
 <span data-ttu-id="e0653-128">다음 예제에서는 이 연습의 전체 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-128">The following example shows the complete code for this walkthrough.</span></span> <span data-ttu-id="e0653-129">또한 블록에 쓰고, 블록에서 읽고, 콘솔에 결과를 인쇄하는 메서드에서 두 슬라이딩 윈도우 블록을 모두 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-129">It also demonstrates how to use the both sliding window blocks in a method that writes to the block, reads from it, and prints the results to the console.</span></span>  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#100)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e0653-130">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e0653-130">Compiling the Code</span></span>  
 <span data-ttu-id="e0653-131">예제 코드를 복사하여 Visual Studio 프로젝트에 붙여넣거나, `SlidingWindowBlock.cs`(Visual Basic의 경우 `SlidingWindowBlock.vb`) 파일에 붙여넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0653-131">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `SlidingWindowBlock.cs` (`SlidingWindowBlock.vb` for Visual Basic) and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="e0653-132">Visual C#</span><span class="sxs-lookup"><span data-stu-id="e0653-132">Visual C#</span></span>  
  
 <span data-ttu-id="e0653-133">**csc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**</span><span class="sxs-lookup"><span data-stu-id="e0653-133">**csc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**</span></span>  
  
 <span data-ttu-id="e0653-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e0653-134">Visual Basic</span></span>  
  
 <span data-ttu-id="e0653-135">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**</span><span class="sxs-lookup"><span data-stu-id="e0653-135">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**</span></span>  

## <a name="see-also"></a><span data-ttu-id="e0653-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0653-136">See Also</span></span>  
 [<span data-ttu-id="e0653-137">데이터 흐름</span><span class="sxs-lookup"><span data-stu-id="e0653-137">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
