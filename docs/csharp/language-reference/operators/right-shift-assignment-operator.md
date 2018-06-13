---
title: '&gt;&gt;= 연산자(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: ccc3f688d985b9e35404550f0c53a7acf8095dd5
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171420"
---
# <a name="gtgt-operator-c-reference"></a>&gt;&gt;= 연산자(C# 참조)
오른쪽 시프트 대입 연산자입니다.  
  
## <a name="remarks"></a>설명  
 다음 형태의 식이 있다고 가정합니다.  
  
```csharp  
x >>= y  
```  
  
 이 식은 다음과 같이 계산됩니다.  
  
```csharp  
x = x >> y  
```  
  
 단, `x`가 한 번만 계산됩니다. [>> 연산자](../../../csharp/language-reference/operators/right-shift-operator.md)는 `y`로 지정된 양만큼 `x`를 오른쪽으로 이동합니다.  
  
 >>= 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [>> 연산자](../../../csharp/language-reference/operators/right-shift-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
