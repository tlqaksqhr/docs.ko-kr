---
title: "How to: Convert Hexadecimal Strings to Numbers (Visual Basic) | Microsoft Docs"
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
  - "numbers, hexadecimals"
  - "hexadecimals, decimals"
  - "examples [Visual Basic], string conversion"
  - "decimals, hexadecimals"
  - "string conversion, hexadecimal to numbers"
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# How to: Convert Hexadecimal Strings to Numbers (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 예제에서는 <xref:System.Convert.ToInt32%2A> 메서드를 사용하여 16진수 문자열을 정수로 변환합니다.  
  
### 16진수 문자열을 숫자로 변환하려면  
  
-   <xref:System.Convert.ToInt32%2A> 메서드를 사용하여 16진수로 표시된 숫자를 정수로 변환합니다.  
  
     <xref:System.Convert.ToInt32%2A> 메서드의 첫 번째 인수는 변환할 문자열입니다.  두 번째 인수는 숫자의 기수를 나타냅니다. 16진수의 기수는 16입니다.  
  
     [!code-vb[VbVbalrStrings#62](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/how-to-convert-hexadecim_1.vb)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>   
 <xref:System.Convert.ToInt32%2A>