---
title: 변수 형식이 &#39; &lt;variablename&gt; &#39; 괄호로 묶인 범위 내의 필드에 바인딩되어 있기 때문에 유추 되지 것입니다
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: cb423e8dcced6956eb86d484607915030c91412b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="the-type-for-variable-39ltvariablenamegt39-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a>변수 형식이 &#39; &lt;variablename&gt; &#39; 괄호로 묶인 범위 내의 필드에 바인딩되어 있기 때문에 유추 되지 것입니다
변수 형식이 '\<variablename >'의 필드는 바깥쪽 범위에 바인딩되어 있기 때문에 유추 되지 것입니다. 이름을 변경 하거나 '\<variablename >', 하거나 정규화 된 이름 (예: 'Me.variablename' 또는 'MyBase.variablename')를 사용 합니다.  
  
 코드에서 루프 제어 변수는 클래스 또는 다른 바깥쪽 범위의 필드와 이름이 동일한 합니다. 제어 변수 없이 사용 되기 때문에 프로그램 `As` 절 바깥쪽 범위의 필드에 바인딩된 및 컴파일러에 대 한 새 변수를 만들 하지 않거나 해당 형식을 유추 하도록 합니다.  
  
 다음 예에서 `Index`, 제어 변수는 `For` 문, 바인딩되는 `Index` 필드에 `Customer` 클래스. 컴파일러 제어 변수의 대 한 새 변수를 만들지 않습니다 `Index` 또는 해당 형식을 유추 하도록 합니다.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
    ' The following line will raise this warning.  
        For Index = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 오류로 처리 하는 방법에 대 한 정보를 참조 하십시오. [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** BC42110  
  
### <a name="to-address-this-warning"></a>이 경고를 해결하려면  
  
-   클래스의 필드 이름을 아닌 식별자에 해당 이름을 변경 하 여 로컬 루프 제어 변수를 확인 합니다.  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   바인딩되도록 합니다 루프 제어 변수 클래스 필드에 접두사로 `Me.` 변수 이름에 있습니다.  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   지역 형식 유추를 사용 하는 대신 사용 하 여 프로그램 `As` 절 루프 제어 변수의 형식을 지정 합니다.  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a>예제  
 다음 코드에에서는 첫 번째 수정 내용과 함께 앞의 예를 보여줍니다.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
        For I = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a>참고 항목  
 [Option Infer 문](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [방법: 개체의 현재 인스턴스 참조](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)  
 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Me, My, MyBase 및 MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
