---
title: 익명 형식이 다른 필드를 초기화하는 데 사용되는 필드를 포함하고 있으므로 식 트리로 변환할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: 2f97a0de74428ce42a088644580a78bf8fd99945
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936804"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a>익명 형식이 다른 필드를 초기화하는 데 사용되는 필드를 포함하고 있으므로 식 트리로 변환할 수 없습니다.
컴파일러를 익명 형식의 다른 속성을 초기화 하려면 익명 형식의 속성을 하나 사용 하는 경우에 익명의 식 트리로 변환할을 사용할 수 없습니다. 예를 들어, 다음 코드에서에서 `Prop1` 초기화 목록에서 선언 되 고 그런 다음에 대 한 초기 값으로 사용 `Prop2`합니다.  
  
```vb  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 **오류 ID:** BC36548  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   에 대 한 초기 값을 할당 `Prop1` 으로 지역 변수입니다. 해당 변수를 둘 다 할당할 `Prop1` 고 `Prop2`다음 코드에 표시 된 것 처럼 합니다.  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a>참고자료

[익명 형식 (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
[식 트리(Visual Basic)](../../programming-guide/concepts/expression-trees/index.md)  
[방법: 식 트리를 사용 하 여 동적 쿼리 (Visual Basic)](../../programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md)  