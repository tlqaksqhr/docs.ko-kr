---
title: "방법: 문자열에 인용 부호 넣기(Windows Forms) | Microsoft Docs"
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
  - "따옴표"
  - "따옴표, 텍스트 상자의 문자열에 추가"
  - "TextBox 컨트롤[Windows Forms], 따옴표 표시"
ms.assetid: 68bdc3f3-4177-4eab-99cd-cac17a82b515
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 문자열에 인용 부호 넣기(Windows Forms)
텍스트 문자열에 따옴표\(" "\)를 넣어야 하는 경우가 있을 수 있습니다.  예를 들면 다음과 같습니다.  
  
 She said, "You deserve a treat\!"  
  
 또는 <xref:Microsoft.VisualBasic.ControlChars.Quote> 필드를 상수로 사용할 수도 있습니다.  
  
### 코드의 문자열에 따옴표를 넣으려면  
  
1.  [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]에서는 한 행에 두 개의 따옴표가 있으면 포함 따옴표로 해석됩니다.  [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]에서는 이스케이프 시퀀스 \\"가 포함 인용 부호로 해석됩니다.  예를 들어, 앞에서 언급한 문자열을 만들려면 다음 코드를 사용합니다.  
  
    ```vb  
    Private Sub InsertQuote()  
       TextBox1.Text = "She said, ""You deserve a treat!"" "  
    End Sub  
  
    ```  
  
    ```csharp  
    private void InsertQuote(){  
       textBox1.Text = "She said, \"You deserve a treat!\" ";  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void InsertQuote()  
       {  
          textBox1->Text = "She said, \"You deserve a treat!\" ";  
       }  
    ```  
  
     또는  
  
2.  따옴표를 ASCII 또는 유니코드 문자로 삽입합니다.  다음과 같이 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]에서는 ASCII 문자\(34\)를 사용하고  [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]에서는 유니코드 문자\(\\u0022\)를 사용합니다.  
  
    ```vb  
    Private Sub InsertAscii()  
       TextBox1.Text = "She said, " & Chr(34) & "You deserve a treat!" & Chr(34)  
    End Sub  
  
    ```  
  
    ```csharp  
    private void InsertAscii(){  
       textBox1.Text = "She said, " + '\u0022' + "You deserve a treat!" + '\u0022';  
    }  
    ```  
  
    > [!NOTE]
    >  이 예제에서는 기본 문자 집합에 있는 문자를 지정하는 유니버설 문자 이름을 사용할 수 없기 때문에 \\u0022를 사용할 수 없습니다.  그렇지 않으면 C3851이 발생합니다.  자세한 내용은 [컴파일러 오류 C3851](../Topic/Compiler%20Error%20C3851.md)을 참조하십시오.  
  
     또는  
  
3.  문자에 대한 상수를 정의한 다음 필요한 위치에 사용할 수도 있습니다.  
  
    ```vb  
    Const quote As String = """"  
    TextBox1.Text = "She said, " & quote & "You deserve a treat!" & quote  
  
    ```  
  
    ```csharp  
    const string quote = "\"";  
    textBox1.Text = "She said, " + quote +  "You deserve a treat!"+ quote ;  
  
    ```  
  
    ```cpp  
    const String^ quote = "\"";  
    textBox1->Text = String::Concat("She said, ",  
       const_cast<String^>(quote), "You deserve a treat!",  
       const_cast<String^>(quote));  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.TextBox>   
 <xref:Microsoft.VisualBasic.ControlChars.Quote>   
 [TextBox 컨트롤 개요](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [방법: 읽기 전용 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [방법: Windows Forms TextBox 컨트롤에서 텍스트 선택](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [방법: Windows Forms TextBox 컨트롤에 여러 줄 표시](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox 컨트롤](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)