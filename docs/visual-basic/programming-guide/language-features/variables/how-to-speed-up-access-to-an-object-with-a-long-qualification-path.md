---
title: "How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic) | Microsoft Docs"
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
  - "variables [Visual Basic], accessing"
  - "variables [Visual Basic], object"
  - "With statement"
  - "With block"
  - "object variables, accessing"
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

여러 메서드 및 속성의 정규화 경로가 필요한 개체에 자주 액세스하는 경우 정규화 경로를 반복하지 않음으로써 코드 속도를 개선할 수 있습니다.  
  
 정규화 경로를 반복하지 않는 방법에는 두 가지가 있습니다.  변수에 개체를 할당하거나 `With`...`End With` 블록에서 개체를 사용하면 됩니다.  
  
### 변수에 정규화된 개체를 지정하여 해당 개체에 대한 액세스 속도를 개선하려면  
  
1.  자주 액세스하는 개체의 형식으로 변수를 선언합니다.  선언의 초기화 부분에서 정규화 경로를 지정합니다.  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  변수를 사용하여 개체의 멤버에 액세스합니다.  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### With...End With 블록을 사용하여 정규화된 개체에 대한 액세스 속도를 개선하려면  
  
1.  `With` 문에 정규화된 경로를 넣습니다.  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  `With` 블록 안\(`End With` 문 앞\)에서 개체의 멤버에 액세스합니다.  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## 참고 항목  
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)