---
title: "방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결 | Microsoft Docs"
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
  - "링크, 다른 폼에 적용"
  - "LinkLabel 컨트롤[Windows Forms], 예제"
  - "LinkLabel 컨트롤[Windows Forms], 개체 또는 웹 페이지에 연결"
  - "링크, 다른 폼에 적용"
  - "웹 페이지 링크 컨트롤"
  - "Windows Forms, 개체에 연결"
  - "Windows Forms, 웹 페이지에 연결"
ms.assetid: 6c91c975-3cb7-4504-82f0-fc6255f8fb85
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결
Windows Forms <xref:System.Windows.Forms.LinkLabel> 컨트롤을 사용하면 폼에서 웹 스타일 링크를 만들 수 있습니다.  링크를 클릭하면 링크 색이 바뀌도록 설정하여 해당 링크를 방문했음을 나타낼 수 있습니다.  색 변경에 대한 자세한 내용은 [방법: Windows Forms LinkLabel 컨트롤의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)을 참조하십시오.  
  
## 다른 폼에 링크  
  
#### LinkLabel 컨트롤을 사용하여 다른 폼에 링크하려면  
  
1.  <xref:System.Windows.Forms.LinkLabel.Text%2A> 속성을 적절한 캡션으로 설정합니다.  
  
2.  캡션에서 링크로 나타낼 부분을 결정하는 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 설정합니다.  표시되는 형태는 링크 레이블의 모양과 관련된 속성에 따라 달라집니다.  <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 값은 문자 시작 위치와 문자 수를 나타내는 두 개의 숫자를 포함하는 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 개체로 표시됩니다.  속성 창이나 다음과 같은 방법으로 코드에서 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 설정할 수 있습니다.  
  
    ```vb  
    ' In this code example, the link area has been set to begin  
    ' at the first character and extend for eight characters.  
    ' You may need to modify this based on the text entered in Step 1.  
    LinkLabel1.LinkArea = New LinkArea(0, 8)  
  
    ```  
  
    ```csharp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1.LinkArea = new LinkArea(0,8);  
  
    ```  
  
    ```cpp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1->LinkArea = LinkArea(0,8);  
    ```  
  
3.  <xref:System.Windows.Forms.LinkLabel.LinkClicked> 이벤트 처리기에서 <xref:System.Windows.Forms.Form.Show%2A> 메서드를 호출하여 프로젝트에서 다른 폼을 열고 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성을 `true`로 설정합니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> 클래스의 인스턴스는 클릭된 <xref:System.Windows.Forms.LinkLabel> 컨트롤에 대한 참조를 포함하기 때문에`sender` 개체를 캐스팅할 필요가 없습니다.  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked(ByVal Sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       ' Show another form.  
       Dim f2 As New Form()  
       f2.Show  
       LinkLabel1.LinkVisited = True  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void linkLabel1_LinkClicked(object sender, System. Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       // Show another form.  
       Form f2 = new Form();  
       f2.Show();  
       linkLabel1.LinkVisited = true;  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Show another form.  
          Form ^ f2 = new Form();  
          f2->Show();  
          linkLabel1->LinkVisited = true;  
       }  
    ```  
  
## 웹 페이지에 링크  
 <xref:System.Windows.Forms.LinkLabel> 컨트롤은 기본 브라우저로 웹 페이지를 표시하는 데 사용할 수도 있습니다.  
  
#### LinkLabel 컨트롤을 사용하여 Internet Explorer를 시작하고 웹 페이지에 링크하려면  
  
1.  <xref:System.Windows.Forms.LinkLabel.Text%2A> 속성을 적절한 캡션으로 설정합니다.  
  
2.  캡션에서 링크로 나타낼 부분을 결정하는 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 설정합니다.  
  
3.  <xref:System.Windows.Forms.LinkLabel.LinkClicked> 이벤트 처리기에 있는 예외 처리 블록의 가운데에서 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성을 `true`로 설정하는 두 번째 프로시저를 호출하고 <xref:System.Diagnostics.Process.Start%2A> 메서드를 사용하여 임의의 URL로 기본 브라우저를 시작합니다.  <xref:System.Diagnostics.Process.Start%2A> 메서드를 사용하려면 <xref:System.Diagnostics?displayProperty=fullName> 네임스페이스에 대한 참조를 추가해야 합니다.  
  
    > [!IMPORTANT]
    >  다음 코드를 공유 드라이브와 같은 부분 신뢰 환경에서 실행하면 `VisitLink` 메서드를 호출할 때 JIT 컴파일러가 실패합니다.  `System.Diagnostics.Process.Start` 문에서 링크 요청이 발생하고 이 요청은 실패합니다.  다음 코드처럼 `VisitLink` 메서드를 호출할 때 예외를 catch하면 JIT 컴파일러가 실패하는 경우 오류가 제대로 처리됩니다.  
  
    ```vb  
    Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       Try  
          VisitLink()  
       Catch ex As Exception  
          ' The error message  
          MessageBox.Show("Unable to open link that was clicked.")  
       End Try  
    End Sub  
  
    Sub VisitLink()  
       ' Change the color of the link text by setting LinkVisited   
       ' to True.  
       LinkLabel1.LinkVisited = True  
       ' Call the Process.Start method to open the default browser   
       ' with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com")  
    End Sub  
  
    ```  
  
    ```csharp  
    private void linkLabel1_LinkClicked(object sender, System.Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       try  
       {  
          VisitLink();  
       }  
       catch (Exception ex )  
       {  
          MessageBox.Show("Unable to open link that was clicked.");  
       }  
    }  
  
    private void VisitLink()  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to true.  
       linkLabel1.LinkVisited = true;  
       //Call the Process.Start method to open the default browser   
       //with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com");  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          try  
          {  
             VisitLink();  
          }  
          catch (Exception ^ ex)  
          {  
             MessageBox::Show("Unable to open link that was clicked.");  
          }  
       }  
    private:  
       void VisitLink()  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to true.  
          linkLabel1->LinkVisited = true;  
          // Call the Process.Start method to open the default browser   
          // with a URL:  
          System::Diagnostics::Process::Start("http://www.microsoft.com");  
       }  
    ```  
  
## 참고 항목  
 <xref:System.Diagnostics.Process.Start%2A?displayProperty=fullName>   
 [LinkLabel 컨트롤 개요](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)   
 [방법: Windows Forms LinkLabel 컨트롤의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)   
 [LinkLabel 컨트롤](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)