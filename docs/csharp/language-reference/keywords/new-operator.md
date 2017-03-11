---
title: "new 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "new 연산자 키워드[C#]"
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# new 연산자(C# 참조)
개체를 만들고 생성자를 호출하는 데 사용됩니다.  예를 들면 다음과 같습니다.  
  
```  
Class1 obj  = new Class1();  
```  
  
 이는 익명 형식의 인스턴스를 만드는 데도 사용됩니다.  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 또한 `new` 연산자는 값 형식에 대한 기본 생성자를 호출하는 데도 사용됩니다.  예를 들면 다음과 같습니다.  
  
```  
int i = new int();  
```  
  
 앞의 문에서 `i`는 `int` 형식의 기본값인 `0`으로 초기화됩니다.  이 문의 결과는 다음 문의 결과와 같습니다.  
  
```  
int i = 0;  
```  
  
 기본값의 전체 목록을 보려면 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)를 참조하십시오.  
  
 모든 값 형식에는 암시적으로 공용 기본 생성자가 포함되기 때문에 [구조체](../../../csharp/language-reference/keywords/struct.md)에 대한 기본 생성자를 선언하면 오류가 발생합니다.  구조체 형식에 대해 매개 변수가 있는 생성자를 선언하여 그 초기 값을 설정할 수 있지만 이 방법은 기본값이 아닌 다른 값이 필요한 경우에만 사용해야 합니다.  
  
 구조체와 같은 값 형식 개체는 스택에 만들어지고 클래스 같은 참조 형식 개체는 힙에 만들어집니다.  두 형식의 개체는 모두 자동으로 소멸됩니다. 그러나 값 형식을 기반으로 한 개체는 범위를 벗어날 때 소멸되는 반면 참조 형식을 기반으로 한 개체는 이에 대한 마지막 참조를 제거한 후에 지정되지 않은 임의의 시간에 소멸된다는 점에서 차이가 있습니다.  많은 용량의 메모리, 파일 핸들 또는 네트워크 연결 같은 고정된 리소스를 사용하는 참조 형식의 경우 개체가 가능한 한 빨리 소멸되도록 명확한 종료 방식을 사용하는 것이 좋을 수도 있습니다.  자세한 내용은 [using 문](../../../csharp/language-reference/keywords/using-statement.md)를 참조하십시오.  
  
 `new` 연산자는 오버로드되지 않습니다.  
  
 `new` 연산자가 메모리 할당에 실패하면 <xref:System.OutOfMemoryException> 예외를 throw합니다.  
  
## 예제  
 다음 예제에서는 `new` 연산자를 사용하여 `struct` 개체 및 클래스 개체를 만들어 초기화한 다음 값을 대입합니다.  그러면 기본값과 할당된 값이 표시됩니다.  
  
 [!code-cs[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsOperator/csrefKeywordsOperators.cs#7)]  
  
 이 예제에서 문자열의 기본값은 `null`입니다.  따라서 값이 표시되지 않습니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [연산자 키워드](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [익명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)