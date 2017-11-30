---
title: "방법: 기존 Windows Forms 컨트롤에서 상속"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6e6133576d65e95ac42a1680de152d84892e2c5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>방법: 기존 Windows Forms 컨트롤에서 상속
기존 컨트롤의 기능을 확장하려는 경우 상속을 통해 기존 컨트롤에서 파생된 컨트롤을 만들 수 있습니다. 기존 컨트롤에서 상속하는 경우 해당 컨트롤의 모든 기능 및 시각적 속성을 상속합니다. 상속 하는 컨트롤을 만들려는 경우 등 <xref:System.Windows.Forms.Button>, 새 컨트롤 모양 및 act 똑같이 표준 <xref:System.Windows.Forms.Button> 제어 합니다. 그런 다음 사용자 지정 메서드 및 속성의 구현을 통해 새 컨트롤의 기능을 확장하거나 수정할 수 있습니다. 일부 컨트롤에서 변경할 수 있습니다 또한 상속 된 컨트롤의 시각적 모양을 재정의 하 여 해당 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-create-an-inherited-control"></a>상속된 컨트롤을 만들려면  
  
1.  새 **Windows Forms 응용 프로그램** 프로젝트를 만듭니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  
  
     **새 항목 추가** 대화 상자가 나타납니다.  
  
3.  **새 항목 추가** 대화 상자에서 **사용자 지정 컨트롤**을 두 번 클릭합니다.  
  
     새 사용자 지정 컨트롤을 프로젝트에 추가합니다.  
  
4.  Visual Basic을 사용하면 **솔루션 탐색기**의 맨 위에서 **모든 파일 표시**를 클릭합니다. CustomControl1.vb를 확장한 다음 코드 편집기에서 CustomControl1.Designer.vb를 엽니다.  
  
5.  C#을 사용하는 경우 코드 편집기에서 CustomControl1.cs를 엽니다.  
  
6.  상속 하는 클래스 선언을 찾아 <xref:System.Windows.Forms.Control>합니다.  
  
7.  기본 클래스를 상속하려는 컨트롤로 변경합니다.  
  
     상속 하려는 경우 등 <xref:System.Windows.Forms.Button>, 다음과 같은 클래스 선언을 변경 합니다.  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  Visual Basic을 사용하는 경우 저장하고 CustomControl1.Designer.vb를 닫습니다. 코드 편집기에서 CustomControl1.vb를 엽니다.  
  
9. 컨트롤이 통합하는 사용자 지정 메서드 또는 속성을 구현합니다.  
  
10. 컨트롤의 그래픽 모양을 수정 하려는 경우 재정의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.  
  
    > [!NOTE]
    >  재정의 <xref:System.Windows.Forms.Control.OnPaint%2A> 모든 컨트롤 모양을 수정할 수를 허용 하지 것입니다. 모든 그리기가 Windows가 수행 되는 컨트롤 (예를 들어 <xref:System.Windows.Forms.TextBox>) 절대 호출 하지 해당 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드, 따라서 사용 하지 것입니다는 사용자 지정 코드 및 합니다. 있는지 수정할 특정 컨트롤에 대 한 도움말을 참고는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드는 사용할 수 있습니다. 모든 Windows Form 컨트롤의 목록은 [Windows Forms에서 사용할 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)을 참조하세요. 컨트롤에 없는 경우 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드가 나열을 변경할 수 없습니다 모양을이 메서드를 재정의 합니다. 사용자 지정 그리기에 대한 자세한 내용은 [사용자 지정 컨트롤 그리기 및 렌더링](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)을 참조하세요.  
  
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
  
11. 컨트롤을 저장하고 테스트합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [방법: Control 클래스에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [방법: UserControl 클래스에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [방법: Windows Forms 컨트롤 작성](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [연습: Visual C#을 사용하여 Windows Forms 컨트롤에서 상속](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
