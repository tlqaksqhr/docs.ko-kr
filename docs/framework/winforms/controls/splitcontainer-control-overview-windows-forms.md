---
title: "SplitContainer 컨트롤 개요(Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SplitContainer"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "SplitContainer 컨트롤[Windows Forms], SplitContainer 컨트롤 정보"
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# SplitContainer 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.SplitContainer> 컨트롤은 이동 가능한 막대로 구분된 두 개의 패널로 구성되어 있습니다.  마우스 포인터를 막대 위에 놓으면 포인터가 바뀌면서 막대를 이동할 수 있음이 표시됩니다.  
  
> [!IMPORTANT]
>  **도구 상자**에서 <xref:System.Windows.Forms.SplitContainer> 컨트롤은 이전 버전의 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에 있던 <xref:System.Windows.Forms.Splitter> 컨트롤을 대체합니다.  <xref:System.Windows.Forms.SplitContainer> 컨트롤은 <xref:System.Windows.Forms.Splitter> 컨트롤보다 훨씬 많이 사용됩니다.  기존 응용 프로그램과의 호환성을 고려하여 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에는 <xref:System.Windows.Forms.Splitter> 클래스가 포함되어 있지만 새 프로젝트에는 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 사용하는 것이 좋습니다.  
  
 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 사용하면 한 패널에서의 선택 항목에 따라 다른 패널에 표시되는 개체가 정해지는 복합 사용자 인터페이스를 만들 수 있습니다.  이러한 배열은 정보를 표시하고 찾아보는 데 매우 효과적입니다.  두 개의 패널을 사용하면 영역, 막대 또는 "분할자"의 정보를 집계할 수 있으므로 사용자가 패널의 크기를 쉽게 조정할 수 있습니다.  
  
 둘 이상의 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 중첩하여 사용할 수 있으며 두 번째 <xref:System.Windows.Forms.SplitContainer> 컨트롤은 가로로 배치하여 위쪽 패널과 아래쪽 패널을 만들 수 있습니다.  
  
 <xref:System.Windows.Forms.SplitContainer> 컨트롤은 기본적으로 키보드에서 액세스할 수 있습니다. 즉, <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성을 `false`로 설정하면 화살표 키를 눌러 분할자를 이동할 수 있습니다.  
  
 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 속성은 컨트롤이 아니라 분할자의 방향을 결정합니다.  따라서 이 속성을 <xref:System.Windows.Forms.Orientation>로 설정하면 분할자는 위에서 아래로 배치되어 왼쪽 패널과 오른쪽 패널을 만듭니다.  
  
 또한 <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> 속성의 값은 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 속성의 값에 따라 달라집니다.  자세한 내용은 <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> 속성을 참조하십시오.  
  
 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 크기와 이동을 제한할 수도 있습니다.  <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> 속성은 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 크기를 조정한 후 같은 크기를 유지할 패널을 결정하며, <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성은 분할자를 키보드나 마우스로 이동할 수 있을지 여부를 결정합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성을 `true`로 설정한 경우에도 <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 속성을 사용하는 방법 등으로 분할자를 프로그래밍 방식으로 이동할 수 있습니다.  
  
 마지막으로, <xref:System.Windows.Forms.SplitContainer> 컨트롤의 각 패널에는 개별 크기를 결정하는 속성이 있습니다.  
  
## 일반적으로 사용되는 속성, 메서드 및 이벤트  
  
|Name|설명|  
|----------|--------|  
|<xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> 속성|<xref:System.Windows.Forms.SplitContainer> 컨트롤의 크기를 조정한 후에도 크기를 그대로 유지할 패널을 결정합니다.|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성|분할자를 키보드나 마우스로 이동할 수 있는지 여부를 결정합니다.|  
|<xref:System.Windows.Forms.SplitContainer.Orientation%2A> 속성|분할자를 가로로 정렬할지 아니면 세로로 정렬할지 결정합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 속성|왼쪽 또는 위쪽 가장자리에서 이동 가능한 분할 막대까지의 거리를 픽셀 단위로 지정합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 속성|사용자가 분할자를 이동할 수 있는 최소 거리를 픽셀 단위로 지정합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A> 속성|분할자의 두께를 픽셀 단위로 지정합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoving> 이벤트|분할자가 이동하고 있을 때 발생합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoved> 이벤트|분할자가 이동한 경우에 발생합니다.|  
  
## 참고 항목  
 <xref:System.Windows.Forms.SplitContainer>   
 [SplitContainer 컨트롤](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)   
 [SplitContainer Control Sample](http://msdn.microsoft.com/ko-kr/9015fad0-7108-4d85-a83a-a72d038c4f65)