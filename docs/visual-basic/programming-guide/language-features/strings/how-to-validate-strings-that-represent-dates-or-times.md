---
title: "How to: Validate Strings That Represent Dates or Times (Visual Basic) | Microsoft Docs"
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
  - "strings [Visual Basic], validating"
  - "String data type, validation"
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# How to: Validate Strings That Represent Dates or Times (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

다음 코드 예제에서는 문자열이 유효한 날짜나 시간을 표시하는지 여부를 나타내는 `Boolean` 값을 설정합니다.  
  
## 예제  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/visualbasic/how-to-validate-strings-_1.vb)]  
  
## 코드 컴파일  
 `("01/01/03")` 및 `"9:30 PM"`을 유효성 검사를 수행할 날짜와 시간으로 바꿉니다.  문자열을 하드 코드된 문자열, `String` 변수 또는 `InputBox`와 같은 문자열을 반환하는 메서드로 바꿀 수 있습니다.  
  
## 강력한 프로그래밍  
 `String`을 `DateTime` 변수로 변환하기 전에 이 메서드를 사용하여 문자열의 유효성을 검사합니다.  날짜 또는 시간을 먼저 검사하여 런타임에 예외가 발생하지 않게 할 수 있습니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>   
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>   
 [Validating Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)