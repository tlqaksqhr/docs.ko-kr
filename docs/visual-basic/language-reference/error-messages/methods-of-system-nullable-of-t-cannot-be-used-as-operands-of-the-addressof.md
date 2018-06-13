---
title: 메서드 &#39;System.Nullable (Of T)&#39; 의 피연산자로 사용할 수 없습니다는 &#39;AddressOf&#39; 연산자
ms.date: 07/20/2015
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords:
- BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
ms.openlocfilehash: 3a3e4fc033f47fb6a72076dff79f1eece8d01a30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594122"
---
# <a name="methods-of-39systemnullableof-t39-cannot-be-used-as-operands-of-the-39addressof39-operator"></a>메서드 &#39;System.Nullable (Of T)&#39; 의 피연산자로 사용할 수 없습니다는 &#39;AddressOf&#39; 연산자
문을 사용 하 여는 `AddressOf` 의 프로시저를 나타내는 피연산자와 연산자는 <xref:System.Nullable%601> 구조입니다.  
  
 **오류 ID:** BC32126  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   프로시저 이름 바꾸기는 `AddressOf` 의 구성원이 아니므로 피연산자로 절 <xref:System.Nullable%601>합니다.  
  
-   메서드를 래핑하는 클래스를 작성 <xref:System.Nullable%601> 사용 하려는 합니다. 다음 예제에서는 `NullableWrapper` 라는 새 메서드를 정의 하는 클래스 `GetValueOrDefault`합니다. 이 새로운 방법을의 구성원이 아니므로 <xref:System.Nullable%601>에 적용할 수 `nullInstance`, 인수에 대 한 nullable 형식의 인스턴스로 `AddressOf`합니다.  
  
```vb  
Module Module1  
  
    Delegate Function Deleg() As Integer  
  
    Sub Main()  
        Dim nullInstance As New Nullable(Of Integer)(1)  
  
        Dim del As Deleg  
  
        ' GetValueOrDefault is a method of the Nullable generic  
        ' type. It cannot be used as an operand of AddressOf.  
        ' del = AddressOf nullInstance.GetValueOrDefault  
  
        ' The following line uses the GetValueOrDefault method  
        ' defined in the NullableWrapper class.  
        del = AddressOf (New NullableWrapper(  
            Of Integer)(nullInstance)).GetValueOrDefault  
  
        Console.WriteLine(del.Invoke())  
    End Sub  
  
    Class NullableWrapper(Of T As Structure)  
        Private m_Value As Nullable(Of T)  
  
        Sub New(ByVal Value As Nullable(Of T))  
            m_Value = Value  
        End Sub  
  
        Public Function GetValueOrDefault() As T  
            Return m_Value.Value  
        End Function  
    End Class  
End Module  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Nullable%601>  
 [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Nullable 값 형식](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
