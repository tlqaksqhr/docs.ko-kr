---
title: 캐스팅 및 형식 변환(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- type conversion [C#]
- data type conversion [C#]
- numeric conversions [C#]
- conversions [C#], type
- casting [C#]
- converting types [C#]
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
ms.openlocfilehash: 0c17fc89d93bdbb01bdef7935e72f8a7d96b0a55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336559"
---
# <a name="casting-and-type-conversions-c-programming-guide"></a>캐스팅 및 형식 변환(C# 프로그래밍 가이드)
C#은 컴파일 시간에 정적으로 형식화되므로 변수가 선언된 후에는 다시 선언되거나 다른 형식의 값을 저장하는 데 사용될 수 없습니다. 단, 형식이 변수의 형식으로 변환될 수 있는 경우는 예외입니다. 예를 들어 정수에서 임의 문자열로의 변환은 없습니다. 따라서 `i`를 정수로 선언한 후에는 다음 코드와 같이 문자열 "Hello"를 할당할 수 없습니다.  
  
```csharp  
int i;  
i = "Hello"; // Error: "Cannot implicitly convert type 'string' to 'int'"  
```  
  
 그러나 다른 형식의 변수 또는 메서드 매개 변수에 값을 복사해야 하는 경우도 있습니다. 예를 들어 매개 변수가 `double`로 형식화된 메서드에 전달해야 하는 정수 변수가 있을 수 있습니다. 또는 인터페이스 형식의 변수에 클래스 변수를 할당해야 할 수 있습니다. 이러한 작업을 *형식 변환*이라고 합니다. C#에서는 다음과 같은 변환을 수행할 수 있습니다.  
  
-   **암시적 변환**: 변환은 형식이 안전하고 데이터가 손실되지 않으므로 특수 구문이 필요하지 않습니다. 예제에는 작은 정수 형식에서 큰 정수 형식으로의 변환 및 파생 클래스에서 기본 클래스로의 변환이 포함됩니다.  
  
-   **명시적 변환(캐스트)**: 명시적 변환에는 캐스트 연산자가 필요합니다. 변환 시 정보가 손실되거나 다른 이유로 변환에 실패할 경우 캐스팅이 필요합니다.  일반적인 예제에는 숫자를 정밀도가 낮거나 범위가 더 작은 형식으로 변환하는 작업과 기본 클래스 인스턴스를 파생 클래스로 변환하는 작업이 포함됩니다.  
  
-   **사용자 정의 변환**: 사용자 정의 변환은 기본 클래스-파생 클래스 관계가 없는 사용자 지정 형식 간의 명시적 및 암시적 변환을 사용하도록 정의할 수 있는 특수 메서드를 통해 수행됩니다. 자세한 내용은 [변환 연산자](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)를 참조하세요.  
  
-   **도우미 클래스를 사용한 변환**: 정수와 <xref:System.DateTime?displayProperty=nameWithType> 개체, 16진수 문자열과 바이트 배열 등 호환되지 않는 형식 간에 변환하려면 <xref:System.BitConverter?displayProperty=nameWithType> 클래스, <xref:System.Convert?displayProperty=nameWithType> 클래스, 기본 제공 숫자 형식(예: <xref:System.Int32.Parse%2A?displayProperty=nameWithType>)의 `Parse` 메서드를 사용할 수 있습니다. 자세한 내용은 [방법: 바이트 배열을 정수로 변환](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [방법: 문자열을 숫자로 변환](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) 및 [방법: 16진수 문자열과 숫자 형식 간 변환](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)을 참조하세요.  
  
## <a name="implicit-conversions"></a>암시적 변환  
 기본 제공 숫자 형식의 경우 저장되는 값이 잘리거나 반올림되지 않고 변수에 맞출 수 있을 때 암시적 변환을 수행할 수 있습니다. 예를 들어 [long](../../../csharp/language-reference/keywords/long.md) 형식의 변수(8바이트 정수)는 [int](../../../csharp/language-reference/keywords/int.md)(32비트 컴퓨터의 4바이트)가 저장할 수 있는 모든 값을 저장할 수 있습니다. 다음 예제에서 컴파일러는 오른쪽의 값을 `long` 형식으로 암시적으로 변환한 후 `bigNum`에 할당합니다.  
  
 [!code-csharp[csProgGuideTypes#34](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_1.cs)]  
  
 모든 암시적 숫자 변환 규칙의 전체 목록은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.  
  
 참조 형식의 경우 클래스에서 직접 또는 간접 기본 클래스나 인터페이스로의 암시적 변환이 항상 존재합니다. 파생 클래스에 항상 기본 클래스의 모든 멤버가 포함되므로 특수 구문이 필요하지 않습니다.  
  
```  
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## <a name="explicit-conversions"></a>명시적 변환  
 그러나 변환을 수행할 때 정보 손실의 위험이 있는 경우에는 컴파일러에서 *캐스트*라는 명시적 변환을 수행해야 합니다. 캐스트는 변환을 수행하고자 하고 데이터 손실이 발생할 가능성을 알고 있음을 컴파일러에 명시적으로 알리는 방법입니다. 캐스트를 수행하려면 변환할 값 또는 변수 앞에 캐스트할 형식을 괄호 안에 지정합니다. 다음 프로그램은 [double](../../../csharp/language-reference/keywords/double.md)을 [int](../../../csharp/language-reference/keywords/int.md)로 캐스트합니다. 캐스트가 없으면 프로그램이 컴파일되지 않습니다.  
  
 [!code-csharp[csProgGuideTypes#2](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_2.cs)]  
  
 허용되는 명시적 숫자 변환 목록은 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)를 참조하세요.  
  
 참조 형식의 경우 기본 형식에서 파생 형식으로 변환해야 할 경우에는 명시적 캐스트가 필요합니다.  
  
```csharp  
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
  
 참조 형식 간 캐스트 작업은 기본 개체의 런타임 형식을 변경하지 않습니다. 참조로 사용되는 값의 형식을 해당 개체로만 변경합니다. 자세한 내용은 [다형성](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)을 참조하세요.  
  
## <a name="type-conversion-exceptions-at-run-time"></a>런타임의 형식 변환 예외  
 일부 참조 형식 변환 시에는 컴파일러에서 캐스트가 유효한지 여부를 확인할 수 없습니다. 제대로 컴파일되는 캐스트 작업이 런타임에 실패할 수 있습니다. 다음 예제와 같이 런타임에 형식 캐스트가 실패하면 <xref:System.InvalidCastException>이 throw됩니다.  
  
 [!code-csharp[csProgGuideTypes#41](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_3.cs)]  
  
 C#에서는 실제로 캐스트를 수행하기 전에 호환성을 테스트할 수 있는 [is](../../../csharp/language-reference/keywords/is.md) 및 [as](../../../csharp/language-reference/keywords/as.md) 연산자를 제공합니다. 자세한 내용은 [방법: AS 및 IS 연산자를 사용한 안전한 캐스트](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md)를 참조하세요.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [유형](../../../csharp/programming-guide/types/index.md)  
 [() 연산자](../../../csharp/language-reference/operators/invocation-operator.md)  
 [explicit](../../../csharp/language-reference/keywords/explicit.md)  
 [implicit](../../../csharp/language-reference/keywords/implicit.md)  
 [변환 연산자](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
 [일반화된 형식 변환](http://msdn.microsoft.com/library/49253ae6-7657-4810-82ab-1176a6feeada)  
 [내보낸 형식 변환](http://msdn.microsoft.com/library/1dfe55f4-07a2-4b61-aabf-a8cf65783a6b)  
 [방법: 문자열을 숫자로 변환](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)
