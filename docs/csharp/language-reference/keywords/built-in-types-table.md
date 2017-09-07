---
title: "기본 제공 형식 표(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: df13a45544491dee9e592a4ab0b90b5235f12abc
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="built-in-types-table-c-reference"></a>기본 제공 형식 표(C# 참조)
다음 표에서는 <xref:System> 네임스페이스에 미리 정의된 형식의 별칭인 기본 제공 C# 형식의 키워드를 보여 줍니다.  
  
|C# 형식|.NET Framework   |  
|--------------|-------------------------|  
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
|[object](../../../csharp/language-reference/keywords/object.md)|`System.Object`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`System.Int16`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`System.UInt16`|  
|[string](../../../csharp/language-reference/keywords/string.md)|`System.String`|  
  
## <a name="remarks"></a>설명  
 `object` 및 `string`을 제외하고 표에 있는 모든 형식을 단순 형식이라고 합니다.  
  
 C# 형식 키워드와 해당 별칭은 서로 바꿔서 사용할 수 있습니다. 예를 들어 다음 선언 중 하나를 사용하여 정수 변수를 선언할 수 있습니다.  
  
```  
int x = 123;  
System.Int32 x = 123;  
```  
  
 C# 형식의 실제 형식을 표시하려면 시스템 메서드 `GetType()`을 사용합니다. 예를 들어 다음 문은 `myVariable`의 형식을 나타내는 시스템 별칭을 표시합니다.  
  
```  
Console.WriteLine(myVariable.GetType());  
```  
  
 [typeof](../../../csharp/language-reference/keywords/typeof.md) 연산자를 사용할 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [값 형식](../../../csharp/language-reference/keywords/value-types.md)   
 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)   
 [숫자 결과 형식 지정 표](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [형식 참조 테이블](../../../csharp/language-reference/keywords/reference-tables-for-types.md)

