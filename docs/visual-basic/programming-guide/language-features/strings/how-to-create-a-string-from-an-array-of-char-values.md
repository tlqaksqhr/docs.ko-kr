---
title: "How to: Create a String from An Array of Char Values (Visual Basic) | Microsoft Docs"
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
  - "examples [Visual Basic], arrays"
  - "examples [Visual Basic], Char data type"
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Create a String from An Array of Char Values (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

이 예제에서는 개별 문자로부터 "abcd"라는 문자열을 만듭니다.  
  
## 예제  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## 코드 컴파일  
 이 메서드에 특별히 필요한 사항은 없습니다.  
  
 `"a"c` 구문은 문자 리터럴을 만드는 데 사용됩니다. 여기서 `c`는 따옴표로 묶은 단일 문자 바로 다음에 옵니다.  
  
## 강력한 프로그래밍  
 문자열에 Null 문자\(`Chr(0)`에 해당됨\)가 포함되면 해당 문자열을 사용할 때 예기치 않은 결과가 발생할 수 있습니다.  null 문자가 문자열에 포함될 수는 있지만 null 문자 뒤에 따라오는 문자는 상황에 따라 표시되지 않을 수도 있습니다.  
  
## 참고 항목  
 <xref:System.String>   
 [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md)   
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)