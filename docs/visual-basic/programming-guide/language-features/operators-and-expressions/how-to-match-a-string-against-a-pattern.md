---
title: "How to: Match a String against a Pattern (Visual Basic) | Microsoft Docs"
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
  - "comparison operators, comparing strings"
  - "pattern matching"
  - "strings [Visual Basic], comparing"
  - "string comparison [Visual Basic], operators"
  - "Visual Basic code, operators"
  - "pattern matching, string comparison"
  - "string comparison [Visual Basic]"
  - "Like operator [Visual Basic], pattern matching"
  - "pattern matching, empty strings"
  - "operators [Visual Basic], comparison"
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Match a String against a Pattern (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md)의 식이 패턴을 만족하는지 확인하려면 [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md)를 사용합니다.  
  
 `Like` 연산자는 두 피연산자를 취합니다.  왼쪽 피연산자는 문자열 식이고 오른쪽 피연산자는 검색에 사용할 패턴을 포함하는 문자열입니다.  `Like`는 문자열 식이 패턴을 만족하는지 여부를 나타내는 `Boolean` 값을 반환합니다.  
  
 특정 문자, 와일드카드 문자, 문자 목록 또는 문자 범위에서 문자열 식의 각 문자를 검색할 수 있습니다.  패턴 문자열의 지정 위치는 문자열 식에서 검색할 문자의 위치에 해당합니다.  
  
### 특정 문자에서 문자열 식의 문자를 검색하려면  
  
-   특정 문자를 패턴 문자열에 직접 넣습니다.  특정 특수 문자는 대괄호\(`[ ]`\)로 묶어야 합니다.  자세한 내용은 [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md)를 참조하십시오.  
  
     다음 예제에서는 `myString`이 단일 문자 `H`로 구성되는지 여부를 테스트합니다.  
  
     [!CODE [VbVbalrOperators#70](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#70)]  
  
### 와일드카드 문자에서 문자열 식의 문자를 검색하려면  
  
-   패턴 문자열에 물음표\(`?`\)를 넣습니다.  이 위치에 있는 유효한 문자가 검색됩니다.  
  
     다음 예제에서는 `myString`이 단일 문자 `W` 뒤에 정확하게 두 개의 문자만 있는 값으로 구성되는지 여부를 테스트합니다.  
  
     [!CODE [VbVbalrOperators#71](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#71)]  
  
### 문자 목록에서 문자열 식의 문자를 검색하려면  
  
-   패턴 문자열에 대괄호\(`[ ]`\)를 넣고 대괄호 안에 문자 목록을 넣습니다.  쉼표나 다른 구분 기호로 문자를 구분하지 않습니다.  목록에서 단일 문자가 검색됩니다.  
  
     다음 예제에서는 `myString`에서 유효 문자 뒤에 `A`, `C` 또는 `E` 문자가 정확히 하나만 오는지 여부를 테스트합니다.  
  
     [!CODE [VbVbalrOperators#72](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#72)]  
  
     이 때 대\/소문자도 일치해야 합니다.  
  
### 문자 범위에서 문자열 식의 문자를 검색하려면  
  
-   패턴 문자열에 대괄호\(`[ ]`\)를 넣고 대괄호 안에 범위의 최소 문자와 최대 문자를 넣은 다음 하이픈\(`–`\)으로 구분합니다.  범위 내의 단일 문자가 검색됩니다.  
  
     다음 예제에서는 `myString`에서 `num` 문자 뒤에 `i`, `j`, `k`, `l`, `m` 또는 `n` 문자가 정확히 하나만 오는지 여부를 테스트합니다.  
  
     [!CODE [VbVbalrOperators#73](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#73)]  
  
     이 때 대\/소문자도 일치해야 합니다.  
  
## 빈 문자열 일치  
 `Like`는 `[]` 시퀀스를 길이가 0인 문자열\(`""`\)로 취급합니다.  `[]`를 사용하여 전체 문자열 식이 비어 있는지 여부를 테스트할 수 있지만, 문자열 식의 특정 위치가 비어 있는지 여부를 테스트할 수는 없습니다.  빈 위치가 테스트해야 할 옵션 중 하나인 경우 `Like`를 여러 번 사용할 수 있습니다.  
  
#### 문자가 아닌 항목이나 문자 목록에서 문자열 식의 문자를 검색하려면  
  
1.  동일한 문자열 식에서 `Like` 연산자를 두 번 호출한 다음 두 호출을 [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) 또는 [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md)와 연결합니다.  
  
2.  첫 번째 `Like` 절의 패턴 문자열에 문자 목록을 포함시키고 대괄호\(`[ ]`\)로 묶습니다.  
  
3.  두 번째 `Like` 절의 패턴 문자열에서 해당 위치에 아무 문자도 넣지 않습니다.  
  
     다음 예제에서는 일곱 자리 전화 번호 `phoneNum`에서 정확히 세 자리의 숫자 뒤에 공백, 하이픈\(`–`\) 또는 마침표\(`.`\)가 오거나 아무 문자도 오지 않고 그 뒤에 정확히 네 자리의 숫자가 오는지를 테스트합니다.  
  
     [!CODE [VbVbalrOperators#74](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#74)]  
  
## 참고 항목  
 [Comparison Operators](../../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Operators and Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md)   
 [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md)