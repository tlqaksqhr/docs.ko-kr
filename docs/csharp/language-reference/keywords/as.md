---
title: as(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: 092c30a858df7baeb35bdf28bae53802fb0916d4
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172021"
---
# <a name="as-c-reference"></a>as(C# 참조)
`as` 연산자를 사용하여 호환되는 참조 형식 또는 [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md) 간에 특정 형식의 변환을 수행할 수 있습니다. 다음 코드는 예제를 보여 줍니다.  
  
 [!code-csharp[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]  
  
## <a name="remarks"></a>설명  
 `as` 연산자는 캐스트 작업과 비슷합니다. 하지만 변환할 수 없는 경우 `as`는 예외를 발생시키지 않고 `null`을 반환합니다. 다음 예제를 참조하세요.  
  
```csharp  
expression as type  
```  
  
 `expression` 변수가 한 번만 계산된다는 점을 제외하고 코드는 다음 식과 같습니다.  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 `as` 연산자는 참조 변환, nullable 변환 및 boxing 변환만 수행합니다. `as` 연산자는 캐스트 식을 사용하여 수행해야 하는 사용자 정의 변환 등의 기타 변환을 수행할 수 없습니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [is](../../../csharp/language-reference/keywords/is.md)  
 [?: 연산자](../../../csharp/language-reference/operators/conditional-operator.md)  
 [연산자 키워드](../../../csharp/language-reference/keywords/operator-keywords.md)
