---
title: "How to: Write Messages to and Read Messages from a Dataflow Block | Microsoft Docs"
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
  - "TPL dataflow library, reading and writing messages"
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Write Messages to and Read Messages from a Dataflow Block
이 문서는 TPL 데이터 흐름 라이브러리 데이터 흐름 블록에서 메시지를 읽고 쓰는 메시지를 사용하는 방법을 설명합니다.  TPL 데이터 흐름 라이브러리는 메시지와 데이터 흐름 블록에서 메시지를 읽거나 쓰기 위해 동기 및 비동기 메서드를 제공합니다.  이 문서는 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=fullName> 클래스를 사용합니다.  <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 클래스는 메시지 버퍼 및 메시지 원본 및 메시지 대상으로 작동합니다.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리 \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName> 네임 스페이스\)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]과 함께 배포 되지 않습니다.  이 <xref:System.Threading.Tasks.Dataflow> 네임스페이스를 설치 할려면, [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]에서 프로젝트를 열고, 프로젝트 메뉴에서 **Manage NuGet Packages** 를 선택한 후, `Microsoft.Tpl.Dataflow` 패키지를 온라인에서 검색합니다.  
  
## 동기적으로 블록 데이터 흐름에서 읽고 쓰기  
 다음 예제는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 메서드를 사용하여 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 블록 데이터 흐름을 읽고 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> 메서드를 사용하여 같은 개체를 읽습니다.  
  
 [!code-csharp[TPLDataflow_ReadWrite#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#2)]
 [!code-vb[TPLDataflow_ReadWrite#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#2)]  
  
 또한 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 메서드를 사용하여 다음 예제와 같이 데이터 흐름 블록에서 읽을 수 있습니다.  <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 메서드는 현재 스레드를 차단하지 않고 때때로 데이터를 폴링할 때 유용합니다.  
  
 [!code-csharp[TPLDataflow_ReadWrite#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#3)]
 [!code-vb[TPLDataflow_ReadWrite#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#3)]  
  
 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 메서드가 동기식으로 작동하기 때문에 앞의 예제에서 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 개체는 데이터를 읽고 두 번째 루프 전에 모든 데이터를 수신합니다.  다음 예제에서는 <xref:System.Threading.Tasks.Parallel.Invoke%2A>을 사용하여 읽고, 동시에 메세지 블록을 작성함으로써 첫번째 예제를 확장합니다.  <xref:System.Threading.Tasks.Parallel.Invoke%2A>는 작업을 동시에 수행하기 때문에, 값은 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 특정 순서로 작성되지 않습니다.  
  
 [!code-csharp[TPLDataflow_ReadWrite#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#4)]
 [!code-vb[TPLDataflow_ReadWrite#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#4)]  
  
## 비동기적으로 블록 데이터 흐름에서 읽고 쓰기  
 다음 예제는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> 메서드를 사용하여 비동기적으로 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 개체에 작성을 하고, <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> 메서드를 사용하여 비동기적으로 동일한 개체에서 읽습니다.  이 예제는 [비동기](../Topic/async%20\(C%23%20Reference\).md) 및  [연산자](../Topic/await%20\(C%23%20Reference\).md) 연산자 \([비동기](../Topic/Async%20\(Visual%20Basic\).md) 및  [Await](../Topic/Await%20Operator%20\(Visual%20Basic\).md) Visual Basic\)를 사용하여 비동기적으로 대상 블록에서 데이터를 읽고 데이터를 보냅니다.  <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> 메서드는 메시지를 연기하는 데이터 흐름 블록을 사용하도록 설정해야 합니다.  <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> 메서드는 데이터를 사용할 수 있을 때 데이터 작업을 수행 하려는 경우에 유용합니다.  메시지 블록 간에 메시지 전파 하는 방법에 대한 자세한 내용은 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)의 전달 메시지 섹션을 참조하십시오.  
  
 [!code-csharp[TPLDataflow_ReadWrite#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#5)]
 [!code-vb[TPLDataflow_ReadWrite#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#5)]  
  
## 완성된 예제  
 다음 예제에서는 이 문서의 전체 코드를 보여 줍니다.  
  
 [!code-csharp[TPLDataflow_ReadWrite#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#1)]
 [!code-vb[TPLDataflow_ReadWrite#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#1)]  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트에 붙여넣거나 `DataflowReadWrite.cs` \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 의 `DataflowReadWrite.vb`\) 파일에 붙여넣은 다음 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.vb**  
  
## 다음 단계  
 이 예제는 메시지 블록를 직접 읽고 쓰는 방법을 보여줍니다.  데이터 블록의 선형 시퀀스인 *pipelines*이나, 데이터 블록의 그래프인 *networks*을 만들기 위해 데이터 흐름 블록을 연결할 수 있습니다.  파이프라인 또는 네트워크에서, 원본은 데이터를 받아들일 수 있는 대상에게 데이터를 비동기적으로 전파합니다.  기본 데이터 흐름 파이프라인을 만드는 예제를 보려면 [Walkthrough: Creating a Dataflow Pipeline](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md)을 참조하십시오.  더 복잡한 데이터 흐름 네트워크를 만드는 예제를 보려면 [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)을 참조하십시오.  
  
## 참고 항목  
 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)