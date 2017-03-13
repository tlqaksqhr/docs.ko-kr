---
title: "How to: Declare A Constant (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.constant"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Integer data type, declaring constants"
  - "Single data type, declaring constants"
  - "Const statement [Visual Basic], declaring constants"
  - "procedures, declaration"
  - "data types [Visual Basic], constants"
  - "Long data type, declaring constants"
  - "Visual Basic code, declaring variables and constants"
  - "Double data type, declaring constants"
  - "Boolean data type, declaring constants"
  - "modules, declaring constants"
  - "Byte data type, declaring constants"
  - "constants, declaring"
  - "Date data type, declaring constants"
  - "String data type, declaring constants"
  - "declaring constants, const keyword"
  - "Currency data type, declaring constants and variants"
  - "module-level constants and variables"
  - "Object data type, declaring constants"
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# How to: Declare A Constant (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Const` 문을 사용하여 상수를 선언하고 상수 값을 설정합니다.  상수를 선언하여 값에 의미 있는 이름을 할당합니다.  상수를 선언한 후에는 수정하거나 새 값을 할당할 수 없습니다.  
  
 프로시저 내에서 또는 모듈, 클래스, 구조체의 선언 섹션에서 상수를 선언합니다.  클래스 또는 구조체 수준의 상수는 기본적으로 `Private`이지만 적절한 코드 액세스 수준을 위해 `Public`, `Friend`, `Protected` 또는 `Protected Friend`로 선언할 수도 있습니다.  
  
 상수는 기호화된 올바른 이름\(변수 이름 만들기 규칙과 같음\)이어야 하고 식은 숫자 또는 문자열 상수와 연산자로 구성됩니다. 그러나 식에 함수 호출을 사용할 수는 없습니다.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### 상수를 선언하려면  
  
-   다음 예제와 같이 액세스 지정자, `Const` 키워드 및 식을 포함하는 선언을 작성합니다.  
  
     [!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)가 `Off`이고 [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)가 `On`인 경우 데이터 형식\(`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single` 또는 `String`\)을 지정하여 명시적으로 상수를 선언해야 합니다.  
  
     `Option Infer`가 `On`이거나 `Option Strict`가 `Off`인 경우 `As` 절로 데이터 형식을 지정하지 않고 상수를 선언할 수 있습니다.  컴파일러는 식의 형식에서 상수 형식을 확인합니다.  자세한 내용은 [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)을 참조하십시오.  
  
### 데이터 형식이 명시적으로 언급된 상수를 선언하려면  
  
-   다음 예제와 같이 `As` 키워드와 명시적 데이터 형식을 포함하는 선언을 작성합니다.  
  
     [!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     상수를 한 줄에 하나만 선언하면 코드를 읽기가 쉬워지기는 하지만, 한 줄에 여러 상수를 선언할 수도 있습니다.  한 줄에 여러 개의 상수를 선언하는 경우에는 각 상수의 액세스 수준\(`Public`, `Private`, `Friend`, `Protected` 또는 `Protected Friend`\)이 모두 동일해야 합니다.  
  
### 한 줄에 여러 개의 상수를 선언하려면  
  
-   다음 예제와 같이 쉼표와 공백을 사용하여 각 상수를 구분합니다.  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## 참고 항목  
 [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md)   
 [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Constants and Enumerations](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)   
 [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)