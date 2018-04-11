---
title: where(제네릭 형식 제약 조건)(C# 참조)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f2b7b159689aa771d3f9d59e3b1dd340c85b1d79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="where-generic-type-constraint-c-reference"></a>where(제네릭 형식 제약 조건)(C# 참조)
제네릭 형식 정의에서 `where` 절은 제네릭 선언에 정의된 형식 매개 변수의 인수로 사용할 수 있는 형식에 대한 제약 조건을 지정하는 데 사용됩니다. 예를 들어 형식 매개 변수 `T`가 <xref:System.IComparable%601> 인터페이스를 구현하도록 제네릭 클래스 `MyGenericClass`를 선언할 수 있습니다.  
  
```csharp  
public class MyGenericClass<T> where T:IComparable { }  
```  
  
> [!NOTE]
>  쿼리 식의 where 절에 대한 자세한 내용은 [where 절](../../../csharp/language-reference/keywords/where-clause.md)을 참조하세요.  
  
 인터페이스 제약 조건 외에도 `where` 절에는 기본 클래스 제약 조건을 포함할 수 있습니다. 여기서는 제네릭 형식에 대한 형식 인수로서 사용할 수 있도록, 지정된 클래스를 기본 클래스로(또는 해당 클래스 자체로) 형식에 포함하도록 명시합니다. 그러한 제약 조건이 사용되는 경우 해당 형식 매개 변수에 대한 다른 제약 조건 앞에 나타나야 합니다.  
  
 [!code-csharp[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]  
  
 `where` 절에 생성자 제약 조건이 포함될 수도 있습니다. 새 연산자를 사용하여 형식 매개 변수의 인스턴스를 만들 수 있습니다. 그러나 그렇게 하려면 생성자 제약 조건 `new()`로 형식 매개 변수를 제한해야 합니다. [new () 제약 조건](../../../csharp/language-reference/keywords/new-constraint.md)을 사용하면 컴파일러는 제공된 인수에 액세스 가능하고 매개 변수가 없는 생성자(또는 기본 생성자)가 있어야 한다는 것을 알게 됩니다. 예:  
  
 [!code-csharp[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]  
  
 `new()` 제약 조건은 `where` 절 맨 끝에 나타납니다.  
  
 형식 매개 변수가 여러 개이면 각 형식 매개 변수에 하나의 `where` 절을 사용합니다. 예를 들면 다음과 같습니다.  
  
 [!code-csharp[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]  
  
 제약 조건을 다음과 같이 제네릭 메서드의 형식 매개 변수에 첨부할 수도 있습니다.  
  
```csharp  
public bool MyMethod<T>(T t) where T : IMyInterface { }  
```  
  
 대리자에 대한 형식 매개 변수 제약 조건을 설명하는 구문은 메서드의 구문과 동일합니다.  
  
```csharp  
delegate T MyDelegate<T>() where T : new()  
```  
  
 제네릭 대리자에 대한 자세한 내용은 [제네릭 대리자](../../../csharp/programming-guide/generics/generic-delegates.md)를 참조하세요.  
  
 제약 조건의 구문 및 사용에 대한 자세한 내용은 [형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)을 참조하세요.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [new 제약 조건](../../../csharp/language-reference/keywords/new-constraint.md)  
 [형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)
