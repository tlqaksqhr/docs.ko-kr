---
title: 메서드(F#)
description: '어떻게는 F # 메서드는 노출 하 고 개체 및 형식과의 동작 및 기능을 구현 하는 데 사용 되는 형식과 연결 하는 함수에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: e30300b4dd6cc26712a5adbc8abf720f2c312a6f
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34456642"
---
# <a name="methods"></a><span data-ttu-id="d1afe-103">메서드</span><span class="sxs-lookup"><span data-stu-id="d1afe-103">Methods</span></span>

<span data-ttu-id="d1afe-104">A *메서드* 되는 형식과 연결 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-104">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="d1afe-105">개체 지향 프로그래밍에서 노출 하 고 기능 및 개체 및 형식과의 동작을 구현 메서드가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-105">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>


## <a name="syntax"></a><span data-ttu-id="d1afe-106">구문</span><span class="sxs-lookup"><span data-stu-id="d1afe-106">Syntax</span></span>

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-name parameter-list [ : return-type ] =
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member method-name : type-signature
[ attributes ]
default self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue( default-value )>] input) [ : return-type ]
```

## <a name="remarks"></a><span data-ttu-id="d1afe-107">설명</span><span class="sxs-lookup"><span data-stu-id="d1afe-107">Remarks</span></span>
<span data-ttu-id="d1afe-108">위 구문에서 다양 한 형태의 메서드 선언 및 정의 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-108">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="d1afe-109">메서드 본문이 긴 줄 바꿈을 등호 (=)를 따르며 전체 메서드 본문을 들여쓰 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-109">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="d1afe-110">메서드 선언에 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-110">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="d1afe-111">이들은 메서드 정의 대 한 구문을 앞에 야 하며 일반적으로 별도 줄에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-111">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="d1afe-112">자세한 내용은 [특성](../attributes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1afe-112">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="d1afe-113">메서드를 표시할 수 있습니다 `inline`합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-113">Methods can be marked `inline`.</span></span> <span data-ttu-id="d1afe-114">`inline`에 대한 내용은 [인라인 함수](../functions/inline-functions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1afe-114">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="d1afe-115">비인라인 메서드; 형식 내에서 재귀적으로 사용된 될 수 있습니다. 명시적으로 사용할 필요가 없습니다는 `rec` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-115">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>


## <a name="instance-methods"></a><span data-ttu-id="d1afe-116">인스턴스 메서드</span><span class="sxs-lookup"><span data-stu-id="d1afe-116">Instance Methods</span></span>
<span data-ttu-id="d1afe-117">인스턴스 메서드에서는 `member` 키워드와 *자체 식별자*, 마침표 (.) 및 메서드 이름과 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-117">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="d1afe-118">에 대 한 경우와 마찬가지로 `let` 바인딩은 *매개 변수 목록* 패턴 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-118">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="d1afe-119">일반적으로 다른.NET Framework 언어로 생성 될 때 F #에서 메서드를 매개 변수는 방식으로 메서드 튜플 형식에서 괄호 안에 표시 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-119">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="d1afe-120">그러나 변환된 형식 (공백으로 구분 하 여 매개 변수) 일반적인 진행 되며 다른 패턴도 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-120">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="d1afe-121">다음 예제 정의와 추상이 아닌 인스턴스 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-121">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="d1afe-122">인스턴스 메서드 내에서 할 수 있도록된 바인딩을 사용 하 여 정의 된 액세스 필드 자체 식별자를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="d1afe-122">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="d1afe-123">다른 멤버와 속성에 액세스할 때에 자체 식별자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-123">Use the self identifier when accessing other members and properties.</span></span>


## <a name="static-methods"></a><span data-ttu-id="d1afe-124">정적 메서드</span><span class="sxs-lookup"><span data-stu-id="d1afe-124">Static Methods</span></span>
<span data-ttu-id="d1afe-125">키워드 `static` 을 사용 하는 메서드 인스턴스 없이 호출 될 수를 지정 하 고 개체 인스턴스에 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-125">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="d1afe-126">그렇지 않으면 메서드는 인스턴스 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-126">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="d1afe-127">으로 선언 된 필드를 표시 하는 다음 섹션의 예제는 `let` 키워드를 사용 하 여 선언 된 속성 멤버는 `member` 키워드 및으로 선언 된 정적 메서드는 `static` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-127">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="d1afe-128">다음 예제에서는 정 및 정적 메서드의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-128">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="d1afe-129">이 메서드 정의 중인 것으로 가정은 `SomeType` 이전 섹션에는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-129">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="d1afe-130">추상 메서드 및 가상 메서드</span><span class="sxs-lookup"><span data-stu-id="d1afe-130">Abstract and Virtual Methods</span></span>
<span data-ttu-id="d1afe-131">키워드 `abstract` 메서드가 가상 디스패치 슬롯 있고 클래스에는 정의 없을 수도 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-131">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="d1afe-132">A *가상 디스패치 슬롯* 은 개체 지향 형식에 호출 되는 런타임 시 가상 함수를 조회 하는 데 사용 되는 함수 내부적으로 유지 되는 테이블의 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-132">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="d1afe-133">가상 디스패치 메커니즘은 구현 하는 메커니즘 *다형성*, 개체 지향 프로그래밍의 중요 한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-133">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="d1afe-134">클래스에 하나 이상의 추상 메서드가 정의 없이는 *추상 클래스*, 즉, 해당 클래스의 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-134">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="d1afe-135">추상 클래스에 대 한 자세한 내용은 참조 [추상 클래스](../abstract-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-135">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="d1afe-136">추상 메서드 선언에서 메서드 본문을 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-136">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="d1afe-137">대신, 메서드 이름 뒤에 콜론 (:) 및 메서드에 대 한 형식 서명을는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-137">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="d1afe-138">메서드의 형식 시그니처에 마우스 포인터 위에 놓으면 Visual Studio 코드 편집기에서 메서드 이름을 제외 하 고 매개 변수 이름이 지정 되지 않은 IntelliSense에서 표시 된 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-138">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="d1afe-139">형식 시그니처 대화형으로 작업 하는 경우에 fsi.exe 인터프리터에 의해 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-139">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="d1afe-140">메서드의 형식 시그니처에 목록 뒤에 해당 하는 구분 기호를 사용 하는 반환 형식, 매개 변수 형식으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-140">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="d1afe-141">변환된 매개 변수는 구분 하 여 `->` 튜플 매개 변수는 공백으로 구분 하 여 `*`합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-141">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="d1afe-142">반환 값은 항상으로 인수에서 분리 되어는 `->` 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-142">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="d1afe-143">괄호를 경우와 같이 함수 유형 매개 변수, 복잡 한 매개 변수를 그룹화 하거나 두 개의 매개 변수가 아닌 단일 매개 변수도 튜플을 처리 되는 경우를 나타내기 위해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-143">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="d1afe-144">있습니다 수 추상 메서드에 제공할 수도 default 정의를 클래스 정의 추가 하 고 사용 하 여는 `default` 키워드에이 항목의 구문 블록에 표시 된 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-144">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="d1afe-145">추상 메서드는 같은 클래스에 정의 되어 다른.NET Framework 언어의 가상 메서드 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-145">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="d1afe-146">정의가 있는지 여부는 `abstract` 키워드는 클래스에 대 한 가상 함수 테이블에 새 디스패치 슬롯을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-146">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="d1afe-147">기본 클래스 추상 메서드를 구현 하는지 여부에 관계 없이 파생된 클래스는 추상 메서드 구현을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-147">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="d1afe-148">파생된 클래스에서 추상 메서드를 구현 하려면 사용 하지 않은 채 파생된 클래스에서 동일한 이름 및 서명을 갖는 메서드를 정의 고 `override` 또는 `default` 키워드, 메서드 본문을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-148">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="d1afe-149">키워드 `override` 및 `default` 완전히 동일한 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-149">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="d1afe-150">사용 하 여 `override` 새 메서드는 기본 클래스 구현을 재정의 하는 경우 사용 하 여 `default` 원래 추상 선언와 같은 클래스에서 구현을 만들 때.</span><span class="sxs-lookup"><span data-stu-id="d1afe-150">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="d1afe-151">사용 하지 않는 `abstract` 추상 기본 클래스에 선언 된 메서드를 구현 하는 방법에 대 한 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-151">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="d1afe-152">다음 예제에서는 추상 메서드 `Rotate` 기본 구현이,.NET Framework 가상 메서드의 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-152">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="d1afe-153">다음 예제에서는 기본 클래스 메서드를 재정의 하는 파생된 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-153">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="d1afe-154">이 경우 재정의 메서드는 아무 작업도 수행 되도록 동작을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-154">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="d1afe-155">오버로드된 메서드</span><span class="sxs-lookup"><span data-stu-id="d1afe-155">Overloaded Methods</span></span>
<span data-ttu-id="d1afe-156">오버 로드 된 메서드는 지정된 된 형식에 이름이 동일 하지만 서로 다른 인수를 포함 하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-156">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="d1afe-157">F #에서 선택적 인수는 일반적으로 오버 로드 된 메서드 대신 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-157">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="d1afe-158">그러나, 오버 로드 된 메서드는 인수에에서는 변환된 되지 형식은 튜플 형식 언어에서 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-158">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="d1afe-159">선택적 인수</span><span class="sxs-lookup"><span data-stu-id="d1afe-159">Optional Arguments</span></span>

<span data-ttu-id="d1afe-160">F # 4.1 부터는 있을 수도 있습니다는 기본 매개 변수 값에 선택적 인수 메서드에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-160">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="d1afe-161">이 C# 코드와의 상호 운용성을 용이 하 게 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-161">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="d1afe-162">다음 예에서는 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-162">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="d1afe-163">에 전달 된 값을 `DefaultParameterValue` 입력된 형식과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-163">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="d1afe-164">위의 샘플에서는 `int`합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-164">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="d1afe-165">정수가 아닌 값을 전달 하 려 `DefaultParameterValue` 컴파일 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-165">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="d1afe-166">예: 속성 및 메서드</span><span class="sxs-lookup"><span data-stu-id="d1afe-166">Example: Properties and Methods</span></span>
<span data-ttu-id="d1afe-167">다음 예제에서는 형식 필드, 개인 함수, 속성 및 정적 메서드의 예에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1afe-167">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="d1afe-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1afe-168">See Also</span></span>
[<span data-ttu-id="d1afe-169">멤버</span><span class="sxs-lookup"><span data-stu-id="d1afe-169">Members</span></span>](index.md)
