---
title: "Variant 제네릭 인터페이스 만들기 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 380af3b29172b1fa13d42d33e574201607cb804b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="creating-variant-generic-interfaces-visual-basic"></a><span data-ttu-id="e1d87-102">Variant 제네릭 인터페이스 만들기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1d87-102">Creating Variant Generic Interfaces (Visual Basic)</span></span>
<span data-ttu-id="e1d87-103">인터페이스에서 제네릭 형식 매개 변수를 공변(covariant) 또는 반공변(contravariant)으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-103">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="e1d87-104">*공변성(covariance)*은 인터페이스 메서드가 제네릭 형식 매개 변수에 정의된 것보다 더 많은 수의 파생된 반환 형식을 갖도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-104">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="e1d87-105">*반공변성(contravariance)*은 인터페이스 메서드가 제네릭 매개 변수에 지정된 것보다 더 적은 수의 파생된 형식의 인수 형식을 갖도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-105">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="e1d87-106">공변(covariant) 또는 반공변(contravariant) 제네릭 형식 매개 변수가 포함된 제네릭 인터페이스를 *variant*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-106">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1d87-107">.NET Framework 4에서는 기존의 몇몇 제네릭 인터페이스에 대한 가변성 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-107">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="e1d87-108">.NET Framework의 variant 인터페이스 목록에 대 한 참조 [제네릭 인터페이스 (Visual Basic)에 대 한 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-108">For the list of the variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>  
  
## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="e1d87-109">Variant 제네릭 인터페이스 선언</span><span class="sxs-lookup"><span data-stu-id="e1d87-109">Declaring Variant Generic Interfaces</span></span>  
 <span data-ttu-id="e1d87-110">제네릭 형식 매개 변수에 `in` 및 `out` 키워드를 사용하여 Variant 제네릭 인터페이스를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-110">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e1d87-111">`ByRef`Visual Basic의 매개 변수는 variant 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-111">`ByRef` parameters in Visual Basic cannot be variant.</span></span> <span data-ttu-id="e1d87-112">또한 값 형식은 가변성을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-112">Value types also do not support variance.</span></span>  
  
 <span data-ttu-id="e1d87-113">`out` 키워드를 사용하여 제네릭 형식 매개 변수를 공변(covariant)으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-113">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="e1d87-114">공변(covariant) 형식은 다음 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-114">The covariant type must satisfy the following conditions:</span></span>  
  
-   <span data-ttu-id="e1d87-115">형식은 인터페이스 메서드의 반환 형식으로만 사용되고 메서드 인수의 형식으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-115">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="e1d87-116">이 내용은 `R` 형식이 공변(covariant)으로 선언된 다음 예제에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-116">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Function GetSomething() As R  
        ' The following statement generates a compiler error.  
        ' Sub SetSomething(ByVal sampleArg As R)  
    End Interface  
    ```  
  
     <span data-ttu-id="e1d87-117">그러나 이 규칙에는 한 가지 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-117">There is one exception to this rule.</span></span> <span data-ttu-id="e1d87-118">반공변(contravariant) 제네릭 대리자가 메서드 매개 변수로 있는 경우 형식을 이 대리자에 대한 제네릭 형식 매개 변수로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-118">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="e1d87-119">다음 예제에서 `R` 형식을 통해 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-119">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="e1d87-120">자세한 내용은 참조 [대리자 (Visual Basic)에 대 한 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) 및 [Func 및 Action 제네릭 대리자 (Visual Basic)에 대 한 분산을 사용 하 여](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-120">For more information, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Sub DoSomething(ByVal callback As Action(Of R))  
    End Interface  
    ```  
  
-   <span data-ttu-id="e1d87-121">형식은 인터페이스 메서드에 대한 제네릭 제약 조건으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-121">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="e1d87-122">이는 다음 코드에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-122">This is illustrated in the following code.</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        ' The following statement generates a compiler error  
        ' because you can use only contravariant or invariant types  
        ' in generic contstraints.  
        ' Sub DoSomething(Of T As R)()  
    End Interface  
    ```  
  
 <span data-ttu-id="e1d87-123">`in` 키워드를 사용하여 제네릭 형식 매개 변수를 반공변(contravariant)으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-123">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="e1d87-124">반공변(contravariant) 형식은 메서드 인수의 형식으로서만 사용할 수 있으며 인터페이스 메서드의 반환 형식으로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-124">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="e1d87-125">반공변(contravariant) 형식은 제네릭 제약 조건에 사용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-125">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="e1d87-126">다음 코드에서는 반공변(contravariant) 인터페이스를 선언하고 해당 메서드 중 하나에 제네릭 제약 조건을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-126">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>  
  
```vb  
Interface IContravariant(Of In A)  
    Sub SetSomething(ByVal sampleArg As A)  
    Sub DoSomething(Of T As A)()  
    ' The following statement generates a compiler error.  
    ' Function GetSomething() As A  
End Interface  
```  
  
 <span data-ttu-id="e1d87-127">같은 인터페이스에서 그러나 서로 다른 형식 매개 변수에 대해 공변성(covariance) 및 반공변성(contravariance)을 모두 지원하는 것도 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-127">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>  
  
```vb  
Interface IVariant(Of Out R, In A)  
    Function GetSomething() As R  
    Sub SetSomething(ByVal sampleArg As A)  
    Function GetSetSomething(ByVal sampleArg As A) As R  
End Interface  
```  
  
 <span data-ttu-id="e1d87-128">Visual Basic에서 대리자 형식을 지정 하지 않고 variant 인터페이스의 이벤트를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-128">In Visual Basic, you can't declare events in variant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="e1d87-129">또한 variant 인터페이스 클래스, 열거형 또는 구조에 중첩 없습니다 되지만 인터페이스 중첩 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-129">Also, a variant interface can't have nested classes, enums, or structures, but it can have nested interfaces.</span></span> <span data-ttu-id="e1d87-130">이는 다음 코드에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-130">This is illustrated in the following code.</span></span>  
  
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
  
## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="e1d87-131">Variant 제네릭 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="e1d87-131">Implementing Variant Generic Interfaces</span></span>  
 <span data-ttu-id="e1d87-132">고정(invariant) 인터페이스에 사용되는 같은 구문을 사용하여 클래스에서 Variant 제네릭 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-132">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="e1d87-133">다음 코드 예제에서는 제네릭 클래스에서 공변(covariant) 인터페이스를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-133">The following code example shows how to implement a covariant interface in a generic class.</span></span>  
  
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
  
 <span data-ttu-id="e1d87-134">Variant 인터페이스를 구현하는 클래스는 고정입니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-134">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="e1d87-135">예를 들어, 다음과 같은 코드를 생각해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-135">For example, consider the following code.</span></span>  
  
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
  
## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="e1d87-136">Variant 제네릭 인터페이스 확장</span><span class="sxs-lookup"><span data-stu-id="e1d87-136">Extending Variant Generic Interfaces</span></span>  
 <span data-ttu-id="e1d87-137">Variant 제네릭 인터페이스를 확장할 경우 `in` 및 `out` 키워드를 사용하여 파생 인터페이스가 가변성을 지원하는지 명시적으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-137">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="e1d87-138">컴파일러에서는 확장되고 있는 인터페이스에서 가변성을 유추하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-138">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="e1d87-139">예를 들어 다음 인터페이스를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-139">For example, consider the following interfaces.</span></span>  
  
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
  
 <span data-ttu-id="e1d87-140">에 `Invariant(Of T)` 인터페이스, 제네릭 형식 매개 변수 `T` 는 고정, 반면에 `IExtCovariant (Of Out T)`형식 매개 변수는 공변 (covariant), 두 인터페이스 모두 동일한 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-140">In the `Invariant(Of T)` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant (Of Out T)`the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="e1d87-141">반공변(contravariant) 제네릭 형식 매개 변수에는 같은 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-141">The same rule is applied to contravariant generic type parameters.</span></span>  
  
 <span data-ttu-id="e1d87-142">제네릭 형식 매개 변수 `T`가 공변(covariant)인 인터페이스 및 확장 인터페이스에서 제네릭 형식 매개 변수 `T`가 고정인 경우 반공변(contravariant)인 인터페이스를 둘 다 확장하는 인터페이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-142">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="e1d87-143">다음 코드 예제에서 이 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-143">This is illustrated in the following code example.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IContravariant(Of In T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T), IContravariant(Of T)  
End Interface  
```  
  
 <span data-ttu-id="e1d87-144">그러나 한 인터페이스에서 제네릭 형식 매개 변수 `T`가 공변(covariant)으로 선언되면 확장 인터페이스에서는 이 매개 변수를 반공변(contravariant)으로 선언할 수 없고, 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-144">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="e1d87-145">다음 코드 예제에서 이 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-145">This is illustrated in the following code example.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
' The following statements generate a compiler error.  
' Interface ICoContraVariant(Of In T)  
'     Inherits ICovariant(Of T)  
' End Interface  
```  
  
### <a name="avoiding-ambiguity"></a><span data-ttu-id="e1d87-146">모호성 방지</span><span class="sxs-lookup"><span data-stu-id="e1d87-146">Avoiding Ambiguity</span></span>  
 <span data-ttu-id="e1d87-147">Variant 제네릭 인터페이스를 구현할 경우 가변성으로 인해 모호성이 나타나는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-147">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="e1d87-148">이러한 경우가 발생해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-148">This should be avoided.</span></span>  
  
 <span data-ttu-id="e1d87-149">예를 들어 서로 다른 제네릭 형식 매개 변수가 포함된 같은 Variant 제네릭 인터페이스를 한 클래스에서 명시적으로 구현하면 모호성이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-149">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="e1d87-150">컴파일러에서는 이 경우 오류를 생성하지 않지만 런타임에 선택될 인터페이스 구현이 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-150">The compiler does not produce an error in this case, but it is not specified which interface implementation will be chosen at runtime.</span></span> <span data-ttu-id="e1d87-151">이로 인해 코드에서 미묘한 버그가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-151">This could lead to subtle bugs in your code.</span></span> <span data-ttu-id="e1d87-152">다음 코드 예제를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-152">Consider the following code example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1d87-153">와 `Option Strict Off`, Visual Basic 모호한 인터페이스 구현 때 컴파일러 경고를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-153">With `Option Strict Off`, Visual Basic generates a compiler warning when there is an ambiguous interface implementation.</span></span> <span data-ttu-id="e1d87-154">와 `Option Strict On`, Visual Basic 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-154">With `Option Strict On`, Visual Basic generates a compiler error.</span></span>  
  
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
  
 <span data-ttu-id="e1d87-155">이 예제에서는 `pets.GetEnumerator` 메서드가 `Cat` 및 `Dog` 중에 선택하는 방법이 지정되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-155">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="e1d87-156">이로 인해 코드에서 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d87-156">This could cause problems in your code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d87-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1d87-157">See Also</span></span>  
 [<span data-ttu-id="e1d87-158">제네릭 인터페이스의 가변성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1d87-158">Variance in Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [<span data-ttu-id="e1d87-159">Func 및 Action 제네릭 대리자에 가변성 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1d87-159">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
