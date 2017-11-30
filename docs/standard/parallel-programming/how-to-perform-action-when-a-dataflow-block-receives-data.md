---
title: "방법: 데이터 흐름 블록에서 데이터를 받을 경우 작업 수행"
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
- TPL dataflow library, receiving data
ms.assetid: fc2585dc-965e-4632-ace7-73dd02684ed3
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d049d20f5e685096a72857cd18a89688633883c3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-perform-action-when-a-dataflow-block-receives-data"></a>방법: 데이터 흐름 블록에서 데이터를 받을 경우 작업 수행
*실행 데이터 흐름 블록* 형식은 데이터를 받을 때 사용자가 제공한 대리자를 호출합니다. <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType> 클래스는 실행 데이터 흐름 블록 형식입니다. 실행 데이터 흐름 블록에 작업 함수를 제공할 때 `delegate`(`Sub`에서는 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 키워드, <xref:System.Action%601>, <xref:System.Func%602> 또는 람다 식을 사용할 수 있습니다. 이 문서에서는 <xref:System.Func%602> 및 람다 식을 사용하여 실행 블록에서 작업을 수행하는 방법을 설명합니다.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리(<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 네임스페이스)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]와 함께 배포되지 않습니다. 설치 하는 <xref:System.Threading.Tasks.Dataflow> 네임 스페이스에서 프로젝트를 열고 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], 선택 **NuGet 패키지 관리** 프로젝트 메뉴에 대 한 온라인 검색에서는 `Microsoft.Tpl.Dataflow` 패키지 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 데이터 흐름을 사용하여 디스크에서 파일을 읽고 파일에서 0인 바이트 수를 계산합니다. 이 예제에서는 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>을 사용하여 파일을 읽고 0바이트의 수를 계산하고, <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>을 사용하여 콘솔에 0바이트의 수를 출력합니다. <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 개체는 블록이 데이터를 받을 때 작업을 수행할 <xref:System.Func%602> 개체를 지정합니다. <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체는 람다 식을 사용하여 콘솔에 읽은 0바이트의 수를 출력합니다.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#1)]
 [!code-vb[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#1)]  
  
 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 개체에 람다 식을 제공할 수 있지만, 이 예제에서는 <xref:System.Func%602>를 사용하여 다른 코드에서 `CountBytes` 메서드를 사용할 수 있도록 합니다. <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체는 수행할 작업이 이 작업에 특정하고 다른 코드에서 유용할 가능성이 적기 때문에 람다 식을 사용합니다. 람다 식이 작업 병렬 라이브러리에서 작동하는 방식에 대한 자세한 내용은 [PLINQ 및 TPL의 람다 식](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)을 참조하세요.  
  
 대리자 형식 요약 섹션에는 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) 문서를 제공할 수 있는 대리자 형식을 요약 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, 및 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> 개체입니다. 또한 대리자 형식이 동기적으로 작동하는지, 아니면 비동기적으로 작동하는지를 지정합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트에 붙여 넣거나, `DataflowExecutionBlocks.cs`([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]의 경우 `DataflowExecutionBlocks.vb`) 파일에 붙여 넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.vb**  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 이 예제에서는 <xref:System.Func%602> 형식의 대리자를 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 개체에 제공하여 데이터 흐름 블록의 작업을 동기적으로 수행합니다. 데이터 흐름 블록이 비동기적으로 동작할 수 있도록 하려면 <xref:System.Func%601> 형식의 대리자를 데이터 흐름 블록에 제공합니다. 데이터 흐름 블록이 비동기적으로 동작하는 경우 데이터 흐름 블록의 작업은 반환된 <xref:System.Threading.Tasks.Task%601> 개체가 완료될 때만 완료됩니다. 다음 예제에서는 `CountBytes` 메서드를 수정하고 [async](~/docs/csharp/language-reference/keywords/async.md) 및 [await](~/docs/csharp/language-reference/keywords/await.md)([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에서는 [Async](~/docs/visual-basic/language-reference/modifiers/async.md) 및 [Await](~/docs/visual-basic/language-reference/operators/await-operator.md)) 연산자를 사용하여 제공된 파일에서 크기가 영인 바이트의 총 수를 비동기적으로 계산합니다. <xref:System.IO.FileStream.ReadAsync%2A> 메서드는 비동기적으로 파일 읽기 작업을 수행합니다.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#2)]
 [!code-vb[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#2)]  
  
 또한 비동기 람다 식을 사용하여 실행 데이터 흐름 블록에서 작업을 수행합니다. 다음 예제에서는 람다 식을 사용하여 비동기적으로 작업을 수행할 수 있도록 이전 예제에서 사용된 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 개체를 수정합니다.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#3)]
 [!code-vb[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#3)]  
  
## <a name="see-also"></a>참고 항목  
 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
