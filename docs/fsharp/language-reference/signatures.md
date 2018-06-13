---
title: 서명(F#)
description: 'F # 시그니처 파일을 사용 하 여 형식, 네임 스페이스 및 모듈 등 F # 프로그램 요소를 집합의 공개 서명에 대 한 정보를 보관 하는 방법에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 6e182a1a0ac7f3f9fab27026e582d83ee737822e
ms.sourcegitcommit: e5bb395ec86f536e114314184288f40a8c745e2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2018
ms.locfileid: "34149025"
---
# <a name="signatures"></a><span data-ttu-id="115a3-103">서명</span><span class="sxs-lookup"><span data-stu-id="115a3-103">Signatures</span></span>

<span data-ttu-id="115a3-104">서명 파일에는 형식, 네임스페이스, 모듈 등 F# 프로그램 요소 집합의 공개 서명에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-104">A signature file contains information about the public signatures of a set of F# program elements, such as types, namespaces, and modules.</span></span> <span data-ttu-id="115a3-105">이러한 프로그램 요소의 접근성을 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-105">It can be used to specify the accessibility of these program elements.</span></span>


## <a name="remarks"></a><span data-ttu-id="115a3-106">설명</span><span class="sxs-lookup"><span data-stu-id="115a3-106">Remarks</span></span>
<span data-ttu-id="115a3-107">각 F# 코드 파일에 대해 코드 파일과 이름이 같지만 확장명이 .fs가 아니라 .fsi인 *서명 파일*이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-107">For each F# code file, you can have a *signature file*, which is a file that has the same name as the code file but with the extension .fsi instead of .fs.</span></span> <span data-ttu-id="115a3-108">명령줄을 직접 사용하는 경우 컴파일 명령줄에 서명 파일을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-108">Signature files can also be added to the compilation command-line if you are using the command line directly.</span></span> <span data-ttu-id="115a3-109">코드 파일과 서명 파일을 구분하기 위해 코드 파일을 *구현 파일*이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-109">To distinguish between code files and signature files, code files are sometimes referred to as *implementation files*.</span></span> <span data-ttu-id="115a3-110">프로젝트에서 서명 파일이 연결된 코드 파일 앞에 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-110">In a project, the signature file should precede the associated code file.</span></span>

<span data-ttu-id="115a3-111">서명 파일은 해당 구현 파일의 네임스페이스, 모듈, 형식 및 멤버에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-111">A signature file describes the namespaces, modules, types, and members in the corresponding implementation file.</span></span> <span data-ttu-id="115a3-112">서명 파일의 정보를 사용하여 구현 파일 외부 코드에서 액세스할 수 있는 해당 구현 파일의 코드 부분 및 구현 파일 내부 부분을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-112">You use the information in a signature file to specify what parts of the code in the corresponding implementation file can be accessed from code outside the implementation file, and what parts are internal to the implementation file.</span></span> <span data-ttu-id="115a3-113">서명 파일에 포함된 네임스페이스, 모듈 및 형식은 구현 파일에 포함된 네임스페이스, 모듈 및 형식의 하위 집합이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-113">The namespaces, modules, and types that are included in the signature file must be a subset of the namespaces, modules, and types that are included in the implementation file.</span></span> <span data-ttu-id="115a3-114">이 항목의 뒷부분에서 설명하는 몇 가지 예외를 제외하고 서명 파일에 나열되지 않은 언어 요소는 구현 파일 전용으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-114">With some exceptions noted later in this topic, those language elements that are not listed in the signature file are considered private to the implementation file.</span></span> <span data-ttu-id="115a3-115">프로젝트 또는 명령줄에 서명 파일이 없는 경우 기본 접근성이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-115">If no signature file is found in the project or command line, the default accessibility is used.</span></span>

<span data-ttu-id="115a3-116">기본 액세스 가능성에 대 한 자세한 내용은 참조 [액세스 제어](access-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-116">For more information about the default accessibility, see [Access Control](access-control.md).</span></span>

<span data-ttu-id="115a3-117">서명 파일에서 형식 정의와 각 메서드 또는 함수의 구현을 반복하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-117">In a signature file, you do not repeat the definition of the types and the implementations of each method or function.</span></span> <span data-ttu-id="115a3-118">대신, 모듈 또는 네임스페이스 조각에 의해 구현되는 기능의 전체 사양 역할을 하는 각 메서드 및 함수에 대한 서명을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-118">Instead, you use the signature for each method and function, which acts as a complete specification of the functionality that is implemented by a module or namespace fragment.</span></span> <span data-ttu-id="115a3-119">형식 서명에 대한 구문은 인터페이스 및 추상 클래스의 추상 메서드 선언에 사용되는 구문과 동일하며 올바르게 컴파일된 입력을 표시할 경우 IntelliSense 및 F# 인터프리터 fsi.exe에 의해서도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-119">The syntax for a type signature is the same as that used in abstract method declarations in interfaces and abstract classes, and is also shown by IntelliSense and by the F# interpreter fsi.exe when it displays correctly compiled input.</span></span>

<span data-ttu-id="115a3-120">형식 서명의 정보가 형식의 봉인 여부 또는 인터페이스 형식인지 여부를 나타내는 데 충분하지 않을 경우 형식의 속성을 나타내는 특성을 컴파일러에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-120">If there is not enough information in the type signature to indicate whether a type is sealed, or whether it is an interface type, you must add an attribute that indicates the nature of the type to the compiler.</span></span> <span data-ttu-id="115a3-121">이 목적에 사용하는 특성은 다음 표에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-121">Attributes that you use for this purpose are described in the following table.</span></span>



|<span data-ttu-id="115a3-122">특성</span><span class="sxs-lookup"><span data-stu-id="115a3-122">Attribute</span></span>|<span data-ttu-id="115a3-123">설명</span><span class="sxs-lookup"><span data-stu-id="115a3-123">Description</span></span>|
|---------|-----------|
|`[<Sealed>]`|<span data-ttu-id="115a3-124">추상 멤버가 없거나 확장되지 않아야 하는 형식에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-124">For a type that has no abstract members, or that should not be extended.</span></span>|
|`[<Interface>]`|<span data-ttu-id="115a3-125">인터페이스인 형식에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-125">For a type that is an interface.</span></span>|
<span data-ttu-id="115a3-126">구현 파일의 선언과 서명 간에 특성이 일치하지 않는 경우 컴파일러에서 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-126">The compiler produces an error if the attributes are not consistent between the signature and the declaration in the implementation file.</span></span>

<span data-ttu-id="115a3-127">`val` 키워드를 사용하여 값 또는 함수 값에 대한 서명을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-127">Use the keyword `val` to create a signature for a value or function value.</span></span> <span data-ttu-id="115a3-128">`type` 키워드는 형식 서명을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-128">The keyword `type` introduces a type signature.</span></span>

<span data-ttu-id="115a3-129">`--sig` 컴파일러 옵션을 사용하여 서명 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-129">You can generate a signature file by using the `--sig` compiler option.</span></span> <span data-ttu-id="115a3-130">일반적으로 .fsi 파일은 수동으로 작성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-130">Generally, you do not write .fsi files manually.</span></span> <span data-ttu-id="115a3-131">대신, 컴파일러를 사용하여 .fsi 파일을 생성하고, 프로젝트에 추가한 다음(있는 경우) 액세스할 수 없게 하려는 메서드 및 함수를 제거하여 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-131">Instead, you generate .fsi files by using the compiler, add them to your project, if you have one, and edit them by removing methods and functions that you do not want to be accessible.</span></span>

<span data-ttu-id="115a3-132">형식 서명에 대한 다음 몇 가지 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-132">There are several rules for type signatures:</span></span>


- <span data-ttu-id="115a3-133">구현 파일의 형식 약어는 서명 파일의 약어가 없는 형식과 일치하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-133">Type abbreviations in an implementation file must not match a type without an abbreviation in a signature file.</span></span>


- <span data-ttu-id="115a3-134">레코드 및 구분된 공용 구조체는 해당 필드와 생성자를 모두 노출하거나 하나도 노출하지 않아야 하며, 서명의 순서가 구현 파일의 순서와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-134">Records and discriminated unions must expose either all or none of their fields and constructors, and the order in the signature must match the order in the implementation file.</span></span> <span data-ttu-id="115a3-135">클래스는 서명의 해당 필드와 메서드를 일부 또는 모두 표시하거나 하나도 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-135">Classes can reveal some, all, or none of their fields and methods in the signature.</span></span>


- <span data-ttu-id="115a3-136">생성자가 있는 클래스와 구조체는 해당 기본 클래스의 선언( `inherits` 선언)을 노출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-136">Classes and structures that have constructors must expose the declarations of their base classes (the `inherits` declaration).</span></span> <span data-ttu-id="115a3-137">또한 생성자가 있는 클래스와 구조체는 모든 추상 메서드 및 인터페이스 선언을 노출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-137">Also, classes and structures that have constructors must expose all of their abstract methods and interface declarations.</span></span>


- <span data-ttu-id="115a3-138">인터페이스 형식은 모든 메서드 및 인터페이스를 노출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-138">Interface types must reveal all their methods and interfaces.</span></span>


<span data-ttu-id="115a3-139">값 서명에 대한 규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-139">The rules for value signatures are as follows:</span></span>


- <span data-ttu-id="115a3-140">서명의 접근성 한정자(`public`, `internal`등)와 `inline` 및 `mutable` 한정자는 구현의 해당 한정자와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-140">Modifiers for accessibility (`public`, `internal`, and so on) and the `inline` and `mutable` modifiers in the signature must match those in the implementation.</span></span>


- <span data-ttu-id="115a3-141">암시적으로 유추되거나 명시적으로 선언된 제네릭 형식 매개 변수 개수가 일치해야 하고, 제네릭 형식 매개 변수의 형식 및 형식 제약 조건이 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-141">The number of generic type parameters (either implicitly inferred or explicitly declared) must match, and the types and type constraints in generic type parameters must match.</span></span>


- <span data-ttu-id="115a3-142">`Literal` 특성을 사용하는 경우 서명과 구현 둘 다에 표시되어야 하며, 둘 다에 동일한 리터럴 값을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-142">If the `Literal` attribute is used, it must appear in both the signature and the implementation, and the same literal value must be used for both.</span></span>


- <span data-ttu-id="115a3-143">서명 및 구현의 매개 변수 패턴( *인자*라고도 함)이 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-143">The pattern of parameters (also known as the *arity*) of signatures and implementations must be consistent.</span></span>


- <span data-ttu-id="115a3-144">서명 파일의 매개 변수 이름을 해당 구현 파일에서 다른 경우 서명 파일에 있는 이름 대신 사용 됩니다, 디버깅 또는 프로 파일링 하는 경우 문제를 일으킬 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-144">If parameter names in a signature file differ from the corresponding implementation file, the name in the signature file will be used instead, which may cause issues when debugging or profiling.</span></span> <span data-ttu-id="115a3-145">이러한 불일치 3218 프로젝트 파일의 경고 활성화 알림을 받을 하려는 경우 또는 컴파일러를 호출할 때 (참조 `--warnon` 아래 [컴파일러 옵션](compiler-options.md)).</span><span class="sxs-lookup"><span data-stu-id="115a3-145">If you wish to be notified of such mismatches, enable warning 3218 in your project file or when invoking the compiler (see `--warnon` under [Compiler Options](compiler-options.md)).</span></span>


<span data-ttu-id="115a3-146">다음 코드 예제에서는 해당 특성과 함께 네임스페이스, 모듈, 함수 값 및 형식 서명을 포함하는 서명 파일의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-146">The following code example shows an example of a signature file that has namespace, module, function value, and type signatures together with the appropriate attributes.</span></span> <span data-ttu-id="115a3-147">또한 해당 구현 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-147">It also shows the corresponding implementation file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssignatures/snippet9002.fs)]

<span data-ttu-id="115a3-148">다음 코드에서는 구현 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="115a3-148">The following code shows the implementation file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssignatures/snippet9001.fs)]
    
## <a name="see-also"></a><span data-ttu-id="115a3-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="115a3-149">See Also</span></span>
[<span data-ttu-id="115a3-150">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="115a3-150">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="115a3-151">Access Control</span><span class="sxs-lookup"><span data-stu-id="115a3-151">Access Control</span></span>](access-control.md)

[<span data-ttu-id="115a3-152">컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="115a3-152">Compiler Options</span></span>](compiler-options.md)
