---
title: "방법: 기존 Windows Forms 컨트롤에서 상속 | Microsoft Docs"
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
  - "사용자 지정 컨트롤[Windows Forms], 상속"
  - "상속, Windows Forms 사용자 지정 컨트롤"
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 방법: 기존 Windows Forms 컨트롤에서 상속
기존 컨트롤의 기능을 확장하려면 상속을 통해 기존 컨트롤에서 파생된 컨트롤을 만들면 됩니다.  기존 컨트롤에서 상속하면 해당 컨트롤의 모든 기능과 시각적 속성을 상속할 수 있습니다.  예를 들어, <xref:System.Windows.Forms.Button>에서 상속한 컨트롤을 만들 경우 새 컨트롤은 표준 <xref:System.Windows.Forms.Button> 컨트롤과 완전히 같은 모양 및 동작을 나타냅니다.  그런 다음 사용자 지정 메서드와 속성의 구현을 통해 새 컨트롤의 기능을 확장하거나 수정할 수 있습니다.  일부 컨트롤의 경우 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의하여 상속된 컨트롤의 시각적 모양을 변경할 수도 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 상속된 컨트롤을 만들려면  
  
1.  **Windows Forms 응용 프로그램** 프로젝트를 만듭니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  
  
     **새 항목 추가** 대화 상자가 나타납니다.  
  
3.  **새 항목 추가** 대화 상자에서 **사용자 지정 컨트롤**을 두 번 클릭합니다.  
  
     새 사용자 지정 컨트롤이 프로젝트에 추가됩니다.  
  
4.  Visual Basic을 사용하는 경우 **솔루션 탐색기**의 맨 위에서 **모든 파일 표시**를 클릭합니다.  CustomControl1.vb를 확장한 다음 코드 편집기에서 CustomControl1.Designer.vb를 엽니다.  
  
5.  C\#을 사용하는 경우에는 코드 편집기에서 CustomControl1.cs를 엽니다.  
  
6.  <xref:System.Windows.Forms.Control>에서 상속되는 클래스 선언을 찾습니다.  
  
7.  기본 클래스를 상속할 컨트롤로 변경합니다.  
  
     예를 들어 <xref:System.Windows.Forms.Button>에서 상속하려는 경우 클래스 선언을 다음과 같이 변경합니다.  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  Visual Basic을 사용하는 경우 CustomControl1.Designer.vb를 저장하고 닫습니다.  코드 편집기에서 CustomControl1.vb를 엽니다.  
  
9. 컨트롤이 구체화할 모든 사용자 지정 메서드나 속성을 구현합니다.  
  
10. 컨트롤의 그래픽 모양을 수정하려면 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의합니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.Control.OnPaint%2A>를 재정의해도 모든 컨트롤의 모양이 수정되지는 않습니다.  Windows에 의해 모든 그리기가 수행되는 컨트롤\(예: <xref:System.Windows.Forms.TextBox>\)은 자체의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 호출하지 않으므로 사용자 지정 코드를 사용하지 않습니다.  <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드의 사용 가능 여부를 확인하려면 수정하려는 특정 컨트롤의 도움말 설명서를 참조하십시오.  모든 Windows Form 컨트롤 목록은 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)을 참조하십시오.  컨트롤의 메서드 목록에 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드가 없는 경우에는 이 메서드를 재정의하여 모양을 변경할 수 없습니다.  사용자 지정 그리기에 대한 자세한 내용은 [사용자 지정 컨트롤 그리기 및 렌더링](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)을 참조하십시오.  
  
    ```vb  
    Protected Overrides Sub OnPaint(ByVal e As _  
       System.Windows.Forms.PaintEventArgs)  
       MyBase.OnPaint(e)  
       ' Insert code to do custom painting.   
       ' If you want to completely change the appearance of your control,  
       ' do not call MyBase.OnPaint(e).  
    End Sub  
  
    ```  
  
    ```csharp  
    protected override void OnPaint(PaintEventArgs pe)  
    {  
       base.OnPaint(pe);  
       // Insert code to do custom painting.  
       // If you want to completely change the appearance of your control,  
       // do not call base.OnPaint(pe).  
    }  
    ```  
  
11. 컨트롤을 저장한 다음 테스트합니다.  
  
## 참고 항목  
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)   
 [방법: Control 클래스에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)   
 [방법: UserControl 클래스에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)   
 [방법: Windows Forms 컨트롤 제작](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)   
 [Troubleshooting Inherited Event Handlers in Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)   
 [연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)   
 [연습: Visual C\#을 사용하여 Windows Forms 컨트롤에서 상속](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)