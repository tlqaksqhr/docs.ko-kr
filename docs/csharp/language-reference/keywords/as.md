---
title: "as(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "as_CSharpKeyword"
  - "as"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "as 키워드[C#]"
  - "형식 변환[C#], as 키워드"
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# as(C# 참조)
사용할 수 있는 `as` 특정 형식의 호환 되는 참조 형식 간에 변환 수행 하는 연산자 또는  [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)을.  다음 코드에서는 이러한 예제를 보여 줍니다.  
  
 [!code-cs[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsOperator/csrefKeywordsOperators.cs#1)]  
  
## 설명  
 `as` 연산자는 캐스트 연산과 비슷합니다.  그러나 변환이 불가능 한 경우 `as` 반환 `null` 예외를 발생 시키는 대신 합니다.  다음 예제를 참조하십시오.  
  
```  
expression as type  
```  
  
 동일 코드를 제외 하 고 다음 식의 `expression` 변수는 한 번만 계산 됩니다.  
  
```  
expression is type ? (type)expression : (type)null  
```  
  
 이때의 `as` 참조 변환, nullable 변환 및 boxing 변환 연산자를 수행 합니다.  `as` 연산자 대신 캐스트 식을 사용 하 여 이루어져야 합니다 사용자 정의 변환과 같은 다른 변환을 수행할 수 없습니다.  
  
## 예제  
 [!code-cs[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsOperator/csrefKeywordsOperators.cs#2)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [?: 연산자](../../../csharp/language-reference/operators/conditional-operator.md)   
 [연산자 키워드](../../../csharp/language-reference/keywords/operator-keywords.md)