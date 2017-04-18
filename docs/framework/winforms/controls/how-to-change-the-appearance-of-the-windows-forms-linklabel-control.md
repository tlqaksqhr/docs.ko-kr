---
title: "방법: Windows Forms LinkLabel 컨트롤의 모양 변경 | Microsoft Docs"
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
  - "예제[Windows Forms], LinkLabel 컨트롤"
  - "LinkLabel 컨트롤[Windows Forms], 링크 모양 변경"
  - "LinkLabel 컨트롤[Windows Forms], 예제"
  - "LinkLabel 속성"
  - "링크, 모양 변경"
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Windows Forms LinkLabel 컨트롤의 모양 변경
<xref:System.Windows.Forms.LinkLabel> 컨트롤에 표시되는 텍스트를 목적에 맞게 변경할 수 있습니다.  예를 들어, 텍스트가 밑줄이 그어진 상태의 특정 색으로 표시되도록 설정하여 클릭할 수 있음을 나타내는 경우가 일반적입니다.  사용자가 이 텍스트를 클릭한 후에는 다른 색으로 변경됩니다.  이 동작을 제어하려면 5개의 서로 다른 속성 <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 및 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성을 설정합니다.  
  
### LinkLabel 컨트롤의 모양을 변경하려면  
  
1.  <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> 및 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 속성을 원하는 색으로 설정합니다.  
  
     이 작업은 프로그래밍 방식으로 수행하거나 디자인 타임에 **속성** 창에서 수행할 수 있습니다.  
  
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
  
2.  <xref:System.Windows.Forms.LinkLabel.Text%2A> 속성을 적절한 캡션으로 설정합니다.  
  
     이 작업은 프로그래밍 방식으로 수행하거나 디자인 타임에 **속성** 창에서 수행할 수 있습니다.  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3.  캡션에서 링크로 나타낼 부분을 결정하는 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 설정합니다.  
  
     <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 값은 문자 시작 위치와 문자의 개수를 나타내는 2개의 숫자로 구성된 <xref:System.Windows.Forms.LinkArea>로 표시됩니다.  이 작업은 프로그래밍 방식으로 수행하거나 디자인 타임에 **속성** 창에서 수행할 수 있습니다.  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4.  <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> 속성을 <xref:System.Windows.Forms.LinkBehavior>, <xref:System.Windows.Forms.LinkBehavior> 또는 <xref:System.Windows.Forms.LinkBehavior>으로 설정합니다.  
  
     <xref:System.Windows.Forms.LinkBehavior>으로 속성을 설정한 경우 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>에 의해 지정된 캡션 부분은 이 위치로 포인터를 가져갈 때만 밑줄이 표시됩니다.  
  
5.  <xref:System.Windows.Forms.LinkLabel.LinkClicked> 이벤트 처리기에서 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성을 `true`로 설정합니다.  
  
     그러면 링크를 방문했을 때 링크의 모양이 변경됩니다\(일반적으로 색이 변경됨\).  텍스트는 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 속성에 지정된 색으로 변경됩니다.  
  
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
  
## 참고 항목  
 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>   
 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>   
 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>   
 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>   
 [LinkLabel 컨트롤 개요](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)   
 [방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)   
 [LinkLabel 컨트롤](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)