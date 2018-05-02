---
title: '방법: 데이터 흐름 블록 링크 끊기'
ms.date: 03/30/2017
ms.prod: .net
ms.technology: dotnet-standard
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow blocks, unlinking in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, unlinking dataflow blocks
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c7cdfa227e330a4b8ed46395c9793e5dca570fac
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-unlink-dataflow-blocks"></a><span data-ttu-id="2e8fa-102">방법: 데이터 흐름 블록 링크 끊기</span><span class="sxs-lookup"><span data-stu-id="2e8fa-102">How to: Unlink Dataflow Blocks</span></span>
<span data-ttu-id="2e8fa-103">이 문서에서는 소스에서 대상 데이터 흐름 블록의 연결을 해제하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-103">This document describes how to unlink a target dataflow block from its source.</span></span>

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a><span data-ttu-id="2e8fa-104">예</span><span class="sxs-lookup"><span data-stu-id="2e8fa-104">Example</span></span>  
 <span data-ttu-id="2e8fa-105">다음 예제에서는 세 개의 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 개체를 만듭니다. 각 개체는 `TrySolution` 메서드를 호출하여 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-105">The following example creates three <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objects, each of which calls the `TrySolution` method to compute a value.</span></span> <span data-ttu-id="2e8fa-106">이 예제는 종료하기 위해서 `TrySolution`에 대한 첫 번째 호출의 결과만 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-106">This example requires only the result from the first call to `TrySolution` to finish.</span></span>  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 <span data-ttu-id="2e8fa-107">종료되는 첫 번째 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 개체에서 값을 받기 위해 이 예제에서는 `ReceiveFromAny(T)` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-107">To receive the value from the first <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> object that finishes, this example defines the `ReceiveFromAny(T)` method.</span></span> <span data-ttu-id="2e8fa-108">`ReceiveFromAny(T)` 메서드는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 개체의 배열을 수락하고 이러한 개체를 각각 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 개체에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-108">The `ReceiveFromAny(T)` method accepts an array of <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> objects and links each of these objects to a <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object.</span></span> <span data-ttu-id="2e8fa-109"><xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> 메서드를 사용하여 소스 데이터 흐름 블록을 대상 블록에 연결하는 경우 소스는 데이터를 사용할 수 있게 될 때 메시지를 대상에 전파합니다.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-109">When you use the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method to link a source dataflow block to a target block, the source propagates messages to the target as data becomes available.</span></span> <span data-ttu-id="2e8fa-110"><xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 클래스가 제공된 첫 번째 메시지만 수락하기 때문에 `ReceiveFromAny(T)` 메서드는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> 메서드를 호출하여 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-110">Because the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> class accepts only the first message that it is offered, the `ReceiveFromAny(T)` method produces its result by calling the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> method.</span></span> <span data-ttu-id="2e8fa-111">이를 통해 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 개체에 제공되는 첫 번째 메시지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-111">This produces the first message that is offered to the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object.</span></span> <span data-ttu-id="2e8fa-112"><xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> 메서드에는 <xref:System.Boolean>로 설정된 경우 대상이 소스에서 메시지를 받은 후 대상에서 연결을 해제하도록 소스 블록에 지시하는 `unlinkAfterOne` 매개 변수인 `True`을 사용하는 오버로드된 버전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-112">The <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method has an overloaded version that takes a <xref:System.Boolean> parameter, `unlinkAfterOne` that, when it is set to `True`, instructs the source block to unlink from the target after the target receives one message from the source.</span></span> <span data-ttu-id="2e8fa-113">소스의 배열과 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 개체의 관계는 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 개체가 메시지를 받은 후 더 이상 필요하지 않기 때문에 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 개체는 소스에서 연결을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-113">It is important for the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object to unlink from its sources because the relationship between the array of sources and the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object is no longer required after the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object receives a message.</span></span>  
  
 <span data-ttu-id="2e8fa-114">`TrySolution`에 대한 나머지 호출이 한 호출에서 값을 계산한 후 종료될 수 있도록 하기 위해 `TrySolution` 메서드는 <xref:System.Threading.CancellationToken> 호출이 반환된 후 취소되는 `ReceiveFromAny(T)` 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-114">To enable the remaining calls to `TrySolution` to end after one of them computes a value, the `TrySolution` method takes a <xref:System.Threading.CancellationToken> object that is canceled after the call to `ReceiveFromAny(T)` returns.</span></span> <span data-ttu-id="2e8fa-115"><xref:System.Threading.SpinWait.SpinUntil%2A> 메서드는 이 <xref:System.Threading.CancellationToken> 개체가 취소될 때 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-115">The <xref:System.Threading.SpinWait.SpinUntil%2A> method returns when this <xref:System.Threading.CancellationToken> object is canceled.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2e8fa-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="2e8fa-116">Compiling the Code</span></span>  
 <span data-ttu-id="2e8fa-117">예제 코드를 복사하여 Visual Studio 프로젝트에 붙여넣거나, `DataflowReceiveAny.cs`(Visual Basic의 경우 `DataflowReceiveAny.vb`) 파일에 붙여넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="2e8fa-118">Visual C#</span><span class="sxs-lookup"><span data-stu-id="2e8fa-118">Visual C#</span></span>  
  
 <span data-ttu-id="2e8fa-119">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**</span><span class="sxs-lookup"><span data-stu-id="2e8fa-119">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**</span></span>  
  
 <span data-ttu-id="2e8fa-120">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2e8fa-120">Visual Basic</span></span>  
  
 <span data-ttu-id="2e8fa-121">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**</span><span class="sxs-lookup"><span data-stu-id="2e8fa-121">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**</span></span>  

## <a name="see-also"></a><span data-ttu-id="2e8fa-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e8fa-122">See Also</span></span>  
 [<span data-ttu-id="2e8fa-123">데이터 흐름</span><span class="sxs-lookup"><span data-stu-id="2e8fa-123">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
