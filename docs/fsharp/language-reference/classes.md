---
title: 클래스(F#)
description: 'F # 클래스는 속성, 메서드 및 이벤트를 가질 수 있는 개체를 나타내는 형식 하는 방법에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 67164bd9f91c14f465bf05630259ad70cb8d90e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565888"
---
# <a name="classes"></a><span data-ttu-id="961ca-103">클래스</span><span class="sxs-lookup"><span data-stu-id="961ca-103">Classes</span></span>

<span data-ttu-id="961ca-104">*클래스* 속성, 메서드 및 이벤트를 가질 수 있는 개체를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-104">*Classes* are types that represent objects that can have properties, methods, and events.</span></span>


## <a name="syntax"></a><span data-ttu-id="961ca-105">구문</span><span class="sxs-lookup"><span data-stu-id="961ca-105">Syntax</span></span>

```fsharp
// Class definition:
type [access-modifier] type-name [type-params] [access-modifier] ( parameter-list ) [ as identifier ] =
[ class ]
[ inherit base-type-name(base-constructor-args) ]
[ let-bindings ]
[ do-bindings ]
member-list
...
[ end ]
// Mutually recursive class definitions:
type [access-modifier] type-name1 ...
and [access-modifier] type-name2 ...
...
```

## <a name="remarks"></a><span data-ttu-id="961ca-106">설명</span><span class="sxs-lookup"><span data-stu-id="961ca-106">Remarks</span></span>
<span data-ttu-id="961ca-107">클래스는.NET 개체 유형;에 대 한 기본적인 설명을 나타냅니다. 클래스는 F #에서 개체 지향 프로그래밍을 지 원하는 기본 형식 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-107">Classes represent the fundamental description of .NET object types; the class is the primary type concept that supports object-oriented programming in F#.</span></span>

<span data-ttu-id="961ca-108">위 구문에는 `type-name` 은 임의의 유효한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-108">In the preceding syntax, the `type-name` is any valid identifier.</span></span> <span data-ttu-id="961ca-109">`type-params` 선택적 제네릭 형식 매개 변수에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-109">The `type-params` describes optional generic type parameters.</span></span> <span data-ttu-id="961ca-110">형식 매개 변수 이름과 꺾쇠 괄호로 묶여 있는 제약 조건을 구성 됩니다 (`<` 및 `>`).</span><span class="sxs-lookup"><span data-stu-id="961ca-110">It consists of type parameter names and constraints enclosed in angle brackets (`<` and `>`).</span></span> <span data-ttu-id="961ca-111">자세한 내용은 참조 [제네릭](generics/index.md) 및 [제약 조건을](generics/constraints.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-111">For more information, see [Generics](generics/index.md) and [Constraints](generics/constraints.md).</span></span> <span data-ttu-id="961ca-112">`parameter-list` 생성자 매개 변수에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-112">The `parameter-list` describes constructor parameters.</span></span> <span data-ttu-id="961ca-113">형식;에 관련 된 첫 번째 액세스 한정자 두 번째 주 생성자에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-113">The first access modifier pertains to the type; the second pertains to the primary constructor.</span></span> <span data-ttu-id="961ca-114">기본값은 두 경우 모두 `public`합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-114">In both cases, the default is `public`.</span></span>

<span data-ttu-id="961ca-115">사용 하 여 클래스에 대 한 기본 클래스를 지정 하는 `inherit` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-115">You specify the base class for a class by using the `inherit` keyword.</span></span> <span data-ttu-id="961ca-116">괄호로 기본 클래스 생성자에 대 한 인수를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-116">You must supply arguments, in parentheses, for the base class constructor.</span></span>

<span data-ttu-id="961ca-117">함수를 사용 하 여 로컬 클래스에 있는 값 또는 필드를 선언 하면 `let` 바인딩 및 사용자에 대 한 일반 규칙을 따라야 `let` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="961ca-117">You declare fields or function values that are local to the class by using `let` bindings, and you must follow the general rules for `let` bindings.</span></span> <span data-ttu-id="961ca-118">`do-bindings` 섹션 개체 생성 시 실행 되는 코드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-118">The `do-bindings` section includes code to be executed upon object construction.</span></span>

<span data-ttu-id="961ca-119">`member-list` 추가 생성자, 인스턴스 및 정적 메서드 선언, 인터페이스 선언, 추상 바인딩 및 속성 및 이벤트 선언으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-119">The `member-list` consists of additional constructors, instance and static method declarations, interface declarations, abstract bindings, and property and event declarations.</span></span> <span data-ttu-id="961ca-120">에 설명 되어 [멤버](members/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-120">These are described in [Members](members/index.md).</span></span>

<span data-ttu-id="961ca-121">`identifier` 선택적 함께 사용 되는 `as` 키워드를 인스턴스 변수 또는 형식의 인스턴스를 참조 하도록 형식 정의에 사용할 수 있는 자체 식별자에는 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-121">The `identifier` that is used with the optional `as` keyword gives a name to the instance variable, or self identifier, which can be used in the type definition to refer to the instance of the type.</span></span> <span data-ttu-id="961ca-122">자세한 내용은이 항목의 뒷부분에 나오는 자체 식별자 섹션을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-122">For more information, see the section Self Identifiers later in this topic.</span></span>

<span data-ttu-id="961ca-123">키워드 `class` 및 `end` 시작을 표시 하 고 정의의 끝은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-123">The keywords `class` and `end` that mark the start and end of the definition are optional.</span></span>

<span data-ttu-id="961ca-124">와 함께 서로 참조 하는 형식 재귀 형식을 조인 하는 상호는 `and` 상호 재귀 함수는 마찬가지로 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-124">Mutually recursive types, which are types that reference each other, are joined together with the `and` keyword just as mutually recursive functions are.</span></span> <span data-ttu-id="961ca-125">예를 들어 상호 재귀 형식 섹션을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-125">For an example, see the section Mutually Recursive Types.</span></span>


## <a name="constructors"></a><span data-ttu-id="961ca-126">생성자</span><span class="sxs-lookup"><span data-stu-id="961ca-126">Constructors</span></span>
<span data-ttu-id="961ca-127">생성자는 클래스 형식의 인스턴스를 생성 하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-127">The constructor is code that creates an instance of the class type.</span></span> <span data-ttu-id="961ca-128">클래스에 대 한 생성자 보다 다른.NET 언어에서 F #에서 약간 다르게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-128">Constructors for classes work somewhat differently in F# than they do in other .NET languages.</span></span> <span data-ttu-id="961ca-129">F # 클래스, 즉 항상에 해당 인수를 설명 하는 기본 생성자는 `parameter-list` 뒤에 형식 이름 및 해당 본문으로 구성 됩니다는 `let` (및 `let rec`) 클래스 선언과 의시작부분에바인딩`do`뒤에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-129">In an F# class, there is always a primary constructor whose arguments are described in the `parameter-list` that follows the type name, and whose body consists of the `let` (and `let rec`) bindings at the start of the class declaration and the `do` bindings that follow.</span></span> <span data-ttu-id="961ca-130">기본 생성자의 인수는 클래스 선언 전체 많습니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-130">The arguments of the primary constructor are in scope throughout the class declaration.</span></span>

<span data-ttu-id="961ca-131">다른 생성자를 사용 하 여 추가할 수 있습니다는 `new` 키워드를 다음과 같이 멤버를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-131">You can add additional constructors by using the `new` keyword to add a member, as follows:</span></span>

<span data-ttu-id="961ca-132">`new`(`argument-list`) = `constructor-body`</span><span class="sxs-lookup"><span data-stu-id="961ca-132">`new`(`argument-list`) = `constructor-body`</span></span>

<span data-ttu-id="961ca-133">새로운 생성자의 본문 위쪽 클래스 선언에 지정 된 기본 생성자를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-133">The body of the new constructor must invoke the primary constructor that is specified at the top of the class declaration.</span></span>

<span data-ttu-id="961ca-134">다음 예제에서는이 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-134">The following example illustrates this concept.</span></span> <span data-ttu-id="961ca-135">다음 코드에서 `MyClass` 두 명의 생성자가, 두 개의 인수 및 다른 생성자를 사용 하는 기본 생성자는 인수가 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-135">In the following code, `MyClass` has two constructors, a primary constructor that takes two arguments and another constructor that takes no arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]
    
## <a name="let-and-do-bindings"></a><span data-ttu-id="961ca-136">let 및 do 바인딩</span><span class="sxs-lookup"><span data-stu-id="961ca-136">let and do Bindings</span></span>

<span data-ttu-id="961ca-137">`let` 및 `do` 바인딩은 클래스 정의에서 기본 클래스 생성자의 본문을 구성 하 고 실행 하므로 클래스 인스턴스를 만들 때마다 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-137">The `let` and `do` bindings in a class definition form the body of the primary class constructor, and therefore they run whenever a class instance is created.</span></span> <span data-ttu-id="961ca-138">경우는 `let` 바인딩은 함수는 다음 멤버로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-138">If a `let` binding is a function, then it is compiled into a member.</span></span> <span data-ttu-id="961ca-139">경우는 `let` 바인딩 함수 또는 멤버에 사용 되지 않는 값은 다음 생성자에 로컬인 변수가 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-139">If the `let` binding is a value that is not used in any function or member, then it is compiled into a variable that is local to the constructor.</span></span> <span data-ttu-id="961ca-140">그렇지 않으면 클래스의 필드에 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-140">Otherwise, it is compiled into a field of the class.</span></span> <span data-ttu-id="961ca-141">`do` 식 다음에 나오는 기본 생성자로 컴파일되고 모든 인스턴스에 대해 초기화 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-141">The `do` expressions that follow are compiled into the primary constructor and execute initialization code for every instance.</span></span> <span data-ttu-id="961ca-142">모든 추가 생성자는 항상 기본 생성자를 호출 하므로 `let` 바인딩 및 `do` 바인딩은 생성자가 호출 프로그램에 관계 없이 항상 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-142">Because any additional constructors always call the primary constructor, the `let` bindings and `do` bindings always execute regardless of which constructor is called.</span></span>

<span data-ttu-id="961ca-143">하지만 필드에 의해 만들어진 `let` 액세스할 수에서 정적 메서드는 정적 메서드를 매개 변수로 인스턴스 변수를 사용 하는 경우에; 바인딩 메서드 및 클래스의 속성을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-143">Fields that are created by `let` bindings can be accessed throughout the methods and properties of the class; however, they cannot be accessed from static methods, even if the static methods take an instance variable as a parameter.</span></span> <span data-ttu-id="961ca-144">이러한 있는 경우 자체 식별자를 사용 하 여 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-144">They cannot be accessed by using the self identifier, if one exists.</span></span>


## <a name="self-identifiers"></a><span data-ttu-id="961ca-145">자체 식별자</span><span class="sxs-lookup"><span data-stu-id="961ca-145">Self Identifiers</span></span>

<span data-ttu-id="961ca-146">A *자체 식별자* 현재 인스턴스를 나타내는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-146">A *self identifier* is a name that represents the current instance.</span></span> <span data-ttu-id="961ca-147">자체 식별자 유사는 `this` C# 또는 c + + 키워드 또는 `Me` Visual Basic의 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-147">Self identifiers resemble the `this` keyword in C# or C++ or `Me` in Visual Basic.</span></span> <span data-ttu-id="961ca-148">자체 식별자의 범위는 개별 방법에 대해서만 또는 전체 클래스 정의 대 한 자체 식별자 여부에 따라 두 가지 방법으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-148">You can define a self identifier in two different ways, depending on whether you want the self identifier to be in scope for the whole class definition or just for an individual method.</span></span>

<span data-ttu-id="961ca-149">전체 클래스에 대 한 자체 식별자를 정의 하려면 사용 하 여는 `as` 생성자 매개 변수의 닫는 괄호 뒤 키워드를 나열 하 고 식별자 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-149">To define a self identifier for the whole class, use the `as` keyword after the closing parentheses of the constructor parameter list, and specify the identifier name.</span></span>

<span data-ttu-id="961ca-150">자체 식별자에 대 한 단 하나의 메서드를 정의 하려면 멤버 선언 바로 앞에 메서드 이름 및 구분 기호로 마침표 (.)에서 자체 식별자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-150">To define a self identifier for just one method, provide the self identifier in the member declaration, just before the method name and a period (.) as a separator.</span></span>

<span data-ttu-id="961ca-151">다음 코드 예제에서는 자체 식별자를 만들려고 하는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-151">The following code example illustrates the two ways to create a self identifier.</span></span> <span data-ttu-id="961ca-152">첫 번째 줄에서은 `as` 키워드 자체 식별자를 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-152">In the first line, the `as` keyword is used to define the self identifier.</span></span> <span data-ttu-id="961ca-153">다섯 번째 줄에서는 식별자 `this` 인 범위를 메서드에 제한 자체 식별자를 정의 하는 데 사용 되 `PrintMessage`합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-153">In the fifth line, the identifier `this` is used to define a self identifier whose scope is restricted to the method `PrintMessage`.</span></span>

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

<span data-ttu-id="961ca-154">와 달리 다른.NET 언어의 이름을 지정할 수 있습니다 자체 식별자 원하는; 있습니다으로 제한 되지 않은 이름 같은 `self`, `Me`, 또는 `this`합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-154">Unlike in other .NET languages, you can name the self identifier however you want; you are not restricted to names such as `self`, `Me`, or `this`.</span></span>

<span data-ttu-id="961ca-155">선언 된 경우 자체 식별자는 `as` 키워드 될 때까지 초기화 되지 않은 후의 `let` 바인딩이 실행 되 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-155">The self identifier that is declared with the `as` keyword is not initialized until after the `let` bindings are executed.</span></span> <span data-ttu-id="961ca-156">따라서에서 사용할 수 없습니다는 `let` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="961ca-156">Therefore, it cannot be used in the `let` bindings.</span></span> <span data-ttu-id="961ca-157">자체 식별자를 사용할 수는 `do` 바인딩 섹션.</span><span class="sxs-lookup"><span data-stu-id="961ca-157">You can use the self identifier in the `do` bindings section.</span></span>


## <a name="generic-type-parameters"></a><span data-ttu-id="961ca-158">제네릭 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="961ca-158">Generic Type Parameters</span></span>

<span data-ttu-id="961ca-159">꺾쇠 괄호에 제네릭 형식 매개 변수에 지정 된 (`<` 및 `>`), 작은따옴표와 식별자의 형식에서입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-159">Generic type parameters are specified in angle brackets (`<` and `>`), in the form of a single quotation mark followed by an identifier.</span></span> <span data-ttu-id="961ca-160">여러 제네릭 형식 매개 변수는 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-160">Multiple generic type parameters are separated by commas.</span></span> <span data-ttu-id="961ca-161">제네릭 형식 매개 변수는 선언 전체 범위에는.</span><span class="sxs-lookup"><span data-stu-id="961ca-161">The generic type parameter is in scope throughout the declaration.</span></span> <span data-ttu-id="961ca-162">다음 코드 예제에서는 제네릭 형식 매개 변수를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-162">The following code example shows how to specify generic type parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

<span data-ttu-id="961ca-163">형식을 사용 하는 경우 형식 인수 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-163">Type arguments are inferred when the type is used.</span></span> <span data-ttu-id="961ca-164">다음 코드에서는 유추 된 형식은 튜플 시퀀스.</span><span class="sxs-lookup"><span data-stu-id="961ca-164">In the following code, the inferred type is a sequence of tuples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]
    
## <a name="specifying-inheritance"></a><span data-ttu-id="961ca-165">상속 지정</span><span class="sxs-lookup"><span data-stu-id="961ca-165">Specifying Inheritance</span></span>

<span data-ttu-id="961ca-166">`inherit` 절이 있는 경우 직접 기본 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-166">The `inherit` clause identifies the direct base class, if there is one.</span></span> <span data-ttu-id="961ca-167">F #에서 직접 기본 클래스를 하나만 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-167">In F#, only one direct base class is allowed.</span></span> <span data-ttu-id="961ca-168">인터페이스는 클래스를 구현 하는 기본 클래스를 고려 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-168">Interfaces that a class implements are not considered base classes.</span></span> <span data-ttu-id="961ca-169">인터페이스에 대해서는 설명의 [인터페이스](Interfaces.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-169">Interfaces are discussed in the [Interfaces](Interfaces.md) topic.</span></span>

<span data-ttu-id="961ca-170">액세스할 수 있습니다 메서드 및 속성 기본 클래스의 파생된 클래스에서 해당 언어 키워드를 사용 하 여 `base` 를 식별자로 뒤에 마침표 (.)와 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-170">You can access the methods and properties of the base class from the derived class by using the language keyword `base` as an identifier, followed by a period (.) and the name of the member.</span></span>

<span data-ttu-id="961ca-171">자세한 내용은 [상속](inheritance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="961ca-171">For more information, see [Inheritance](inheritance.md).</span></span>


## <a name="members-section"></a><span data-ttu-id="961ca-172">구성원 섹션</span><span class="sxs-lookup"><span data-stu-id="961ca-172">Members Section</span></span>
<span data-ttu-id="961ca-173">이 섹션의 정적 또는 인스턴스 메서드, 속성, 인터페이스 구현, 추상 멤버, 이벤트 선언 및 추가 생성자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-173">You can define static or instance methods, properties, interface implementations, abstract members, event declarations, and additional constructors in this section.</span></span> <span data-ttu-id="961ca-174">Let 및 않는 바인딩을이 섹션에 나타날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-174">Let and do bindings cannot appear in this section.</span></span> <span data-ttu-id="961ca-175">다양 한 클래스 뿐만 아니라 F # 형식에 멤버를 추가할 수 있습니다, 때문에 별도 항목에서 설명 [멤버](members/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-175">Because members can be added to a variety of F# types in addition to classes, they are discussed in a separate topic, [Members](members/index.md).</span></span>


## <a name="mutually-recursive-types"></a><span data-ttu-id="961ca-176">상호 재귀 형식</span><span class="sxs-lookup"><span data-stu-id="961ca-176">Mutually Recursive Types</span></span>
<span data-ttu-id="961ca-177">서로 순환 방식으로 참조 하는 형식을 정의할 때는 있습니다 문자열 함께 형식 정의 사용 하 여는 `and` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-177">When you define types that reference each other in a circular way, you string together the type definitions by using the `and` keyword.</span></span> <span data-ttu-id="961ca-178">`and` 키워드를 대체는 `type` 다음과 같이 첫 번째 정의 제외한 모든 페이지에 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-178">The `and` keyword replaces the `type` keyword on all except the first definition, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

<span data-ttu-id="961ca-179">출력은 현재 디렉터리에 있는 모든 파일의 목록.</span><span class="sxs-lookup"><span data-stu-id="961ca-179">The output is a list of all the files in the current directory.</span></span>


## <a name="when-to-use-classes-unions-records-and-structures"></a><span data-ttu-id="961ca-180">클래스, 공용 구조체, 레코드 및 구조를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="961ca-180">When to Use Classes, Unions, Records, and Structures</span></span>
<span data-ttu-id="961ca-181">어떤 유형별로 용인지 특정 상황에 대 한 적절 한 유형을 선택 하 게 파악 해야 해야 다양 한 형식에서 선택할 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-181">Given the variety of types to choose from, you need to have a good understanding of what each type is designed for to select the appropriate type for a particular situation.</span></span> <span data-ttu-id="961ca-182">클래스는 개체 지향 프로그래밍 컨텍스트에서 사용 하도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-182">Classes are designed for use in object-oriented programming contexts.</span></span> <span data-ttu-id="961ca-183">개체 지향 프로그래밍은.NET Framework에는 작성 된 응용 프로그램에서 사용 되는 주요 패러다임입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-183">Object-oriented programming is the dominant paradigm used in applications that are written for the .NET Framework.</span></span> <span data-ttu-id="961ca-184">F # 코드는.NET Framework 또는 다른 개체 지향 라이브러리와 밀접 하 게 작업 해야 하는 경우와 같은 UI 라이브러리는 개체 지향 형식 시스템에서를 확장 해야 할 경우에 특히 클래스는 적절 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-184">If your F# code has to work closely with the .NET Framework or another object-oriented library, and especially if you have to extend from an object-oriented type system such as a UI library, classes are probably appropriate.</span></span>

<span data-ttu-id="961ca-185">개체 지향 코드와 밀접 하 게 작용할 되지 있습니다 또는 자체 포함 하 고 따라서 개체 지향 코드와 자주 상호 작용 으로부터 보호 되는 코드를 작성 하는 경우 레코드를 사용 하 여 고려해 야 하 고 구별 된 공용 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-185">If you are not interoperating closely with object-oriented code, or if you are writing code that is self-contained and therefore protected from frequent interaction with object-oriented code, you should consider using records and discriminated unions.</span></span> <span data-ttu-id="961ca-186">단일도 하 게 고려 하 여 작성 한 코드와 일치 하는 적절 한 패턴 함께 구별 된 공용 구조체 개체 계층에 더 간단한 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-186">A single, well thought–out discriminated union, together with appropriate pattern matching code, can often be used as a simpler alternative to an object hierarchy.</span></span> <span data-ttu-id="961ca-187">구분 된 공용 구조체에 대 한 자세한 내용은 참조 [구별 된 공용 구조체](discriminated-unions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-187">For more information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

<span data-ttu-id="961ca-188">레코드 클래스를 보다 간단 하다는 이점이 했지만 그 단순 함으로 수행할 수 있는 형식의 요구를 초과할 때 레코드 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-188">Records have the advantage of being simpler than classes, but records are not appropriate when the demands of a type exceed what can be accomplished with their simplicity.</span></span> <span data-ttu-id="961ca-189">레코드는 기본적으로 단순 집계 값을 사용자 지정 작업을 수행할 수 있는 별도 생성자가 없는, 숨겨진된 필드를 상속 또는 인터페이스 구현 없이입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-189">Records are basically simple aggregates of values, without separate constructors that can perform custom actions, without hidden fields, and without inheritance or interface implementations.</span></span> <span data-ttu-id="961ca-190">속성 및 메서드와 같은 멤버 자체 동작을 더 복잡 한 레코드를 추가할 수 있지만 레코드에 저장 되는 필드는 여전히 값의 간단한 집계.</span><span class="sxs-lookup"><span data-stu-id="961ca-190">Although members such as properties and methods can be added to records to make their behavior more complex, the fields stored in a record are still a simple aggregate of values.</span></span> <span data-ttu-id="961ca-191">레코드에 대 한 자세한 내용은 참조 [레코드](records.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-191">For more information about records, see [Records](records.md).</span></span>

<span data-ttu-id="961ca-192">또한 구조 소규모 데이터를 집계 하는 데 유용 하지만.NET 값 형식에 있는 클래스와 레코드에서 서로 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-192">Structures are also useful for small aggregates of data, but they differ from classes and records in that they are .NET value types.</span></span> <span data-ttu-id="961ca-193">클래스와 레코드.NET 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-193">Classes and records are .NET reference types.</span></span> <span data-ttu-id="961ca-194">값 형식을 값으로 전달 됩니다 한다는 점에서 값 형식과 참조 형식이의 의미 체계가 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-194">The semantics of value types and reference types are different in that value types are passed by value.</span></span> <span data-ttu-id="961ca-195">즉, 복사 되는 비트 수준 매개 변수로 전달 되거나 함수에서 반환 된 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-195">This means that they are copied bit for bit when they are passed as a parameter or returned from a function.</span></span> <span data-ttu-id="961ca-196">또한 스택에 저장 인지, 대신 부모 개체 안에 포함 된 필드로 사용 되는 경우 힙의 고유한 별도 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-196">They are also stored on the stack or, if they are used as a field, embedded inside the parent object instead of stored in their own separate location on the heap.</span></span> <span data-ttu-id="961ca-197">따라서 힙 액세스의 오버 헤드가 문제가 때 구조는 자주 액세스 하는 데이터에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-197">Therefore, structures are appropriate for frequently accessed data when the overhead of accessing the heap is a problem.</span></span> <span data-ttu-id="961ca-198">구조에 대 한 자세한 내용은 참조 [구조](structures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="961ca-198">For more information about structures, see [Structures](structures.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="961ca-199">참고 항목</span><span class="sxs-lookup"><span data-stu-id="961ca-199">See Also</span></span>
[<span data-ttu-id="961ca-200">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="961ca-200">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="961ca-201">멤버</span><span class="sxs-lookup"><span data-stu-id="961ca-201">Members</span></span>](members/index.md)

[<span data-ttu-id="961ca-202">상속</span><span class="sxs-lookup"><span data-stu-id="961ca-202">Inheritance</span></span>](inheritance.md)

[<span data-ttu-id="961ca-203">인터페이스</span><span class="sxs-lookup"><span data-stu-id="961ca-203">Interfaces</span></span>](interfaces.md)

