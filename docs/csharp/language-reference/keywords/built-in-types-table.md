---
title: "기본 제공 형식 표(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "기본 제공 C# 형식"
  - "형식[C#], 기본 제공"
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# 기본 제공 형식 표(C# 참조)
다음 표에서는 C\#의 기본 제공 형식에 대한 키워드를 보여 줍니다. 이러한 키워드는 <xref:System> 네임스페이스에 미리 정의된 형식의 별칭입니다.  
  
|C\# 형식|.NET Framework 형식|  
|------------|-----------------------|  
|[bool](../../../csharp/language-reference/keywords/bool.md)|`System.Boolean`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`System.Byte`|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`System.SByte`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`System.Char`|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|`System.Decimal`|  
|[double](../../../csharp/language-reference/keywords/double.md)|`System.Double`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`System.Single`|  
|[int](../../../csharp/language-reference/keywords/int.md)|`System.Int32`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`System.UInt32`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`System.Int64`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`System.UInt64`|  
|[개체](../../../csharp/language-reference/keywords/object.md)|`System.Object`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`System.Int16`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`System.UInt16`|  
|[string](../../../csharp/language-reference/keywords/string.md)|`System.String`|  
  
## 설명  
 위 표에서 `object` 및 `string`을 제외한 모든 형식을 단순 형식이라고 합니다.  
  
 C\# 형식 키워드와 그 별칭은 상호 호환이 가능합니다.  예를 들어, 다음 두 선언 중 하나를 사용하여 정수 변수를 선언할 수 있습니다.  
  
```  
int x = 123;  
System.Int32 x = 123;  
```  
  
 모든 C\# 형식의 실제 형식을 표시하려면 `GetType()` 시스템 메서드를 사용합니다.  예를 들어, 다음 문에서는 `myVariable`의 형식을 나타내는 시스템 별칭이 표시됩니다.  
  
```  
Console.WriteLine(myVariable.GetType());  
```  
  
 [typeof](../../../csharp/language-reference/keywords/typeof.md) 연산자를 사용할 수도 있습니다.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [값 형식](../../../csharp/language-reference/keywords/value-types.md)   
 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)   
 [숫자 결과 형식 지정 표](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)   
 [동적](../../../csharp/language-reference/keywords/dynamic.md)   
 [형식 참조 테이블](../../../csharp/language-reference/keywords/reference-tables-for-types.md)