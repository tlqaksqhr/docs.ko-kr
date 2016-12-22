---
title: "When to Use an Enumeration (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "enumerations [Visual Basic]"
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# When to Use an Enumeration (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

열거형은 일련의 관련 상수 집합을 사용하여 작업하는 편리한 방법을 제공합니다.  열거형\(또는 `Enum`\)은 일련의 값을 나타내는 기호화된 이름입니다.  열거형은 데이터 형식으로 처리되며, 변수 및 속성과 함께 사용할 상수 집합을 만드는 데 사용할 수 있습니다.  
  
## 열거형을 사용하는 경우  
 프로시저에서 사용하는 변수가 특정 집합으로 제한되어 있으면 열거형을 사용하는 것이 좋습니다.  열거형을 사용하면 코드가 보다 간결해지고 읽기 쉬워집니다. 특히 의미 있는 이름을 사용하면 더 편리합니다.  
  
 열거형을 사용할 때의 장점은 다음과 같습니다.  
  
-   숫자를 잘못 입력하여 생기는 오류를 줄일 수 있습니다.  
  
-   나중에 값을 변경하기가 쉽습니다.  
  
-   코드가 읽기 쉬워지므로 오류가 발생할 가능성이 줄어듭니다.  
  
-   이전 버전과의 호환성이 유지됩니다.  열거형을 사용하면 나중에 다른 사용자가 멤버 이름에 해당하는 값을 변경해도 코드가 실패할 가능성이 거의 없습니다.  
  
## 열거형 이름 지정  
 열거형 멤버에는 명명 규칙을 사용합니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 열거형 멤버 이름을 발견한 경우 참조되는 다른 형식 라이브러리에 동일한 이름이 들어 있으면 예외가 thrown될 수 있습니다.  따라서 응용 프로그램이나 구성 요소에서 값을 식별하는 고유 접두사를 사용합니다.  
  
 열거형의 멤버를 참조할 때는 멤버 이름을 열거형 이름으로 한정하거나 `Imports` 문을 사용해야 합니다.  자세한 내용은 [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)을 참조하십시오.  
  
## 미리 정의된 열거형  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 `FirstDayOfWeek` 및 `MsgBoxResult`와 같이 코드를 간단하게 해 주는 미리 정의된 열거형을 여러 가지 제공합니다.  미리 정의된 열거형의 목록은 [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)을 참조하십시오.  
  
## 참고 항목  
 [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [How to: Iterate Through An Enumeration in Visual Basic](../Topic/How%20to:%20Iterate%20Through%20An%20Enumeration%20in%20Visual%20Basic.md)   
 [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)