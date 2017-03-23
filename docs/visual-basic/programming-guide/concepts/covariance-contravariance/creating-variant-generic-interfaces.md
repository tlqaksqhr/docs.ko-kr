---
title: "Variant 제네릭 인터페이스 (Visual Basic) 만들기 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 324e2a906e84950aa9019bbf68a524458492646e
ms.lasthandoff: 03/13/2017

---
# <a name="creating-variant-generic-interfaces-visual-basic"></a>Variant 제네릭 인터페이스 만들기 (Visual Basic)
공변 (covariant)에 따라 인터페이스의 제네릭 형식 매개 변수를 선언할 수 또는 반공 변입니다. *공변성 (covariance)* 인터페이스 메서드를 더 많이 파생 된 반환 형식이 제네릭 형식 매개 변수에 의해 정의 된 것을 허용 합니다. *반 공변성* 인터페이스 메서드는 제네릭 매개 변수에 지정 된 것 보다 더 적게 파생 된 인수 형식을 가질 수 있습니다. 공변 (covariant)이 있는 제네릭 인터페이스 또는 반공 변 제네릭 형식 매개 변수 라고 *variant*합니다.  
  
> [!NOTE]
>  .NET framework 4에는 여러 기존 제네릭 인터페이스에 대 한 분산 지원이 추가 되었습니다. .NET Framework의 variant 인터페이스 목록에 대 한 참조 [제네릭 인터페이스 (Visual Basic)에 대 한 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)합니다.  
  
## <a name="declaring-variant-generic-interfaces"></a>Variant 제네릭 인터페이스 선언  
 사용 하 여 variant 제네릭 인터페이스를 선언할 수는 `in` 및 `out` 제네릭 형식 매개 변수에 대 한 키워드입니다.  
  
> [!IMPORTANT]
>  `ByRef`Visual Basic의 매개 변수는 variant 일 수 없습니다. 또한 값 형식의 차이 지원 하지 않습니다.  
  
 선언할 수 있습니다 제네릭 형식 매개 변수는 공변 (covariant)를 사용 하 여는 `out` 키워드입니다. 공변 (covariant) 형식에는 다음 조건을 충족 해야 합니다.  
  
-   형식을은 인터페이스 메서드의 반환 형식 으로만 사용 되 고 메서드 인수 형식으로 사용 되지 않습니다. 이에 다음 예제에서는 설명 형식을 `R` 공변 (covariant) 선언 됩니다.  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Function GetSomething() As R  
        ' The following statement generates a compiler error.  
        ' Sub SetSomething(ByVal sampleArg As R)  
    End Interface  
    ```  
  
     그러나 이 규칙에는 한 가지 예외가 있습니다. 메서드 매개 변수는 반공 변 제네릭 대리자를 사용 하도록 설정한 경우 대리자에 대 한 형식을 제네릭 형식 매개 변수로 사용할 수 있습니다. 형식에서이 확인할 `R` 다음 예제에서입니다. 자세한 내용은 참조 [대리자 (Visual Basic)에 대 한 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) 및 [Func 및 Action 제네릭 대리자 (Visual Basic)를 사용 하 여 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)합니다.  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Sub DoSomething(ByVal callback As Action(Of R))  
    End Interface  
    ```  
  
-   인터페이스 메서드에 대 한 형식은 제네릭 제약 조건으로 사용 되지 않습니다. 다음 코드에 나와 있습니다.  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        ' The following statement generates a compiler error  
        ' because you can use only contravariant or invariant types  
        ' in generic contstraints.  
        ' Sub DoSomething(Of T As R)()  
    End Interface  
    ```  
  
 사용 하 여 제네릭 형식 매개 변수가 반공 변을 선언할 수는 `in` 키워드입니다. 반공 변 형식 인터페이스 메서드의 반환 형식이 아닌 메서드 인수의 형식으로만 사용할 수 있습니다. 반공 변 형식이 제네릭 제약 조건에도 사용할 수 있습니다. 다음 코드에는 반공 변 인터페이스를 선언 하 고 해당 메서드 중 하나에 대 한 제네릭 제약 조건을 사용 하는 방법을 보여 줍니다.  
  
```vb  
Interface IContravariant(Of In A)  
    Sub SetSomething(ByVal sampleArg As A)  
    Sub DoSomething(Of T As A)()  
    ' The following statement generates a compiler error.  
    ' Function GetSomething() As A  
