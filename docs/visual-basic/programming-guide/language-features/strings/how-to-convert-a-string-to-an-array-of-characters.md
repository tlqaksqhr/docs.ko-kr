---
title: "How to: Convert a String to an Array of Characters in Visual Basic | Microsoft Docs"
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
  - "character arrays, converting strings"
  - "arrays [Visual Basic], converting strings to"
  - "examples [Visual Basic], string conversion"
  - "strings [Visual Basic], converting to arrays"
  - "string conversion [Visual Basic], arrays"
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# How to: Convert a String to an Array of Characters in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

문자열을 구문 분석할 때처럼 문자열 내의 문자 관련 데이터 및 문자열 내에서 해당 문자의 위치를 알고 있으면 유용할 때가 있습니다.  다음 예제에서는 문자열의 <xref:System.String.ToCharArray%2A> 메서드를 호출하여 문자열에서 문자 배열을 가져오는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 문자열을 `Char` 배열로 분할하는 방법 및 문자열을 유니코드 텍스트 문자 `String` 배열로 분할하는 방법을 보여 줍니다.  이렇게 구별하는 이유는 유니코드 텍스트 문자가 두 개 이상의 `Char` 문자\(예: 서로게이트 쌍 또는 조합 문자 시퀀스\)로 구성될 수 있기 때문입니다.  자세한 내용은 <xref:System.Globalization.TextElementEnumerator> 및 http:\/\/www.unicode.org에 있는 "The Unicode Standard"를 참조하십시오.  
  
 [!code-vb[VbVbalrStrings#75](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_1.vb)]  
  
## 예제  
 문자열을 유니코드 텍스트 문자로 분할하는 것은 더 어렵지만 시각적으로 표시된 문자열에 대한 정보가 필요한 경우에 필수적입니다.  다음 예제에서는 <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> 메서드를 사용하여 문자열을 구성하는 유니코드 텍스트 문자에 대한 정보를 가져옵니다.  
  
 [!code-vb[VbVbalrStrings#76](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_2.vb)]  
  
## 참고 항목  
 <xref:System.String.Chars%2A>   
 <xref:System.Globalization.StringInfo?displayProperty=fullName>   
 [How to: Access Characters in Strings](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)   
 [Converting Between Strings and Other Data Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)   
 [Strings](../../../../visual-basic/programming-guide/language-features/strings/index.md)