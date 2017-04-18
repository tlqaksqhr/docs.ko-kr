---
title: "방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정 | Microsoft Docs"
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
  - "Button 컨트롤[Windows Forms], 단추 텍스트"
  - "Button 컨트롤[Windows Forms], 텍스트 표시"
  - "단추, 텍스트"
  - "캡션, 설정"
  - "캡션, Windows Forms 컨트롤"
  - "컨트롤[Windows Forms], 캡션"
  - "예제[Windows Forms], 컨트롤"
  - "폼, 캡션"
  - "레이블, CommandButton 컨트롤에 추가"
  - "StdFont 개체 및 CommandButton 캡션"
  - "텍스트"
  - "Text 속성, Windows Forms 컨트롤"
  - "텍스트, Windows Forms 컨트롤"
  - "Windows Forms, 캡션"
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정
Windows Forms 컨트롤은 일반적으로 컨트롤의 기본 기능과 관련된 일부 텍스트를 표시합니다.  예를 들어 <xref:System.Windows.Forms.Button> 컨트롤은 일반적으로 단추를 클릭할 때 수행되는 동작을 나타내는 캡션을 표시합니다.  모든 컨트롤에 대해 <xref:System.Windows.Forms.Control.Text%2A> 속성을 사용하여 텍스트를 설정하거나 반환할 수 있습니다.  <xref:System.Windows.Forms.Control.Font%2A> 속성을 사용하여 글꼴을 변경할 수 있습니다.  디자이너를 사용하여 텍스트를 설정할 수도 있습니다.  [방법: 디자이너를 사용하여 Windows Forms 컨트롤에 대한 액세스 키 만들기](http://msdn.microsoft.com/library/ms233673\(v=vs.110\)), [방법: 디자이너를 사용하여 Windows Forms 컨트롤에 표시되는 텍스트 설정](http://msdn.microsoft.com/library/ms233665\(v=vs.110\)), [방법: 디자이너를 사용하여 Windows Forms 컨트롤에 표시되는 이미지 설정](http://msdn.microsoft.com/library/ms233656\(v=vs.110\))을 참조하세요.  
  
### 프로그래밍 방식으로 컨트롤에 표시되는 텍스트를 설정하려면  
  
1.  <xref:System.Windows.Forms.Control.Text%2A> 속성을 문자열로 설정합니다.  
  
     밑줄이 그어진 액세스 키를 만들려면 액세스 키로 사용할 문자 앞에 앰퍼샌드\(&\)를 포함합니다.  
  
2.  <xref:System.Windows.Forms.Control.Font%2A> 속성을 <xref:System.Drawing.Font> 형식의 개체로 설정합니다.  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp#  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  이스케이프 문자를 사용하여 일반적으로 다르게 해석하는 메뉴 항목과 같은 사용자 인터페이스 요소에 특수 문자를 표시할 수 있습니다.  예를 들어 다음 코드 줄에서는 메뉴 항목의 텍스트를 "& Now For Something Completely Different"로 설정합니다.  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp#  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.Control.Text%2A?displayProperty=fullName>   
 [방법: Windows Forms 컨트롤에 대한 선택키 만들기](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)   
 [방법: Windows Forms 단추 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)