---
title: "대리자 (Visual Basic)에 대 한 분산 | Microsoft 문서"
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
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
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
ms.openlocfilehash: cbab7da8c97ca202f8a4d0a1a65b8fa240cca32d
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-delegates-visual-basic"></a>(Visual Basic) 대리자의 가변성
.NET framework 3.5에는 메서드 시그니처를 대리자 형식과 C# 및 Visual Basic에서 모든 대리자에 일치 하는 분산 지원이 추가 되었습니다. 서명, 일치 하는 방법 뿐만 아니라 더 많이 파생 된 형식 (공 분산) 또는 대리자 형식에 지정 된 것 보다 더 적은 파생 형식을 (반공 분산)는 매개 변수를 허용 하는 반환 하는 방법에 할당할 수 있는이 것을 위임 합니다. 제네릭 및 제네릭이 아닌 대리자 포함 됩니다.  
  
 예를 들어 다음 코드에서는 두 개의 클래스 및 두 명의 대리자가: 제네릭 및 제네릭이 아닌 합니다.  
  
```vb  
Public Class First  
End Class  
  
Public Class Second  
    Inherits First  
End Class  
  
Public Delegate Function SampleDelegate(ByVal a As Second) As First  
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R  
```  
  
 대리자를 만드는 경우는 `SampleDelegate` 또는 `SampleDelegate(Of A, R)` 형식, 이러한 대리자에는 다음 방법 중 하나를 할당할 수 있습니다.  
  
```vb  
' Matching signature.  
Public Shared Function ASecondRFirst(  
    ByVal second As Second) As First  
    Return New First()  
End Function  
  
' The return type is more derived.  
Public Shared Function ASecondRSecond(  
    ByVal second As Second) As Second  
    Return New Second()  
End Function  
  
' The argument type is less derived.  
Public Shared Function AFirstRFirst(  
    ByVal first As First) As First  
    Return New First()  
End Function  
  
' The return type is more derived   
' and the argument type is less derived.  
Public Shared Function AFirstRSecond(  
    ByVal first As First) As Second  
    Return New Second()  
End Function  
```  
  
 다음 코드 예제에서는 메서드 시그니처 및 대리자 형식 사이의 암시적 변환을 보여 줍니다.  
  
```vb  
' Assigning a method with a matching signature   
' to a non-generic delegate. No conversion is necessary.  
Dim dNonGeneric As SampleDelegate = AddressOf ASecondRFirst  
' Assigning a method with a more derived return type   
' and less derived argument type to a non-generic delegate.  
' The implicit conversion is used.  
Dim dNonGenericConversion As SampleDelegate = AddressOf AFirstRSecond  
  
' Assigning a method with a matching signature to a generic delegate.  
' No conversion is necessary.  
Dim dGeneric As SampleGenericDelegate(Of Second, First) = AddressOf ASecondRFirst  
' Assigning a method with a more derived return type   
' and less derived argument type to a generic delegate.  
' The implicit conversion is used.  
Dim dGenericConversion As SampleGenericDelegate(Of Second, First) = AddressOf AFirstRSecond  
```  
  
 더 많은 예제를 참조 하십시오. [대리자 (Visual Basic)에서 사용 하 여 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) 및 [Func 및 Action 제네릭 대리자 (Visual Basic)를 사용 하 여 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)합니다.  
  
## <a name="variance-in-generic-type-parameters"></a>제네릭 형식 매개 변수에 대 한 분산  
 .NET Framework 4에서 이상를 분산 하 여 필요에 따라 서로 형식을 상속 된 경우, 제네릭 형식 매개 변수로 지정 된 다른 형식을 포함 하는 제네릭 대리자를 할당할 수 있습니다 대리자 간의 암시적 변환을 사용할 수 있습니다.  
  
 을 암시적으로 변환 하기 위해 명시적으로 선언 해야 공변 (covariant)으로 사용 되는 대리자의 제네릭 매개 변수 또는 사용 하 여 반 공변성은 `in` 또는 `out` 키워드입니다.  
  
 다음 코드 예제에서는 공변 (covariant) 제네릭 형식 매개 변수가 있는 대리자를 만드는 방법을 보여 줍니다.  
  
