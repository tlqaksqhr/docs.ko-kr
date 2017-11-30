---
title: "방법: 공급자-소비자 데이터 흐름 패턴 구현"
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
- TPL dataflow library, implementing producer-consumer pattern
- Task Parallel Library, dataflows
- producer-consumer patterns, implementing [TPL]
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1aba08e8364d8a21f70ab480d58041115a4849e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-implement-a-producer-consumer-dataflow-pattern"></a><span data-ttu-id="45d00-102">방법: 공급자-소비자 데이터 흐름 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="45d00-102">How to: Implement a Producer-Consumer Dataflow Pattern</span></span>
<span data-ttu-id="45d00-103">이 문서에서는 TPL 데이터 흐름 라이브러리를 사용하여 생산자-소비자 패턴을 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-103">This document describes how to use the TPL Dataflow Library to implement a producer-consumer pattern.</span></span> <span data-ttu-id="45d00-104">이 패턴에서 *생산자*는 메시지 블록에 메시지를 보내고 *소비자*는 해당 블록에서 메시지를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-104">In this pattern, the *producer* sends messages to a message block, and the *consumer* reads messages from that block.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="45d00-105">TPL 데이터 흐름 라이브러리(<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 네임스페이스)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]와 함께 배포되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-105">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="45d00-106">설치 하는 <xref:System.Threading.Tasks.Dataflow> 네임 스페이스에서 프로젝트를 열고 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], 선택 **NuGet 패키지 관리** 프로젝트 메뉴에 대 한 온라인 검색에서는 `Microsoft.Tpl.Dataflow` 패키지 합니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-106">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45d00-107">예제</span><span class="sxs-lookup"><span data-stu-id="45d00-107">Example</span></span>  
 <span data-ttu-id="45d00-108">다음 예제에서는 데이터 흐름을 사용하는 기본적인 생산자-소비자 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-108">The following example demonstrates a basic producer- consumer model that uses dataflow.</span></span> <span data-ttu-id="45d00-109">`Produce` 메서드는 임의의 데이터 바이트를 포함하는 배열을 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> 개체에 쓰고 `Consume` 메서드는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType> 개체에서 바이트를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-109">The `Produce` method writes arrays that contain random bytes of data to a <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> object and the `Consume` method reads bytes from a <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="45d00-110">파생 형식 대신 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 및 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 인터페이스에서 작업함으로써 다양한 데이터 흐름 블록 형식에서 작업할 수 있는 재사용 가능한 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-110">By acting on the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> and <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> interfaces, instead of their derived types, you can write reusable code that can act on a variety of dataflow block types.</span></span> <span data-ttu-id="45d00-111">이 예제에서는 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-111">This example uses the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> class.</span></span> <span data-ttu-id="45d00-112"><xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 클래스가 소스 블록과 대상 블록 역할을 하고, 생산자와 소비자는 공유 개체를 사용하여 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-112">Because the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> class acts as both a source block and as a target block, the producer and the consumer can use a shared object to transfer data.</span></span>  
  
 <span data-ttu-id="45d00-113">`Produce` 메서드는 루프에서 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 메서드를 호출하여 대상 블록에 동기적으로 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-113">The `Produce` method calls the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> method in a loop to synchronously write data to the target block.</span></span> <span data-ttu-id="45d00-114">`Produce` 메서드는 모든 데이터를 대상 블록에 쓴 후 <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> 메서드를 호출하여 블록에 사용 가능한 추가 데이터가 더 이상 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-114">After the `Produce` method writes all data to the target block, it calls the <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> method to indicate that the block will never have additional data available.</span></span> <span data-ttu-id="45d00-115">`Consume` 메서드는 [비동기](~/docs/csharp/language-reference/keywords/async.md) 및 [await](~/docs/csharp/language-reference/keywords/await.md) 연산자 ([비동기](~/docs/visual-basic/language-reference/modifiers/async.md) 및 [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) 에 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)])를 비동기적으로 로부터 받은 바이트의 총 수를 계산에서 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-115">The `Consume` method uses the [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) operators ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) to asynchronously compute the total number of bytes that are received from the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> object.</span></span> <span data-ttu-id="45d00-116">비동기적으로 작동하기 위해 `Consume` 메서드는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> 메서드를 호출하여 소스 블록에 사용 가능한 데이터가 있을 때와 소스 블록에 사용 가능한 추가 데이터가 더 이상 없을 때 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-116">To act asynchronously, the `Consume` method calls the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> method to receive a notification when the source block has data available and when the source block will never have additional data available.</span></span>  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="45d00-117">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="45d00-117">Compiling the Code</span></span>  
 <span data-ttu-id="45d00-118">예제 코드를 복사하여 Visual Studio 프로젝트에 붙여 넣거나, `DataflowProducerConsumer.cs`([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]의 경우 `DataflowProducerConsumer.vb`) 파일에 붙여 넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-118">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowProducerConsumer.cs` (`DataflowProducerConsumer.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="45d00-119">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**</span><span class="sxs-lookup"><span data-stu-id="45d00-119">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="45d00-120">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**</span><span class="sxs-lookup"><span data-stu-id="45d00-120">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="45d00-121">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="45d00-121">Robust Programming</span></span>  
 <span data-ttu-id="45d00-122">이 예제에서는 소비자를 하나만 사용하여 소스 데이터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-122">This example uses just one consumer to process the source data.</span></span> <span data-ttu-id="45d00-123">응용 프로그램에 여러 소비자가 있는 경우 다음 예제와 같이 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 메서드를 사용하여 소스 블록에서 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-123">If you have multiple consumers in your application, use the <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method to read data from the source block, as shown in the following example.</span></span>  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 <span data-ttu-id="45d00-124"><xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 메서드는 사용 가능한 데이터가 없을 때 `False`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-124">The <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method returns `False` when no data is available.</span></span> <span data-ttu-id="45d00-125">여러 소비자가 소스 블록에 동시에 액세스해야 하는 경우 이 메커니즘은 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> 호출 후에 데이터를 계속 사용할 수 있도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="45d00-125">When multiple consumers must access the source block concurrently, this mechanism guarantees that data is still available after the call to <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d00-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45d00-126">See Also</span></span>  
 [<span data-ttu-id="45d00-127">데이터 흐름</span><span class="sxs-lookup"><span data-stu-id="45d00-127">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