End Interface  
```  
  
 다음 코드 예제와 같이 동일한 인터페이스에 있지만 서로 다른 형식 매개 변수에 대해 모두 공 분산과 반공 분산을 지원 하기 위해도 가능 합니다.  
  
```vb  
Interface IVariant(Of Out R, In A)  
    Function GetSomething() As R  
    Sub SetSomething(ByVal sampleArg As A)  
    Function GetSetSomething(ByVal sampleArg As A) As R  
End Interface  
```  
  
 Visual Basic에서 대리자 형식을 지정 하지 않고 variant 인터페이스의 이벤트를 선언할 수 없습니다. 또한 없습니다 중첩 변형 인터페이스 클래스, 열거형 또는 구조를 하지만 인터페이스 중첩 있을 수도 있습니다. 다음 코드에 나와 있습니다.  
  
```vb  
Interface ICovariant(Of Out R)  
    ' The following statement generates a compiler error.  
    ' Event SampleEvent()  
    ' The following statement specifies the delegate type and   
    ' does not generate an error.  
    Event AnotherEvent As EventHandler  
  
    ' The following statements generate compiler errors,  
    ' because a variant interface cannot have  
    ' nested enums, classes, or structures.  
  
    'Enum SampleEnum : test : End Enum  
    'Class SampleClass : End Class  
    'Structure SampleStructure : Dim value As Integer : End Structure  
  
    ' Variant interfaces can have nested interfaces.  
    Interface INested : End Interface  
End Interface  
```  
  
## <a name="implementing-variant-generic-interfaces"></a>Variant 제네릭 인터페이스 구현  
 클래스에서 고정 인터페이스에 사용 되는 구문과 동일한 구문을 사용 하 여 variant 제네릭 인터페이스를 구현 합니다. 다음 코드 예제는 제네릭 클래스에는 공변 (covariant) 인터페이스를 구현 하는 방법을 보여 줍니다.  
  
```vb  
Interface ICovariant(Of Out R)  
    Function GetSomething() As R  
End Interface  
  
Class SampleImplementation(Of R)  
    Implements ICovariant(Of R)  
    Public Function GetSomething() As R _  
    Implements ICovariant(Of R).GetSomething  
        ' Some code.  
    End Function  
End Class  
```  
  
 Variant 인터페이스를 구현 하는 클래스 변하지 않습니다. 예를 들어, 다음과 같은 코드를 생각해 볼 수 있습니다.  
  
```vb  
 The interface is covariant.  
Dim ibutton As ICovariant(Of Button) =  
    New SampleImplementation(Of Button)  
Dim iobj As ICovariant(Of Object) = ibutton  
  
' The class is invariant.  
Dim button As SampleImplementation(Of Button) =  
    New SampleImplementation(Of Button)  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim obj As SampleImplementation(Of Object) = button  
