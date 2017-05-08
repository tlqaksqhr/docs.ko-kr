---
title: "방법: Windows Forms NumericUpDown 컨트롤을 사용하여 숫자 값 설정 및 반환 | Microsoft Docs"
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
  - "숫자 값, Windows Forms"
  - "NumericUpDown 컨트롤[Windows Forms], 값 설정 및 반환"
  - "Windows Forms 컨트롤, NumericUpDown"
  - "Windows Forms, 숫자 값"
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Windows Forms NumericUpDown 컨트롤을 사용하여 숫자 값 설정 및 반환
Windows Forms <xref:System.Windows.Forms.NumericUpDown> 컨트롤의 숫자 값은 이 컨트롤의 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성에 의해 결정됩니다.  다른 속성과 마찬가지로 컨트롤 값에 대한 조건부 테스트를 작성할 수 있습니다.  <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성이 설정되면 이 속성에 대해 작업을 수행하는 코드를 작성하여 직접 값을 조정하거나 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> 및 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> 메서드를 호출할 수 있습니다.  
  
### 숫자 값을 설정하려면  
  
1.  코드 또는 속성 창에서 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성에 값을 할당합니다.  
  
    ```vb  
    NumericUpDown1.Value = 55  
  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     또는  
  
2.  <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> 또는 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> 메서드를 호출하여 <xref:System.Windows.Forms.NumericUpDown.Increment%2A> 속성에 지정된 값만큼 증가시키거나 감소시킵니다.  
  
    ```vb  
    NumericUpDown1.UpButton()  
  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### 숫자 값을 반환하려면  
  
-   코드를 작성하여 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성에 액세스합니다.  
  
    ```vb  
    If NumericUpDown1.Value >= 65 Then  
       MessageBox.Show("Age is: " & NumericUpDown1.Value.ToString)  
    Else  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.")  
    End If  
  
    ```  
  
    ```csharp  
    if(numericUpDown1.Value >= 65)  
    {  
       MessageBox.Show("Age is: " + numericUpDown1.Value.ToString());  
    }  
    else  
    {  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.");  
    }  
  
    ```  
  
    ```cpp  
    if(numericUpDown1->Value >= 65)  
    {  
       MessageBox::Show(String::Concat("Age is: ",  
          numericUpDown1->Value.ToString()));  
    }  
    else  
    {  
       MessageBox::Show  
          ("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.NumericUpDown>   
 <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=fullName>   
 [NumericUpDown 컨트롤](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)   
 [NumericUpDown 컨트롤 개요](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)