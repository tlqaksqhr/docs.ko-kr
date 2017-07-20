---
title: "sizeof(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
dev_langs:
- CSharp
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
caps.latest.revision: 20
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7a1944caceaba3ffb8d83a8f67e5ef2975bf9644
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="sizeof-c-reference"></a>sizeof(C# 참조)
관리되지 않는 형식의 크기(바이트)를 가져오는 데 사용됩니다. 관리되지 않는 형식에는 뒤에 나오는 표에 나열된 기본 제공 형식과 다음 형식이 포함됩니다.  
  
-   열거형  
  
-   포인터 형식  
  
-   참조 형식인 필드 또는 속성을 포함하지 않는 사용자 정의 구조체  
  
 다음 예제에서는 `int`의 크기를 검색하는 방법을 보여 줍니다.  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a>주의  
 C# 버전 2.0부터 기본 제공 형식에 `sizeof`를 적용하기 위해 [비안전](../../../csharp/language-reference/keywords/unsafe.md) 모드를 사용할 필요가 없습니다.  
  
 `sizeof` 연산자를 오버로드할 수 없습니다. `sizeof` 연산자에서 반환되는 값은 `int` 형식입니다. 다음 표에서는 특정 기본 제공 형식이 피연산자로 포함된 `sizeof` 식을 대체하는 상수 값을 보여 줍니다.  
  
|식|상수 값|  
|----------------|--------------------|  
|`sizeof(sbyte)`|1|  
|`sizeof(byte)`|1|  
|`sizeof(short)`|2|  
|`sizeof(ushort)`|2|  
|`sizeof(int)`|4|  
|`sizeof(uint)`|4|  
|`sizeof(long)`|8|  
|`sizeof(ulong)`|8|  
|`sizeof(char)`|2(유니코드)|  
|`sizeof(float)`|4|  
|`sizeof(double)`|8|  
|`sizeof(decimal)`|16|  
|`sizeof(bool)`|1|  
  
 구조체를 비롯한 다른 모든 형식의 경우 `sizeof` 연산자는 안전하지 않은 코드 블록에서만 사용할 수 있습니다. <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> 메서드를 사용할 수도 있지만 이 메서드에서 반환된 값이 `sizeof`에서 반환된 값과 항상 같지는 않습니다. <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName>은 형식이 마샬링된 후의 크기를 반환하는 반면, `sizeof`는 안쪽 여백을 포함하여 공용 언어 런타임에 의해 할당된 크기를 반환합니다.  
  
## <a name="example"></a>예제  
 [!code-cs[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [연산자 키워드](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [enum](../../../csharp/language-reference/keywords/enum.md)   
 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [구조체](../../../csharp/programming-guide/classes-and-structs/structs.md)   
 [상수](../../../csharp/programming-guide/classes-and-structs/constants.md)
