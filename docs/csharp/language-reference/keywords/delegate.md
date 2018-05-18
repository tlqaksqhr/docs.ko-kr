---
title: delegate(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
ms.openlocfilehash: 923d746927063490236a721e8d2600889084dac0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="delegate-c-reference"></a>delegate(C# 참조)
delegate 형식의 선언은 메서드 시그니처와 유사합니다. 반환 값이 있으며 모든 형식의 매개 변수를 개수에 관계없이 사용할 수 있습니다.  
  
```  
public delegate void TestDelegate(string message);  
public delegate int TestDelegate(MyType m, long num);  
```  
  
 `delegate`는 명명된 메서드나 무명 메서드를 캡슐화하는 데 사용할 수 있는 참조 형식입니다. 대리자는 C++의 함수 포인터와 비슷하지만 형식 안전성과 보안성을 제공한다는 점이 다릅니다. 대리자 적용에 대해서는 [대리자](../../../csharp/programming-guide/delegates/index.md) 및 [제네릭 대리자](../../../csharp/programming-guide/generics/generic-delegates.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 대리자는 [이벤트](../../../csharp/programming-guide/events/index.md)의 기반이 됩니다.  
  
 대리자는 명명된 메서드나 무명 메서드와 연결하여 인스턴스화할 수 있습니다. 자세한 내용은 [명명된 메서드](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) 및 [무명 메서드](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)를 참조하세요.  
  
 대리자는 호환되는 반환 형식 및 입력 매개 변수가 있는 메서드나 람다 식을 사용하여 인스턴스화해야 합니다. 메서드 시그니처에서 허용되는 가변성 수준에 대한 자세한 내용은 [대리자의 가변성](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)을 참조하세요. 무명 메서드에서 사용하기 위해 메서드에 연결할 대리자와 코드를 함께 선언합니다. 대리자를 인스턴스화하는 두 가지 방법은 이 섹션에서 설명합니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)  
 [대리자](../../../csharp/programming-guide/delegates/index.md)  
 [이벤트](../../../csharp/programming-guide/events/index.md)  
 [명명된 메서드 및 무명 메서드가 있는 대리자](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
 [무명 메서드](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
