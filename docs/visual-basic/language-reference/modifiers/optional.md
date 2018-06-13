---
title: Optional(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: f88020c7407fb9c91e06bc2ee177773171e344fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599306"
---
# <a name="optional-visual-basic"></a>Optional(Visual Basic)
프로시저가 호출 될 때 프로시저 인수를 생략할 수 있도록 지정 합니다.  
  
## <a name="remarks"></a>설명  
 각 선택적 매개 변수를 상수 식의 매개 변수 값을 기본값으로 지정 해야 합니다. 식이 계산 되는 경우 [Nothing](../../../visual-basic/language-reference/nothing.md), 값 데이터 형식의 기본 값 매개 변수의 값을 기본값으로 사용 됩니다.  
  
 선택적 매개 변수를 포함 하는 매개 변수 목록, 그 다음에 오는 모든 매개 변수에 선택적 수도 있어야 합니다.  
  
 `Optional` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
-   [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  또는 선택적 매개 변수 없이 프로시저를 호출할 때 위치 또는 이름으로 인수를 전달할 수 있습니다. 자세한 내용은 참조 [이름 및 위치도 인수 전달](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)합니다.  
  
> [!NOTE]
>  오버 로드를 사용 하 여 선택적 매개 변수가 있는 프로시저를 정의할 수도 있습니다. 하나의 선택적 매개 변수를 설정한 경우에 프로시저, 매개 변수를 허용 하 고 다른 하나는 하지 않는 두 개의 오버 로드 된 버전을 정의할 수 있습니다. 자세한 내용은 참조 [프로시저 오버 로드](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 선택적 매개 변수가 있는 프로시저를 정의 합니다.  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 위치로 전달 된 인수를 사용 하 고 이름으로 전달 된 인수와 함께 프로시저를 호출 하는 방법을 보여 줍니다. 프로시저에는 두 가지 선택적 매개 변수입니다.  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [선택적 매개 변수](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [키워드](../../../visual-basic/language-reference/keywords/index.md)
