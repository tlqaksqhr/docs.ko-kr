---
title: "How to: Unlink Dataflow Blocks | Microsoft Docs"
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
  - "dataflow blocks, unlinking in TPL"
  - "Task Parallel Library, dataflows"
  - "TPL dataflow library, unlinking dataflow blocks"
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Unlink Dataflow Blocks
이 문서에서는 원본에서 데이터 흐름 대상 블록의 연결을 해제하는 방법을 설명 합니다.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리 \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName> 네임 스페이스\)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]과 함께 배포 되지 않습니다.  이 <xref:System.Threading.Tasks.Dataflow> 네임스페이스를 설치 할려면, [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]에서 프로젝트를 열고, 프로젝트 메뉴에서 **Manage NuGet Packages** 를 선택한 후, `Microsoft.Tpl.Dataflow` 패키지를 온라인에서 검색합니다.  
  
## 예제  
 다음 예제에서는 세 개의 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 개체를 생성하고 각 개체는 `TrySolution` 메서드를 호출하여 값을 계산 합니다.  이 예제에서는 종료하기 위해서 `TrySolution` 의 첫 번째 호출에서의 결과만 필요로 합니다.  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 종료된 첫번째 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 개체에서 값을 받기 위해 이 예제는 `ReceiveFromAny(T)` 메서드를 정의합니다.  `ReceiveFromAny(T)` 메서드는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 개체의 배열을 받고 이러한 개체를 각각 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 개체에 연결합니다.  <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> 메서드를 사용하여 소스 데이터 흐름 블록을 대상 블록에 연결할 때, 소스는 데이터를 사용할 수 있게 메시지를 대상에 전파 합니다.  <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 클래스는 제공된 첫 번째 메시지만 수락하기 때문에 `ReceiveFromAny(T)` 메서드는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> 메서드를 호출하여 결과를 생성합니다.  이것은 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 개체에 제공된 첫 번째 메시지를 생성합니다.  <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> 메서드는 `unlinkAfterOne` 이 `True` 로 설정 된 경우 대상이 소스에서 메세지를 받은 후 소스 블록에게 대상으로부터 연결을 해제하도록 지시하는 <xref:System.Boolean> 매개 변수를 사용하는 오버 로드된 버전을 사용합니다.  소스의 배열과 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 개체의 관계는 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 개체가 메세지를 수신한 이후 더 이상 필요하지 않기 때문에 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 개체는 소스와의 연결을 끊어야 합니다.  
  
 각각 값을 입력한 후 `TrySolution` 의 나머지 호출을 끝내기 위해 `TrySolution` 메서드는 `ReceiveFromAny(T)` 호출이 반환된 후 취소되는 <xref:System.Threading.CancellationToken> 개체를 사용합니다.  <xref:System.Threading.SpinWait.SpinUntil%2A> 메서드는 이 <xref:System.Threading.CancellationToken> 개체가 취소 될 때 반환합니다.  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트에 붙여넣거나 `DataflowReceiveAny.cs` \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 의 `DataflowReceiveAny.vb`\) 파일에 붙여넣은 다음 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**  
  
## 강력한 프로그래밍  
  
## 참고 항목  
 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)