---
title: '방법: Windows Forms LinkLabel 컨트롤의 모양 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
ms.openlocfilehash: e1bb0ecba6fd8ddf66c6debb90ef4dd94641a97e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531488"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a>방법: Windows Forms LinkLabel 컨트롤의 모양 변경
표시 되는 텍스트를 변경할 수는 <xref:System.Windows.Forms.LinkLabel> 다양 한 목적에 맞게 컨트롤을 합니다. 예를 들어 것이 일반적 텍스트에 밑줄 특정 색에 표시할 텍스트를 설정 하 여 클릭 수 있는 사용자에 게 나타냅니다. 텍스트를 클릭 한 후 다른 색으로 변경 합니다. 이러한 동작을 제어 하려면 5 개의 서로 다른 속성을 설정할 수 있습니다:는 <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, 및 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성입니다.  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a>LinkLabel 컨트롤의 모양을 변경 하려면  
  
1.  설정의 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> 및 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 속성을 원하는 색입니다.  
  
     이렇게 중 하나에서 프로그래밍 방식으로 또는 디자인 타임에는 **속성** 창.  
  
    ```vb  
    ' You can set the color using decimal values for red, green, and blue  
    LinkLabel1.LinkColor = Color.FromArgb(0, 0, 255)  
    ' Or you can set the color using defined constants  
    LinkLabel1.VisitedLinkColor = Color.Purple  
    ```  
  
    ```csharp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1.LinkColor = Color.FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1.VisitedLinkColor = Color.Purple;  
    ```  
  
    ```cpp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1->LinkColor = Color::FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1->VisitedLinkColor = Color::Purple;  
    ```  
  
2.  설정의 <xref:System.Windows.Forms.LinkLabel.Text%2A> 속성을 적절 한 캡션입니다.  
  
     이렇게 중 하나에서 프로그래밍 방식으로 또는 디자인 타임에는 **속성** 창.  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3.  설정의 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 어느 부분이 캡션 링크로 표시 됩니다.  
  
     <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 표시는 <xref:System.Windows.Forms.LinkArea> 두 개의 번호, 시작 문자 위치 및 문자 수를 포함 합니다. 이렇게 중 하나에서 프로그래밍 방식으로 또는 디자인 타임에는 **속성** 창.  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4.  설정의 <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> 속성을 <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, 또는 <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>합니다.  
  
     로 설정 되어 있으면 <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, 부분에 의해 결정 캡션 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 포인터 위에 있을 때만 밑줄이 됩니다.  
  
5.  에 <xref:System.Windows.Forms.LinkLabel.LinkClicked> 설정 하는 이벤트 처리기는 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성을 `true`합니다.  
  
     링크를 방문 했을 때 어떤 방식으로든에서 모양을 일반적으로 색으로 변경 하려면 일반적으로 되었기입니다. 텍스트로 지정 된 색으로 변경 됩니다는 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 속성입니다.  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked (ByVal sender As Object, _  
       ByVal e As EventArgs) Handles LinkLabel1.LinkClicked  
       ' Change the color of the link text  
       ' by setting LinkVisited to True.  
       LinkLabel1.LinkVisited = True  
       ' Then do whatever other action is appropriate  
    End Sub  
    ```  
  
    ```csharp  
    protected void LinkLabel1_LinkClicked(object sender, System.EventArgs e)  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to True.  
       linkLabel1.LinkVisited = true;  
       // Then do whatever other action is appropriate  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to True.  
          linkLabel1->LinkVisited = true;  
          // Then do whatever other action is appropriate  
       }  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>  
 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>  
 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>  
 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>  
 [LinkLabel 컨트롤 개요](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)  
 [방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)  
 [LinkLabel 컨트롤](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
