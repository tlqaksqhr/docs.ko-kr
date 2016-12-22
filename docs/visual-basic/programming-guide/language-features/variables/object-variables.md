---
title: "Object Variables in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "object variables, about object variables"
  - "variables [Visual Basic], object"
  - "objects [Visual Basic], accessing"
  - "object variables"
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Object Variables in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

변수는 값을 직접 저장할 뿐 아니라 개체를 참조할 수 있습니다.  값을 변수에 대입하는 경우와 같이 개체를 변수에 할당할 수 있습니다.  
  
-   일반적으로 변수 이름은 개체 자체에 액세스하는 데 필요한 메서드와 속성의 전체 경로보다 짧으므로 쉽게 기억할 수 있습니다.  
  
-   개체를 참조하는 변수를 사용하는 것이 해당 메서드나 속성을 통해 개체 자체에 반복적으로 액세스하는 것보다 효율적입니다.  
  
-   코드 실행 중에 다른 개체를 참조하도록 변수를 변경할 수 있습니다.  
  
## 코드 길이 줄이기  
 개체 변수를 사용하면 입력해야 하는 코드 길이를 줄일 수 있습니다.  다음 예제에서는 메서드 및 속성의 전체 경로를 사용하여 <xref:System.Windows.Forms.Control> 개체에 액세스합니다.  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 컨트롤에 대해 개체 변수를 사용하면 코드의 길이도 줄어 들고 실행 속도도 빨라집니다.  할당할 특정 클래스\(이 예제에서는 `Control`\)를 사용하여 개체 변수를 선언해야 합니다.  개체를 해당 변수에 할당하면 개체 자체를 처리하는 것과 똑같이 변수를 통해 해당 개체를 처리할 수 있습니다.  개체의 속성을 설정하거나 가져오거나 개체의 메서드를 사용할 수 있습니다.  다음 예제에서는 개체 변수를 사용하여 위 예제의 코드를 단순화합니다.  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## 참고 항목  
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [How to: Speed Up Access to an Object with a Long Qualification Path](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)   
 [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Object Variable Assignment](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)