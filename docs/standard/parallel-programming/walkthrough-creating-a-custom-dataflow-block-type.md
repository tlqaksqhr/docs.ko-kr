---
title: "Walkthrough: Creating a Custom Dataflow Block Type | Microsoft Docs"
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
  - "TPL dataflow library, creating custom dataflow blocks"
  - "dataflow blocks, creating custom in TPL"
ms.assetid: a6147146-0a6a-4d9b-ab0f-237b3c1ac691
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Walkthrough: Creating a Custom Dataflow Block Type
TPL 데이터 흐름 라이브러리에서 다양한 기능을 제공하는 여러 데이터 흐름 블록 형식을 제공하긴 하지만, 사용자는 또한 블록 사용자 지정 형식을 만들 수 있습니다.  이 문서에서는 사용자 지정 동작을 구현하는 데이터 흐름 블록 형식을 만드는 방법을 설명 합니다.  
  
## 사전 요구 사항  
 이 문서를 읽기 전에 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) 을 읽으십시오.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리 \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName> 네임 스페이스\)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]과 함께 배포 되지 않습니다.  이 <xref:System.Threading.Tasks.Dataflow> 네임스페이스를 설치 할려면, [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]에서 프로젝트를 열고, 프로젝트 메뉴에서 **Manage NuGet Packages** 를 선택한 후, `Microsoft.Tpl.Dataflow` 패키지를 온라인에서 검색합니다.  
  
## 스랑이딩 창 데이터 흐름 블록 정의  
 입력값이 저장된 다음 슬라이딩 창에서의 출력을 필요로 하는 데이터 흐름 응용 프로그램을 고려해야 합니다.  예를 들어, 입력값인 {0, 1, 2} 와 3 창 크기의 경우, 슬라이딩 창 데이터 흐름 블록은 출력 배열로 {0, 1, 2, 3, 4, 5}, {1, 2, 3}, {2, 3, 4}, 그리고 {3, 4, 5} 을 생성합니다.  다음 섹션에서는 이 사용자 지정 동작을 구현하는 데이터 흐름 블록 형식을 만드는 두 가지 방법을 설명 합니다.  첫 번째 방법은 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> 메서드를 사용하여 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 개체와 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 개체의 기능을 한 전파자 블록 개체로 결합합니다.  두 번째 방법은 <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> 에서 파생 되는 클래스를 정의하고 기존 기능을 결합하여 사용자 지정 동작을 수행합니다.  
  
## 캡슐화 메서드를 사용하여 슬라이딩 창 데이터 흐름 블록을 정의  
 다음 예제는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> 메서드를 사용하여 소스 및 대상으로 부터 전파자 블록을 만듭니다.  전파자 블록은 원본 블록과 대상 블록을 사용하여 데이터의 수신자 및 발신자처럼 행동할 수 있습니다.  
  
 이 기술은 사용자 지정 데이터 흐름 기능이 필요하지만 추가적인 메서드, 속성, 또는 필드를 제공하는 타입을 필요로 하지 않을 경우 유용합니다.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#1)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#1)]  
  
## IPropagatorBlock에서 파생하여 슬라이딩 창 데이터 흐름 블록을 정의  
 다음 예제에서는 `SlidingWindowBlock` 클래스를 보여 줍니다.  이 클래스는 데이터의 소스 및 대상처럼 작동할 수 있도록 <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> 로 부터 파생되었습니다.  앞의 예와 같이, `SlidingWindowBlock` 클래스는 기존 데이터 흐름 블록 형식에서 만들어집니다.  그러나 `SlidingWindowBlock` 클래스는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, 그리고 <xref:System.Threading.Tasks.Dataflow.IDataflowBlock> 인터페이스로 부터 필요로 하는 메서드들을 구현합니다.  이러한 메서드들은 모두 미리 정의된 데이터 흐름 블록 형식 멤버들에 작업을 보냅니다.  예를 들어, `Post` 메서드는 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 이기도 한 `m_target` 데이터 멤버로 작업을 미룹니다.  
  
 이 기술은 사용자 지정 데이터 흐름 기능이 필요할 때 유용하고, 또한 추가적인 메서드, 속성, 또는 필드를 제공하는 타입을 필요로 하지 않을 경우 유용합니다.  예를 들어, `SlidingWindowBlock` 클래스는 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 및 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A> 메서드를 제공할 수 있도록 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601> 로 부터 파생됩니다.  `SlidingWindowBlock` 클래스는 슬라이딩 창에서의 구성 요소 수를 검색하는 `WindowSize` 속성을 제공하여 확장성을 보여줍니다.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#2)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#2)]  
  
## 전체 예제  
 다음 예제에서는 이 연습의 전체 코드를 보여 줍니다.  이것은 또한 결과를 콘솔에 쓰고, 읽고, 출력하는 메서드의 양쪽 슬라이딩 창 블록을 사용 하는 방법을 보여 줍니다.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#100)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#100)]  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트에 붙여넣거나 `SlidingWindowBlock.cs` \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 의 `SlidingWindowBlock.vb`\) 파일에 붙여넣은 다음 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**  
  
## 다음 단계  
  
## 참고 항목  
 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)