---
title: "Expression is a value and therefore cannot be the target of an assignment | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30068"
  - "vbc30068"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30068"
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Expression is a value and therefore cannot be the target of an assignment
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

문에서 식에 값을 할당하려고 했습니다.  런타임에 쓰기 가능한 변수, 속성 또는 배열 요소에만 값을 할당할 수 있습니다.  다음 예제에서는 이 오류가 발생할 수 있는 상황을 보여 줍니다.  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 속성과 배열 요소에도 비슷한 예제를 적용할 수 있습니다.  
  
 **간접 액세스.** 값 형식을 통한 간접 액세스에서도 이 오류가 생성될 수 있습니다.  <xref:System.Windows.Forms.Control.Location%2A>을 통해 간접적으로 액세스하여 <xref:System.Drawing.Point>의 값을 설정하려고 시도하는 다음과 같은 코드 예제를 참조하십시오.  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 <xref:System.Windows.Forms.Control.Location%2A> 속성에서 반환되는 <xref:System.Drawing.Point> 구조체에 대해 임시 할당만 만들기 때문에 이 예제의 마지막 문은 실패합니다.  구조체는 값 형식이고 문이 실행된 후에는 임시 구조체가 유지되지 않습니다.  <xref:System.Windows.Forms.Control.Location%2A>에 대한 변수를 선언하고 사용하면 <xref:System.Drawing.Point> 구조체에 대해 보다 지속적인 할당이 만들어지므로 문제를 해결할 수 있습니다.  다음 예제에서는 위 예제의 마지막 문을 대신할 수 있는 코드를 보여 줍니다.  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 **오류 ID:** BC30068  
  
### 이 오류를 해결하려면  
  
-   문에서 식에 값을 할당할 경우 쓰기 가능한 변수, 속성 또는 배열 요소 하나로 식을 대체합니다.  
  
-   문에서 값 형식\(대개 구조체\)을 통해 간접적으로 액세스하는 경우 값 형식을 포함할 변수를 만듭니다.  
  
-   알맞은 구조체 또는 다른 값 형식을 변수에 할당합니다.  
  
-   속성에 액세스할 변수를 사용하여 값을 할당합니다.  
  
## 참고 항목  
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Troubleshooting Procedures](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)