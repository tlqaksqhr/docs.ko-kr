---
title: "How to: Implement a Producer-Consumer Dataflow Pattern | Microsoft Docs"
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
  - "TPL dataflow library, implementing producer-consumer pattern"
  - "Task Parallel Library, dataflows"
  - "producer-consumer patterns, implementing [TPL]"
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Implement a Producer-Consumer Dataflow Pattern
이 문서에서는 TPL 데이터 흐름 라이브러리를 사용하여 공급자\-소비자 패턴을 구현 하는 방법을 설명 합니다.  이 패턴에서 *공급자*는 메시지 블록에 메시지를 보내고 *소비자*는 해당 블록에서 메시지를 읽습니다.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리 \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName> 네임 스페이스\)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]과 함께 배포 되지 않습니다.  이 <xref:System.Threading.Tasks.Dataflow> 네임스페이스를 설치 할려면, [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]에서 프로젝트를 열고, 프로젝트 메뉴에서 **Manage NuGet Packages** 를 선택한 후, `Microsoft.Tpl.Dataflow` 패키지를 온라인에서 검색합니다.  
  
## 예제  
 다음 예제에서는 데이터 흐름을 사용하는 기본 공급자\-소비자 모델을 보여 줍니다.  `Produce` 메서드는 데이터의 임의의 바이트를 포함 하는 배열을 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=fullName> 개체에 작성하고 `Consume` 메서드는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=fullName> 개체로 부터 바이트를 읽습니다.  파생된 형식 대신 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 및 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 인터페이스에서 작업하여 다양한 데이터 흐름 블록 형식에 사용할 수 있는 재사용 가능한 코드를 작성할 수 있습니다.  이 예제에서는 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 클래스를 사용합니다.  <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 클래스는 소스 블록 및 대상 블록에서 작동하고, 생산자와 소비자는 공유된 개체를 사용하여 데이터를 전송할 수 있습니다.  
  
 `Produce` 메서드는 루프에서 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 메서드를 호출하여 대상 블록에 동기적으로 데이터를 기록합니다.  `Produce` 메서드가 모든 데이터를 대상 블록에 작성한 후 <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> 메서드를 호출하여 블록이 사용할 수 있는 추가 데이터를 갖지 않음을 나타냅니다.  `Consume` 메서드는 [async](../Topic/async%20\(C%23%20Reference\).md) 및 [await](../Topic/await%20\(C%23%20Reference\).md) 연산자 \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 에서 [Async](../Topic/Async%20\(Visual%20Basic\).md) 및 [Await](../Topic/Await%20Operator%20\(Visual%20Basic\).md)\) 를 사용하여 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 개체로 부터 받은 총 바이트 수를 비동기적으로 계산합니다.  비동기적으로 작동 하기 위해 `Consume` 메서드는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> 메서드를 호출하여 소스 블록이 사용할 수 있는 데이터를 가지고 있을 때, 그리고 소스 블록이 사용할 수 있는 추가 데이터를 더이상 갖지 않을 때에 대한 알림을 받습니다.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트에 붙여넣거나 `DataflowProducerConsumer.cs` \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 의 `DataflowProducerConsumer.vb`\) 파일에 붙여넣은 다음 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**  
  
## 강력한 프로그래밍  
 이 예제에서는 소스 데이터를 처리하기 위해 하나의 소비자를 사용합니다.  응용 프로그램에 여러 소비자가 있는 경우, 다음 예제와 같이 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 메서드를 사용하여 소스 블록에서 데이터를 읽을 수 있습니다.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 메서드는 데이터가 없을 때 `False` 을 반환합니다.  여러 소비자 소스 블록을 동시에 액세스 해야 하는 경우, 이 메커니즘은 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> 후에 데이터를 계속 사용할 수 있음을 보장합니다.  
  
## 참고 항목  
 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)