```vb  
' Type T is declared covariant by using the out keyword.  
Public Delegate Function SampleGenericDelegate(Of Out T)() As T  
Sub Test()  
    Dim dString As SampleGenericDelegate(Of String) = Function() " "  
    ' You can assign delegates to each other,  
    ' because the type T is declared covariant.  
    Dim dObject As SampleGenericDelegate(Of Object) = dString  
End Sub  
```  
  
 메서드 시그니처를 대리자 형식 및 사용 하지 않는 일치 하도록 분산 지원만을 사용 하는 경우는 `in` 및 `out` 키워드를 사용할 수 있습니다는 동일한 람다 식 또는 메서드를 대리자 인스턴스화할 수 있지만 다른 대리자를 할당할 수 없습니다.  
  
 다음 코드 예제에서 `SampleGenericDelegate(Of String)` 로 명시적으로 변환할 수 없는 `SampleGenericDelegate(Of Object)`이지만 `String` 상속 `Object`합니다. 제네릭 매개 변수를 표시 하 여이 문제를 해결할 수 `T` 와 `out` 키워드입니다.  
  
```vb  
Public Delegate Function SampleGenericDelegate(Of T)() As T  
Sub Test()  
    Dim dString As SampleGenericDelegate(Of String) = Function() " "  
  
    ' You can assign the dObject delegate  
    ' to the same lambda expression as dString delegate  
    ' because of the variance support for   
    ' matching method signatures with delegate types.  
    Dim dObject As SampleGenericDelegate(Of Object) = Function() " "  
  
    ' The following statement generates a compiler error  
    ' because the generic type T is not marked as covariant.  
    ' Dim dObject As SampleGenericDelegate(Of Object) = dString  
  
End Sub  
```  
  
### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a>.NET Framework의 변형이 있는 제네릭 대리자 형식 매개 변수  
 .NET framework 4에는 몇 가지 기존 제네릭 대리자의 제네릭 형식 매개 변수에 대 한 분산 지원이 도입 되었습니다.  
  
-   `Action`위임 된 <xref:System>네임 스페이스, 예를 들어 <xref:System.Action%601>및 <xref:System.Action%602></xref:System.Action%602> </xref:System.Action%601> </xref:System>  
  
-   `Func`위임 된 <xref:System>네임 스페이스, 예를 들어 <xref:System.Func%601>및 <xref:System.Func%602></xref:System.Func%602> </xref:System.Func%601> </xref:System>  
  
-   <xref:System.Predicate%601>위임</xref:System.Predicate%601>  
  
-   <xref:System.Comparison%601>위임</xref:System.Comparison%601>  
  
-   <xref:System.Converter%602>위임</xref:System.Converter%602>  
  
 자세한 내용 및 예제에 대 한 참조 [Func 및 Action 제네릭 대리자 (Visual Basic)를 사용 하 여 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)합니다.  
  
### <a name="declaring-variant-type-parameters-in-generic-delegates"></a>제네릭 대리자에 Variant 형식 매개 변수를 선언합니다.  
 제네릭 대리자가 공변 또는 반공 변 제네릭 형식 매개 변수를 그 수 라고 하는 경우는 *변형 제네릭 대리자*합니다.  
  
 선언할 수 있습니다 제네릭 형식 매개 변수는 제네릭 대리자에 공변 (covariant)를 사용 하 여는 `out` 키워드입니다. 공변 형식 메서드 인수의 형식이 아닌 메서드 반환 형식으로만 사용할 수 있습니다. 다음 코드 예제에서는 공변 (covariant) 제네릭 대리자를 선언 하는 방법을 보여 줍니다.  
  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
 사용 하 여는 제네릭 형식 매개 변수가 반공 변 제네릭 대리자에서를 선언할 수는 `in` 키워드입니다. 반공 변 형식 메서드 반환 형식이 아닌 메서드 인수의 형식으로만 사용할 수 있습니다. 다음 코드 예제에서는 반공 변 제네릭 대리자를 선언 하는 방법을 보여 줍니다.  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
