---
title: "How to: Access Characters in Strings in Visual Basic | Microsoft Docs"
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
  - "strings [Visual Basic], accessing characters"
  - "characters [Visual Basic], accessing in strings"
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# How to: Access Characters in Strings in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 예제에서는 <xref:System.String.Chars%2A> 속성을 사용하여 문자열의 지정된 위치에 있는 문자에 액세스하는 방법을 보여 줍니다.  
  
## 예제  
 문자열 내의 문자 관련 데이터 및 문자열 내에서 해당 문자의 위치를 알고 있으면 유용할 때가 있습니다.  문자열은 문자의 배열\(`Char` 인스턴스\)로 간주할 수 있으며 <xref:System.String.Chars%2A> 속성을 사용하여 해당 문자의 인덱스를 참조하면 특정 문자를 검색할 수 있습니다.  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/how-to-access-characters_1.vb)]  
  
 <xref:System.String.Chars%2A> 속성의 `index` 매개 변수는 0에서 시작합니다.  
  
## 강력한 프로그래밍  
 <xref:System.String.Chars%2A> 속성은 지정된 위치의 문자를 반환합니다.  그러나 일부 유니코드 문자는 여러 문자로 표시될 수도 있습니다.  유니코드 문자 작업 방법은 [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)을 참조하십시오.  
  
 <xref:System.String.Chars%2A> 속성은 `index` 매개 변수가 문자열 길이보다 크거나 같거나, 0 미만인 경우 <xref:System.IndexOutOfRangeException> 예외를 throw합니다.  
  
## 참고 항목  
 <xref:System.String.Chars%2A>   
 [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)   
 [Converting Between Strings and Other Data Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)   
 [Strings](../../../../visual-basic/programming-guide/language-features/strings/index.md)