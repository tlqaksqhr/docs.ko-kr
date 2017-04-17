---
title: "방법: Windows Forms ColorDialog 구성 요소의 모양 변경 | Microsoft Docs"
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
  - "색 대화 상자, 모양 구성"
  - "ColorDialog 구성 요소, 예제"
  - "ColorDialog 구성 요소, 모양 형식 지정"
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Forms ColorDialog 구성 요소의 모양 변경
다양한 속성을 사용하여 Windows Forms <xref:System.Windows.Forms.ColorDialog> 구성 요소의 모양을 구성할 수 있습니다.  이 대화 상자는 기본색을 표시하는 영역과 사용자 지정 색을 정의할 수 있는 영역으로 구성되어 있습니다.  
  
 대부분의 속성은 사용자가 대화 상자에서 선택할 수 있는 색을 제한합니다.  <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> 속성이 `true`로 설정되면 사용자가 사용자 지정 색을 정의할 수 있습니다.  사용자 지정 색을 정의할 수 있도록 대화 상자가 확장된 경우에는 <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> 속성이 `true`이고 그렇지 않은 경우에는 사용자가 "사용자 지정 색 만들기" 단추를 클릭해야 합니다.  <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> 속성이 `true`로 설정되면 기본 색 집합에서 사용 가능한 모든 색이 대화 상자에 표시됩니다.  또한 <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> 속성이 `true`로 설정되면 사용자는 디더링된 색을 선택할 수 없고 단색만 선택할 수 있습니다.  
  
 <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> 속성이 `true`로 설정되면 대화 상자에 도움말 단추가 나타납니다.  사용자가 도움말 단추를 클릭하면 <xref:System.Windows.Forms.ColorDialog> 구성 요소의 <xref:System.Windows.Forms.CommonDialog.HelpRequest> 이벤트가 발생합니다.  
  
### 색 대화 상자의 모양을 구성하려면  
  
1.  <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> 및 <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> 속성을 원하는 값으로 설정합니다.  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.ColorDialog>   
 [ColorDialog 구성 요소](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)   
 [ColorDialog 구성 요소 개요](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md)