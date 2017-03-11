---
title: "Anonymous Type Definition (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "anonymous types [Visual Basic], type definition"
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Anonymous Type Definition (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

익명 형식의 인스턴스 선언에 대한 응답으로 컴파일러에서는 형식에 대해 지정된 속성을 포함하는 새 클래스 정의를 만듭니다.  
  
## 컴파일러 생성 코드  
 `product`의 다음 정의에 대해서 컴파일러에서는 `Name`, `Price` 및 `OnHand` 속성을 포함하는 새 클래스 정의를 만듭니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#25](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-type-definition_1.vb)]  
  
 클래스 정의에는 다음과 유사한 속성 정의가 포함되어 있습니다.  키 속성에 대한 `Set` 메서드는 없습니다.  키 속성의 값은 읽기 전용입니다.  
  
```vb#  
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
  
 또한 익명 형식 정의에는 기본 생성자가 포함되어 있습니다.  매개 변수를 필요로 하는 생성자는 허용되지 않습니다.  
  
 익명 형식 선언에 적어도 하나의 키 속성이 포함되어 있으면 형식 정의는 <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A> 및 <xref:System.Object.ToString%2A>에서 상속된 세 개의 멤버를 재정의합니다.  선언된 키 속성이 없으면 <xref:System.Object.ToString%2A>만 재정의됩니다.  재정의는 다음과 같은 기능을 제공합니다.  
  
-   두 개의 익명 형식 인스턴스가 동일한 인스턴스이거나 다음과 같은 조건을 만족하면 `Equals`에서 `True`를 반환합니다.  
  
    -   두 개의 익명 형식 인스턴스가 동일한 수의 속성을 갖는 경우  
  
    -   속성이 동일한 이름과 유추된 형식 갖고 동일한 순서로 선언된 경우  이름을 비교할 때 대\/소문자를 구분하지 않습니다.  
  
    -   적어도 하나의 속성이 키 속성이고 `Key` 키워드가 동일한 속성에 적용된 경우  
  
    -   키 속성의 각 해당 쌍을 비교했을 때 `True`를 반환하는 경우  
  
     예를 들어 다음 예제에서 `Equals`는 `employee01` 및 `employee08`에 대해 `True`만 반환합니다.  각 줄 앞의 주석은 새 인스턴스가 `employee01`과 일치하지 않는 이유를 설명합니다.  
  
     [!code-vb[VbVbalrAnonymousTypes#24](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-type-definition_2.vb)]  
  
-   `GetHashcode`에서는 고유한 GetHashCode 알고리즘을 제공합니다.  알고리즘에서는 키 속성만을 사용하여 해시 코드를 계산합니다.  
  
-   `ToString`에서는 다음 예제와 같이 연결된 속성 값의 문자열을 반환합니다.  키 속성 및 키가 아닌 속성 모두 포함됩니다.  
  
     [!code-vb[VbVbalrAnonymousTypes#29](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-type-definition_3.vb)]  
  
 명시적으로 명명된 익명 형식 속성은 이러한 생성된 메서드와 충돌하지 않습니다.  즉, `.Equals`, `.GetHashCode` 또는 `.ToString`을 사용하여 속성의 이름을 지정할 수 없습니다.  
  
 또한 적어도 하나의 키 속성을 포함하고 있는 익명 형식 선언에서는 `T`가 익명 형식의 형식인 <xref:System.IEquatable%601?displayProperty=fullName> 인터페이스를 구현합니다.  
  
> [!NOTE]
>  익명 형식 선언은 익명 형식 선언이 동일한 어셈블리에서 발생한 경우, 익명 형식 선언의 속성이 동일한 이름과 유추된 형식을 갖는 경우, 속성이 동일한 순서로 선언된 경우 및 동일한 속성이 키 속성으로 표시된 경우에만 동일한 익명 형식을 만듭니다.  
  
## 참고 항목  
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)