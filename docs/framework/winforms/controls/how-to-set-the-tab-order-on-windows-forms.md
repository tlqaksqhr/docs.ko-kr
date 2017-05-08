---
title: "방법: Windows Forms에서 탭 순서 설정 | Microsoft Docs"
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
  - "TabStop"
  - "TabIndex"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "컨트롤[Windows Forms], 탭 순서 설정"
  - "탭 순서, Windows forms의 컨트롤"
  - "Windows Forms 컨트롤, 탭 순서 설정"
  - "Windows Forms, 탭 순서 설정"
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: Windows Forms에서 탭 순서 설정
탭 순서는 사용자가 Tab 키를 눌렀을 때 한 컨트롤에서 다른 컨트롤로 포커스가 이동되는 순서입니다.  각 폼은 고유한 탭 순서를 가지고 있습니다.  기본적으로 탭 순서는 컨트롤을 만든 순서와 같으며  탭 순서 번호는 0부터 시작합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 컨트롤의 탭 순서를 설정하려면  
  
1.  **보기** 메뉴에서 **탭 순서**를 클릭합니다.  
  
     이렇게 하면 폼에서 탭 순서 선택 모드가 활성화됩니다.  <xref:System.Windows.Forms.Control.TabIndex%2A> 속성을 나타내는 숫자가 각 컨트롤의 왼쪽 위 모퉁이에 표시됩니다.  
  
2.  컨트롤을 순서대로 클릭하여 원하는 탭 순서를 설정합니다.  
  
    > [!NOTE]
    >  컨트롤의 탭 순서 값은 0보다 크거나 같은 값으로 설정할 수 있습니다.  값이 중복될 경우에는 두 컨트롤의 z 순서가 확인되어 맨 위에 있는 컨트롤이 첫 번째 탭으로 구성됩니다.  z 순서는 z축\(깊이\)을 따라 폼의 컨트롤을 시각적으로 계층화한 것입니다.  z 순서에 따라 다른 컨트롤 앞에 배치할 컨트롤이 결정됩니다. z 순서에 대한 자세한 내용은 [Windows Forms에서 개체 계층화](../../../../docs/framework/winforms/controls/how-to-layer-objects-on-windows-forms.md)를 참조하십시오.  
  
3.  설정을 마쳤으면 **보기** 메뉴에서 **탭 순서**를 다시 클릭하여 탭 순서 모드를 종료합니다.  
  
    > [!NOTE]
    >  사용할 수 없는 컨트롤, 보이지 않는 컨트롤 및 포커스를 받을 수 없는 컨트롤은 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성을 사용할 수 없으며 탭 순서에 포함되지 않습니다.  Tab 키를 누를 때 이러한 컨트롤은 건너 뜁니다.  
  
 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성을 사용하여 속성 창에서 탭 순서를 설정할 수도 있습니다.  컨트롤의 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성은 탭 순서 상에 지정될 위치를 결정합니다.  기본적으로 처음 그린 컨트롤의 <xref:System.Windows.Forms.Control.TabIndex%2A> 값은 0으로 지정되고 두 번째 컨트롤의 <xref:System.Windows.Forms.Control.TabIndex%2A> 값은 1로 지정되며 나머지 컨트롤에도 같은 방식으로 지정됩니다.  
  
 또한 기본적으로 <xref:System.Windows.Forms.GroupBox> 컨트롤은 정수로 설정된 고유한 <xref:System.Windows.Forms.Control.TabIndex%2A> 값을 가집니다.  <xref:System.Windows.Forms.GroupBox> 컨트롤 자체는 런타임에 포커스를 받을 수 없습니다.  따라서 <xref:System.Windows.Forms.GroupBox> 컨트롤에 포함된 각 컨트롤은 .0부터 시작하는 고유한 10진수 <xref:System.Windows.Forms.Control.TabIndex%2A> 값을 가집니다.  기본적으로 <xref:System.Windows.Forms.GroupBox> 컨트롤의 <xref:System.Windows.Forms.Control.TabIndex%2A> 값이 증가하면 여기에 포함된 컨트롤의 값도 이에 따라 적절하게 증가합니다.  예를 들어, <xref:System.Windows.Forms.Control.TabIndex%2A> 값을 5에서 6으로 변경하면 해당 그룹의 첫 번째 컨트롤의 <xref:System.Windows.Forms.Control.TabIndex%2A> 값이 자동으로 6.0으로 변경됩니다.  
  
 마지막으로, 폼에 있는 특정 컨트롤의 탭 순서를 건너 뛸 수 있습니다.  대개 런타임에 Tab 키를 연속적으로 누르면 탭 순서대로 각 컨트롤이 선택됩니다.  <xref:System.Windows.Forms.Control.TabStop%2A> 속성을 False로 설정하면 폼의 탭 순서에서 특정 컨트롤을 건너 뛸 수 있습니다.  
  
#### 탭 순서에서 컨트롤을 제거하려면  
  
1.  속성 창에서 컨트롤의 <xref:System.Windows.Forms.Control.TabStop%2A> 속성을 `false`로 설정합니다.  
  
     <xref:System.Windows.Forms.Control.TabStop%2A> 속성이 `false`로 설정된 컨트롤은 Tab 키를 사용하여 전체 컨트롤 간을 이동할 때 이 컨트롤을 건너 뛰더라도 탭 순서에서 해당 위치가 계속 유지됩니다.  
  
    > [!NOTE]
    >  라디오 단추 그룹에는 런타임에 하나의 탭 정지 컨트롤만 포함됩니다.  선택된 단추, 즉 <xref:System.Windows.Forms.RadioButton.Checked%2A> 속성이 `true`로 설정된 단추의 <xref:System.Windows.Forms.Control.TabStop%2A> 속성은 자동으로 `true`로 설정되고 선택되지 않은 다른 단추의 <xref:System.Windows.Forms.Control.TabStop%2A> 속성은 `false`로 설정됩니다.  <xref:System.Windows.Forms.RadioButton> 컨트롤 그룹화에 대한 자세한 내용은 [Windows Forms RadioButton 컨트롤을 기능별로 그룹화](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)를 참조하십시오.  
  
## 참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)   
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [기능별 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)