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
# <a name="how-to-implement-a-producer-consumer-dataflow-pattern"></a>방법: 공급자-소비자 데이터 흐름 패턴 구현
이 문서에서는 TPL 데이터 흐름 라이브러리를 사용하여 생산자-소비자 패턴을 구현하는 방법을 설명합니다. 이 패턴에서 *생산자*는 메시지 블록에 메시지를 보내고 *소비자*는 해당 블록에서 메시지를 읽습니다.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리(<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 네임스페이스)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]와 함께 배포되지 않습니다. 설치 하는 <xref:System.Threading.Tasks.Dataflow> 네임 스페이스에서 프로젝트를 열고 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], 선택 **NuGet 패키지 관리** 프로젝트 메뉴에 대 한 온라인 검색에서는 `Microsoft.Tpl.Dataflow` 패키지 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 데이터 흐름을 사용하는 기본적인 생산자-소비자 모델을 보여 줍니다. `Produce` 메서드는 임의의 데이터 바이트를 포함하는 배열을 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> 개체에 쓰고 `Consume` 메서드는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType> 개체에서 바이트를 읽습니다. 파생 형식 대신 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 및 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 인터페이스에서 작업함으로써 다양한 데이터 흐름 블록 형식에서 작업할 수 있는 재사용 가능한 코드를 작성할 수 있습니다. 이 예제에서는 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 클래스를 사용합니다. <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 클래스가 소스 블록과 대상 블록 역할을 하고, 생산자와 소비자는 공유 개체를 사용하여 데이터를 전송할 수 있습니다.  
  
 `Produce` 메서드는 루프에서 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 메서드를 호출하여 대상 블록에 동기적으로 데이터를 씁니다. `Produce` 메서드는 모든 데이터를 대상 블록에 쓴 후 <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> 메서드를 호출하여 블록에 사용 가능한 추가 데이터가 더 이상 없음을 나타냅니다. `Consume` 메서드는 [비동기](~/docs/csharp/language-reference/keywords/async.md) 및 [await](~/docs/csharp/language-reference/keywords/await.md) 연산자 ([비동기](~/docs/visual-basic/language-reference/modifiers/async.md) 및 [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) 에 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)])를 비동기적으로 로부터 받은 바이트의 총 수를 계산에서 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 개체입니다. 비동기적으로 작동하기 위해 `Consume` 메서드는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> 메서드를 호출하여 소스 블록에 사용 가능한 데이터가 있을 때와 소스 블록에 사용 가능한 추가 데이터가 더 이상 없을 때 알림을 받습니다.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트에 붙여 넣거나, `DataflowProducerConsumer.cs`([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]의 경우 `DataflowProducerConsumer.vb`) 파일에 붙여 넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 이 예제에서는 소비자를 하나만 사용하여 소스 데이터를 처리합니다. 응용 프로그램에 여러 소비자가 있는 경우 다음 예제와 같이 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 메서드를 사용하여 소스 블록에서 데이터를 읽습니다.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 메서드는 사용 가능한 데이터가 없을 때 `False`를 반환합니다. 여러 소비자가 소스 블록에 동시에 액세스해야 하는 경우 이 메커니즘은 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> 호출 후에 데이터를 계속 사용할 수 있도록 보장합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
