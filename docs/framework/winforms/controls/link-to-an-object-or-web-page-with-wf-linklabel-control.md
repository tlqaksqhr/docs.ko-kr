---
title: "방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결"
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
- cpp
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Windows Forms, linking to objects
- Web page link control
- linking [Windows Forms], to other forms
- Windows Forms, linking to Web pages
- links [Windows Forms], to other forms
- LinkLabel control [Windows Forms], linking to object or Web page
- LinkLabel control [Windows Forms], examples
ms.assetid: 6c91c975-3cb7-4504-82f0-fc6255f8fb85
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3921c15de59deaa68b63d7dbfbfeb18c776d31f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a>방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결
Windows Forms <xref:System.Windows.Forms.LinkLabel> 컨트롤 폼에서 웹 스타일 링크를 만들 수 있습니다. 링크를 클릭할 때 링크를 방문한 나타내는 색을 변경할 수 있습니다. 색 변경에 대 한 자세한 내용은 참조 하십시오. [하는 방법: Windows Forms LinkLabel 컨트롤의 모양을 변경](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)합니다.  
  
## <a name="linking-to-another-form"></a>다른 폼에 링크  
  
#### <a name="to-link-to-another-form-with-a-linklabel-control"></a>LinkLabel 컨트롤에 다른 폼에 연결 하려면  
  
1.  설정의 <xref:System.Windows.Forms.LinkLabel.Text%2A> 속성을 적절 한 캡션입니다.  
  
2.  설정의 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 어느 부분이 캡션 링크로 표시 됩니다. 표시 되는 링크 레이블 모양 관련 속성에 따라 달라 집니다. <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 값으로 표시 됩니다는 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 두 숫자, 시작 문자 위치와 문자 수가 들어 있는 개체입니다. <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 또는 다음과 유사한 방식으로 코드를 속성 창에서 속성을 설정할 수 있습니다.  
  
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
  
3.  에 <xref:System.Windows.Forms.LinkLabel.LinkClicked> 이벤트 처리기 호출의 <xref:System.Windows.Forms.Form.Show%2A> 다른 폼에서 프로젝트를 열고 설정 하는 메서드는 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성을 `true`합니다.  
  
    > [!NOTE]
    >  인스턴스는 <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> 클래스에 대 한 참조를 전달는 <xref:System.Windows.Forms.LinkLabel> 캐스팅할 필요가 없습니다 이므로 클릭 된 컨트롤의 `sender` 개체입니다.  
  
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
  
## <a name="linking-to-a-web-page"></a>웹 페이지에 연결  
 <xref:System.Windows.Forms.LinkLabel> 컨트롤 기본 브라우저와 웹 페이지를 표시 하려면 사용할 수도 있습니다.  
  
#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a>LinkLabel 컨트롤을 Internet Explorer와 웹 페이지 링크를 시작 하려면  
  
1.  설정의 <xref:System.Windows.Forms.LinkLabel.Text%2A> 속성을 적절 한 캡션입니다.  
  
2.  설정의 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 어느 부분이 캡션 링크로 표시 됩니다.  
  
3.  <xref:System.Windows.Forms.LinkLabel.LinkClicked> 예외 처리 블록을 가운데 이벤트 처리기 호출을 설정 하는 두 번째 절차는 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성을 `true` 사용 하 여는 <xref:System.Diagnostics.Process.Start%2A> 메서드를 URL로 기본 브라우저를 시작 합니다. 사용 하는 <xref:System.Diagnostics.Process.Start%2A> 에 대 한 참조를 추가 해야 하는 메서드는 <xref:System.Diagnostics?displayProperty=nameWithType> 네임 스페이스입니다.  
  
    > [!IMPORTANT]
    >  아래 코드는 부분 신뢰 환경에서 실행 된 경우 (같은 공유 드라이브에 있음) 때 JIT 컴파일러가 실패는 `VisitLink` 메서드를 호출 합니다. `System.Diagnostics.Process.Start` 문을 실행 하면 실패 하는 링크 요청 합니다. 예외를 catch 하 여 때는 `VisitLink` 메서드가 호출 되 면 아래 코드에서 JIT 컴파일러에 오류가 발생 하면 오류는 처리 되도록 적절 하 게 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>  
 [LinkLabel 컨트롤 개요](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)  
 [방법: Windows Forms LinkLabel 컨트롤의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)  
 [LinkLabel 컨트롤](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
