---
title: "(Visual Basic) 대리자의 가변성"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9fe76a32f76f760497021289ec1c6ce673cec1b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="variance-in-delegates-visual-basic"></a><span data-ttu-id="8b98b-102">(Visual Basic) 대리자의 가변성</span><span class="sxs-lookup"><span data-stu-id="8b98b-102">Variance in Delegates (Visual Basic)</span></span>
<span data-ttu-id="8b98b-103">.NET framework 3.5를 C# 및 Visual Basic에서 모든 대리자의 대리자 형식과 일치 하는 메서드 서명이 대 한 분산 지원을 기능이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-103">.NET Framework 3.5 introduced variance support for matching method signatures with delegate types in all delegates in C# and Visual Basic.</span></span> <span data-ttu-id="8b98b-104">즉, 일치하는 시그니처가 있는 메서드만이 아니라 더 많은 파생된 형식(공변성(covariance))을 반환하는 메서드 또는 대리자 형식에 지정된 것보다 더 적은 수의 파생된 형식(반공변성(contravariance))을 가지고 있는 매개 변수를 수락하는 메서드도 대리자에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-104">This means that you can assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="8b98b-105">여기에는 제네릭 및 비 제네릭 대리자가 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-105">This includes both generic and non-generic delegates.</span></span>  
  
 <span data-ttu-id="8b98b-106">다음과 같이 두 개의 클래스 및 두 개의 대리자(제네릭 및 비 제네릭)를 가지고 있는 코드를 예로 들어보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-106">For example, consider the following code, which has two classes and two delegates: generic and non-generic.</span></span>  
  
