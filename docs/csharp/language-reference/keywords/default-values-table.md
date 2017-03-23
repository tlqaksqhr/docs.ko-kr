---
title: "기본값 표(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "생성자[C#], 반환 값"
  - "키워드[C#], new"
  - "기본 생성자[C#]"
  - "기본값[C#]"
  - "값 형식[C#], 초기화"
  - "변수[C#], 값 형식"
  - "생성자[C#], 기본 생성자"
  - "형식[C#], 기본 생성자 반환 값"
ms.assetid: 4af2c1df-9e3a-48c1-83ac-b192986fc5bc
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# 기본값 표(C# 참조)
다음 표에서는 기본 생성자가 반환하는 값 형식의 기본값을 보여 줍니다.  예를 들어, 다음과 같이 `new` 연산자를 사용하여 기본 생성자를 호출합니다.  
  
```  
int myInt = new int();  
```  
  
 위의 문은 다음 문과 동일한 효과를가집니다.  
  
```  
int myInt = 0;  
```  
  
 C\#에서는 초기화되지 않은 변수를 사용할 수 없습니다.  
  
|값 형식|기본값|  
|----------|---------|  
|[bool](../../../csharp/language-reference/keywords/bool.md)|`false`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|0|  
|[char](../../../csharp/language-reference/keywords/char.md)|'\\0'|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|0.0M|  
|[double](../../../csharp/language-reference/keywords/double.md)|0.0D|  
|[enum](../../../csharp/language-reference/keywords/enum.md)|식 \(E\)0으로 계산된 값입니다. 여기서 E는 열거형 식별자입니다.|  
|[float](../../../csharp/language-reference/keywords/float.md)|0.0F|  
|[int](../../../csharp/language-reference/keywords/int.md)|0|  
|[long](../../../csharp/language-reference/keywords/long.md)|0L|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|0|  
|[short](../../../csharp/language-reference/keywords/short.md)|0|  
|[struct](../../../csharp/language-reference/keywords/struct.md)|모든 값 형식 필드를 기본값으로 설정하고 모든 참조 형식 필드를 `null`로 설정하여 계산된 값입니다.|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|0|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|0|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|0|  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [값 형식 표](../../../csharp/language-reference/keywords/value-types-table.md)   
 [값 형식](../../../csharp/language-reference/keywords/value-types.md)   
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [형식 참조 테이블](../../../csharp/language-reference/keywords/reference-tables-for-types.md)