---
title: "How to: Declare Enumerations (Visual Basic) | Microsoft Docs"
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
  - "declarations, enumerations"
  - "enumerations [Visual Basic], declaring"
  - "declaring enumerations"
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# How to: Declare Enumerations (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

클래스 또는 모듈의 선언 섹션에서 `Enum` 문을 사용하여 열거형을 만듭니다.  메서드 내에서는 열거형을 선언할 수 없습니다.  적절한 액세스 수준을 지정하려면 `Private`, `Protected`, `Friend` 또는 `Public`을 사용합니다.  
  
 `Enum` 형식은 이름, 내부 형식 및 각각 상수를 나타내는 일련의 필드 집합을 가집니다.  이름은 올바른 [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] 한정자여야 합니다.  내부 형식은 정수 형식인 `Byte`, `Short`, `Long` 또는 `Integer` 중 하나여야 하며  `Integer`가 기본값입니다.  열거형은 항상 강력하게 형식화되며, 열거형 형식을 정수 숫자 형식으로 변경하거나 정수 숫자 형식을 열거형 형식으로 변경할 수 없습니다.  
  
 열거형에는 부동 소수점 값을 사용할 수 없습니다.  `Option Strict On` 상태에서 열거형에 부동 소수점 값을 할당하면 컴파일러 오류가 발생합니다.  `Option Strict`가 `Off`인 경우에는 값이 자동으로 `Enum` 형식으로 변환됩니다.  
  
 이름에 대한 설명과 `Imports` 문을 사용하여 이름 한정이 필요 없게 만드는 방법은 [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)을 참조하십시오.  
  
### 열거형을 선언하려면  
  
1.  각각 다른 `Enum`을 선언하는 다음 예제와 같이 코드 액세스 수준, `Enum` 키워드 및 올바른 이름을 포함하는 선언을 작성합니다.  
  
     [!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#3)]  
  
2.  열거형의 상수를 정의합니다.  기본적으로 열거형의 첫째 상수는 `0`으로 초기화되고 다음 상수는 이전 상수보다 하나 더 큰 값으로 초기화됩니다.  예를 들어, 다음 `Days` 열거형은 이름이 `Sunday`이고 값이 `0`인 상수, 이름이 `Monday`이고 값이 `1`인 상수, 이름이 `Tuesday`이고 값이 `2`인 상수 등을 포함합니다.  
  
     [!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#4)]  
  
3.  열거형에서 대입문을 사용하여 상수에 명시적으로 값을 대입할 수 있습니다.  음수를 포함하여 모든 정수 값을 대입할 수 있습니다.  예를 들면 값이 0보다 작은 상수로 오류 조건을 나타낼 수 있습니다.  다음 열거형에서 상수 `Invalid`는 값 `–1`에, 상수 `Sunday`는 값 `0`에 명시적으로 할당됩니다.  또한 `Saturday`는 열거형의 첫째 상수이므로 값 `0`으로 초기화됩니다.  `Monday`의 값은 `Sunday`의 값보다 하나 더 큰 `1`이고 `Tuesday`의 값은 `2`이며 이런 식으로 값이 증가합니다.  
  
     [!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#5)]  
  
### 열거형을 명시적 형식으로 선언하려면  
  
-   다음 예제와 같이 `As` 절을 사용하여 열거형의 형식을 지정합니다.  
  
     [!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#6)]  
  
## 참고 항목  
 [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [When to Use an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)