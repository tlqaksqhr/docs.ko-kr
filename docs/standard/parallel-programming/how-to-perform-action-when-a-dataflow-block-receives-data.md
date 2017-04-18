---
title: "How to: Perform Action When a Dataflow Block Receives Data | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Task Parallel Library, dataflows"
  - "TPL dataflow library, receiving data"
ms.assetid: fc2585dc-965e-4632-ace7-73dd02684ed3
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Perform Action When a Dataflow Block Receives Data
*데이터 흐름 실행 블록* 유형은 데이터를 받을 때 사용자가 제공한 대리자를 호출 합니다.  <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=fullName>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=fullName>, 그리고 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=fullName> 클래스는 실행 데이터 흐름 블록 형식입니다.  실행 데이터 흐름 블록에 작업 기능을 제공하는 경우 `delegate` 키워드 \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 에서의 `Sub`\), <xref:System.Action%601>, <xref:System.Func%602>, 또는 람다 식을 사용할 수 있습니다.  이 문서에서는 <xref:System.Func%602> 및 람다 식을 사용하여 실행 블록에서 작업을 수행하는 방법을 보여줍니다.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리 \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName> 네임 스페이스\)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]과 함께 배포 되지 않습니다.  이 <xref:System.Threading.Tasks.Dataflow> 네임스페이스를 설치 할려면, [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]에서 프로젝트를 열고, 프로젝트 메뉴에서 **Manage NuGet Packages** 를 선택한 후, `Microsoft.Tpl.Dataflow` 패키지를 온라인에서 검색합니다.  
  
## 예제  
 다음 예제에서는 데이터 흐름을 사용하여 디스크에서 파일을 읽고 파일에서 0인 바이트 수를 계산 합니다.  이것은 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 을 사용하여 파일을 읽기 및 0 바이트의 수를 계산하고, <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 을 사용하여 콘솔에 0 바이트의 수 출력합니다.  <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 개체는 블록이 데이터를 받을 때 <xref:System.Func%602> 개체를 지정하여 작업을 수행합니다.  <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체는 람다 식을 사용하여 읽혀진 0 바이트의 수를 콘솔에 출력합니다.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#1)]
 [!code-vb[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#1)]  
  
 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 개체에 람다 식을 제공할수 있지만, 이 예제에서는 <xref:System.Func%602> 을 사용하여 `CountBytes` 메서드를 사용하는 다른 코드를 사용할 수 있도록 합니다.  <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체는 수행할 작업이 이 작업에서 특정적이고 다른 코드에서 유용하게 사용할 수 없기 때문에 람다 식을 사용 합니다.  작업 병렬 라이브러리에서 람다 식의 작동 방식에 대한 자세한 내용은 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md) 을 참조하십시오.  
  
 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) 문서에서 대리자 형식들의 요약 섹션에는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, 그리고 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> 개체에 제공할수 있는 대리자 형식들을 요약합니다.  또한 이 표는 대리자 형식을 동기적 또는 비동기적으로 작동하는지를 지정합니다.  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트에 붙여넣거나 `DataflowExecutionBlocks.cs` \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 의 `DataflowExecutionBlocks.vb`\) 파일에 붙여넣은 다음 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.vb**  
  
## 강력한 프로그래밍  
 이 예제에서는 <xref:System.Func%602> 형식의 대리자를 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 개체에 제공하여 데이터 흐름 블록의 작업을 동기적으로 수행합니다.  비동기적으로 동작 하는 데이터 흐름 블록을 사용하려면, <xref:System.Func%601> 형식의 대리자를 데이터 흐름 블록에 제공합니다.  데이터 흐름 블록이 비동기적으로 동작하는 경우, 데이터 흐름 블록의 작업은 <xref:System.Threading.Tasks.Task%601> 개체가 완료된 경우에만 완료됩니다.  다음 예제는 `CountBytes` 메서드를 수정하고 [async](../Topic/async%20\(C%23%20Reference\).md) 및 [await](../Topic/await%20\(C%23%20Reference\).md) \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 의 [Async](../Topic/Async%20\(Visual%20Basic\).md) 및 [Await](../Topic/Await%20Operator%20\(Visual%20Basic\).md)\) 연산자를 사용하여 제공된 파일에서의 0 바이트의 수를 비동기적으로 계산합니다.  <xref:System.IO.FileStream.ReadAsync%2A> 메서드는 비동기적으로 파일 읽기 작업을 수행 합니다.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#2)]
 [!code-vb[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#2)]  
  
 또한 비동기 람다 식을 사용하여 실행 데이터 흐름 블록에서 작업을 수행 합니다.  다음 예제에서는 람다식을 사용하여 작업을 비동기적으로 수행할 수 있도록 이전 예제에서 사용된 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 개체를 수정합니다.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#3)]
 [!code-vb[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#3)]  
  
## 참고 항목  
 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)