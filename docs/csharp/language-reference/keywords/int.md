---
title: "int(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "int_CSharpKeyword"
  - "int"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "int 키워드[C#]"
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# int(C# 참조)
`int` 키워드는 다음 표에 표시된 크기와 범위에 따라 값을 저장하는 정수 계열 형식을 나타냅니다.  
  
|형식|범위|크기|.NET Framework 형식|기본값|  
|--------|--------|--------|-----------------------|---------|  
|`int`|\-2,147,483,648 ~ 2,147,483,647|부호 있는 32비트 정수|<xref:System.Int32?displayProperty=fullName>|0|  
  
## 리터럴  
 다음 예제에서와 같이 `int` 형식 변수를 선언하고 초기화할 수 있습니다.  
  
```  
  
int i = 123;  
```  
  
 정수 리터럴에 접미사가 없는 경우 해당 정수 리터럴의 형식은 그 값이 표현될 수 있는 형식인 `int`, [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md) 중에서 첫째 형식입니다.  이 예제에서 정수 리터럴의 형식은 `int`입니다.  
  
## 변환  
 `int`에서 [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로의 미리 정의된 암시적 변환이 있습니다.  예를 들면 다음과 같습니다.  
  
```  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) 또는 [char](../../../csharp/language-reference/keywords/char.md)에서 `int`로의 암시적 변환이 미리 정의되어 있습니다.  예를 들어, 캐스트를 사용하지 않으면 다음 대입문에서 컴파일 오류가 발생합니다.  
  
```  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 또한 부동 소수점 형식에서 `int`로의 암시적 변환은 없습니다.  예를 들어, 다음 문에서 명시적 캐스트를 사용하지 않으면 컴파일러 오류가 발생합니다.  
  
```  
  
        int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 부동 소수점 형식 및 정수 계열 형식이 함께 사용되는 산술식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하십시오.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 <xref:System.Int32>   
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)