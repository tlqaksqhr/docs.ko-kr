---
title: "방법: 데이터 흐름 블록에 메시지 쓰기 및 테이터 흐름 블록에서 메시지 읽기"
ms.date: 03/30/2017
ms.prod: .net
ms.technology: dotnet-standard
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, reading and writing messages
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b64ef07c6ef28377c11dc879ad17f7c806e9f66a
ms.sourcegitcommit: 6a9030eb5bd0f00e1d144f81958adb195cfb1f6f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-write-messages-to-and-read-messages-from-a-dataflow-block"></a><span data-ttu-id="a864f-102">방법: 데이터 흐름 블록에 메시지 쓰기 및 테이터 흐름 블록에서 메시지 읽기</span><span class="sxs-lookup"><span data-stu-id="a864f-102">How to: Write Messages to and Read Messages from a Dataflow Block</span></span>
<span data-ttu-id="a864f-103">이 문서에서는 TPL 데이터 흐름 라이브러리를 사용하여 데이터 흐름 블록에서 메시지를 읽고 쓰는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-103">This document describes how to use the TPL Dataflow Library to write messages to and read messages from a dataflow block.</span></span> <span data-ttu-id="a864f-104">TPL 데이터 흐름 라이브러리는 데이터 흐름 블록에서 메시지를 쓰고 읽기 위한 동기 메서드와 비동기 메서드를 모두 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-104">The TPL Dataflow Library provides both synchronous and asynchronous methods for writing messages to and reading messages from a dataflow block.</span></span> <span data-ttu-id="a864f-105">이 문서에서는 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-105">This document uses the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="a864f-106"><xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 클래스는 메시지를 버퍼링하고 메시지 소스와 메시지 대상으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-106">The <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> class buffers messages and behaves as both a message source and as a message target.</span></span>  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="writing-to-and-reading-from-a-dataflow-block-synchronously"></a><span data-ttu-id="a864f-107">동기적으로 데이터 흐름 블록에서 읽고 쓰기</span><span class="sxs-lookup"><span data-stu-id="a864f-107">Writing to and Reading from a Dataflow Block Synchronously</span></span>  
 <span data-ttu-id="a864f-108">다음 예제에서는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 메서드를 사용하여 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 데이터 흐름 블록에 쓰고 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> 메서드를 사용하여 동일한 개체에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-108">The following example uses the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> method to write to a <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> dataflow block and the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> method to read from the same object.</span></span>  
  
 [!code-csharp[TPLDataflow_ReadWrite#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#2)]
 [!code-vb[TPLDataflow_ReadWrite#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#2)]  
  
 <span data-ttu-id="a864f-109">또한 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 메서드를 사용하여 다음 예제와 같이 데이터 흐름 블록에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-109">You can also use the <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method to read from a dataflow block, as shown in the following example.</span></span> <span data-ttu-id="a864f-110"><xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 메서드는 현재 스레드를 차단하지 않고 때때로 데이터를 폴링할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-110">The <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method does not block the current thread and is useful when you occasionally poll for data.</span></span>  
  
 [!code-csharp[TPLDataflow_ReadWrite#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#3)]
 [!code-vb[TPLDataflow_ReadWrite#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#3)]  
  
 <span data-ttu-id="a864f-111"><xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 메서드가 동기적으로 작동하기 때문에 앞의 예제에 있는 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 개체는 두 번째 루프에서 데이터를 읽기 전에 모든 데이터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-111">Because the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> method acts synchronously, the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> object in the previous examples receives all data before the second loop reads data.</span></span> <span data-ttu-id="a864f-112">다음 예제에서는 <xref:System.Threading.Tasks.Parallel.Invoke%2A>를 사용하여 메시지 블록에서 동시에 읽고 쓰는 방법으로 첫 번째 예제를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-112">The following example extends the first example by using <xref:System.Threading.Tasks.Parallel.Invoke%2A> to read from and write to the message block concurrently.</span></span> <span data-ttu-id="a864f-113"><xref:System.Threading.Tasks.Parallel.Invoke%2A>가 작업을 동시에 수행하기 때문에 값은 특정 순서로 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 개체에 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-113">Because <xref:System.Threading.Tasks.Parallel.Invoke%2A> performs actions concurrently, the values are not written to the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> object in any specific order.</span></span>  
  
 [!code-csharp[TPLDataflow_ReadWrite#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#4)]
 [!code-vb[TPLDataflow_ReadWrite#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#4)]  
  
## <a name="writing-to-and-reading-from-a-dataflow-block-asynchronously"></a><span data-ttu-id="a864f-114">비동기적으로 데이터 흐름 블록에서 읽고 쓰기</span><span class="sxs-lookup"><span data-stu-id="a864f-114">Writing to and Reading from a Dataflow Block Asynchronously</span></span>  
 <span data-ttu-id="a864f-115">다음 예제에서는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> 메서드를 사용하여 비동기적으로 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 개체에 쓰고 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> 메서드를 사용하여 비동기적으로 동일한 개체에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-115">The following example uses the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> method to asynchronously write to a <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> object and the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> method to asynchronously read from the same object.</span></span> <span data-ttu-id="a864f-116">이 예제에서는 [async](~/docs/csharp/language-reference/keywords/async.md) 및 [await](~/docs/csharp/language-reference/keywords/await.md)(Visual Basic에서는 [Async](~/docs/visual-basic/language-reference/modifiers/async.md) 및 [Await](~/docs/visual-basic/language-reference/operators/await-operator.md)) 연산자를 사용하여 비동기적으로 대상 블록에 데이터를 보내고 대상 블록에서 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-116">This example uses the [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) operators ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in Visual Basic) to asynchronously send data to and read data from the target block.</span></span> <span data-ttu-id="a864f-117"><xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> 메서드는 데이터 흐름 블록이 메시지를 연기할 수 있도록 해야 하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-117">The <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> method is useful when you must enable a dataflow block to postpone messages.</span></span> <span data-ttu-id="a864f-118"><xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> 메서드는 데이터를 사용할 수 있게 될 때 데이터에 대한 작업을 수행하려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-118">The <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> method is useful when you want to act on data when that data becomes available.</span></span> <span data-ttu-id="a864f-119">메시지가 메시지 블록 간에 전파되는 방법에 대한 자세한 내용은 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)의 [메시지 전달] 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a864f-119">For more information about how messages propagate among message blocks, see the section Message Passing in [Dataflow](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).</span></span>  
  
 [!code-csharp[TPLDataflow_ReadWrite#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#5)]
 [!code-vb[TPLDataflow_ReadWrite#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#5)]  
  
## <a name="a-complete-example"></a><span data-ttu-id="a864f-120">전체 예제</span><span class="sxs-lookup"><span data-stu-id="a864f-120">A Complete Example</span></span>  
 <span data-ttu-id="a864f-121">다음 예제에서는 이 문서의 전체 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-121">The following example shows the complete code for this document.</span></span>  
  
 [!code-csharp[TPLDataflow_ReadWrite#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#1)]
 [!code-vb[TPLDataflow_ReadWrite#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a864f-122">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a864f-122">Compiling the Code</span></span>  
 <span data-ttu-id="a864f-123">예제 코드를 복사하여 Visual Studio 프로젝트에 붙여 넣거나, `DataflowReadWrite.cs`([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]의 경우 `DataflowReadWrite.vb`) 파일에 붙여 넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-123">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowReadWrite.cs` (`DataflowReadWrite.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="a864f-124">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.cs**</span><span class="sxs-lookup"><span data-stu-id="a864f-124">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="a864f-125">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.vb**</span><span class="sxs-lookup"><span data-stu-id="a864f-125">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.vb**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a864f-126">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a864f-126">Next Steps</span></span>  
 <span data-ttu-id="a864f-127">이 예제에서는 메시지 블록에서 직접 읽고 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-127">This example shows how to read from and write to a message block directly.</span></span> <span data-ttu-id="a864f-128">데이터 흐름 블록을 연결하여 데이터 흐름 블록의 선형 시퀀스인 *파이프라인*이나 데이터 흐름 블록의 그래프인 *네트워크*를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-128">You can also connect dataflow blocks to form *pipelines*, which are linear sequences of dataflow blocks, or *networks*, which are graphs of dataflow blocks.</span></span> <span data-ttu-id="a864f-129">파이프라인 또는 네트워크에서 소스는 데이터를 사용할 수 있게 되면 대상에 데이터를 비동기적으로 전파합니다.</span><span class="sxs-lookup"><span data-stu-id="a864f-129">In a pipeline or network, sources asynchronously propagate data to targets as that data becomes available.</span></span> <span data-ttu-id="a864f-130">기본 데이터 흐름 파이프라인을 만드는 예제는 [연습: 데이터 흐름 파이프라인 만들기](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a864f-130">For an example that creates a basic dataflow pipeline, see [Walkthrough: Creating a Dataflow Pipeline](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md).</span></span> <span data-ttu-id="a864f-131">더 복잡한 데이터 흐름 네트워크를 만드는 예제는 [연습: Windows Forms 응용 프로그램에서 데이터 흐름 사용](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a864f-131">For an example that creates a more complex dataflow network, see [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a864f-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a864f-132">See Also</span></span>  
 [<span data-ttu-id="a864f-133">데이터 흐름</span><span class="sxs-lookup"><span data-stu-id="a864f-133">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
