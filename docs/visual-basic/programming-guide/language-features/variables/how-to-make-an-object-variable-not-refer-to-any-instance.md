---
title: "How to: Make an Object Variable Not Refer to Any Instance (Visual Basic) | Microsoft Docs"
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
  - "Nothing keyword, variable assignment"
  - "object variables, null reference"
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

개체 변수를 [Nothing](../../../../visual-basic/language-reference/nothing.md)으로 설정하여 개체 인스턴스에서 개체 변수를 분리할 수 있습니다.  
  
### 개체 인스턴스에서 개체 변수를 분리하려면  
  
-   대입문에서 변수를 `Nothing`으로 설정합니다.  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## 강력한 프로그래밍  
 코드에서 `Nothing`으로 설정된 개체 변수의 멤버에 액세스하려고 하면 <xref:System.NullReferenceException>이 발생합니다.  개체 변수를 `Nothing`으로 설정해야 하는 경우가 자주 있거나 변수가 초기화되지 않을 가능성이 있는 경우에는 멤버 액세스를 `Try...Catch...Finally` 블록 안에 포함시키는 것이 좋습니다.  
  
## .NET Framework 보안  
 기밀이거나 중요한 데이터가 포함된 개체에 대해 개체 변수를 사용하는 경우, 이러한 개체 중 하나를 실제로 처리하지 않을 때 변수를 `Nothing`으로 설정할 수 있습니다.  이렇게 하면 악의적인 코드가 해당 데이터에 대한 액세스 권한을 얻을 가능성을 줄일 수 있습니다.  
  
## 참고 항목  
 <xref:System.NullReferenceException>   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Assignment](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Nothing](../../../../visual-basic/language-reference/nothing.md)   
 [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [예외 문제 해결: System.NullReferenceException](../Topic/Troubleshooting%20Exceptions:%20System.NullReferenceException.md)