```vb  
Public Class First  
End Class  
  
Public Class Second  
    Inherits First  
End Class  
  
Public Delegate Function SampleDelegate(ByVal a As Second) As First  
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R  
```  
  
 <span data-ttu-id="8b98b-107">`SampleDelegate` 또는 `SampleDelegate(Of A, R)` 형식의 대리자를 만들 때 다음 메서드 중 하나를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-107">When you create delegates of the `SampleDelegate` or `SampleDelegate(Of A, R)` types, you can assign any one of the following methods to those delegates.</span></span>  
  
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
  
 <span data-ttu-id="8b98b-108">다음 코드 예제에서는 메서드 시그니처 및 대리자 형식 사이의 암시적 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-108">The following code example illustrates the implicit conversion between the method signature and the delegate type.</span></span>  
  
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
  
 <span data-ttu-id="8b98b-109">더 많은 예제를 참조 하십시오. [(Visual Basic의 경우) 대리자의 가변성 사용 하 여](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) 및 [Func 및 Action 제네릭 대리자 (Visual Basic)에 대 한 분산을 사용 하 여](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-109">For more examples, see [Using Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
## <a name="variance-in-generic-type-parameters"></a><span data-ttu-id="8b98b-110">제네릭 형식 매개 변수에서의 가변성</span><span class="sxs-lookup"><span data-stu-id="8b98b-110">Variance in Generic Type Parameters</span></span>  
 <span data-ttu-id="8b98b-111">제네릭 형식 매개 변수로 지정 하는 다른 형식이 있는 제네릭 대리자 형식 요구에 따라 서로에서 상속 된 경우, 할당할 수 수 있도록 대리자 사이의 암시적 변환을.NET Framework 4에서와 이후 활성화할 수 있습니다. 분산입니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-111">In .NET Framework 4 and later you can enable implicit conversion between delegates, so that generic delegates that have different types specified by generic type parameters can be assigned to each other, if the types are inherited from each other as required by variance.</span></span>  
  
 <span data-ttu-id="8b98b-112">암시적 변환을 사용하도록 설정하려면 `in` 및 `out` 키워드를 사용하여 대리자에서 제네릭 매개 변수를 공변(covariant) 또는 반공변(contravariant)으로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-112">To enable implicit conversion, you must explicitly declare generic parameters in a delegate as covariant or contravariant by using the `in` or `out` keyword.</span></span>  
  
 <span data-ttu-id="8b98b-113">다음 코드 예제에서는 공변(covariant) 제네릭 형식 매개 변수가 있는 대리자를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-113">The following code example shows how you can create a delegate that has a covariant generic type parameter.</span></span>  
  
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
  
 <span data-ttu-id="8b98b-114">메서드 시그니처를 대리자 형식과 일치시키는 용도로만 가변성 지원을 사용하고 `in` 및 `out` 키워드를 사용하지 않는 경우, 대리자를 동일한 람다 식 또는 메서드로 인스턴스화할 수는 있지만 한 대리자를 다른 대리자에 할당할 수는 없는 경우가 더러 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-114">If you use only variance support to match method signatures with delegate types and do not use the `in` and `out` keywords, you may find that sometimes you can instantiate delegates with identical lambda expressions or methods, but you cannot assign one delegate to another.</span></span>  
  
 <span data-ttu-id="8b98b-115">다음 코드 예에서 `SampleGenericDelegate(Of String)` 로 명시적으로 변환할 수 없는 `SampleGenericDelegate(Of Object)`하지만, `String` 상속 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-115">In the following code example, `SampleGenericDelegate(Of String)` can't be explicitly converted to `SampleGenericDelegate(Of Object)`, although `String` inherits `Object`.</span></span> <span data-ttu-id="8b98b-116">`T` 제네릭 매개 변수를 `out` 키워드로 표시하면 이 문제를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-116">You can fix this problem by marking the generic parameter `T` with the `out` keyword.</span></span>  
  
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
  
### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a><span data-ttu-id="8b98b-117">.NET Framework에 Variant 형식 매개 변수를 가지고 있는 제네릭 대리자</span><span class="sxs-lookup"><span data-stu-id="8b98b-117">Generic Delegates That Have Variant Type Parameters in the .NET Framework</span></span>  
 <span data-ttu-id="8b98b-118">.NET Framework 4에는 기존의 몇몇 제네릭 대리자에서 제네릭 형식 매개 변수에 대한 가변성 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-118">.NET Framework 4 introduced variance support for generic type parameters in several existing generic delegates:</span></span>  
  
-   <span data-ttu-id="8b98b-119"><xref:System> 네임스페이스의 `Action` 대리자(예: <xref:System.Action%601> 및 <xref:System.Action%602>)</span><span class="sxs-lookup"><span data-stu-id="8b98b-119">`Action` delegates from the <xref:System> namespace, for example, <xref:System.Action%601> and <xref:System.Action%602></span></span>  
  
-   <span data-ttu-id="8b98b-120"><xref:System> 네임스페이스의 `Func` 대리자(예: <xref:System.Func%601> 및 <xref:System.Func%602>)</span><span class="sxs-lookup"><span data-stu-id="8b98b-120">`Func` delegates from the <xref:System> namespace, for example, <xref:System.Func%601> and <xref:System.Func%602></span></span>  
  
-   <span data-ttu-id="8b98b-121"><xref:System.Predicate%601> 대리자</span><span class="sxs-lookup"><span data-stu-id="8b98b-121">The <xref:System.Predicate%601> delegate</span></span>  
  
-   <span data-ttu-id="8b98b-122"><xref:System.Comparison%601> 대리자</span><span class="sxs-lookup"><span data-stu-id="8b98b-122">The <xref:System.Comparison%601> delegate</span></span>  
  
-   <span data-ttu-id="8b98b-123"><xref:System.Converter%602> 대리자</span><span class="sxs-lookup"><span data-stu-id="8b98b-123">The <xref:System.Converter%602> delegate</span></span>  
  
 <span data-ttu-id="8b98b-124">자세한 내용 및 예제에 대 한 참조 [Func 및 Action 제네릭 대리자 (Visual Basic)에 대 한 분산을 사용 하 여](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-124">For more information and examples, see [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
### <a name="declaring-variant-type-parameters-in-generic-delegates"></a><span data-ttu-id="8b98b-125">제네릭 대리자에서 Variant 형식 매개 변수 선언</span><span class="sxs-lookup"><span data-stu-id="8b98b-125">Declaring Variant Type Parameters in Generic Delegates</span></span>  
 <span data-ttu-id="8b98b-126">제네릭 대리자가 공변(covariant) 또는 반공변(contravariant) 제네릭 형식 매개 변수를 가지고 있는 경우 이를 *variant 제네릭 대리자*라고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-126">If a generic delegate has covariant or contravariant generic type parameters, it can be referred to as a *variant generic delegate*.</span></span>  
  
 <span data-ttu-id="8b98b-127">`out` 키워드를 사용하여 제네릭 대리자에서 제네릭 형식 매개 변수를 공변(covariant)으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-127">You can declare a generic type parameter covariant in a generic delegate by using the `out` keyword.</span></span> <span data-ttu-id="8b98b-128">공변(covariant) 형식은 메서드 반환 형식으로만 사용할 수 있으며 메서드 인수의 형식으로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-128">The covariant type can be used only as a method return type and not as a type of method arguments.</span></span> <span data-ttu-id="8b98b-129">다음 코드 예제에서는 공변(covariant) 제네릭 대리자를 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-129">The following code example shows how to declare a covariant generic delegate.</span></span>  
  
```vb  
Public Delegate Function DCovariant(Of Out R)() As R  
```  
  
 <span data-ttu-id="8b98b-130">`in` 키워드를 사용하여 제네릭 대리자에서 제네릭 형식 매개 변수를 반공변(contravariant)으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-130">You can declare a generic type parameter contravariant in a generic delegate by using the `in` keyword.</span></span> <span data-ttu-id="8b98b-131">반공변(contravariant) 형식은 메서드 인수의 형식으로서만 사용할 수 있으며 메서드 반환 형식으로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-131">The contravariant type can be used only as a type of method arguments and not as a method return type.</span></span> <span data-ttu-id="8b98b-132">다음 코드 예제에서는 반공변(contravariant) 제네릭 대리자를 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-132">The following code example shows how to declare a contravariant generic delegate.</span></span>  
  
```vb  
Public Delegate Sub DContravariant(Of In A)(ByVal a As A)  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="8b98b-133">`ByRef`Visual Basic의 매개 변수는 variant로 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-133">`ByRef` parameters in Visual Basic can't be marked as variant.</span></span>  
  
 <span data-ttu-id="8b98b-134">동일한 대리자에서, 그러나 서로 다른 형식 매개 변수에 대해 분산 및 공변성(covariance)을 모두 지원하는 것도 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-134">It is also possible to support both variance and covariance in the same delegate, but for different type parameters.</span></span> <span data-ttu-id="8b98b-135">다음 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-135">This is shown in the following example.</span></span>  
  
```vb  
Public Delegate Function DVariant(Of In A, Out R)(ByVal a As A) As R  
```  
  
### <a name="instantiating-and-invoking-variant-generic-delegates"></a><span data-ttu-id="8b98b-136">Variant 제네릭 대리자 인스턴스화 및 호출</span><span class="sxs-lookup"><span data-stu-id="8b98b-136">Instantiating and Invoking Variant Generic Delegates</span></span>  
 <span data-ttu-id="8b98b-137">비 variant 대리자를 인스턴스화 및 호출하듯 variant 대리자를 인스턴스화 및 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-137">You can instantiate and invoke variant delegates just as you instantiate and invoke invariant delegates.</span></span> <span data-ttu-id="8b98b-138">다음 예제에서는 람다 식을 사용하여 대리자가 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-138">In the following example, the delegate is instantiated by a lambda expression.</span></span>  
  
```vb  
Dim dvariant As DVariant(Of String, String) = Function(str) str + " "  
dvariant("test")  
```  
  
### <a name="combining-variant-generic-delegates"></a><span data-ttu-id="8b98b-139">Variant 제네릭 대리자 결합</span><span class="sxs-lookup"><span data-stu-id="8b98b-139">Combining Variant Generic Delegates</span></span>  
 <span data-ttu-id="8b98b-140">Variant 대리자는 결합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-140">You should not combine variant delegates.</span></span> <span data-ttu-id="8b98b-141"><xref:System.Delegate.Combine%2A> 메서드는 variant 대리자 변환을 지원하지 않으며 대리자가 정확히 동일한 형식일 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-141">The <xref:System.Delegate.Combine%2A> method does not support variant delegate conversion and expects delegates to be of exactly the same type.</span></span> <span data-ttu-id="8b98b-142">사용 하 여 대리자를 결합 하는 경우 런타임 예외가 발생할 수 있습니다는 <xref:System.Delegate.Combine%2A> 메서드 (C# 및 Visual Basic) 또는 사용 하 여는 `+` 연산자 (C#), 다음 코드 예제에서와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-142">This can lead to a run-time exception when you combine delegates either by using the <xref:System.Delegate.Combine%2A> method (in C# and Visual Basic) or by using the `+` operator (in C#), as shown in the following code example.</span></span>  
  
```vb  
Dim actObj As Action(Of Object) = Sub(x) Console.WriteLine("object: {0}", x)  
Dim actStr As Action(Of String) = Sub(x) Console.WriteLine("string: {0}", x)  
  
' The following statement throws an exception at run time.  
' Dim actCombine = [Delegate].Combine(actStr, actObj)  
```  
  
## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a><span data-ttu-id="8b98b-143">값 및 참조 형식에 대한 제네릭 형식 매개 변수에서의 가변성</span><span class="sxs-lookup"><span data-stu-id="8b98b-143">Variance in Generic Type Parameters for Value and Reference Types</span></span>  
 <span data-ttu-id="8b98b-144">제네릭 형식 매개 변수에 대한 가변성은 참조 형식에 대해서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-144">Variance for generic type parameters is supported for reference types only.</span></span> <span data-ttu-id="8b98b-145">예를 들어 `DVariant(Of Int)`로 암시적으로 변환할 수 없는 `DVariant(Of Object)` 또는 `DVariant(Of Long)`정수는 값 형식, 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-145">For example, `DVariant(Of Int)`can't be implicitly converted to `DVariant(Of Object)` or `DVariant(Of Long)`, because integer is a value type.</span></span>  
  
 <span data-ttu-id="8b98b-146">다음 예제에서는 제네릭 형식 매개 변수에서의 가변성이 값 형식에 대해 지원되지 않음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-146">The following example demonstrates that variance in generic type parameters is not supported for value types.</span></span>  
  
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
  
## <a name="relaxed-delegate-conversion-in-visual-basic"></a><span data-ttu-id="8b98b-147">Visual Basic의 완화 된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="8b98b-147">Relaxed Delegate Conversion in Visual Basic</span></span>  
 <span data-ttu-id="8b98b-148">완화 된 대리자 변환 메서드 시그니처를 일치 하는 대리자 형식에서 더 많은 융통성을 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-148">Relaxed delegate conversion enables more flexibility in matching method signatures with delegate types.</span></span> <span data-ttu-id="8b98b-149">예를 들어, 매개 변수 사양 생략 하 고 메서드를 대리자에 할당할 때 함수 반환 값을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-149">For example, it lets you omit parameter specifications and omit function return values when you assign a method to a delegate.</span></span> <span data-ttu-id="8b98b-150">자세한 내용은 참조 [완화 된 대리자 변환](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8b98b-150">For more information, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b98b-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b98b-151">See Also</span></span>  
 [<span data-ttu-id="8b98b-152">제네릭</span><span class="sxs-lookup"><span data-stu-id="8b98b-152">Generics</span></span>](~/docs/standard/generics/index.md)  
 [<span data-ttu-id="8b98b-153">Func 및 Action 제네릭 대리자에 가변성 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b98b-153">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