> [!IMPORTANT]
>  `ByRef`Visual Basic의 매개 변수는 variant로 표시할 수 없습니다.  
  
 또한 동일한 대리자 되지만 다른 형식 매개 변수에 대 한 분산 및 공변성 (covariance) 모두를 지원 하도록도 가능 합니다. 다음 예제에서 이를 확인할 수 있습니다.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
### <a name="instantiating-and-invoking-variant-generic-delegates"></a>Variant 제네릭 대리자를 호출 하는 인스턴스화  
 인스턴스화할 수 있으며 인스턴스화 및 고정 대리자를 호출 처럼 variant 대리자를 호출 수 있습니다. 다음 예제에서는 대리자 람다 식을 사용 하 여 인스턴스화됩니다.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
### <a name="combining-variant-generic-delegates"></a>Variant 제네릭 대리자를 결합합니다.  
 Variant 대리자 결합할 수 없습니다. <xref:System.Delegate.Combine%2A>variant 대리자 변환을 지원 하지 않음을 메서드와 정확히 같은 형식 이어야 하는 대리자를 예상 합니다.</xref:System.Delegate.Combine%2A> 사용 하 여 대리자를 결합 하는 경우 런타임 예외가 발생할 수 있습니다는 <xref:System.Delegate.Combine%2A>메서드 (C# 및 Visual Basic) 또는 사용 하 여는 `+` 연산자 (C#), 다음 코드 예제에 나온 것 처럼.</xref:System.Delegate.Combine%2A>  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a>제네릭 형식 매개 변수 값 및 참조 형식에 대 한 가변성  
 제네릭 형식 매개 변수에 대 한 분산 참조 형식에만 사용할 수 있습니다. 예를 들어 `DVariant(Of Int)`로 암시적으로 변환할 수 없는 `DVariant(Of Object)` 또는 `DVariant(Of Long)`정수는 값 형식, 합니다.  
  
 다음 예제에서는 그 차이 보여 줍니다. 제네릭 형식 매개 변수 값 형식에 대해 지원 되지 않습니다.  
  
```vb  
' The type T is covariant.  
Public Delegate Function DVariant(Of Out T)() As T  
' The type T is invariant.  
Public Delegate Function DInvariant(Of T)() As T  
Sub Test()  
    Dim i As Integer = 0  
    Dim dInt As DInvariant(Of Integer) = Function() i  
    Dim dVaraintInt As DVariant(Of Integer) = Function() i  
  
    ' All of the following statements generate a compiler error  
    ' because type variance in generic parameters is not supported  
    ' for value types, even if generic type parameters are declared variant.  
    ' Dim dObject As DInvariant(Of Object) = dInt  
    ' Dim dLong As DInvariant(Of Long) = dInt  
    ' Dim dVaraintObject As DInvariant(Of Object) = dInt  
    ' Dim dVaraintLong As DInvariant(Of Long) = dInt  
End Sub  
```  
  
## <a name="relaxed-delegate-conversion-in-visual-basic"></a>Visual Basic의 완화 된 대리자 변환  
 완화 된 대리자 변환 보다 유연 하 게를 메서드 시그니처를 대리자 형식과 일치 시킬 수 있습니다. 예를 들어, 매개 변수 사양을 생략 하 고 메서드는 대리자에 할당할 때 함수 반환 값을 생략할 수 있습니다. 자세한 내용은 참조 [완화 된 대리자 변환](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [제네릭](https://msdn.microsoft.com/library/ms172192)   
 [Func 및 Action 제네릭 대리자 (Visual Basic)에 대 한 분산을 사용 하 여](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
