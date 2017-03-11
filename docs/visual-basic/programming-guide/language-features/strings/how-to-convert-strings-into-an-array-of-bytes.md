---
title: "How to: Convert Strings into an Array of Bytes in Visual Basic | Microsoft Docs"
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
  - "string conversion, arrays"
  - "arrays [Visual Basic], converting strings to"
  - "byte arrays"
  - "examples [Visual Basic], string conversion"
  - "arrays [Visual Basic], byte arrays"
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# How to: Convert Strings into an Array of Bytes in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 항목에서는 문자열을 바이트 배열로 변환하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Text.Encoding.Unicode%2A?displayProperty=fullName> 인코딩 클래스의 <xref:System.Text.Encoding.GetBytes%2A> 메서드를 사용하여 문자열을 바이트 배열로 변환합니다.  
  
 [!code-vb[VbVbalrStrings#74](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/how-to-convert-strings-i_1.vb)]  
  
 다음과 같은 몇 가지 인코딩 옵션을 사용하여 문자열을 바이트 배열로 변환할 수 있습니다.  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=fullName>: ASCII\(7비트\) 문자 집합에 대한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=fullName>: Big\-Endian 바이트 순서를 사용하는 UTF\-16 형식에 대한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=fullName>: 시스템의 현재 ANSI 코드 페이지에 대한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=fullName>: little\-endian 바이트 순서를 사용하는 UTF\-16 형식에 대한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=fullName>: little\-endian 바이트 순서를 사용하는 UTF\-32 형식에 대한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=fullName>: UTF\-7 형식에 대한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=fullName>: UTF\-8 형식에 대한 인코딩을 가져옵니다.  
  
## 참고 항목  
 <xref:System.Text.Encoding?displayProperty=fullName>   
 <xref:System.Text.Encoding.GetBytes%2A>   
 [How to: Convert an Array of Bytes into a String in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)