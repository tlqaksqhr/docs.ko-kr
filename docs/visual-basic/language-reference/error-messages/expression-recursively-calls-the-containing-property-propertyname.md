---
title: "포함 하는 속성을 호출 하는 식을 재귀적으로 &quot;&lt;propertyname&gt;&quot; | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42026
- BC42026
dev_langs:
- VB
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ca20bf1a539f2727a80f8e781c1e9ebc5a4a253d
ms.lasthandoff: 03/13/2017

---
# <a name="expression-recursively-calls-the-containing-property-39ltpropertynamegt39"></a>포함 하는 속성을 호출 하는 식을 재귀적으로 '&lt;propertyname&gt;'
문에 `Set` 프로시저 속성 정의의 값을 속성의 이름에 저장 합니다.  
  
 정의 하는 속성의 값을 보유 하는 것이 좋습니다는 `Private` 속성의 컨테이너에 있는 변수 둘 다에서 사용 하는 `Get` 및 `Set` 프로시저입니다. `Set` 프로시저 들어오는 값이 다음 저장 해야 `Private` 변수입니다.  
  
 `Get` 프로시저 처럼 동작는 `Function` 속성 이름에 값을 할당 하 고 발생 하 여 컨트롤을 반환할 수 있도록 프로시저는 `End Get` 문입니다. 그러나 포함 하는 권장 되는 방법, 것은 `Private` 에 값으로 변수는 [Return 문을](../../../visual-basic/language-reference/statements/return-statement.md)합니다.  
  
 `Set` 프로시저 처럼 동작을 `Sub` 프로시저에서 값을 반환 하지 않습니다. 따라서 프로시저 또는 속성 이름에 내에서 특별 한 의미는 `Set` 프로시저에 값을 저장할 수 없습니다.  
  
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
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 하십시오 [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** BC42026  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   앞의 예제와 같이 권장 되는 방법을 사용 하 여 속성 정의 다시 작성 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 프로시저](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Set 문](../../../visual-basic/language-reference/statements/set-statement.md)
