---
title: "방법: Windows Forms에서 컨트롤 고정 | Microsoft Docs"
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
  - "Anchor 속성, 크기 조정 가능한 폼 사용"
  - "컨트롤[Windows Forms], 고정"
  - "컨트롤[Windows Forms], 위치 지정"
  - "폼, 크기 조정"
  - "폼 크기 조정"
  - "화면 해상도 및 컨트롤 표시"
  - "Windows Forms 컨트롤, 화면 해상도"
  - "Windows Forms 컨트롤, 크기"
  - "Windows Forms, 크기 조정"
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: Windows Forms에서 컨트롤 고정
런타임에 크기를 조정할 수 있는 폼을 디자인하는 경우 폼의 컨트롤은 크기 및 위치가 적절하게 조정되어야 합니다.  Windows Forms 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 사용하면 폼에 따라 컨트롤의 크기를 동적으로 조정할 수 있습니다.  <xref:System.Windows.Forms.Control.Anchor%2A> 속성은 컨트롤에 대한 앵커 위치를 정의합니다.  컨트롤을 폼에 고정하면 폼의 크기를 조정할 때 컨트롤과 앵커 위치 사이의 간격이 일정하게 유지됩니다.  예를 들어 폼의 왼쪽, 오른쪽 및 아래쪽 가장자리에 <xref:System.Windows.Forms.TextBox> 컨트롤을 고정한 경우 폼의 크기를 조정할 때 폼의 오른쪽 가장자리 및 왼쪽 가장자리와의 거리가 동일하게 유지되도록 <xref:System.Windows.Forms.TextBox> 컨트롤의 가로 크기가 조정됩니다.  또한 컨트롤이 폼의 아래쪽 가장자리와의 간격이 항상 동일하게 유지되도록 컨트롤의 세로 위치가 조정됩니다.  컨트롤을 폼에 고정하지 않으면 폼의 크기를 조정할 때 폼의 가장자리를 기준으로 한 컨트롤의 위치가 변경됩니다.  
  
 <xref:System.Windows.Forms.Control.Anchor%2A> 속성은 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성과 상호 작용합니다.  자세한 내용은 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 폼에 컨트롤을 고정하려면  
  
1.  고정할 컨트롤을 선택합니다.  
  
    > [!NOTE]
    >  Ctrl 키를 누른 상태에서 각 컨트롤을 클릭하여 선택하고 다음의 나머지 단계를 수행하면 여러 컨트롤을 동시에 고정할 수 있습니다.  
  
2.  **속성** 창에서 <xref:System.Windows.Forms.Control.Anchor%2A> 속성의 오른쪽에 있는 화살표를 클릭합니다.  
  
     십자형 표시가 있는 편집기가 표시됩니다.  
  
3.  앵커를 설정하려면 십자형의 위쪽, 왼쪽, 오른쪽 또는 아래쪽 섹션을 클릭합니다.  
  
     컨트롤은 기본적으로 위쪽과 왼쪽에 고정되어 있습니다.  
  
4.  고정된 컨트롤의 한 쪽을 취소하려면 십자형에서 해당 막대를 클릭합니다.  
  
5.  <xref:System.Windows.Forms.Control.Anchor%2A> 속성 편집기를 닫으려면 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 이름을 다시 클릭합니다.  
  
 런타임에 폼을 표시하면 폼의 가장자리와 동일한 간격의 위치를 유지하도록 컨트롤의 크기가 조정됩니다.  고정된 가장자리와의 간격은 항상 Windows Forms 디자이너에서 컨트롤의 위치를 지정할 때 정의한 거리와 동일하게 유지됩니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ComboBox> 컨트롤과 같은 특정 컨트롤에는 높이 제한이 있습니다.  폼이나 컨테이너 아래쪽에 컨트롤을 고정해도 해당 컨트롤의 높이 제한을 초과할 수는 없습니다.  
  
 상속된 컨트롤을 고정하려면 컨트롤이 `Protected`여야 합니다.  컨트롤의 액세스 수준을 변경하려면 **속성** 창에서 컨트롤의 `Modifiers` 속성을 설정합니다.  
  
## 참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)   
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)   
 [방법: Windows Forms에 컨트롤 도킹](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)   
 [연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)