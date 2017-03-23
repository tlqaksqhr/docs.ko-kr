---
title: "방법: 쿼리에 람다 식 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "람다 식[C#], LINQ"
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# 방법: 쿼리에 람다 식 사용(C# 프로그래밍 가이드)
람다 식은 쿼리 구문에 직접 사용하지 않지만 쿼리 식에 포함할 수 있는 메서드 호출 안에 사용합니다.  실제로 일부 쿼리 작업은 메서드 구문으로만 표현될 수 있습니다.  쿼리 구문 및 메서드 구문 간의 차이에 대한 자세한 내용은 [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 표준 쿼리 연산자 <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName>를 사용하여 메서드 기반 쿼리에 람다 식을 사용하는 방법을 보여 줍니다.  이 예제에서 <xref:System.Linq.Enumerable.Where%2A> 메서드는 <xref:System.Func%601> 대리자 형식의 입력 매개 변수를 사용하며, 이 대리자는 정수를 입력으로 받아 부울을 반환합니다.  람다 식을 이 대리자로 변환할 수 있습니다.  이 쿼리가 <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName> 메서드를 사용하는 [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq-md.md)] 쿼리인 경우에는 매개 변수 형식은 `Expression<Func\<int,bool>>`이겠지만 람다 식은 동일할 것입니다.  식 형식에 대한 자세한 내용은 <xref:System.Linq.Expressions.Expression?displayProperty=fullName>을 참조하십시오.  
  
 [!code-cs[csProgGuideLINQ#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_1.cs)]  
  
## 예제  
 다음 예제에서는 쿼리 식의 메서드 호출에 람다 식을 사용하는 방법을 보여 줍니다.  쿼리 구문으로는 <xref:System.Linq.Enumerable.Sum%2A> 표준 쿼리 연산자를 호출할 수 없기 때문에 람다 식을 사용해야 합니다.  
  
 이 쿼리는 먼저 `GradeLevel` 열거형에 정의되어 있는 등급에 따라 학생을 그룹화합니다.  그런 다음 각 그룹에 대해 각 학생의 총점을 추가합니다.  이 작업에는 `Sum` 연산 두 개가 필요합니다.  내부 `Sum`은 각 학생의 총점을 계산하고 외부 `Sum`은 그룹에 속한 모든 학생의 누계를 계산합니다.  
  
 [!code-cs[csProgGuideLINQ#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_2.cs)]  
  
## 코드 컴파일  
 이 코드를 실행하려면 이 메서드를 복사하여 [방법: 개체 컬렉션 쿼리](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md)에 제공된 `StudentClass`에 붙여 넣은 다음 `Main` 메서드에서 호출합니다.  
  
## 참고 항목  
 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [식 트리](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)