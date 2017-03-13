---
title: "캐스팅 및 형식 변환(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "캐스팅[C#]"
  - "변환[C#], 형식"
  - "형식 변환[C#]"
  - "데이터 형식 변환[C#]"
  - "숫자 변환[C#]"
  - "형식 변환[C#]"
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
caps.latest.revision: 52
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 52
---
# 캐스팅 및 형식 변환(C# 프로그래밍 가이드)
C\#은 컴파일 타임에 정적으로 형식이 지정되므로 변수를 선언하고 나면 해당 형식을 변수의 형식으로 변환하지 않는 한 변수를 다시 선언하거나 다른 형식의 값을 저장하는 데 사용할 수 없습니다.  예를 들어 정수를 임의의 문자열로 변환할 수 없습니다.  따라서 다음 코드에서 볼 수 있는 것처럼 `i`를 정수로 선언한 후에는 해당 변수에 문자열 "Hello"를 할당할 수 없습니다.  
  
```c#  
int i;  
i = "Hello"; // Error: "Cannot implicitly convert type 'string' to 'int'"  
```  
  
 하지만 값을 다른 형식의 변수나 메서드 매개 변수에 복사해야 하는 경우가 있습니다.  예를 들어 `double` 형식의 매개 변수를 사용하는 메서드에 정수 변수를 전달해야 하거나  클래스 변수를 인터페이스 형식의 변수에 할당해야 할 경우가 있습니다.  이런 종류의 작업을 *형식 변환*이라고 합니다.  C\#에서는 다음과 같은 변환을 수행할 수 있습니다.  
  
-   **암시적 변환**: 변환의 형식 안전성이 유지되며 데이터가 손실되지 않으므로 특수한 구문이 필요 없습니다.  작은 정수 형식에서 큰 정수 형식으로의 변환, 파생 클래스에서 기본 클래스로의 변환 등이 여기에 포함됩니다.  
  
-   **명시적 변환\(캐스트\)**: 명시적 변환에는 캐스트 연산자가 필요합니다.  캐스팅은 변환 시 정보가 손실될 수 있거나 다른 이유로 변환이 성공하지 못할 수 있을 때 필요합니다. 일반적인 예제에는 숫자를 정밀도가 낮거나 범위가 작은 형식으로 변환, 기본 클래스 인스턴스를 파생 클래스로 변환하는 것을 포함합니다.  
  
-   **사용자 정의 변환**: 사용자 정의 변환은 기본 클래스\-파생 클래스 관계가 없는 사용자 지정 형식 간의 명시적 변환과 암시적 변환이 가능하도록 사용자가 정의할 수 있는 특수한 메서드를 통해 수행됩니다.  자세한 내용은 [변환 연산자](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)를 참조하십시오.  
  
-   **도우미 클래스를 사용한 변환**: 정수와 <xref:System.DateTime?displayProperty=fullName> 개체 또는 16진수 문자열과 바이트 배열과 같이 서로 호환되지 않는 형식 간에 변환하려면 <xref:System.Int32.Parse%2A?displayProperty=fullName>와 같은 기본 제공 숫자 형식의 <xref:System.BitConverter?displayProperty=fullName> 클래스, <xref:System.Convert?displayProperty=fullName> 클래스 및 `Parse` 메서드를 사용합니다.  자세한 내용은 [방법: 바이트 배열을 정수로 변환](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [방법: 문자열을 숫자로 변환](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) 및 [방법: 16진수 문자열과 숫자 형식 간 변환](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)을 참조하십시오.  
  
## 암시적 변환  
 기본 제공 숫자 형식의 경우 저장되는 값을 자르거나 반올림하지 않고 변수에 저장할 수 있으면 암시적 변환을 수행할 수 있습니다.  예를 들어, [long](../../../csharp/language-reference/keywords/long.md)\(8바이트 정수\) 형식의 변수에는 [int](../../../csharp/language-reference/keywords/int.md)\(32비트 컴퓨터에서 4바이트\)에 저장할 수 있는 모든 값을 저장할 수 있습니다.  다음 예제의 경우 컴파일러에서는 우변에 있는 값을 `bigNum`에 할당하기 전에 암시적으로 `long` 형식으로 변환합니다.  
  
 [!code-cs[csProgGuideTypes#34](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_1.cs)]  
  
 암시적 숫자 변환의 전체 목록은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하십시오.  
  
 참조 형식의 경우 특정 클래스에서 해당 클래스의 직접 또는 간접 기본 클래스나 인터페이스로의 암시적 변환이 항상 존재합니다.  이 경우 파생 클래스는 항상 기본 클래스의 모든 멤버를 포함하기 때문에 특별한 구문이 필요 없습니다.  
  
```  
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## 명시적 변환  
 하지만 정보가 손실될 위험이 없이 변환을 수행할 수 없는 경우에는 컴파일러에서 *캐스트*라는 명시적 변환을 수행하도록 합니다.  캐스트는 컴파일러에게 변환을 수행하는 의도와 데이터 손실이 발생할 수 있다는 것을 인식하고 있다는 명시적으로 알리는 방법입니다.  캐스팅을 수행하려면 변환할 값이나 변수 앞에 캐스팅하려는 형식을 괄호로 둘러쌉니다.  다음 프로그램에서는 [double](../../../csharp/language-reference/keywords/double.md)을 [int](../../../csharp/language-reference/keywords/int.md)로 캐스팅합니다.  캐스팅하지 않으면 프로그램이 컴파일되지 않습니다.  
  
 [!code-cs[csProgGuideTypes#2](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_2.cs)]  
  
 허용되는 명시적 숫자 변환의 목록은 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)를 참조하십시오.  
  
 참조 형식의 경우 기본 형식을 파생 형식으로 변환해야 한다면 명시적 캐스트가 필요합니다.  
  
```c#  
// Create a new derived type.  
Giraffe g = new Giraffe();  
  
// Implicit conversion to base type is safe.  
Animal a = g;  
  
// Explicit conversion is required to cast back  
// to derived type. Note: This will compile but will  
// throw an exception at run time if the right-side  
// object is not in fact a Giraffe.  
Giraffe g2 = (Giraffe) a;  
```  
  
 참조 형식 사이에 캐스트 연산을 수행하면 내부 개체의 런타임 형식은 변경되지 않고 해당 개체에 대한 참조로 사용되는 값의 형식만 변경됩니다.  자세한 내용은 [다형성](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)를 참조하십시오.  
  
## 런타임의 형식 변환 예외  
 일부 참조 형식 변환에서는 컴파일러가 캐스트의 유효성 여부를 확인하지 못합니다.  따라서 올바르게 컴파일된 캐스트 작업이 런타임에 실패할 수 있습니다.  다음 예제에서 볼 수 있는 것처럼, 런타임에 실패하는 형식 캐스트는 <xref:System.InvalidCastException>을 throw하게 됩니다.  
  
 [!code-cs[csProgGuideTypes#41](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_3.cs)]  
  
 C\#은 캐스팅을 실제로 수행하기 전에 호환성을 테스트할 수 있도록 [is](../../../csharp/language-reference/keywords/is.md) 및 [as](../../../csharp/language-reference/keywords/as.md) 연산자를 제공합니다.  자세한 내용은 [방법: AS 및 IS 연산자를 사용한 안전한 캐스팅](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md)를 참조하십시오.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 중요 설명서 장  
 [변수에 대 한 자세한](란?LinkId%20=%20221230) 에서 [처음 Visual C\# 2010](란?LinkId%20=%20221214)  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [형식](../../../csharp/programming-guide/types/index.md)   
 [\(\) 연산자](../../../csharp/language-reference/operators/invocation-operator.md)   
 [explicit](../../../csharp/language-reference/keywords/explicit.md)   
 [implicit](../../../csharp/language-reference/keywords/implicit.md)   
 [변환 연산자](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)   
 [Generalized Type Conversion](../Topic/Generalized%20Type%20Conversion.md)   
 [Exported Type Conversion](http://msdn.microsoft.com/ko-kr/1dfe55f4-07a2-4b61-aabf-a8cf65783a6b)   
 [방법: 문자열을 숫자로 변환](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)