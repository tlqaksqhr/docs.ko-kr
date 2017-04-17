---
title: "How to: Cancel a Dataflow Block | Microsoft Docs"
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
  - "dataflow blocks, canceling in TPL"
  - "TPL dataflow library,canceling dataflow blocks"
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Cancel a Dataflow Block
이 문서에서는 응용 프로그램에서 취소를 사용할 수 있도록 하는 방법을 보여 줍니다.  이 예제에서는 데이터 흐름 파이프라인에서 어느 작업 항목이 활성되있는지와 취소의 효과를 표시해주는 Windows Forms을 사용 합니다.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리 \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName> 네임 스페이스\)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]과 함께 배포 되지 않습니다.  이 <xref:System.Threading.Tasks.Dataflow> 네임스페이스를 설치 할려면, [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]에서 프로젝트를 열고, 프로젝트 메뉴에서 **Manage NuGet Packages** 를 선택한 후, `Microsoft.Tpl.Dataflow` 패키지를 온라인에서 검색합니다.  
  
### 새 Windows Forms 응용 프로그램을 만들려면  
  
1.  C\# 또는 Visual Basic **Windows Forms 응용 프로그램** 프로젝트를 생성합니다  다음 단계에서 프로젝트를 `CancellationWinForms` 로 명명합니다.  
  
2.  메인 폼의 폼 디자이너인 Form1.cs \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 의 Form1.vb\) 에서, <xref:System.Windows.Forms.ToolStrip> 컨트롤을 추가 합니다.  
  
3.  <xref:System.Windows.Forms.ToolStrip> 컨트롤에 <xref:System.Windows.Forms.ToolStripButton> 컨트롤을 추가합니다.  <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 속성을 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 로 설정하고 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 작업 항목 추가로 설정합니다.  
  
4.  <xref:System.Windows.Forms.ToolStrip> 컨트롤에 두번째 <xref:System.Windows.Forms.ToolStripButton> 컨트롤을 추가합니다.  <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 속성을 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 로, <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 Cancel로, 그리고 <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> 속성을 `False` 로 설정합니다.  
  
5.  네개의 <xref:> System.Windows.Forms.ToolStripProgressBar?qualifyHint=False&autoUpgrade=True 개체를 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 추가합니다.  
  
## 데이터 흐름 파이프라인 만들기  
 이 섹션에서는 작업 항목을 처리하고 진행률 표시줄을 업데이트 하는 데이터 흐름 파이프라인을 만드는 방법을 설명 합니다.  
  
#### 데이터 흐름 파이프라인을 만들려면  
  
1.  프로젝트에서 System.Threading.Tasks.Dataflow.dll에 대한 참조를 추가 합니다.  
  
2.  다음 `using` \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에서 `Imports`\) 명세서들을 포함하는 해당 Form1.cs \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에 대한 Form1.vb\) 을 확인하세요.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3.  `WorkItem` 클래스를 `Form1` 클래스의 내부 유형으로 추가합니다.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4.  `Form1` 클래스에 다음의 데이터 멤버를 추가합니다.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5.  다음 `CreatePipeline` 메서드를 `Form1` 클래스에 추가합니다.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 `incrementProgress` 및 `decrementProgress` 데이터 흐름 블록이 사용자 인터페이스에서 동작하기 때문에, 이러한 동작들은 사용자 인터페이스 스레드에서 일어나야 합니다.  이를 수행하기 위해, 생성하는 동안 이러한 개체는 각각 <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=fullName> 로 설정된 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> 속성을 가진 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> 개체를 제공합니다.  <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=fullName> 메서드는 현재 동기화 컨텍스트에서 작업을 수행하는 <xref:System.Threading.Tasks.TaskScheduler> 개체를 생성합니다.  `Form1` 생성자는 사용자 인터페이스 스레드로부터 호출되기 때문에, `incrementProgress` 및 `decrementProgress` 데이터 흐름 블록은 사용자 인터페이스 스레드에서 실행됩니다.  
  
 이 예제는 이것이 파이프라인의 멤버를 생성할 때 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> 속성을 설정합니다.  <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> 속성은 데이터 흐름 블록 실행을 영구적으로 취소하기 때문에, 전체 파이프라인은 사용자가 작업을 취소한 다음 파이프라인에 더 많은 작업 항목을 추가하려고 한 후 재 생성 되어야 합니다.  작업이 취소된 후 다른 작업을 수행할 수 있도록 데이터 흐름 블록을 취소하는 다른 방법을 보여 주는 예제를 보려면 [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md) 을 참조하십시오.  
  
## 사용자 인터페이스에 데이터 흐름 파이프라인 연결  
 이 섹션에서는 사용자 인터페이스에 데이터 흐름 파이프라인을 연결 하는 방법을 설명 합니다.  파이프라인 만들기와 파이프라인에 작업 항목 추가하기 둘 다 작업 항목 추가 단추에 대한 이벤트 처리기에 의해 제어 됩니다.  취소는 취소 단추에 의해 시작 됩니다.  사용자가 이 단추 중 하나를 선택 하는 경우 적절한 조치가 비동기식으로 시작 됩니다.  
  
#### 사용자 인터페이스에 데이터 흐름 파이프라인 연결하려면  
  
1.  메인 폼의 폼 디자이너에서, 작업 항목 추가 단추에 대한 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트의 이벤트 핸들러를 생성합니다.  
  
2.  작업 항목 추가 단추에 대한 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트를 구현합니다.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3.  기본 폼의 폼 디자이너에서, 취소 단추에 대한 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트 처리기의 이벤트 처리기를 만듭니다.  
  
4.  취소 단추에 대한 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트 처리기를 구현합니다.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## 예제  
 다음 예제에서는 Form1.cs에 대한 전체 코드를 보여 줍니다 \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]의 Form1.vb\).  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 다음 그림에서는 실행중인 응용 프로그램을 보여 줍니다.  
  
 ![Windows Forms 응용 프로그램](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow\_Cancellation")  
  
## 강력한 프로그래밍  
  
## 참고 항목  
 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)