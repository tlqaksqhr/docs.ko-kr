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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cbab7da8c97ca202f8a4d0a1a65b8fa240cca32d
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-delegates-visual-basic"></a><span data-ttu-id="fc179-102">(Visual Basic) 대리자의 가변성</span><span class="sxs-lookup"><span data-stu-id="fc179-102">Variance in Delegates (Visual Basic)</span></span>
<span data-ttu-id="fc179-103">.NET framework 3.5에는 메서드 시그니처를 대리자 형식과 C# 및 Visual Basic에서 모든 대리자에 일치 하는 분산 지원이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-103">.NET Framework 3.5 introduced variance support for matching method signatures with delegate types in all delegates in C# and Visual Basic.</span></span> <span data-ttu-id="fc179-104">서명, 일치 하는 방법 뿐만 아니라 더 많이 파생 된 형식 (공 분산) 또는 대리자 형식에 지정 된 것 보다 더 적은 파생 형식을 (반공 분산)는 매개 변수를 허용 하는 반환 하는 방법에 할당할 수 있는이 것을 위임 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-104">This means that you can assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="fc179-105">제네릭 및 제네릭이 아닌 대리자 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-105">This includes both generic and non-generic delegates.</span></span>  
  
 <span data-ttu-id="fc179-106">예를 들어 다음 코드에서는 두 개의 클래스 및 두 명의 대리자가: 제네릭 및 제네릭이 아닌 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-106">For example, consider the following code, which has two classes and two delegates: generic and non-generic.</span></span>  
  
