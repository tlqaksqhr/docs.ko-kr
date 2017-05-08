---
title: "Windows Form의 컨트롤에 내게 필요한 옵션 정보 제공 | Microsoft Docs"
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
  - "Windows Forms 컨트롤, 접근성"
  - "컨트롤[Windows Forms], 접근성"
  - "접근성, Windows Forms 컨트롤"
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Windows Form의 컨트롤에 내게 필요한 옵션 정보 제공
접근성 보조 기능은 장애가 있는 사용자가 컴퓨터를 보다 효율적으로 사용하도록 돕는 특수 프로그램 및 장치입니다. 시력 장애가 있는 사용자를 위한 화면 판독기와 마우스나 키보드를 사용하지 않고 구두 명령을 제공하는 사용자를 위한 음성 입력 유틸리티를 예로 들 수 있습니다. 이러한 접근성 보조 기능은 Windows Forms 컨트롤에서 노출하는 접근성 속성을 조작합니다. 이러한 속성은 다음과 같습니다.  
  
-   **AccessibilityObject**  
  
-   **AccessibleDefaultActionDescription**  
  
-   **AccessibleDescription**  
  
-   **AccessibleName**  
  
-   **AccessibleRole**  
  
## AccessibilityObject 속성  
 이 읽기 전용 속성은 [AccessibleObject Class](frlrfSystemWindowsFormsAccessibleObjectClassTopic) 인스턴스를 포함합니다.**AccessibleObject**는 컨트롤의 설명, 화면 위치, 탐색 기능 및 값 정보를 제공하는 <xref:Accessibility.IAccessible> 인터페이스를 구현합니다. 디자이너에서는 컨트롤이 폼에 추가될 때 이 값을 설정합니다.  
  
## AccessibleDefaultActionDescription 속성  
 이 문자열은 컨트롤의 동작을 설명합니다. 이 문자열은 속성 창에는 나타나지 않고 코드로만 설정할 수 있습니다. 다음은 button 컨트롤에 이 속성을 설정하는 예입니다.  
  
```  
' Visual Basic  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
  
// C#  
Button1.AccessibleDefaultActionDescription =   
   "Closes the application.";  
  
// C++  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## AccessibleDescription 속성  
 이 문자열은 컨트롤을 설명합니다. 속성 창에서 설정할 수도 있고 다음과 같이 코드로 설정할 수도 있습니다.  
  
```  
' Visual Basic  
Button1.AccessibleDescription = "A button with text 'Exit'."  
  
// C#  
Button1.AccessibleDescription = "A button with text 'Exit'";  
  
// C++  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## AccessibleName 속성  
 이 속성은 접근성 보조 기능에 보고되는 컨트롤의 이름입니다. 속성 창에서 설정할 수도 있고 다음과 같이 코드로 설정할 수도 있습니다.  
  
```  
' Visual Basic  
Button1.AccessibleName = "Order"  
  
// C#  
Button1.AccessibleName = "Order";  
  
// C++  
button1->AccessibleName = "Order";  
```  
  
## AccessibleRole 속성  
 [AccessibleRole 열거형](frlrfSystemWindowsFormsAccessibleRoleClassTopic) 열거형을 포함하는 이 속성은 컨트롤의 사용자 인터페이스 역할을 설명합니다. 새 컨트롤에는 이 값이 `Default`로 설정됩니다. 이것은 기본적으로 **Button** 컨트롤이 **Button**으로 동작함을 의미합니다. 컨트롤이 다른 역할을 수행할 경우에는 이 속성을 다시 설정할 수 있습니다. 예를 들어 **PictureBox** 컨트롤을 **Chart**로 사용할 수 있으며 이때 접근성 보조 기능에서 **PictureBox**가 아닌 **Chart**로 역할을 보고하도록 할 수 있습니다. 또한 직접 개발한 사용자 지정 컨트롤에 이 속성을 지정할 수도 있습니다. 이 속성은 속성 창에서 설정하거나 다음과 같이 코드로 설정할 수 있습니다.  
  
```  
' Visual Basic  
PictureBox1.AccessibleRole = AccessibleRole.Chart  
  
// C#  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
  
// C++  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## 참고 항목  
 <xref:System.Windows.Forms.AccessibleObject>   
 <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.AccessibleRole>