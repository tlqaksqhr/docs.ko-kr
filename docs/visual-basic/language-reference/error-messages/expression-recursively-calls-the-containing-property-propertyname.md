---
title: 식이 재귀적으로 포함 하는 속성을 호출 &#39; &lt;propertyname&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: f14e2645772b22a8f6ff2385dcd316a42d1d5cf0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="expression-recursively-calls-the-containing-property-39ltpropertynamegt39"></a>식이 재귀적으로 포함 하는 속성을 호출 &#39; &lt;propertyname&gt;&#39;
문은 `Set` 프로시저 속성 정의의 값을 속성의 이름에 저장 합니다.  
  
 정의 하는 속성의 값을 보유 하는 것이 좋습니다는 `Private` 속성의 컨테이너에 변수 둘 다에서 사용 하는 `Get` 및 `Set` 프로시저입니다. `Set` 프로시저 해야이 들어오는 값을 저장 한 다음 `Private` 변수입니다.  
  
 `Get` 프로시저 처럼 동작는 `Function` 프로시저, 속성 이름에 값을 할당 하 고 발생 하 여 컨트롤을 반환할 수 있도록는 `End Get` 문. 그러나 권장 되는 방법 포함 하도록는 `Private` 에 값으로 변수는 [Return 문을](../../../visual-basic/language-reference/statements/return-statement.md)합니다.  
  
 `Set` 프로시저 처럼 동작는 `Sub` 프로시저에서 값을 반환 하지 않습니다. 따라서 프로시저 또는 속성 이름에 내에서 특별 한 의미는 `Set` 프로시저에 값을 저장할 수 없습니다.  
  
 다음 예제에는 뒤에 권장 되는 방법으로이 오류를 일으킬 수 있는 방법을 보여 줍니다.  
  
```  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 하십시오 [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** BC42026  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   앞의 예제와 같이 한 권장된 접근 방식을 사용 하도록 속성 정의 다시 작성 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 프로시저](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Set 문](../../../visual-basic/language-reference/statements/set-statement.md)
