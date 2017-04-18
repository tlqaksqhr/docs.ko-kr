---
title: "방법: Windows Forms RichTextBox 컨트롤에서 서식 특성의 변경 시기 결정 | Microsoft Docs"
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
  - "예제[Windows Forms], 텍스트 상자"
  - "RichTextBox 컨트롤[Windows Forms], 글꼴 변경 확인"
  - "SelBold 속성"
  - "SelChange 이벤트"
  - "텍스트 상자, 글꼴 변경 확인"
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Windows Forms RichTextBox 컨트롤에서 서식 특성의 변경 시기 결정
일반적으로 Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤은 글꼴 옵션이나 단락 스타일 같은 특성을 사용하여 텍스트의 서식을 지정하는 데 사용됩니다.  대부분의 워드 프로세서 응용 프로그램과 마찬가지로 사용자 응용 프로그램에서는 도구 모음을 표시하기 위해 텍스트 서식의 변경 내용을 추적해야 할 수도 있습니다.  
  
### 서식 특성의 변경 내용에 반응하려면  
  
1.  특성 값에 따라 적절한 동작을 수행하는 코드를 <xref:System.Windows.Forms.RichTextBox.SelectionChanged> 이벤트 처리기에 작성합니다.  다음 예제에서는 <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> 속성 값에 따라 도구 모음 단추의 모양을 변경합니다.  도구 모음 단추는 컨트롤에서 삽입 지점을 이동할 때만 업데이트됩니다.  
  
     아래 예제에서는 폼에 도구 모음 단추를 포함하는 <xref:System.Windows.Forms.ToolBar> 컨트롤과 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 있다고 가정합니다.  도구 모음 및 도구 모음 단추에 대한 자세한 내용은 [방법: ToolBar 컨트롤에 단추 추가](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)를 참조하십시오.  
  
    ```vb  
    ' The following code assumes the existence of a toolbar control  
    ' with at least one toolbar button.  
    Private Sub RichTextBox1_SelectionChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles RichTextBox1.SelectionChanged  
       If RichTextBox1.SelectionBullet = True Then  
          ' Bullet button on toolbar should appear pressed  
          ToolBarButton1.Pushed = True  
       Else  
           ' Bullet button on toolbar should appear unpressed  
           ToolBarButton1.Pushed = False  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private void richTextBox1_SelectionChanged(object sender,  
    System.EventArgs e)  
    {  
       if (richTextBox1.SelectionBullet == true)   
       {  
          // Bullet button on toolbar should appear pressed  
          toolBarButton1.Pushed = true;  
       }  
       else   
       {  
          // Bullet button on toolbar should appear unpressed  
          toolBarButton1.Pushed = false;  
       }  
    }  
  
    ```  
  
    ```cpp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private:  
       System::Void richTextBox1_SelectionChanged(  
          System::Object ^  sender, System::EventArgs ^  e)  
       {  
          if (richTextBox1->SelectionBullet == true)  
          {  
             // Bullet button on toolbar should appear pressed  
             toolBarButton1->Pushed = true;  
          }  
          else  
          {  
             // Bullet button on toolbar should appear unpressed  
             toolBarButton1->Pushed = false;  
          }  
       }  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.RichTextBox.SelectionChanged>   
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox 컨트롤](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)