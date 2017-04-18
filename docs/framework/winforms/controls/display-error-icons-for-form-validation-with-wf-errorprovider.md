---
title: "방법: Windows Forms ErrorProvider 구성 요소를 사용하여 폼 유효성에 대한 오류 아이콘 표시 | Microsoft Docs"
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
  - "오류 아이콘"
  - "오류 메시지, 아이콘 표시"
  - "ErrorProvider 구성 요소[Windows Forms], 오류 아이콘 표시"
  - "오류[Windows Forms], 사용자에게 표시"
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: Windows Forms ErrorProvider 구성 요소를 사용하여 폼 유효성에 대한 오류 아이콘 표시
Windows Forms <xref:System.Windows.Forms.ErrorProvider> 구성 요소를 사용하면 사용자가 잘못된 데이터를 입력할 때 오류 아이콘을 표시할 수 있습니다.  폼에 최소 두 개의 컨트롤이 있어야 이러한 컨트롤 사이를 이동하여 유효성 검사 코드를 호출할 수 있습니다.  
  
### 컨트롤 값이 잘못되었을 때 오류 아이콘을 표시하려면  
  
1.  Windows Form에 텍스트 상자와 같은 컨트롤을 두 개 추가합니다.  
  
2.  폼에 <xref:System.Windows.Forms.ErrorProvider> 구성 요소를 추가합니다.  
  
3.  첫 번째 컨트롤을 선택하고 해당 <xref:System.Windows.Forms.Control.Validating> 이벤트 처리기에 코드를 추가합니다.  코드가 올바르게 실행되려면 프로시저가 이벤트에 연결되어 있어야 합니다.  자세한 내용은 [방법: 런타임에 Windows Forms의 이벤트 처리기 만들기](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)를 참조하십시오.  
  
     다음 코드는 사용자가 입력한 데이터의 유효성을 테스트합니다. 데이터가 잘못된 경우에는 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 메서드가 호출됩니다.  <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 메서드의 첫 번째 인수는 옆에 아이콘을 표시할 컨트롤을 지정합니다.  두 번째 인수는 표시할 오류 텍스트입니다.  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 폼의 생성자에 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4.  프로젝트를 실행합니다.  첫 번째 컨트롤에 잘못된 데이터\(여기서는 숫자가 아닌 데이터\)를 입력한 다음 두 번째 컨트롤로 이동합니다.  오류 아이콘이 표시되면 마우스 포인터로 가리켜서 오류 텍스트를 봅니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ErrorProvider.SetError%2A>   
 [ErrorProvider 구성 요소 개요](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)   
 [방법: Windows Forms ErrorProvider 구성 요소를 사용하여 데이터 집합에 있는 오류 보기](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)