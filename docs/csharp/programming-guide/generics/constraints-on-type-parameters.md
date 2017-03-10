---
title: "형식 매개 변수에 대한 제약 조건(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "제네릭[C#], 형식 제약 조건"
  - "형식 제약 조건[C#]"
  - "형식 매개 변수[C#], 제약 조건"
  - "바인딩되지 않은 형식 매개 변수[C#]"
ms.assetid: 141b003e-1ddb-4e1c-bcb2-e1c3870e6a51
caps.latest.revision: 41
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 41
---
# 형식 매개 변수에 대한 제약 조건(C# 프로그래밍 가이드)
제네릭 클래스를 정의하는 경우 클래스를 인스턴스화할 때 클라이언트 코드에서 형식 인수에 사용할 수 있는 형식의 종류에 제약 조건을 적용할 수 있습니다.  클라이언트 코드가 제약 조건에서 허용하지 않는 형식을 사용하여 클래스를 인스턴스화하려고 하면 컴파일 타임 오류가 발생합니다.  이러한 제한을 제약 조건이라고 합니다.  제약 조건은 컨텍스트 키워드 `where`를 사용하여 지정합니다.  다음 표에서는 여섯 가지의 형식 제약 조건을 보여 줍니다.  
  
|제약 조건|설명|  
|-----------|--------|  
|where T: struct|형식 인수가 값 형식이어야 합니다.  <xref:System.Nullable>를 제외한 임의의 값 형식을 지정할 수 있습니다.  자세한 내용은 [Nullable 형식 사용](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)를 참조하십시오.|  
|where T : class|형식 인수가 참조 형식이어야 합니다. 이는 모든 클래스, 인터페이스, 대리자 또는 배열 형식에도 적용됩니다.|  
|where T : new\(\)|형식 인수가 매개 변수 없는 공용 생성자여야 합니다.  다른 제약 조건과 함께 사용하는 경우 `new()` 제약 조건은 마지막에 지정해야 합니다.|  
|where T : \<기본 클래스 이름\>|형식 인수가 지정된 기본 클래스이거나 지정된 기본 클래스에서 파생되어야 합니다.|  
|where T : \<인터페이스 이름\>|형식 인수가 지정된 인터페이스이거나 지정된 인터페이스를 구현해야 합니다.  여러 인터페이스 제약 조건을 지정할 수 있습니다.  제한하는 인터페이스는 제네릭이 될 수도 있습니다.|  
|where T : U|T에 대해 지정한 형식 인수가 U에 대해 지정한 인수이거나 이 인수에서 파생되어야 합니다.|  
  
## 제약 조건 사용 이유  
 제네릭 목록의 항목을 검사하여 그 유효성 여부를 확인하거나 이 항목을 다른 항목과 비교하려는 경우, 컴파일러는 클라이언트 코드에서 지정할 수 있는 모든 형식 인수에 대해 호출해야 할 메서드나 연산자가 지원되는지 확인해야 합니다.  하나 이상의 제약 조건을 제네릭 클래스 정의에 적용하면 이러한 확인이 가능합니다.  예를 들어, 기본 클래스 제약 조건에서는 이 형식의 개체와 이 형식에서 파생된 개체만이 형식 인수로 사용될 수 있음을 컴파일러에 알립니다.  컴파일러에서 이를 확인하면 사용자는 제네릭 클래스에서 해당 형식의 메서드를 호출할 수 있습니다.  제약 조건은 컨텍스트 키워드 `where`를 사용하여 적용됩니다.  다음 코드 예제에서는 기본 클래스 제약 조건을 적용하여 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)의 `GenericList<T>` 클래스에 추가할 수 있는 기능을 보여 줍니다.  
  
 [!code-cs[csProgGuideGenerics#11](../../../csharp/programming-guide/generics/codesnippet/csharp/constraints-on-type-para_1.cs)]  
  
 제약 조건을 사용하면 형식 T의 모든 항목이 항상 `Employee` 개체이거나 `Employee`에서 상속된 개체이므로 제네릭 클래스에서 `Employee.Name` 속성을 사용할 수 있습니다.  
  
 여러 제약 조건을 동일한 형식 매개 변수에 적용할 수 있고 제약 조건 자체가 제네릭 형식일 수도 있습니다. 예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideGenerics#12](../../../csharp/programming-guide/generics/codesnippet/csharp/constraints-on-type-para_2.cs)]  
  
 형식 매개 변수를 제한하면, 허용되는 작업의 수 및 제한하는 형식과 해당 상속 계층 구조의 모든 형식에서 지원하는 메서드에 대해 허용되는 호출의 수를 늘릴 수 있습니다.  따라서 제네릭 클래스나 메서드를 디자인할 때 `System.Object`에서 지원하지 않는 메서드를 호출하거나 제네릭 멤버에 대해 단순한 할당 이상의 작업을 수행하려는 경우에는 형식 매개 변수에 제약 조건을 적용해야 합니다.  
  
 `where T : class` 제약 조건을 적용할 때는 형식 매개 변수에 대해 `==` 및 `!=` 연산자를 사용하지 않아야 합니다. 이러한 연산자에서는 값이 같은지 확인하는 대신 참조가 동일한지만 테스트하기 때문입니다.  인수로 사용되는 형식에서 이러한 연산자를 오버로드한 경우에도 마찬가지입니다.  다음 코드에서는 이러한 경우의 예를 보여 줍니다. <xref:System.String> 클래스에서 `==` 연산자를 오버로드해도 false가 출력됩니다.  
  
 [!code-cs[csProgGuideGenerics#13](../../../csharp/programming-guide/generics/codesnippet/csharp/constraints-on-type-para_3.cs)]  
  
 이러한 방식으로 동작하는 이유는 컴파일 시 컴파일러에는 T가 참조 형식이라는 정보만 제공되므로 모든 참조 형식에 유효한 기본 연산자가 사용되기 때문입니다.  값이 동일한지 테스트하려면 `where T : IComparable<T>` 제약 조건을 함께 적용하고 제네릭 클래스를 생성하는 데 사용되는 모든 클래스에서 해당 인터페이스를 구현하는 것이 좋습니다.  
  
## 여러 매개 변수 제한  
 다음 예제와 같이 여러 매개 변수에 제약 조건을 적용하고 단일 매개 변수에 여러 제약 조건을 적용할 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#64](../../../csharp/programming-guide/generics/codesnippet/csharp/constraints-on-type-para_4.cs)]  
  
## 바인딩되지 않은 형식 매개 변수  
 공용 클래스 `SampleClass<T>{}`의 T와 같이 제약 조건이 없는 형식 매개 변수를 바인딩되지 않은 형식 매개 변수라고 합니다.  바인딩되지 않은 형식 매개 변수에는 다음과 같은 규칙이 적용됩니다.  
  
-   `!=` 및 `==` 연산자를 사용할 수 없습니다. 구체적인 형식 인수에서 이러한 연산자를 지원하리라는 보장이 없기 때문입니다.  
  
-   바인딩되지 않은 형식 매개 변수와 `System.Object` 사이에 변환하거나 이 매개 변수를 임의의 인터페이스 형식으로 명시적으로 변환할 수 있습니다.  
  
-   바인딩되지 않은 형식 매개 변수를 [null](../../../csharp/language-reference/keywords/null.md)과 비교할 수 있습니다.  바인딩되지 않은 매개 변수를 `null`과 비교하는 경우 형식 인수가 값 형식이면 비교 결과로 항상 false가 반환됩니다.  
  
## 제약 조건으로서의 형식 매개 변수  
 일반 형식을 제약 조건으로 사용하면 다음 예제에서와 같이 자체 형식 매개 변수가 있는 멤버 함수에서 해당 매개 변수를 포함 형식의 형식 매개 변수로 제한해야 하는 경우에 유용합니다.  
  
 [!code-cs[csProgGuideGenerics#14](../../../csharp/programming-guide/generics/codesnippet/csharp/constraints-on-type-para_5.cs)]  
  
 위 예제에서 `T`는 `Add` 메서드의 컨텍스트에서는 형식 제약 조건이고 `List` 클래스의 컨텍스트에서는 바인딩되지 않은 형식 매개 변수입니다.  
  
 형식 매개 변수는 제네릭 클래스 정의에서 제약 조건으로도 사용할 수 있습니다.  형식 매개 변수는 다른 형식의 매개 변수와 함께 꺾쇠 괄호 안에 선언되어야 합니다.  
  
 [!code-cs[csProgGuideGenerics#15](../../../csharp/programming-guide/generics/codesnippet/csharp/constraints-on-type-para_6.cs)]  
  
 컴파일러에서는 형식 매개 변수가 `System.Object`에서 파생된다는 점을 제외하고는 이 제약 조건에 대해 어떠한 정보도 알 수 없으므로 형식 매개 변수와 제네릭 클래스를 함께 사용할 필요는 거의 없습니다.  제네릭 클래스에 대해 형식 매개 변수를 제약 조건으로 사용하는 경우로는 두 형식 매개 변수 사이에 반드시 상속 관계가 있도록 정의하는 경우를 들 수 있습니다.  
  
## 참고 항목  
 <xref:System.Collections.Generic>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [제네릭 클래스](../../../csharp/programming-guide/generics/generic-classes.md)   
 [new 제약 조건](../../../csharp/language-reference/keywords/new-constraint.md)