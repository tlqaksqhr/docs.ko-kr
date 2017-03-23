---
title: "How to: Create Strings Using a StringBuilder in Visual Basic | Microsoft Docs"
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
  - "StringBuilder class"
  - "strings [Visual Basic], using StringBuilder"
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# How to: Create Strings Using a StringBuilder in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

다음 예제에서는 <xref:System.Text.StringBuilder> 클래스를 사용하여 여러 개의 짧은 문자열에서 하나의 긴 문자열을 만듭니다.  여러 문자열을 연결하는 데는 <xref:System.Text.StringBuilder> 클래스가 `&=` 연산자보다 더 효율적입니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Text.StringBuilder> 클래스의 인스턴스를 만들고 1,000개의 문자열을 이 인스턴스에 추가한 다음 결과 문자열을 반환합니다.  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## 참고 항목  
 [StringBuilder 클래스 사용](../Topic/Using%20the%20StringBuilder%20Class%20in%20the%20.NET%20Framework.md)   
 [&\= Operator](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)   
 [Strings](../../../../visual-basic/programming-guide/language-features/strings/index.md)   
 [새 문자열 만들기](../Topic/Creating%20New%20Strings%20in%20the%20.NET%20Framework.md)   
 [문자열 조작](../Topic/Manipulating%20Strings%20in%20the%20.NET%20Framework.md)   
 [Strings Sample](http://msdn.microsoft.com/ko-kr/be9e82a3-dc95-4aaa-9396-61b66e467e02)