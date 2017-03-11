---
title: "new 제약 조건(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "new 제약 조건 키워드[C#]"
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# new 제약 조건(C# 참조)
`new` 제약 조건은 제네릭 클래스 선언의 모든 형식 인수가 매개 변수 없는 public 생성자를 갖도록 지정합니다.  new 제약 조건을 사용하려면 형식이 abstract일 수 없습니다.  
  
## 예제  
 다음 예제에서와 같이 제네릭 클래스로 형식의 새 인스턴스를 만들 때 형식 매개 변수에 `new` 제약 조건을 적용합니다.  
  
 [!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsOperator/csrefKeywordsOperators.cs#5)]  
  
## 예제  
 다른 제약 조건과 함께 `new()` 제약 조건을 사용하는 경우 이 제약 조건은 마지막에 지정해야 합니다.  
  
 [!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsOperator/csrefKeywordsOperators.cs#6)]  
  
 자세한 내용은 [형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)를 참조하십시오.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 <xref:System.Collections.Generic>   
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [연산자 키워드](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [제네릭](../../../csharp/programming-guide/generics/index.md)