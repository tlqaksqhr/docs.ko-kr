---
title: -&gt; 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: 09d67b8386da371f7d98a8171f60298b316091ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-gt-operator-c-reference"></a>-&gt; 연산자(C# 참조)
`->` 연산자는 포인터 역참조와 멤버 액세스를 결합합니다.  
  
## <a name="remarks"></a>설명  
 다음 형태의 식이 있다고 가정합니다.  
  
```  
x->y  
```  
  
 여기서 `x`는 `T*` 형식의 포인터이고 `y`는 `T`의 멤버입니다. 이 식은 다음 식과 같습니다.  
  
```  
(*x).y  
```  
  
 `->` 연산자는 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)로 표시된 코드에만 사용할 수 있습니다.  
  
 `->` 연산자를 오버로드할 수 없습니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
