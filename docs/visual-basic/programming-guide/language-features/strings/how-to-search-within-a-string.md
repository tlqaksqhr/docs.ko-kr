---
title: "How to: Search Within a String (Visual Basic) | Microsoft Docs"
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
  - "strings [Visual Basic], finding"
  - "strings [Visual Basic], searching"
  - "examples [Visual Basic], strings"
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Search Within a String (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

이 예제에서는 <xref:System.String> 개체의 <xref:System.String.IndexOf%2A> 메서드를 호출하여 해당 부분 문자열이 처음 나타나는 위치의 인덱스를 보고합니다.  
  
## 예제  
 [!code-vb[VbVbalrStrings#71](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-search-within-a-string_1.vb)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System> 네임스페이스를 지정하는 `Imports` 문.  자세한 내용은 [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하십시오.  
  
## 강력한 프로그래밍  
 <xref:System.String.IndexOf%2A> 메서드는 해당 부분 문자열이 처음 나타나는 곳을 찾아 첫 번째 문자의 위치를 보고합니다.  인덱스는 0부터 시작합니다. 즉, 문자열에서 첫 번째 문자의 인덱스는 0입니다.  
  
 <xref:System.String.IndexOf%2A>가 부분 문자열을 찾지 못하면 –1을 반환합니다.  
  
 <xref:System.String.IndexOf%2A> 메서드는 대\/소문자를 구분하며 현재 문화권을 사용합니다.  
  
 오류를 제어하려면 문자열 검색을 [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) 구문의 `Try` 블록 안에 넣는 것이 좋습니다.  
  
## 참고 항목  
 <xref:System.String.IndexOf%2A>   
 [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Introduction to Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)   
 [Strings](../../../../visual-basic/programming-guide/language-features/strings/index.md)