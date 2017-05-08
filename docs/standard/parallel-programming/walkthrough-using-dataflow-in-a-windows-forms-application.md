---
title: "Walkthrough: Using Dataflow in a Windows Forms Application | Microsoft Docs"
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
  - "TPL dataflow library, in Windows Forms"
  - "Task Parallel Library, dataflows"
  - "Windows Forms, and TPL"
ms.assetid: 9c65cdf7-660c-409f-89ea-59d7ec8e127c
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Walkthrough: Using Dataflow in a Windows Forms Application
이 문서에서는 Windows Forms 응용 프로그램에서 이미지 처리를 수행하는 데이터 흐름 블록의 네트워크를 만드는 방법을 보여 줍니다.  
  
 이 예제에서는 지정한 폴더에서 이미지 파일을 로드, 합성 이미지를 생성 및 결과를 표시 합니다.  이 예제에서는 데이터 흐름 모델을 사용하여 네트워크를 통해 이미지 경로를 지정합니다.  데이터 모델에서 프로그램의 독립 구성 요소는 메시지를 보내 서로 통신합니다.  구성 요소가 메시지를 받으면 임의의 동작을 수행한 다음 결과를 다른 구성 요소에 전달합니다.  데이터 흐름 모델을 제어 흐름 모델과 비교해 볼 수 있습니다. 제어 흐름 모델의 경우 응용 프로그램에서 조건문, 루프 등의 제어 구조를 사용하여 프로그램의 작업 순서를 제어합니다.  
  
## 사전 요구 사항  
 이 연습을 시작하기 전에 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) 항목의 내용을 읽어 보십시오.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리 \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName> 네임 스페이스\)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]과 함께 배포 되지 않습니다.  이 <xref:System.Threading.Tasks.Dataflow> 네임스페이스를 설치 할려면, [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]에서 프로젝트를 열고, 프로젝트 메뉴에서 **Manage NuGet Packages** 를 선택한 후, `Microsoft.Tpl.Dataflow` 패키지를 온라인에서 검색합니다.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리 \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName> 네임 스페이스\)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]과 함께 배포 되지 않습니다.  이 <xref:System.Threading.Tasks.Dataflow> 네임스페이스를 설치 할려면, [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]에서 프로젝트를 열고, 프로젝트 메뉴에서 **Manage NuGet Packages** 를 선택한 후, `Microsoft.Tpl.Dataflow` 패키지를 온라인에서 검색합니다.  
  
## 단원  
 이 연습에는 다음 단원이 포함되어 있습니다.  
  
