---
title: "방법: Windows Forms NumericUpDown 컨트롤의 형식 설정 | Microsoft Docs"
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
  - "NumericUpDown 컨트롤[Windows Forms], 값 형식 지정"
  - "up-down 컨트롤, 숫자 값 형식 지정"
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Forms NumericUpDown 컨트롤의 형식 설정
Windows Forms <xref:System.Windows.Forms.NumericUpDown> 컨트롤에 표시되는 값의 형식을 구성할 수 있습니다.  <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> 속성은 소수점 뒤에 나타나는 숫자의 개수를 결정하고 기본값은 0입니다.  <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> 속성은 10진수 3자리마다 구분 기호를 삽입할지 여부를 결정하고 기본값은 `false`입니다.  <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> 속성이 `true`로 설정될 경우 이 컨트롤은 10진수 형식 대신 16진수 형식으로 값을 표시할 수 있습니다. 기본값은 `false`입니다.  
  
### 숫자 값의 형식을 지정하려면  
  
-   <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> 속성을 정수로 설정하고 <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> 속성을 `true` 또는 `false`로 설정하여 10진수 값을 표시합니다.  
  
    ```vb  
    NumericUpDown1.DecimalPlaces = 2  
    NumericUpDown1.ThousandsSeparator = True  
  
    ```  
  
    ```csharp  
    numericUpDown1.DecimalPlaces = 2;  
    numericUpDown1.ThousandsSeparator = true;  
  
    ```  
  
    ```cpp  
    numericUpDown1->DecimalPlaces = 2;  
    numericUpDown1->ThousandsSeparator = true;  
    ```  
  
     또는  
  
-   <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> 속성을 `true`로 설정하여 16진수 값을 표시합니다.  
  
    ```vb  
    NumericUpDown1.Hexadecimal = True  
  
    ```  
  
    ```csharp  
    numericUpDown1.Hexadecimal = true;  
  
    ```  
  
    ```cpp  
    numericUpDown1->Hexadecimal = true;  
    ```  
  
    > [!NOTE]
    >  폼에서 값이 16진수로 표시되더라도 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성에 대해 수행되는 테스트는 10진수 값을 테스트합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.NumericUpDown>   
 [NumericUpDown 컨트롤](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)   
 [NumericUpDown 컨트롤 개요](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)