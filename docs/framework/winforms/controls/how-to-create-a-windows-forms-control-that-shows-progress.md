---
title: "방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "컨트롤[Windows Forms], 만들기"
  - "컨트롤[Windows Forms], 진행률 추적"
  - "FlashTrackBar 사용자 지정 컨트롤"
  - "진행률, 보고[Windows Forms]"
ms.assetid: 24c5a2e3-058c-4b8d-a217-c06e6a130c2f
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기
다음 코드 예제에서는 `FlashTrackBar`라는 사용자 지정 컨트롤을 보여 줍니다. 이 컨트롤은 응용 프로그램의 진행 수준을 표시하는 데 사용됩니다.  이 컨트롤에서는 그라데이션을 사용하여 진행 상태를 시각적으로 표시합니다.  
  
 `FlashTrackBar` 컨트롤에서는 다음과 같은 개념을 보여 줍니다.  
  
-   사용자 지정 속성의 정의  
  
-   사용자 지정 이벤트의 정의.  `FlashTrackBar`에서는 `ValueChanged` 이벤트를 정의합니다.  
  
-   컨트롤 그리기 논리를 제공하기 위해 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의합니다.  
  
-   <xref:System.Windows.Forms.Control.ClientRectangle%2A> 속성을 사용하여 컨트롤을 그리는 데 필요한 면적을 계산합니다.  이 작업은 `FlashTrackBar`의 `OptimizedInvalidate` 메서드에서 수행됩니다.  
  
-   Windows Forms 디자이너에서 속성이 변경되는 경우 이 속성의 serialization 또는 지속성을 구현합니다.  `FlashTrackBar`에서는 `ShouldSerializeStartColor` 및 `ShouldSerializeEndColor` 메서드를 정의하여 `StartColor` 및 `EndColor` 속성을 serialize합니다.  
  
 다음 표에서는 `FlashTrackBar`에서 정의되는 사용자 지정 속성을 보여 줍니다.  
  
|Property|설명|  
|--------------|--------|  
|`AllowUserEdit`|사용자가 플래시 트랙 막대를 클릭하고 끌어서 이 막대를 변경할 수 있는지 지정합니다.|  
|`EndColor`|트랙 막대의 끝 색을 지정합니다.|  
|`DarkenBy`|전경 그라데이션에 대한 배경의 상대적인 밝기를 지정합니다.|  
|`Max`|트랙 막대의 최대값을 지정합니다.|  
|`Min`|트랙 막대의 최소값을 지정합니다.|  
|`StartColor`|그라데이션의 시작 색을 지정합니다.|  
|`ShowPercentage`|그라데이션의 백분율을 표시할지 지정합니다.|  
|`ShowValue`|그라데이션의 현재 값을 표시할지 지정합니다.|  
|`ShowGradient`|현재 값을 나타내는 색 그라데이션을 트랙 막대에서 표시할지 지정합니다.|  
|-   `Value`|트랙 막대의 현재 값을 지정합니다.|  
  
 다음 표에서는 `FlashTrackBar:`에서 정의되는 추가 멤버\(속성 변경 이벤트 및 해당 이벤트를 발생시키는 메서드\)를 보여 줍니다.  
  
|멤버|설명|  
|--------|--------|  
|`ValueChanged`|트랙 막대의 `Value` 속성이 변경될 때 발생하는 이벤트입니다.|  
|`OnValueChanged`|`ValueChanged` 이벤트를 발생시키는 메서드입니다.|  
  
> [!NOTE]
>  `FlashTrackBar`는 이벤트 데이터에 <xref:System.EventArgs> 클래스를 사용하고 이벤트 대리자에 <xref:System.EventHandler> 클래스를 사용합니다.  
  
 해당 *EventName* 이벤트를 처리하기 위해 `FlashTrackBar`는 다음과 같은 메서드를 재정의합니다. 이 메서드는 <xref:System.Windows.Forms.Control?displayProperty=fullName>에서 상속됩니다.  
  
-   <xref:System.Windows.Forms.Control.OnPaint%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseDown%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseMove%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseUp%2A>  
  
-   <xref:System.Windows.Forms.Control.OnResize%2A>  
  
 해당 속성 변경 이벤트를 처리하기 위해 `FlashTrackBar`는 다음과 같은 메서드를 재정의합니다. 이 메서드는 <xref:System.Windows.Forms.Control?displayProperty=fullName>에서 상속됩니다.  
  
-   <xref:System.Windows.Forms.Control.OnBackColorChanged%2A>  
  
-   <xref:System.Windows.Forms.Control.OnBackgroundImageChanged%2A>  
  
-   <xref:System.Windows.Forms.Control.OnTextChanged%2A>  
  
## 예제  
 `FlashTrackBar` 컨트롤은 다음 코드 목록에 표시되는 두 UI 형식 편집기인 `FlashTrackBarValueEditor` 및 `FlashTrackBarDarkenByEditor`를 정의합니다.  `HostApp` 클래스는 Windows Form의 `FlashTrackBar` 컨트롤을 사용합니다.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#1)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#1)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarDarkenByEditor.cs#10)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarDarkenByEditor.vb#10)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarValueEditor.cs#20)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarValueEditor.vb#20)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/HostApp.cs#30)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/HostApp.vb#30)]  
  
## 참고 항목  
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)   
 [Windows Forms 컨트롤 개발 기본 사항](../../../../docs/framework/winforms/controls/windows-forms-control-development-basics.md)