-   [Windows Forms 응용 프로그램 만들기](#winforms)  
  
-   [데이터 흐름 네트워크 생성](#network)  
  
-   [사용자 인터페이스에 데이터 흐름 네트워크 연결](#ui)  
  
-   [전체 예제](#complete)  
  
<a name="winforms"></a>   
## Windows Forms 응용 프로그램 만들기  
 기본 Windows Forms 응용 프로그램 만들기 및 기본 폼에 컨트롤을 추가 하는 방법을 설명 합니다.  
  
#### 새 Windows Forms 응용 프로그램을 만들려면  
  
1.  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 에서 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] 또는 Visual Basic **Windows Forms 프로그램** 프로젝트를 만듭니다.  이 문서에서, 프로젝트 이름은 `CompositeImages` 입니다.  
  
2.  메인 폼의 폼 디자이너인 Form1.cs \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 의 Form1.vb\) 에서, <xref:System.Windows.Forms.ToolStrip> 컨트롤을 추가 합니다.  
  
3.  <xref:System.Windows.Forms.ToolStrip> 컨트롤에 <xref:System.Windows.Forms.ToolStripButton> 컨트롤을 추가합니다.  <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 속성을 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 로, 그리고 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 Choose Folder로 설정합니다.  
  
4.  <xref:System.Windows.Forms.ToolStrip> 컨트롤에 <xref:System.Windows.Forms.ToolStripButton> 컨트롤을 추가합니다.  <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 속성을 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 로, <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 Cancel로, 그리고 <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> 속성을 `False` 로 설정합니다.  
  
5.  메인 폼에 <xref:System.Windows.Forms.PictureBox> 개체를 추가합니다.  <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle>으로 설정합니다.  
  
<a name="network"></a>   
## 데이터 흐름 네트워크 생성  
 이 섹션에서는 이미지 처리를 수행하여 데이터 흐름 네트워크를 만드는 방법에 대해 설명 합니다.  
  
#### 데이터 흐름 네트워크를 만들려면  
  
1.  프로젝트에 System.Threading.Tasks.Dataflow.dll에 대한 참조를 추가 합니다.  
  
2.  다음 `using` \( [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 에서의 `Using` \) 명세서들을 포함하는 해당 Form1.cs \( [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]의 Form1.vb\) 을 확인하세요.  
  
     [!code-csharp[TPLDataflow_CompositeImages#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#1)]  
  
3.  `Form1` 클래스에 다음의 데이터 멤버를 추가합니다.  
  
     [!code-csharp[TPLDataflow_CompositeImages#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#2)]  
  
4.  다음 `CreateImageProcessingNetwork` 메서드를 `Form1` 클래스에 추가합니다.  이 메서드는 이미지 처리 네트워크를 만듭니다.  
  
     [!code-csharp[TPLDataflow_CompositeImages#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#3)]  
  
5.  `LoadBitmaps` 메서드를 구현합니다.  
  
     [!code-csharp[TPLDataflow_CompositeImages#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#4)]  
  
6.  `CreateCompositeBitmap` 메서드를 구현합니다.  
  
     [!code-csharp[TPLDataflow_CompositeImages#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#5)]  
  
    > [!NOTE]
    >  C\# 버전의 `CreateCompositeBitmap` 메서드는 포인터를 사용하여 <xref:System.Drawing.Bitmap?displayProperty=fullName> 개체의 효율적인 처리를 하도록 해줍니다.  따라서 프로젝트에서 [unsafe](../Topic/unsafe%20\(C%23%20Reference\).md) 키위드를 사용하기 위해서는 **unsafe 코드 허용** 옵션을 사용해야 합니다.  [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] 프로젝트에서 unsafe 코드를 사용 하는 방법에 대한 자세한 내용은 [프로젝트 디자이너, 빌드 페이지\(C\#\)](../Topic/Build%20Page,%20Project%20Designer%20\(C%23\).md) 을 참조 하십시오..  
  
 다음 표에서는 네트워크 멤버에 대해 설명합니다.  
  
|멤버|형식|설명|  
|--------|--------|--------|  
|`loadBitmaps`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|폴더 경로를 입력으로 사용하여 <xref:System.Drawing.Bitmap> 개체의 컬렉션을 출력으로 생성합니다.|  
|`createCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|<xref:System.Drawing.Bitmap> 의 컬렉션을 입력으로 사용하여 복합 비트맵을 출력으로 생성합니다.|  
|`displayCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|폼에서 합성 비트맵을 표시합니다.|  
|`operationCancelled`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|이미지를 표시하여 작업이 취소 되었음을 나타내고 사용자가 다른 폴더를 선택하도록 해줍니다.|  
  
 네트워크를 구성 하는 데이터 흐름 블록을 연결 하기 위해 이 예제에서는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> 메서드를 사용합니다.  <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> 메서드는 대상 블록이 메세지를 수락 또는 거부할지를 결정하는 <xref:System.Predicate%601> 개체를 사용하는 오버로드된 버전을 포함합니다.  이 필터링 메커니즘은 메시지 블록이 특정 값만 받을 수 있게 해줍니다.  이 예제에서 네트워크는 두 가지 방법 중 하나로 분기할 수 있습니다.  Main 분기는 디스크에서 이미지를 로드하고 합성 이미지를 만든 다음 폼에 이미지를 표시 합니다.  대체 분기는 현재 작업을 취소 합니다.  <xref:System.Predicate%601> 개체는 특정 메세지를 거부하여 메인 분기에서 다른 분기로 전환하게끔 데이터 흐름을 차단하도록 해줍니다.  예를 들어, 사용자가 작업을 취소하는 경우, 데이터 흐름 블록 `createCompositeBitmap` 은 출력으로 `null` \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 의 `Nothing`\) 을 생성합니다.  데이터 흐름 블록 `displayCompositeBitmap` `null` 입력 값을 거부하고, 따라서 메시지는 `operationCancelled` 에 제공됩니다.  데이터 흐름 블록 `operationCancelled` 은 모든 메시지를 수락하고, 따라서 작업이 취소 되었음을 나타내는 이미지를 표시합니다.  
  
 다음 그림에서는 이미지 처리 네트워크를 보여 줍니다.  
  
 ![이미지 처리 네트워크](../../../docs/standard/parallel-programming/media/dataflowwinforms.png "DataflowWinForms")  
  
 `displayCompositeBitmap` 및 `operationCancelled` 데이터 흐름 블록이 사용자 인터페이스에서 동작하기 때문에, 이러한 동작들은 사용자 인터페이스 스레드에서 일어나야 합니다.  이를 수행하기 위해, 생성하는 동안 이러한 개체는 각각 <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=fullName> 로 설정된 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> 속성을 가진 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> 개체를 제공합니다.  <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=fullName> 메서드는 현재 동기화 컨텍스트에서 작업을 수행하는 <xref:System.Threading.Tasks.TaskScheduler> 개체를 생성합니다.  `CreateImageProcessingNetwork` 메서드가 폴더 선택 단추의 처리기에서 호출 되었기 때문에, `displayCompositeBitmap` 및 `operationCancelled` 데이터 흐름 블록에 대한 동작들 또한 사용자 인터페이스 스레드에서 실행됩니다.  
  
 이 예제에서는 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> 속성이 영구적으로 데이터 흐름 블록 실행을 취소하기 때문에 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> 속성을 설정하는 대신 공유된 취소 토큰을 사용합니다.  이 예제에서 취소 토큰은 사용자가 하나 이상의 작업을 취소 하더라도 동일한 데이터 흐름 네트워크를 여러 번 재사용할 수 있게 해줍니다.  데이터 흐름 블록의 실행을 영구적으로 취소하기 위해 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> 을 사용하는 예제의 경우 [How to: Cancel a Dataflow Block](../../../docs/standard/parallel-programming/how-to-cancel-a-dataflow-block.md) 를 참조 하십시오.  
  
<a name="ui"></a>   
## 사용자 인터페이스에 데이터 흐름 네트워크 연결  
 이 섹션에서는 사용자 인터페이스에 데이터 흐름 네트워크를 연결 하는 방법을 설명 합니다.  합성 이미지 만들기 및 작업의 취소는 폴더 선택 및 취소 단추에서 시작 됩니다.  사용자가 이 단추 중 하나를 선택 하는 경우 적절한 조치가 비동기식으로 시작 됩니다.  
  
#### 사용자 인터페이스에 데이터 흐름 네트워크 연결하려면  
  
1.  기본 폼의 폼 디자이너에서, 폴더 선택 단추에 대한 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트의 이벤트 처리기를 만듭니다.  
  
2.  폴더 선택 단추에 대한 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트를 구현합니다.  
  
     [!code-csharp[TPLDataflow_CompositeImages#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#6)]  
  
3.  기본 폼의 폼 디자이너에서, 취소 단추에 대한 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트의 이벤트 처리기를 만듭니다.  
  
4.  취소 단추에 대한 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트를 구현합니다.  
  
     [!code-csharp[TPLDataflow_CompositeImages#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#7)]  
  
<a name="complete"></a>   
## 전체 예제  
 다음 예제에서는 이 연습의 전체 코드를 보여 줍니다.  
  
 [!code-csharp[TPLDataflow_CompositeImages#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#100)]  
  
 다음 그림은 일반적인 \\Sample Pictures\\ 폴더에 대한 일반적인 출력을 보여줍니다.  
  
 ![Windows Forms 응용 프로그램](../../../docs/standard/parallel-programming/media/tpldataflow-compositeimages.gif "TPLDataflow\_CompositeImages")  
  
## 다음 단계  
  
## 참고 항목  
 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)