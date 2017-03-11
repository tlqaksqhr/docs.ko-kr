---
title: "long(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "long_CSharpKeyword"
  - "long"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "long 키워드[C#]"
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# long(C# 참조)
`long` 키워드는 다음 표에 표시된 크기와 범위에 따라 값을 저장하는 정수 계열 형식을 나타냅니다.  
  
|형식|범위|크기|.NET Framework 형식|  
|--------|--------|--------|-----------------------|  
|`long`|–9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807|부호 있는 64비트 정수|<xref:System.Int64?displayProperty=fullName>|  
  
## 리터럴  
 다음 예제에서와 같이 `long` 변수를 선언하고 초기화할 수 있습니다.  
  
```  
  
long long1 = 4294967296;  
```  
  
 정수 리터럴에 접미사가 없는 경우 해당 정수 리터럴의 형식은 그 값이 표현될 수 있는 형식인 [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), `long`, [ulong](../../../csharp/language-reference/keywords/ulong.md) 중에서 첫째 형식입니다.  앞의 예제에서 정수 리터럴의 형식은 [uint](../../../csharp/language-reference/keywords/uint.md)의 범위를 초과하기 때문에 `long`입니다. 정수 계열 형식의 저장 크기에 대해서는 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)를 참조하십시오.  
  
 또한 다음과 같이 `long` 형식에 L 접미사를 사용할 수도 있습니다.  
  
```  
  
long long2 = 4294967296L;  
```  
  
 L 접미사를 사용할 경우 리터럴 정수의 형식은 크기에 따라 `long` 또는 [ulong](../../../csharp/language-reference/keywords/ulong.md)으로 결정됩니다.  위의 경우 리터럴 정수는 [ulong](../../../csharp/language-reference/keywords/ulong.md) 범위보다 작기 때문에 `long` 형식입니다.  
  
 접미사는 오버로드된 메서드를 호출할 때 주로 사용됩니다.  예를 들어 다음과 같이 `long` 및 [int](../../../csharp/language-reference/keywords/int.md) 매개 변수를 사용하는 오버로드된 메서드가 있습니다.  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 이 경우, L 접미사를 사용하면 올바른 형식이 호출됩니다. 예를 들면 다음과 같습니다.  
  
```  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5L);   // Calling the method with the long parameter  
```  
  
 같은 식에서 다른 숫자 정수 계열 형식과 함께 `long` 형식을 사용할 수 있습니다. 이런 경우 식은 `long`으로 계산되고 부울 식 또는 관계식의 경우에는 [bool](../../../csharp/language-reference/keywords/bool.md)로 계산됩니다.  예를 들어 다음 식은 `long`으로 계산됩니다.  
  
```  
898L + 88  
```  
  
> [!NOTE]
>  소문자 "l"도 접미사로 사용할 수 있습니다.  그러나 이 접미사는 숫자 "1"과 쉽게 혼동될 수 있기 때문에 컴파일러 경고가 발생합니다. 혼동을 피하려면 "L"을 사용하는 것이 좋습니다.  
  
 부동 소수점 형식 및 정수 계열 형식이 함께 사용되는 산술식에 대한 내용은 [double](../../../csharp/language-reference/keywords/double.md) 및 [float](../../../csharp/language-reference/keywords/float.md)을 참조하십시오.  
  
## 변환  
 `long`에서 [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로의 암시적 변환이 미리 정의되어 있습니다.  그 외의 다른 경우에는 캐스트를 사용해야 합니다.  예를 들어, 명시적 캐스트를 사용하지 않으면 다음 문에서 컴파일 오류가 발생합니다.  
  
```  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) 또는 [char](../../../csharp/language-reference/keywords/char.md)에서 `long`으로의 암시적 변환이 미리 정의되어 있습니다.  
  
 또한 부동 소수점 형식에서 `long`으로의 암시적 변환은 없습니다.  예를 들어, 다음 문에서 명시적 캐스트를 사용하지 않으면 컴파일러 오류가 발생합니다.  
  
```  
  
        long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 <xref:System.Int64>   
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)