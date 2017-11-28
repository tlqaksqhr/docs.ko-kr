---
title: "값 형식(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 281b811f2a8a1f2c364405b563f9f103899b492c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="value-types-c-reference"></a>값 형식(C# 참조)
값 형식은 다음 두 가지 기본 범주로 구성됩니다.  
  
-   [구조체](../../../csharp/language-reference/keywords/struct.md)  
  
-   [열거형](../../../csharp/language-reference/keywords/enum.md)  
  
 구조체는 다음 범주로 구분됩니다.  
  
-   숫자 형식  
  
    -   [정수 형식](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [부동 소수점 형식](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
    -   [decimal](../../../csharp/language-reference/keywords/decimal.md)  
  
-   [bool](../../../csharp/language-reference/keywords/bool.md)  
  
-   사용자 정의 구조체입니다.  
  
## <a name="main-features-of-value-types"></a>값 형식의 주요 기능  
 값 형식을 기반으로 하는 변수에는 직접 값이 포함됩니다. 값 형식 변수를 다른 값 형식 변수에 할당하면 포함된 값이 복사됩니다. 이는 개체 자체가 아니라 참조를 개체에 복사하는 참조 형식 변수의 할당과 다릅니다.  
  
 모든 값 형식은 <xref:System.ValueType?displayProperty=nameWithType>에서 암시적으로 파생됩니다.  
  
 참조 형식과 달리 값 형식에서는 새 형식을 파생할 수 없습니다. 그러나 참조 형식과 마찬가지로 구조체가 인터페이스를 구현할 수 있습니다.  
  
 참조 형식과 달리 값 형식에는 `null` 값을 포함할 수 없습니다. 그러나 [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md) 기능은 `null`에 값 형식 할당을 허용하지 않습니다.  
  
 각 값 형식에는 해당 형식의 기본값을 초기화하는 암시적 기본 생성자가 있습니다. 값 형식의 기본값에 대한 자세한 내용은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)를 참조하세요.  
  
## <a name="main-features-of-simple-types"></a>단순 형식의 주요 기능  
 C# 언어의 필수 형식인 모든 단순 형식은 .NET Framework 시스템 형식의 별칭입니다. 예를 들어 [int](../../../csharp/language-reference/keywords/int.md)는 <xref:System.Int32?displayProperty=nameWithType>의 별칭입니다. 별칭의 전체 목록은 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)를 참조하세요.  
  
 해당 피연산자가 모두 단순 형식 상수인 상수 식은 컴파일 시간에 계산됩니다.  
  
 리터럴을 사용하여 단순 형식을 초기화할 수 있습니다. 예를 들어 ‘A’는 `char` 형식의 리터럴이고, 2001은 `int` 형식의 리터럴입니다.  
  
## <a name="initializing-value-types"></a>값 형식 초기화  
 C#의 지역 변수는 사용하기 전에 초기화해야 합니다. 예를 들어 다음 예제와 같이 초기화하지 않고 지역 변수를 선언할 수 있습니다.  
  
```  
int myInt;  
```  
  
 초기화하기 전에는 사용할 수 없습니다. 다음 문을 사용하여 초기화할 수 있습니다.  
  
```  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 이 문은 다음 문과 같습니다.  
  
```  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 물론, 다음 예제와 같이 선언과 초기화를 동일한 문에 포함할 수 있습니다.  
  
```  
int myInt = new int();  
```  
  
 – 또는 –  
  
```  
int myInt = 0;  
```  
  
 [new](../../../csharp/language-reference/keywords/new.md) 연산자를 사용하면 특정 형식의 기본 생성자가 호출되고 변수에 기본값이 할당됩니다. 앞의 예제에서는 기본 생성자가 `0` 값을 `myInt`에 할당했습니다. 기본 생성자를 호출하여 할당된 값에 대한 자세한 내용은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)를 참조하세요.  
  
 사용자 정의 형식의 경우 [new](../../../csharp/language-reference/keywords/new.md)를 사용하여 기본 생성자를 호출합니다. 예를 들어 다음 문은 `Point` 구조체의 기본 생성자를 호출합니다.  
  
```  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 이 호출 후에는 구조체가 한정적으로 할당된 것으로 간주됩니다. 즉, 모든 멤버가 기본값으로 초기화됩니다.  
  
 새 연산자에 대한 자세한 내용은 [new](../../../csharp/language-reference/keywords/new.md)를 참조하세요.  
  
 숫자 형식의 출력에 서식을 지정하는 방법에 대한 자세한 내용은 [숫자 결과 형식 지정 표](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [유형](../../../csharp/language-reference/keywords/types.md)  
 [형식 참조 테이블](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)
