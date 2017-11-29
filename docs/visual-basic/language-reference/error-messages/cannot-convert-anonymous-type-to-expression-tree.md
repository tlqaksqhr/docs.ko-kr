---
title: "익명 형식이 다른 필드를 초기화하는 데 사용되는 필드를 포함하고 있으므로 식 트리로 변환할 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords: BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c2cf8a40060359393807cfb648c46fef9ed853af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a>익명 형식이 다른 필드를 초기화하는 데 사용되는 필드를 포함하고 있으므로 식 트리로 변환할 수 없습니다.
익명 형식의 한 속성은 익명 형식의 다른 속성을 초기화 하는 데 사용 하는 경우 컴파일러는 익명의 식 트리로 변환할을 허용 하지 않습니다. 예를 들어, 다음 코드에서에서 `Prop1` 초기화 목록에서 선언 되 고 다음에 대 한 초기 값으로 사용 `Prop2`합니다.  
  
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
  
-   에 대 한 초기 값을 할당 `Prop1` 지역 변수에 합니다. 둘 다에 해당 변수에 할당 `Prop1` 및 `Prop2`다음 코드에 나온 것 처럼 합니다.  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [식 트리](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)  
 [방법: 식 트리를 사용하여 동적 쿼리 빌드](http://msdn.microsoft.com/library/1e37e0cc-eef3-48bb-8b69-3adabf322735)
