---
title: '방법: 공급자-소비자 데이터 흐름 패턴 구현'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TPL dataflow library, implementing producer-consumer pattern
- Task Parallel Library, dataflows
- producer-consumer patterns, implementing [TPL]
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d94cfeecc9556fb01dd3d72649d960ce68f929d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580899"
---
# <a name="how-to-implement-a-producer-consumer-dataflow-pattern"></a><span data-ttu-id="fe33f-102">방법: 공급자-소비자 데이터 흐름 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="fe33f-102">How to: Implement a Producer-Consumer Dataflow Pattern</span></span>
<span data-ttu-id="fe33f-103">이 문서에서는 TPL 데이터 흐름 라이브러리를 사용하여 생산자-소비자 패턴을 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fe33f-103">This document describes how to use the TPL Dataflow Library to implement a producer-consumer pattern.</span></span> <span data-ttu-id="fe33f-104">이 패턴에서 *생산자*는 메시지 블록에 메시지를 보내고 *소비자*는 해당 블록에서 메시지를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="fe33f-104">In this pattern, the *producer* sends messages to a message block, and the *consumer* reads messages from that block.</span></span>  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="example"></a><span data-ttu-id="fe33f-105">예</span><span class="sxs-lookup"><span data-stu-id="fe33f-105">Example</span></span>  
 <span data-ttu-id="fe33f-106">다음 예제에서는 데이터 흐름을 사용하는 기본적인 생산자-소비자 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fe33f-106">The following example demonstrates a basic producer- consumer model that uses dataflow.</span></span> <span data-ttu-id="fe33f-107">`Produce` 메서드는 임의의 데이터 바이트를 포함하는 배열을 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> 개체에 쓰고 `Consume` 메서드는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType> 개체에서 바이트를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="fe33f-107">The `Produce` method writes arrays that contain random bytes of data to a <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> object and the `Consume` method reads bytes from a <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="fe33f-108">파생 형식 대신 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 및 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 인터페이스에서 작업함으로써 다양한 데이터 흐름 블록 형식에서 작업할 수 있는 재사용 가능한 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe33f-108">By acting on the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> and <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> interfaces, instead of their derived types, you can write reusable code that can act on a variety of dataflow block types.</span></span> <span data-ttu-id="fe33f-109">이 예제에서는 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fe33f-109">This example uses the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> class.</span></span> <span data-ttu-id="fe33f-110"><xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 클래스가 소스 블록과 대상 블록 역할을 하고, 생산자와 소비자는 공유 개체를 사용하여 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe33f-110">Because the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> class acts as both a source block and as a target block, the producer and the consumer can use a shared object to transfer data.</span></span>  
  
 <span data-ttu-id="fe33f-111">`Produce` 메서드는 루프에서 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 메서드를 호출하여 대상 블록에 동기적으로 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="fe33f-111">The `Produce` method calls the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> method in a loop to synchronously write data to the target block.</span></span> <span data-ttu-id="fe33f-112">`Produce` 메서드는 모든 데이터를 대상 블록에 쓴 후 <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> 메서드를 호출하여 블록에 사용 가능한 추가 데이터가 더 이상 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe33f-112">After the `Produce` method writes all data to the target block, it calls the <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> method to indicate that the block will never have additional data available.</span></span> <span data-ttu-id="fe33f-113">`Consume` 메서드는 [async](~/docs/csharp/language-reference/keywords/async.md) 및 [await](~/docs/csharp/language-reference/keywords/await.md)(Visual Basic에서는 [Async](~/docs/visual-basic/language-reference/modifiers/async.md) 및 [Await](~/docs/visual-basic/language-reference/operators/await-operator.md)) 연산자를 사용하여 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 개체에서 받은 총 바이트 수를 비동기적으로 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="fe33f-113">The `Consume` method uses the [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) operators ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in Visual Basic) to asynchronously compute the total number of bytes that are received from the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> object.</span></span> <span data-ttu-id="fe33f-114">비동기적으로 작동하기 위해 `Consume` 메서드는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> 메서드를 호출하여 소스 블록에 사용 가능한 데이터가 있을 때와 소스 블록에 사용 가능한 추가 데이터가 더 이상 없을 때 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="fe33f-114">To act asynchronously, the `Consume` method calls the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> method to receive a notification when the source block has data available and when the source block will never have additional data available.</span></span>  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fe33f-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="fe33f-115">Compiling the Code</span></span>  
 <span data-ttu-id="fe33f-116">예제 코드를 복사하여 Visual Studio 프로젝트에 붙여넣거나, `DataflowProducerConsumer.cs`(Visual Basic의 경우 `DataflowProducerConsumer.vb`) 파일에 붙여넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fe33f-116">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowProducerConsumer.cs` (`DataflowProducerConsumer.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="fe33f-117">Visual C#</span><span class="sxs-lookup"><span data-stu-id="fe33f-117">Visual C#</span></span>  
  
 <span data-ttu-id="fe33f-118">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**</span><span class="sxs-lookup"><span data-stu-id="fe33f-118">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**</span></span>  
  
 <span data-ttu-id="fe33f-119">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fe33f-119">Visual Basic</span></span>  
  
 <span data-ttu-id="fe33f-120">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**</span><span class="sxs-lookup"><span data-stu-id="fe33f-120">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="fe33f-121">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="fe33f-121">Robust Programming</span></span>  
 <span data-ttu-id="fe33f-122">이 예제에서는 소비자를 하나만 사용하여 소스 데이터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="fe33f-122">This example uses just one consumer to process the source data.</span></span> <span data-ttu-id="fe33f-123">응용 프로그램에 여러 소비자가 있는 경우 다음 예제와 같이 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 메서드를 사용하여 소스 블록에서 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="fe33f-123">If you have multiple consumers in your application, use the <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method to read data from the source block, as shown in the following example.</span></span>  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 <span data-ttu-id="fe33f-124"><xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 메서드는 사용 가능한 데이터가 없을 때 `False`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fe33f-124">The <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method returns `False` when no data is available.</span></span> <span data-ttu-id="fe33f-125">여러 소비자가 소스 블록에 동시에 액세스해야 하는 경우 이 메커니즘은 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> 호출 후에 데이터를 계속 사용할 수 있도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="fe33f-125">When multiple consumers must access the source block concurrently, this mechanism guarantees that data is still available after the call to <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe33f-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe33f-126">See Also</span></span>  
 [<span data-ttu-id="fe33f-127">데이터 흐름</span><span class="sxs-lookup"><span data-stu-id="fe33f-127">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
