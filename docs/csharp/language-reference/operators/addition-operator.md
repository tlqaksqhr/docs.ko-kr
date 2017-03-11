---
title: "+ 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "+_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "+ 연산자[C#]"
  - "더하기 연산자[C#]"
  - "연결 연산자[C#]"
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# + 연산자(C# 참조)
`+` 연산자는 단항 연산자로 사용하거나 이항 연산자로 사용할 수 있습니다.  
  
## 설명  
 단항 `+` 연산자는 모든 숫자 형식에 대해 미리 정의되어 있습니다.  숫자 형식에 대한 단항 `+` 연산의 결과는 단순히 피연산자의 값입니다.  
  
 이항 `+` 연산자는 숫자 형식과 문자열 형식에 대해 미리 정의되어 있습니다.  숫자 형식의 경우 \+ 연산자는 두 피연산자의 합을 계산합니다.  하나 또는 두 피연산자가 문자열 형식인 경우 \+ 연산자는 피연산자를 나타내는 문자열을 연결합니다.  
  
 또한 대리자 형식도 이항 `+` 연산자를 제공합니다. 이 경우에는 대리자 연결을 수행합니다.  
  
 사용자 정의 형식으로 단항 `+` 연산자와 이항 `+` 연산자를 오버로드할 수 있습니다.  정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.  자세한 내용은 [operator](../../../csharp/language-reference/keywords/operator.md)를 참조하십시오.  
  
## 예제  
 [!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#28)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)   
 [operator](../../../csharp/language-reference/keywords/operator.md)