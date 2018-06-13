---
title: '&#39;IsNot&#39; 형식의 피연산자 &#39;typename&#39; 만 비교할 수 있게 &#39;Nothing&#39;때문에, &#39;typename&#39; 이 nullable 형식이'
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 44cc17c73b476e5e322b9b58b021bc7bcd63167f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587598"
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a>&#39;IsNot&#39; 형식의 피연산자 &#39;typename&#39; 만 비교할 수 있게 &#39;Nothing&#39;때문에, &#39;typename&#39; 이 nullable 형식이
Nullable로 선언 된 변수에 비교 되었습니다 식을 이외의 `Nothing` 를 사용 하는 `IsNot` 연산자입니다.  
  
 **오류 ID:** BC32128  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  `IsNot` 연산자를 사용하여 nullable 형식을 `Nothing` 이외의 식과 비교하려면 다음 예제와 같이 nullable 형식에서 `GetType` 메서드를 호출하고 그 결과를 식과 비교합니다.  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a>참고 항목  
 [Nullable 값 형식](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [IsNot 연산자](../../../visual-basic/language-reference/operators/isnot-operator.md)
