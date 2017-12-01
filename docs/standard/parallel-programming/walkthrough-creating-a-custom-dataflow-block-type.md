---
title: "연습: 사용자 지정 데이터 흐름 블록 형식 만들기"
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
- TPL dataflow library, creating custom dataflow blocks
- dataflow blocks, creating custom in TPL
ms.assetid: a6147146-0a6a-4d9b-ab0f-237b3c1ac691
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 809b21fa6e1470890011604792d849998dd03ede
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-creating-a-custom-dataflow-block-type"></a>연습: 사용자 지정 데이터 흐름 블록 형식 만들기
TPL 데이터 흐름 라이브러리는 다양 한 기능을 사용할 수 있는 몇 가지 데이터 흐름 블록 형식은 제공 하지만 사용자 지정 블록 형식을 만들 수도 있습니다. 이 문서에는 사용자 지정 동작을 구현 하는 데이터 흐름 블록 형식을 만드는 방법을 설명 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 읽기 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) 이 문서를 읽기 전에 합니다.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리(<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 네임스페이스)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]와 함께 배포되지 않습니다. 설치 하는 <xref:System.Threading.Tasks.Dataflow> 네임 스페이스에서 프로젝트를 열고 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], 선택 **NuGet 패키지 관리** 프로젝트 메뉴에 대 한 온라인 검색에서는 `Microsoft.Tpl.Dataflow` 패키지 합니다.  
  
## <a name="defining-the-sliding-window-dataflow-block"></a>슬라이딩 창 데이터 흐름 블록을 정의합니다.  
 입력된 값 버퍼링 되 고 다음 슬라이딩 윈도우 방식으로 출력 필요로 하는 데이터 흐름 응용 프로그램을 고려 합니다. 예를 들어 입력된 값 {0, 1, 2, 3, 4, 5} 및 3의 창 크기에 대 한 슬라이딩 창 데이터 흐름 블록을 생성 출력 배열의 {0, 1, 2} {1, 2, 3} {2, 3, 4}와 {3, 4, 5}. 다음 섹션에서는이 사용자 지정 동작을 구현 하는 데이터 흐름 블록 형식을 만드는 두 가지 방법에 설명 합니다. 첫 번째 방법을 사용 하 여는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> 의 기능을 결합 하는 메서드는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 개체 및 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 하나의 전파자 블록에는 개체입니다. 파생 되는 클래스를 정의 하는 두 번째 기술은 <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> 하 고 사용자 지정 동작을 수행 하는 기존 기능을 결합 합니다.  
  
## <a name="using-the-encapsulate-method-to-define-the-sliding-window-dataflow-block"></a>사용 하 여 슬라이딩 창 데이터 흐름 블록을 정의 하는 메서드를 캡슐화 합니다.  
 다음 예제에서는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> 대상과 원본이에서 전파자 블록을 만드는 메서드를 합니다. 전파자 블록은 소스 블록과 대상 블록 역할 수신기 및 데이터의 보낸 사람을 수 있습니다.  
  
 이 방법은 사용자 지정 데이터 흐름 기능이 필요 하지만 추가 메서드, 속성 또는 필드를 제공 하는 형식 필요 하지 않은 경우에 유용 합니다.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#1)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#1)]  
  
## <a name="deriving-from-ipropagatorblock-to-define-the-sliding-window-dataflow-block"></a>슬라이딩 창 데이터 흐름 블록을 정의 하려면 IPropagatorBlock에서 파생  
 다음 예제와 `SlidingWindowBlock` 클래스입니다. 이 클래스에서 파생 <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> 는 소스와 데이터의 대상으로 작동할 수 있도록 합니다. 위의 예와 `SlidingWindowBlock` 클래스는 기존 데이터 흐름 블록 형식을 기반으로 합니다. 그러나는 `SlidingWindowBlock` 클래스 구현에 필요한 메서드는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, 및 <xref:System.Threading.Tasks.Dataflow.IDataflowBlock> 인터페이스입니다. 이러한 메서드를 앞으로 모든 미리 정의 된 데이터 흐름 블록 형식 멤버에 작동합니다. 예를 들어는 `Post` 에 작업을 지연 하는 메서드는 `m_target` 이기도 데이터 멤버는 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 개체입니다.  
  
 이 방법은 사용자 지정 데이터 흐름 기능을 필요로 하 고 추가 메서드, 속성 또는 필드를 제공 하는 형식에 있어야 하는 경우에 유용 합니다. 예를 들어는 `SlidingWindowBlock` 클래스에서 파생 되기도 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601> 제공할 수 있도록는 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 및 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A> 메서드. `SlidingWindowBlock` 클래스에서는 확장성을 제공 하 여는 `WindowSize` 슬라이딩 윈도우에 있는 요소의 수를 검색 하는 속성입니다.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#2)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#2)]  
  
## <a name="the-complete-example"></a>전체 예제  
 다음 예제에서는 이 연습의 전체 코드를 보여 줍니다. 또한 블록, 여기에서 읽고 쓰고 콘솔에 결과 출력 하는 메서드에서 두 슬라이딩 창 블록을 사용 하는 방법을 보여 줍니다.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#100)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#100)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `SlidingWindowBlock.cs` (`SlidingWindowBlock.vb` 에 대 한 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 및 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**  
  
## <a name="next-steps"></a>다음 단계  
  
## <a name="see-also"></a>참고 항목  
 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