```vb  
Public Class First  
End Class  
  
Public Class Second  
    Inherits First  
End Class  
  
Public Delegate Function SampleDelegate(ByVal a As Second) As First  
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R  
```  
  
 <span data-ttu-id="fc179-107">대리자를 만드는 경우는 `SampleDelegate` 또는 `SampleDelegate(Of A, R)` 형식, 이러한 대리자에는 다음 방법 중 하나를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-107">When you create delegates of the `SampleDelegate` or `SampleDelegate(Of A, R)` types, you can assign any one of the following methods to those delegates.</span></span>  
  
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
  
 <span data-ttu-id="fc179-108">다음 코드 예제에서는 메서드 시그니처 및 대리자 형식 사이의 암시적 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-108">The following code example illustrates the implicit conversion between the method signature and the delegate type.</span></span>  
  
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
  
 <span data-ttu-id="fc179-109">더 많은 예제를 참조 하십시오. [대리자 (Visual Basic)에서 사용 하 여 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) 및 [Func 및 Action 제네릭 대리자 (Visual Basic)를 사용 하 여 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-109">For more examples, see [Using Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
## <a name="variance-in-generic-type-parameters"></a><span data-ttu-id="fc179-110">제네릭 형식 매개 변수에 대 한 분산</span><span class="sxs-lookup"><span data-stu-id="fc179-110">Variance in Generic Type Parameters</span></span>  
 <span data-ttu-id="fc179-111">.NET Framework 4에서 이상를 분산 하 여 필요에 따라 서로 형식을 상속 된 경우, 제네릭 형식 매개 변수로 지정 된 다른 형식을 포함 하는 제네릭 대리자를 할당할 수 있습니다 대리자 간의 암시적 변환을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-111">In .NET Framework 4 and later you can enable implicit conversion between delegates, so that generic delegates that have different types specified by generic type parameters can be assigned to each other, if the types are inherited from each other as required by variance.</span></span>  
  
 <span data-ttu-id="fc179-112">을 암시적으로 변환 하기 위해 명시적으로 선언 해야 공변 (covariant)으로 사용 되는 대리자의 제네릭 매개 변수 또는 사용 하 여 반 공변성은 `in` 또는 `out` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-112">To enable implicit conversion, you must explicitly declare generic parameters in a delegate as covariant or contravariant by using the `in` or `out` keyword.</span></span>  
  
 <span data-ttu-id="fc179-113">다음 코드 예제에서는 공변 (covariant) 제네릭 형식 매개 변수가 있는 대리자를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-113">The following code example shows how you can create a delegate that has a covariant generic type parameter.</span></span>  
  
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
  
 <span data-ttu-id="fc179-114">메서드 시그니처를 대리자 형식 및 사용 하지 않는 일치 하도록 분산 지원만을 사용 하는 경우는 `in` 및 `out` 키워드를 사용할 수 있습니다는 동일한 람다 식 또는 메서드를 대리자 인스턴스화할 수 있지만 다른 대리자를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-114">If you use only variance support to match method signatures with delegate types and do not use the `in` and `out` keywords, you may find that sometimes you can instantiate delegates with identical lambda expressions or methods, but you cannot assign one delegate to another.</span></span>  
  
 <span data-ttu-id="fc179-115">다음 코드 예제에서 `SampleGenericDelegate(Of String)` 로 명시적으로 변환할 수 없는 `SampleGenericDelegate(Of Object)`이지만 `String` 상속 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-115">In the following code example, `SampleGenericDelegate(Of String)` can't be explicitly converted to `SampleGenericDelegate(Of Object)`, although `String` inherits `Object`.</span></span> <span data-ttu-id="fc179-116">제네릭 매개 변수를 표시 하 여이 문제를 해결할 수 `T` 와 `out` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-116">You can fix this problem by marking the generic parameter `T` with the `out` keyword.</span></span>  
  
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
  
### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a><span data-ttu-id="fc179-117">.NET Framework의 변형이 있는 제네릭 대리자 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc179-117">Generic Delegates That Have Variant Type Parameters in the .NET Framework</span></span>  
 <span data-ttu-id="fc179-118">.NET framework 4에는 몇 가지 기존 제네릭 대리자의 제네릭 형식 매개 변수에 대 한 분산 지원이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-118">.NET Framework 4 introduced variance support for generic type parameters in several existing generic delegates:</span></span>  
  
-   <span data-ttu-id="fc179-119">`Action`위임 된 <xref:System>네임 스페이스, 예를 들어 <xref:System.Action%601>및 <xref:System.Action%602></xref:System.Action%602> </xref:System.Action%601> </xref:System></span><span class="sxs-lookup"><span data-stu-id="fc179-119">`Action` delegates from the <xref:System> namespace, for example, <xref:System.Action%601> and <xref:System.Action%602></span></span>  
  
-   <span data-ttu-id="fc179-120">`Func`위임 된 <xref:System>네임 스페이스, 예를 들어 <xref:System.Func%601>및 <xref:System.Func%602></xref:System.Func%602> </xref:System.Func%601> </xref:System></span><span class="sxs-lookup"><span data-stu-id="fc179-120">`Func` delegates from the <xref:System> namespace, for example, <xref:System.Func%601> and <xref:System.Func%602></span></span>  
  
-   <span data-ttu-id="fc179-121"><xref:System.Predicate%601>위임</xref:System.Predicate%601></span><span class="sxs-lookup"><span data-stu-id="fc179-121">The <xref:System.Predicate%601> delegate</span></span>  
  
-   <span data-ttu-id="fc179-122"><xref:System.Comparison%601>위임</xref:System.Comparison%601></span><span class="sxs-lookup"><span data-stu-id="fc179-122">The <xref:System.Comparison%601> delegate</span></span>  
  
-   <span data-ttu-id="fc179-123"><xref:System.Converter%602>위임</xref:System.Converter%602></span><span class="sxs-lookup"><span data-stu-id="fc179-123">The <xref:System.Converter%602> delegate</span></span>  
  
 <span data-ttu-id="fc179-124">자세한 내용 및 예제에 대 한 참조 [Func 및 Action 제네릭 대리자 (Visual Basic)를 사용 하 여 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-124">For more information and examples, see [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
### <a name="declaring-variant-type-parameters-in-generic-delegates"></a><span data-ttu-id="fc179-125">제네릭 대리자에 Variant 형식 매개 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-125">Declaring Variant Type Parameters in Generic Delegates</span></span>  
 <span data-ttu-id="fc179-126">제네릭 대리자가 공변 또는 반공 변 제네릭 형식 매개 변수를 그 수 라고 하는 경우는 *변형 제네릭 대리자*합니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-126">If a generic delegate has covariant or contravariant generic type parameters, it can be referred to as a *variant generic delegate*.</span></span>  
  
 <span data-ttu-id="fc179-127">선언할 수 있습니다 제네릭 형식 매개 변수는 제네릭 대리자에 공변 (covariant)를 사용 하 여는 `out` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-127">You can declare a generic type parameter covariant in a generic delegate by using the `out` keyword.</span></span> <span data-ttu-id="fc179-128">공변 형식 메서드 인수의 형식이 아닌 메서드 반환 형식으로만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-128">The covariant type can be used only as a method return type and not as a type of method arguments.</span></span> <span data-ttu-id="fc179-129">다음 코드 예제에서는 공변 (covariant) 제네릭 대리자를 선언 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-129">The following code example shows how to declare a covariant generic delegate.</span></span>  
  
<span data-ttu-id="fc179-130"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fc179-130"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="fc179-131">사용 하 여는 제네릭 형식 매개 변수가 반공 변 제네릭 대리자에서를 선언할 수는 `in` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-131">You can declare a generic type parameter contravariant in a generic delegate by using the `in` keyword.</span></span> <span data-ttu-id="fc179-132">반공 변 형식 메서드 반환 형식이 아닌 메서드 인수의 형식으로만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-132">The contravariant type can be used only as a type of method arguments and not as a method return type.</span></span> <span data-ttu-id="fc179-133">다음 코드 예제에서는 반공 변 제네릭 대리자를 선언 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-133">The following code example shows how to declare a contravariant generic delegate.</span></span>  
  
<span data-ttu-id="fc179-134"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fc179-134"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
> [!IMPORTANT]
> <span data-ttu-id="fc179-135"> `ByRef`Visual Basic의 매개 변수는 variant로 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-135"> `ByRef` parameters in Visual Basic can't be marked as variant.</span></span>  
  
 <span data-ttu-id="fc179-136">또한 동일한 대리자 되지만 다른 형식 매개 변수에 대 한 분산 및 공변성 (covariance) 모두를 지원 하도록도 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-136">It is also possible to support both variance and covariance in the same delegate, but for different type parameters.</span></span> <span data-ttu-id="fc179-137">다음 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-137">This is shown in the following example.</span></span>  
  
<span data-ttu-id="fc179-138"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fc179-138"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span></span>  
### <a name="instantiating-and-invoking-variant-generic-delegates"></a><span data-ttu-id="fc179-139">Variant 제네릭 대리자를 호출 하는 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="fc179-139">Instantiating and Invoking Variant Generic Delegates</span></span>  
 <span data-ttu-id="fc179-140">인스턴스화할 수 있으며 인스턴스화 및 고정 대리자를 호출 처럼 variant 대리자를 호출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-140">You can instantiate and invoke variant delegates just as you instantiate and invoke invariant delegates.</span></span> <span data-ttu-id="fc179-141">다음 예제에서는 대리자 람다 식을 사용 하 여 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-141">In the following example, the delegate is instantiated by a lambda expression.</span></span>  
  
<span data-ttu-id="fc179-142"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fc179-142"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
### <a name="combining-variant-generic-delegates"></a><span data-ttu-id="fc179-143">Variant 제네릭 대리자를 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-143">Combining Variant Generic Delegates</span></span>  
 <span data-ttu-id="fc179-144">Variant 대리자 결합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-144">You should not combine variant delegates.</span></span> <span data-ttu-id="fc179-145"><xref:System.Delegate.Combine%2A>variant 대리자 변환을 지원 하지 않음을 메서드와 정확히 같은 형식 이어야 하는 대리자를 예상 합니다.</xref:System.Delegate.Combine%2A></span><span class="sxs-lookup"><span data-stu-id="fc179-145">The <xref:System.Delegate.Combine%2A> method does not support variant delegate conversion and expects delegates to be of exactly the same type.</span></span> <span data-ttu-id="fc179-146">사용 하 여 대리자를 결합 하는 경우 런타임 예외가 발생할 수 있습니다는 <xref:System.Delegate.Combine%2A>메서드 (C# 및 Visual Basic) 또는 사용 하 여는 `+` 연산자 (C#), 다음 코드 예제에 나온 것 처럼.</xref:System.Delegate.Combine%2A></span><span class="sxs-lookup"><span data-stu-id="fc179-146">This can lead to a run-time exception when you combine delegates either by using the <xref:System.Delegate.Combine%2A> method (in C# and Visual Basic) or by using the `+` operator (in C#), as shown in the following code example.</span></span>  
  
<span data-ttu-id="fc179-147"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fc179-147"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a><span data-ttu-id="fc179-148">제네릭 형식 매개 변수 값 및 참조 형식에 대 한 가변성</span><span class="sxs-lookup"><span data-stu-id="fc179-148">Variance in Generic Type Parameters for Value and Reference Types</span></span>  
 <span data-ttu-id="fc179-149">제네릭 형식 매개 변수에 대 한 분산 참조 형식에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-149">Variance for generic type parameters is supported for reference types only.</span></span> <span data-ttu-id="fc179-150">예를 들어 `DVariant(Of Int)`로 암시적으로 변환할 수 없는 `DVariant(Of Object)` 또는 `DVariant(Of Long)`정수는 값 형식, 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-150">For example, `DVariant(Of Int)`can't be implicitly converted to `DVariant(Of Object)` or `DVariant(Of Long)`, because integer is a value type.</span></span>  
  
 <span data-ttu-id="fc179-151">다음 예제에서는 그 차이 보여 줍니다. 제네릭 형식 매개 변수 값 형식에 대해 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-151">The following example demonstrates that variance in generic type parameters is not supported for value types.</span></span>  
  
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
  
## <a name="relaxed-delegate-conversion-in-visual-basic"></a><span data-ttu-id="fc179-152">Visual Basic의 완화 된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="fc179-152">Relaxed Delegate Conversion in Visual Basic</span></span>  
 <span data-ttu-id="fc179-153">완화 된 대리자 변환 보다 유연 하 게를 메서드 시그니처를 대리자 형식과 일치 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-153">Relaxed delegate conversion enables more flexibility in matching method signatures with delegate types.</span></span> <span data-ttu-id="fc179-154">예를 들어, 매개 변수 사양을 생략 하 고 메서드는 대리자에 할당할 때 함수 반환 값을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-154">For example, it lets you omit parameter specifications and omit function return values when you assign a method to a delegate.</span></span> <span data-ttu-id="fc179-155">자세한 내용은 참조 [완화 된 대리자 변환](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fc179-155">For more information, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc179-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc179-156">See Also</span></span>  
 <span data-ttu-id="fc179-157">[제네릭](https://msdn.microsoft.com/library/ms172192) </span><span class="sxs-lookup"><span data-stu-id="fc179-157">[Generics](https://msdn.microsoft.com/library/ms172192) </span></span>  
<span data-ttu-id="fc179-158"> [Func 및 Action 제네릭 대리자 (Visual Basic)에 대 한 분산을 사용 하 여](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="fc179-158"> [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span></span>
