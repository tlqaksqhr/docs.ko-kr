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
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a2cbf0a204a5a3af45f55a14c011518c7021f5b4
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="creating-variant-generic-interfaces-visual-basic"></a><span data-ttu-id="4b028-102">Variant 제네릭 인터페이스 만들기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b028-102">Creating Variant Generic Interfaces (Visual Basic)</span></span>
<span data-ttu-id="4b028-103">공변 (covariant)에 따라 인터페이스의 제네릭 형식 매개 변수를 선언할 수 또는 반공 변입니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-103">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="4b028-104">*공변성 (covariance)* 인터페이스 메서드를 더 많이 파생 된 반환 형식이 제네릭 형식 매개 변수에 의해 정의 된 것을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-104">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="4b028-105">*반 공변성* 인터페이스 메서드는 제네릭 매개 변수에 지정 된 것 보다 더 적게 파생 된 인수 형식을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-105">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="4b028-106">공변 (covariant)이 있는 제네릭 인터페이스 또는 반공 변 제네릭 형식 매개 변수 라고 *variant*합니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-106">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b028-107">.NET framework 4에는 여러 기존 제네릭 인터페이스에 대 한 분산 지원이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-107">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="4b028-108">.NET Framework의 variant 인터페이스 목록에 대 한 참조 [제네릭 인터페이스 (Visual Basic)에 대 한 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-108">For the list of the variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>  
  
## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="4b028-109">Variant 제네릭 인터페이스 선언</span><span class="sxs-lookup"><span data-stu-id="4b028-109">Declaring Variant Generic Interfaces</span></span>  
 <span data-ttu-id="4b028-110">사용 하 여 variant 제네릭 인터페이스를 선언할 수는 `in` 및 `out` 제네릭 형식 매개 변수에 대 한 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-110">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4b028-111"> `ByRef`Visual Basic의 매개 변수는 variant 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-111"> `ByRef` parameters in Visual Basic cannot be variant.</span></span> <span data-ttu-id="4b028-112">또한 값 형식의 차이 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-112">Value types also do not support variance.</span></span>  
  
 <span data-ttu-id="4b028-113">선언할 수 있습니다 제네릭 형식 매개 변수는 공변 (covariant)를 사용 하 여는 `out` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-113">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="4b028-114">공변 (covariant) 형식에는 다음 조건을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-114">The covariant type must satisfy the following conditions:</span></span>  
  
-   <span data-ttu-id="4b028-115">형식을은 인터페이스 메서드의 반환 형식 으로만 사용 되 고 메서드 인수 형식으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-115">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="4b028-116">이에 다음 예제에서는 설명 형식을 `R` 공변 (covariant) 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-116">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Function GetSomething() As R  
        ' The following statement generates a compiler error.  
        ' Sub SetSomething(ByVal sampleArg As R)  
    End Interface  
    ```  
  
     <span data-ttu-id="4b028-117">그러나 이 규칙에는 한 가지 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-117">There is one exception to this rule.</span></span> <span data-ttu-id="4b028-118">메서드 매개 변수는 반공 변 제네릭 대리자를 사용 하도록 설정한 경우 대리자에 대 한 형식을 제네릭 형식 매개 변수로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-118">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="4b028-119">형식에서이 확인할 `R` 다음 예제에서입니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-119">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="4b028-120">자세한 내용은 참조 [대리자 (Visual Basic)에 대 한 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) 및 [Func 및 Action 제네릭 대리자 (Visual Basic)를 사용 하 여 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-120">For more information, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Sub DoSomething(ByVal callback As Action(Of R))  
    End Interface  
    ```  
  
-   <span data-ttu-id="4b028-121">인터페이스 메서드에 대 한 형식은 제네릭 제약 조건으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-121">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="4b028-122">다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-122">This is illustrated in the following code.</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        ' The following statement generates a compiler error  
        ' because you can use only contravariant or invariant types  
        ' in generic contstraints.  
        ' Sub DoSomething(Of T As R)()  
    End Interface  
    ```  
  
 <span data-ttu-id="4b028-123">사용 하 여 제네릭 형식 매개 변수가 반공 변을 선언할 수는 `in` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-123">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="4b028-124">반공 변 형식 인터페이스 메서드의 반환 형식이 아닌 메서드 인수의 형식으로만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-124">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="4b028-125">반공 변 형식이 제네릭 제약 조건에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-125">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="4b028-126">다음 코드에는 반공 변 인터페이스를 선언 하 고 해당 메서드 중 하나에 대 한 제네릭 제약 조건을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-126">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>  
  
```vb  
Interface IContravariant(Of In A)  
    Sub SetSomething(ByVal sampleArg As A)  
    Sub DoSomething(Of T As A)()  
    ' The following statement generates a compiler error.  
    ' Function GetSomething() As A  
End Interface  
```  
  
 <span data-ttu-id="4b028-127">다음 코드 예제와 같이 동일한 인터페이스에 있지만 서로 다른 형식 매개 변수에 대해 모두 공 분산과 반공 분산을 지원 하기 위해도 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-127">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>  
  
```vb  
Interface IVariant(Of Out R, In A)  
    Function GetSomething() As R  
    Sub SetSomething(ByVal sampleArg As A)  
    Function GetSetSomething(ByVal sampleArg As A) As R  
End Interface  
```  
  
 <span data-ttu-id="4b028-128">Visual Basic에서 대리자 형식을 지정 하지 않고 variant 인터페이스의 이벤트를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-128">In Visual Basic, you can't declare events in variant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="4b028-129">또한 없습니다 중첩 변형 인터페이스 클래스, 열거형 또는 구조를 하지만 인터페이스 중첩 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-129">Also, a variant interface can't have nested classes, enums, or structures, but it can have nested interfaces.</span></span> <span data-ttu-id="4b028-130">다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-130">This is illustrated in the following code.</span></span>  
  
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
  
## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="4b028-131">Variant 제네릭 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="4b028-131">Implementing Variant Generic Interfaces</span></span>  
 <span data-ttu-id="4b028-132">클래스에서 고정 인터페이스에 사용 되는 구문과 동일한 구문을 사용 하 여 variant 제네릭 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-132">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="4b028-133">다음 코드 예제는 제네릭 클래스에는 공변 (covariant) 인터페이스를 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-133">The following code example shows how to implement a covariant interface in a generic class.</span></span>  
  
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
  
 <span data-ttu-id="4b028-134">Variant 인터페이스를 구현 하는 클래스 변하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-134">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="4b028-135">예를 들어, 다음과 같은 코드를 생각해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-135">For example, consider the following code.</span></span>  
  
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
  
## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="4b028-136">Variant 제네릭 인터페이스를 확장 하는 방법</span><span class="sxs-lookup"><span data-stu-id="4b028-136">Extending Variant Generic Interfaces</span></span>  
 <span data-ttu-id="4b028-137">Variant 제네릭 인터페이스를 확장할 때 사용 해야는 `in` 및 `out` 키워드를 명시적으로 파생 된 인터페이스 분산을 지원 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-137">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="4b028-138">컴파일러에서는 확장 되는 인터페이스에서 차이 유추 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-138">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="4b028-139">예를 들어 다음 인터페이스를 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-139">For example, consider the following interfaces.</span></span>  
  
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
  
 <span data-ttu-id="4b028-140">에 `Invariant(Of T)` 인터페이스를 제네릭 형식 매개 변수 `T` 는 고정, 반면에 `IExtCovariant (Of Out T)`형식 매개 변수는 공변 (covariant), 두 인터페이스 모두 동일한 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-140">In the `Invariant(Of T)` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant (Of Out T)`the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="4b028-141">반공 변 제네릭 형식 매개 변수에 동일한 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-141">The same rule is applied to contravariant generic type parameters.</span></span>  
  
 <span data-ttu-id="4b028-142">여기서는 제네릭 형식 매개 변수는 모두 인터페이스를 확장 하는 인터페이스를 만들 수 있습니다 `T` 는 공변 (covariant)는 확장에 반 공변성을 있기 인터페이스 인터페이스는 제네릭 형식 매개 변수 및 `T` 변하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-142">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="4b028-143">다음 코드 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-143">This is illustrated in the following code example.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IContravariant(Of In T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T), IContravariant(Of T)  
End Interface  
```  
  
 <span data-ttu-id="4b028-144">그러나 제네릭 형식 매개 변수 이면 `T` 는 하나의 인터페이스에 공변 (covariant)를 선언를 선언할 수는 없으며 반공 변 확장 인터페이스 또는 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-144">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="4b028-145">다음 코드 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-145">This is illustrated in the following code example.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
' The following statements generate a compiler error.  
' Interface ICoContraVariant(Of In T)  
'     Inherits ICovariant(Of T)  
' End Interface  
```  
  
### <a name="avoiding-ambiguity"></a><span data-ttu-id="4b028-146">모호성을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-146">Avoiding Ambiguity</span></span>  
 <span data-ttu-id="4b028-147">Variant 제네릭 인터페이스를 구현 하는 경우 모호성 분산 경우가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-147">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="4b028-148">이러한 경우가 발생해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-148">This should be avoided.</span></span>  
  
 <span data-ttu-id="4b028-149">예를 들어 하나의 클래스에는 동일한 변형 제네릭 인터페이스를 다른 제네릭 형식 매개 변수를 명시적으로 구현 하는 경우 모호성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-149">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="4b028-150">컴파일러 오류가 경우에 발생 하지는 않지만 인터페이스 구현이 런타임에 선택 될 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-150">The compiler does not produce an error in this case, but it is not specified which interface implementation will be chosen at runtime.</span></span> <span data-ttu-id="4b028-151">이 코드에 버그가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-151">This could lead to subtle bugs in your code.</span></span> <span data-ttu-id="4b028-152">다음 코드 예제를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-152">Consider the following code example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b028-153">와 `Option Strict Off`, Visual Basic 모호한 인터페이스 구현을 때 컴파일러 경고를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-153">With `Option Strict Off`, Visual Basic generates a compiler warning when there is an ambiguous interface implementation.</span></span> <span data-ttu-id="4b028-154">와 `Option Strict On`, Visual Basic 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-154">With `Option Strict On`, Visual Basic generates a compiler error.</span></span>  
  
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
  
 <span data-ttu-id="4b028-155">이 예제에서는 지정 되지 않습니다 방법을 `pets.GetEnumerator` 메서드 간의 선택 `Cat` 및 `Dog`합니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-155">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="4b028-156">코드에서 문제를 일으킬 수이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b028-156">This could cause problems in your code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b028-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b028-157">See Also</span></span>  
 <span data-ttu-id="4b028-158">[(Visual Basic) 제네릭 인터페이스의 가변성](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="4b028-158">[Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span></span>  
<span data-ttu-id="4b028-159"> [Func 및 Action 제네릭 대리자 (Visual Basic)에 대 한 분산을 사용 하 여](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="4b028-159"> [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span></span>