```  
  
## <a name="extending-variant-generic-interfaces"></a>Variant 제네릭 인터페이스를 확장 하는 방법  
 Variant 제네릭 인터페이스를 확장할 때 사용 해야는 `in` 및 `out` 키워드를 명시적으로 파생 된 인터페이스 분산을 지원 하는지 여부를 지정 합니다. 컴파일러에서는 확장 되는 인터페이스에서 차이 유추 하지 않습니다. 예를 들어 다음 인터페이스를 것이 좋습니다.  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T)  
End Interface  
  
Interface IExtCovariant(Of Out T)  
    Inherits ICovariant(Of T)  
End Interface  
```  
  
 에 `Invariant(Of T)` 인터페이스를 제네릭 형식 매개 변수 `T` 는 고정, 반면에 `IExtCovariant (Of Out T)`형식 매개 변수는 공변 (covariant), 두 인터페이스 모두 동일한 인터페이스를 확장 합니다. 반공 변 제네릭 형식 매개 변수에 동일한 규칙이 적용 됩니다.  
  
 여기서는 제네릭 형식 매개 변수는 모두 인터페이스를 확장 하는 인터페이스를 만들 수 있습니다 `T` 는 공변 (covariant)는 확장에 반 공변성을 있기 인터페이스 인터페이스는 제네릭 형식 매개 변수 및 `T` 변하지 않습니다. 다음 코드 예제에 나와 있습니다.  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IContravariant(Of In T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T), IContravariant(Of T)  
End Interface  
```  
  
 그러나 제네릭 형식 매개 변수 이면 `T` 는 하나의 인터페이스에 공변 (covariant)를 선언를 선언할 수는 없으며 반공 변 확장 인터페이스 또는 그 반대의 경우도 마찬가지입니다. 다음 코드 예제에 나와 있습니다.  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
' The following statements generate a compiler error.  
' Interface ICoContraVariant(Of In T)  
'     Inherits ICovariant(Of T)  
' End Interface  
```  
  
### <a name="avoiding-ambiguity"></a>모호성을 방지합니다.  
 Variant 제네릭 인터페이스를 구현 하는 경우 모호성 분산 경우가 발생할 수 있습니다. 이러한 경우가 발생해서는 안 됩니다.  
  
 예를 들어 하나의 클래스에는 동일한 변형 제네릭 인터페이스를 다른 제네릭 형식 매개 변수를 명시적으로 구현 하는 경우 모호성을 만들 수 있습니다. 컴파일러 오류가 경우에 발생 하지는 않지만 인터페이스 구현이 런타임에 선택 될 지정 되지 않습니다. 이 코드에 버그가 발생할 수 있습니다. 다음 코드 예제를 고려해 야 합니다.  
  
> [!NOTE]
>  와 `Option Strict Off`, Visual Basic 모호한 인터페이스 구현을 때 컴파일러 경고를 생성 합니다. 와 `Option Strict On`, Visual Basic 컴파일러 오류를 생성 합니다.  
  
```vb  
' Simple class hierarchy.  
Class Animal  
End Class  
  
Class Cat  
    Inherits Animal  
End Class  
  
Class Dog  
    Inherits Animal  
End Class  
  
' This class introduces ambiguity  
' because IEnumerable(Of Out T) is covariant.  
Class Pets  
    Implements IEnumerable(Of Cat), IEnumerable(Of Dog)  
  
    Public Function GetEnumerator() As IEnumerator(Of Cat) _  
        Implements IEnumerable(Of Cat).GetEnumerator  
        Console.WriteLine("Cat")  
        ' Some code.  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator(Of Dog) _  
        Implements IEnumerable(Of Dog).GetEnumerator  
        Console.WriteLine("Dog")  
        ' Some code.  
    End Function  
  
    Public Function GetEnumerator2() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
        ' Some code.  
    End Function  
End Class  
  
Sub Main()  
    Dim pets As IEnumerable(Of Animal) = New Pets()  
    pets.GetEnumerator()  
End Sub  
```  
  
 이 예제에서는 지정 되지 않습니다 방법을 `pets.GetEnumerator` 메서드 간의 선택 `Cat` 및 `Dog`합니다. 코드에서 문제를 일으킬 수이 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [(Visual Basic) 제네릭 인터페이스의 가변성](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)   
 [Func 및 Action 제네릭 대리자 (Visual Basic)에 대 한 분산을 사용 하 여](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
