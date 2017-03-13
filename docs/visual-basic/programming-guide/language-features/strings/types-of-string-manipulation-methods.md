---
title: "Types of String Manipulation Methods in Visual Basic | Microsoft Docs"
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
  - "strings [Visual Basic], manipulating [Visual Basic]"
  - "string manipulation"
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Types of String Manipulation Methods in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

문자열을 분석하고 조작하는 데는 여러 가지 방법이 있습니다.  이 중 일부 메서드는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 언어의 부분이고 나머지는 `String` 클래스 고유의 것입니다.  
  
## Visual Basic 언어 및 .NET Framework  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 메서드는 해당 언어의 고유 함수로 사용되며  코드에서 한정자 없이 사용될 수 있습니다.  다음 예제에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 문자열 조작 명령의 일반적인 사용 예를 보여 줍니다.  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 위의 예제에서 `Mid` 함수는 `aString`에 대해 직접 연산을 수행하여 값을 `bString`에 할당합니다.  
  
 Visual Basic 문자열 조작 메서드의 목록은 [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)을 참조하십시오.  
  
### 공유 메서드 및 인스턴스 메서드  
 또한 `String` 클래스의 메서드를 사용하여 문자열을 조작할 수도 있습니다.  `String` 클래스에는 *공유* 메서드와 *인스턴스* 메서드라는 두 가지 유형의 메서드가 있습니다.  
  
#### 공유 메서드  
 공유 메서드는 `String` 클래스 자체에서 생기고 클래스의 인스턴스로 작업할 필요가 없는 메서드입니다.  이 메서드는 `String` 클래스의 인스턴스 대신 클래스\(`String`\)의 이름을 사용하여 한정할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 앞의 예제에서는 <xref:System.String.Copy%2A?displayProperty=fullName> 메서드는 정적 메서드이며 할당된 식에 사용되고 결과 값을 `bString`에 할당합니다.  
  
#### 인스턴스 메서드  
 이와 반대로 인스턴스 메서드는 `String`의 특정 인스턴스에서 생기고 인스턴스 이름을 사용하여 한정해야 합니다.  예를 들면 다음과 같습니다.  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 위의 예제에서 <xref:System.String.Substring%2A?displayProperty=fullName> 메서드는 `String` 인스턴스\(`aString`\)의 메서드이며  `aString`에 대해 연산을 수행하여 해당 값을 `bString`에 할당합니다.  
  
 자세한 내용은 <xref:System.String> 클래스 설명서를 참조하십시오.  
  
## 참고 항목  
 [Introduction to Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)