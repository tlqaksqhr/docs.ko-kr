---
title: "기본값 표(C# 참조)"
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.assetid: 4af2c1df-9e3a-48c1-83ac-b192986fc5bc
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d034c1daf495c50e299fec4c5bf399652dad08ce
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2017
---
# <a name="default-values-table-c-reference"></a>기본값 표(C# 참조)
다음 표는 기본 생성자에서 반환한 값 형식의 기본값을 보여 줍니다. 기본 생성자는 다음과 같이 `new` 연산자를 사용하여 호출됩니다.

```csharp
int myInt = new int();
```

위의 문은 다음에 오는 문과 동일한 효과가 있습니다.

```csharp
int myInt = 0;
```

C#에서는 초기화되지 않은 변수를 사용할 수 없음에 유의하세요.

|값 형식|기본값|
|----------------|-------------------|
|[bool](../../../csharp/language-reference/keywords/bool.md)|`false`|
|[byte](../../../csharp/language-reference/keywords/byte.md)|0|
|[char](../../../csharp/language-reference/keywords/char.md)|'\0'|
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|M 0|
|[double](../../../csharp/language-reference/keywords/double.md)|0.0D|
|[enum](../../../csharp/language-reference/keywords/enum.md)|식 (E)0으로 생성한 값이며 여기서 E는 열거형 식별자입니다.|
|[float](../../../csharp/language-reference/keywords/float.md)|0.0F|
|[int](../../../csharp/language-reference/keywords/int.md)|0|
|[long](../../../csharp/language-reference/keywords/long.md)|0L|
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|0|
|[short](../../../csharp/language-reference/keywords/short.md)|0|
|[struct](../../../csharp/language-reference/keywords/struct.md)|모든 값 형식 필드를 기본값으로 설정하고 모든 참조 형식 필드를 `null`로 설정하여 생성한 값입니다.|
|[uint](../../../csharp/language-reference/keywords/uint.md)|0|
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|0|
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|0|

## <a name="see-also"></a>참고 항목
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [값 형식 표](../../../csharp/language-reference/keywords/value-types-table.md)  
 [값 형식](../../../csharp/language-reference/keywords/value-types.md)  
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [형식 참조 테이블](../../../csharp/language-reference/keywords/reference-tables-for-types.md)
