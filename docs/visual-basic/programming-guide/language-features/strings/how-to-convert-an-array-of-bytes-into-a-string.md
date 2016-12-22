---
title: "How to: Convert an Array of Bytes into a String in Visual Basic | Microsoft Docs"
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
  - "string conversion, arrays"
  - "byte arrays, converting to strings"
  - "examples [Visual Basic], strings"
  - "arrays [Visual Basic], converting to strings"
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Convert an Array of Bytes into a String in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

이 항목에서는 바이트 배열의 바이트를 문자열로 변환하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Text.Encoding.Unicode%2A?displayProperty=fullName> 인코딩 클래스의 <xref:System.Text.Encoding.GetString%2A> 메서드를 사용하여 바이트 배열의 모든 바이트를 문자열로 변환합니다.  
  
 [!code-vb[VbVbalrStrings#72](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-an-array-of-bytes-into-a-string_1.vb)]  
  
 다음과 같은 몇 가지 인코딩 옵션을 사용하여 바이트 배열을 문자열로 변환할 수 있습니다.  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=fullName>: ASCII\(7비트\) 문자 집합에 대한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=fullName>: Big\-Endian 바이트 순서를 사용하는 UTF\-16 형식에 대한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=fullName>: 시스템의 현재 ANSI 코드 페이지에 대한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=fullName>: little\-endian 바이트 순서를 사용하는 UTF\-16 형식에 대한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=fullName>: little\-endian 바이트 순서를 사용하는 UTF\-32 형식에 대한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=fullName>: UTF\-7 형식에 대한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=fullName>: UTF\-8 형식에 대한 인코딩을 가져옵니다.  
  
## 참고 항목  
 <xref:System.Text.Encoding?displayProperty=fullName>   
 <xref:System.Text.Encoding.GetString%2A>   
 [How to: Convert Strings into an Array of Bytes in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)