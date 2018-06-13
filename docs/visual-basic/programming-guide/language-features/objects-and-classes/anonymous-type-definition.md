---
title: 익명 형식 정의(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 179fb9773fde2631666498d54894037b2bbfd087
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649622"
---
# <a name="anonymous-type-definition-visual-basic"></a>익명 형식 정의(Visual Basic)
익명 형식의 인스턴스 선언에 대 한 응답, 컴파일러는 형식에 대 한 지정 된 속성을 포함 하는 새 클래스 정을 만듭니다.  
  
## <a name="compiler-generated-code"></a>컴파일러에서 생성 된 코드  
 다음과 같이 정의 대 한 `product`, 컴파일러는 속성을 포함 하는 새 클래스 정의 만듭니다 `Name`, `Price`, 및 `OnHand`합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#25](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_1.vb)]  
  
 클래스 정의 다음과 유사한 속성 정의 포함합니다. 없는 `Set` 키 속성에 대 한 메서드. 키 속성의 값은 읽기 전용입니다.  
  
```vb  
Public Class $Anonymous1  
    Private _name As String  
    Private _price As Double  
    Private _onHand As Integer  
     Public ReadOnly Property Name() As String  
        Get  
            Return _name  
        End Get  
    End Property  
  
    Public ReadOnly Property Price() As Double  
        Get  
            Return _price  
        End Get  
    End Property  
  
    Public Property OnHand() As Integer  
        Get  
            Return _onHand  
        End Get  
        Set(ByVal Value As Integer)  
            _onHand = Value  
        End Set  
    End Property  
  
End Class  
```  
  
 또한 익명 형식 정의 기본 생성자를 포함 합니다. 매개 변수를 필요로 하는 생성자는 허용 되지 않습니다.  
  
 형식 정의에서 상속 되며, 세 가지 멤버를 재정의 무명 형식 선언 키 속성이 하나 이상 들어 있을 경우 <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, 및 <xref:System.Object.ToString%2A>합니다. 만 키 속성이 없는 선언 된 경우 <xref:System.Object.ToString%2A> 재정의 됩니다. 재정의 다음 기능을 제공 합니다.  
  
-   `Equals` 반환 `True` 두 익명 형식 인스턴스는 동일한 인스턴스 또는 다음 조건을 충족 하는 경우:  
  
    -   동일한 수의 속성을 갖게 됩니다.  
  
    -   동일한 순서로 동일한 이름 가진 속성이 선언 되 고 유추 된 형식입니다. 이름을 비교할 때는 대/소문자 구분 하지 않습니다.  
  
    -   키 속성은 속성 중 하나 이상 및 `Key` 키워드는 동일한 속성에 적용 됩니다.  
  
    -   키 속성의 각 해당 쌍의 비교 반환 `True`합니다.  
  
     예를 들어 다음 예제에서에서 `Equals` 반환 `True` 에 대해서만 `employee01` 및 `employee08`합니다. 새 인스턴스 일치 하지 않는 이유를 지정 하는 각 줄 앞의 주석이 `employee01`합니다.  
  
     [!code-vb[VbVbalrAnonymousTypes#24](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_2.vb)]  
  
-   `GetHashcode` 적절 하 게 고유 GetHashCode 알고리즘을 제공합니다. 알고리즘 해시 코드를 계산 하는 키 속성만 사용 합니다.  
  
-   `ToString` 다음 예제와 같이 연결 된 속성 값의 문자열을 반환 합니다. 키와 키가 아닌 속성이 포함 됩니다.  
  
     [!code-vb[VbVbalrAnonymousTypes#29](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_3.vb)]  
  
 익명 형식을 명시적으로 명명 된 속성은 이러한 생성 된 메서드와 충돌 하지 않습니다. 사용할 수 없습니다, 즉 `.Equals`, `.GetHashCode`, 또는 `.ToString` 속성 이름을 지정 합니다.  
  
 익명 형식 정의 하나 이상 포함 하는 키 속성이 구현은 <xref:System.IEquatable%601?displayProperty=nameWithType> 인터페이스를 여기서 `T` 유형 익명 형식입니다.  
  
> [!NOTE]
>  익명 형식 선언 동일한 어셈블리에서 발생 하는, 동일한 이름을 갖는 및 유추 된 형식, 같은 순서로 속성이 선언 되 고 동일한 속성이 키 속성으로 표시 됩니다 경우에 동일한 익명 형식의 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
