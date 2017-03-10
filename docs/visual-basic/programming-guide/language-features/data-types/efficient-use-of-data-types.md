---
title: "Efficient Use of Data Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "performance, data type efficiency"
  - "data types [Visual Basic], weak typing"
  - "AscW function, preferred to Asc"
  - "data types [Visual Basic], using efficiently"
  - "optimization, data types"
  - "data types [Visual Basic], strong typing"
  - "strong typing"
  - "typing, strong"
  - "data types [Visual Basic], optimizing"
  - "ChrW function, preferred to Chr"
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Efficient Use of Data Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

선언되지 않은 변수와 데이터 형식을 사용하지 않고 선언된 변수에는 `Object` 데이터 형식이 지정됩니다.  이렇게 하면 프로그램 작성 속도는 빨라지지만 실행 속도는 느려질 수 있습니다.  
  
## 강력한 형식화  
 모든 변수에 대해 데이터 형식을 지정하는 것을 *강력한 형식화*라고 합니다.  강력한 형식화의 장점은 다음과 같습니다.  
  
-   이 변수에 대해 IntelliSense 지원이 있습니다.  이를 사용하면 코드로 입력할 때 변수의 속성과 다른 멤버를 볼 수 있습니다.  
  
-   컴파일러에서 형식 검사를 수행하여  오버플로와 같은 오류로 인해 런타임에서 실패할 가능성이 있는 문을 찾아낼 수 있습니다.  또한 지원되지 않는 개체에 대한 메서드 호출을 찾아냅니다.  
  
-   코드 실행이 빨라집니다.  
  
## 가장 효율적인 데이터 형식  
 소수를 포함하지 않은 변수의 경우 정수 계열 데이터 형식이 비정수 계열 형식보다 효율적입니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 `Integer`와 `UInteger`가 가장 효율적인 숫자 형식입니다.  
  
 현재 플랫폼의 프로세서는 배정밀도의 부동 소수점 연산을 수행하므로 소수에는 `Double`이 가장 효율적인 데이터 형식입니다.  그러나 `Double`을 사용하는 연산 작업은 `Integer` 등의 정수 계열 형식을 사용하는 연산보다 속도가 느립니다.  
  
## 데이터 형식 지정  
 특정 형식의 변수를 선언하려면 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)을 사용합니다.  다음 예제와 같이 [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 또는 [Private](../../../../visual-basic/language-reference/modifiers/private.md) 키워드를 사용하여 변수를 선언할 때 동시에 액세스 수준도 지정할 수 있습니다.  
  
```  
Private x As Double  
Protected s As String  
```  
  
## 문자 변환  
 `AscW` 및 `ChrW` 함수는 유니코드에서 작동합니다.  유니코드와의 변환을 필요로 하는 `Asc` 및 `Chr`보다는 이 함수를 우선적으로 사용해야 합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>   
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>   
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Numeric Data Types](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)   
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [IntelliSense 사용](/visual-studio/ide/using-intellisense)