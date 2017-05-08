---
title: "방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정 | Microsoft Docs"
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
  - "예제[Windows Forms], 도구 설명"
  - "도구 설명[Windows Forms], 컨트롤"
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정
코드 또는 Windows Forms 디자이너에서 <xref:System.Windows.Forms.ToolTip> 문자열을 설정할 수 있습니다.  <xref:System.Windows.Forms.ToolTip> 구성 요소에 대한 자세한 내용은 [ToolTip 구성 요소 개요](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 프로그래밍 방식으로 도구 설명을 설정하려면  
  
1.  도구 설명을 표시할 컨트롤을 추가합니다.  
  
2.  <xref:System.Windows.Forms.ToolTip> 구성 요소의 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 메서드를 사용합니다.  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### 디자이너에서 도구 설명을 설정하려면  
  
1.  폼에 <xref:System.Windows.Forms.ToolTip> 구성 요소를 추가합니다.  
  
2.  도구 설명을 표시할 컨트롤을 선택하거나 해당 컨트롤을 폼에 추가합니다.  
  
3.  **속성** 창에서 **ToolTip on ToolTip1** 값에 해당 텍스트 문자열을 설정합니다.  
  
## 참고 항목  
 [ToolTip 구성 요소 개요](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)   
 [방법: Windows Forms ToolTip 구성 요소의 지연 변경](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)   
 [ToolTip 구성 요소](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)