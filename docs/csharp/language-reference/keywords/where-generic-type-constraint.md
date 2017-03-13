---
title: "where(제네릭 형식 제약 조건)(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "whereconstraint"
  - "whereconstraint_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "where(제네릭 형식 제약 조건)[C#]"
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 10
---
# where(제네릭 형식 제약 조건)(C# 참조)
제네릭 형식 정의에서 `where` 절은 제네릭 선언에 정의된 형식 매개 변수의 인수로 사용할 수 있는 형식에 대해 제약 조건을 지정하는 데 사용됩니다.  예를 들어, 다음과 같이 형식 매개 변수 `T`가 <xref:System.IComparable%601> 인터페이스를 구현하도록 제네릭 클래스 `MyGenericClass`를 선언할 수 있습니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
> [!NOTE]
>  쿼리 식의 where 절에 대한 자세한 내용은 [where 절](../../../csharp/language-reference/keywords/where-clause.md)을 참조하십시오.  
  
 `where` 절에는 인터페이스 제약 조건 외에 기본 클래스 제약 조건도 포함될 수 있습니다. 이 제약 조건은 지정된 클래스를 기본 클래스로 갖거나 지정된 클래스 자체인 형식만 해당 제네릭 형식의 형식 인수로 사용할 수 있도록 제한합니다.  이러한 제약 조건을 사용할 경우에는 해당 형식 매개 변수에 대한 다른 모든 제약 조건 앞에 사용해야 합니다.  
  
 [!code-cs[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]  
  
 `where` 절에는 생성자 제약 조건도 포함될 수 있습니다.  new 연산자를 사용하여 형식 매개 변수의 인스턴스를 만들 수 있지만, 이렇게 하려면 형식 매개 변수를 생성자 제약 조건 `new()`로 제한해야 합니다.  [new\(\) 제약 조건](../../../csharp/language-reference/keywords/new-constraint.md)을 사용하면 컴파일러에서는 제공된 모든 형식 인수가 액세스 가능하고 매개 변수 없는\(또는 기본\) 생성자를 가져야 한다는 것을 알 수 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]  
  
 `new()` 제약 조건은 `where` 절의 마지막에 나와 있습니다.  
  
 형식 매개 변수가 여러 개이면 다음 예제와 같이 `where` 절을 각 형식 매개 변수마다 하나씩 사용합니다.  
  
 [!code-cs[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]  
  
 다음과 같이 제네릭 메서드의 형식 매개 변수에 제약 조건을 연결할 수도 있습니다.  
  
```  
public bool MyMethod<T>(T t) where T : IMyInterface { }  
```  
  
 대리자에 대한 형식 매개 변수 제약 조건을 설명하기 위한 구문은 메서드에 사용하는 구문과 동일합니다.  
  
```  
delegate T MyDelegate<T>() where T : new()  
```  
  
 제네릭 대리자에 대한 자세한 내용은 [제네릭 대리자](../../../csharp/programming-guide/generics/generic-delegates.md)를 참조하십시오.  
  
 제약 조건의 구문 및 사용 방법에 대한 자세한 내용은 [형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)을 참조하십시오.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [new 제약 조건](../../../csharp/language-reference/keywords/new-constraint.md)   
 [형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)