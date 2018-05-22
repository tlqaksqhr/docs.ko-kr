---
title: 기본값 표(C# 참조)
description: 기본 생성자에서 반환한 값 형식의 기본값에 대해 알아봅니다.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.openlocfilehash: 634a55304534b4269487f29be1fbb4930f51d8ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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
|[bool](bool.md)|`false`|
|[byte](byte.md)|0|
|[char](char.md)|'\0'|
|[decimal](decimal.md)|0M|
|[double](double.md)|0.0D|
|[enum](enum.md)|식 (E)0으로 생성한 값이며 여기서 E는 열거형 식별자입니다.|
|[float](float.md)|0.0F|
|[int](int.md)|0|
|[long](long.md)|0L|
|[sbyte](sbyte.md)|0|
|[short](short.md)|0|
|[struct](struct.md)|모든 값 형식 필드를 기본값으로 설정하고 모든 참조 형식 필드를 `null`로 설정하여 생성한 값입니다.|
|[uint](uint.md)|0|
|[ulong](ulong.md)|0|
|[ushort](ushort.md)|0|

## <a name="see-also"></a>참고 항목
 [C# 참조](../index.md)  
 [C# 프로그래밍 가이드](../../programming-guide/index.md)  
 [값 형식 표](value-types-table.md)  
 [값 형식](value-types.md)  
 [기본 제공 형식 표](built-in-types-table.md)  
 [형식 참조 테이블](reference-tables-for-types.md)
