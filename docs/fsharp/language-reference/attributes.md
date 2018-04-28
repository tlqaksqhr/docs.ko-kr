---
title: 특성(F#)
description: 'F # 특성 프로그래밍 구문에 적용할 메타 데이터를 사용 하는 방법에 대해 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: b8efc0cdc14e690bbc5c24456d0b1eaa3d55988e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="attributes"></a><span data-ttu-id="749ab-103">특성</span><span class="sxs-lookup"><span data-stu-id="749ab-103">Attributes</span></span>

<span data-ttu-id="749ab-104">프로그래밍 구문에 적용할 메타 데이터를 사용 하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-104">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="749ab-105">구문</span><span class="sxs-lookup"><span data-stu-id="749ab-105">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="749ab-106">설명</span><span class="sxs-lookup"><span data-stu-id="749ab-106">Remarks</span></span>

<span data-ttu-id="749ab-107">위 구문에는 *대상* 는 선택 사항이 며이 있는 경우 특성에 적용 되는 프로그램 엔터티의 종류를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-107">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="749ab-108">유효한 값에 대 한 *대상* 이 문서의 뒷부분에 표시 되는 테이블에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-108">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="749ab-109">*특성 이름* 접미사 유무 유효한 특성 유형 (네임 스페이스와 정규화) 이름을 가리킵니다 `Attribute` 특성 형식 이름에서 일반적으로 사용 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-109">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="749ab-110">예를 들어 `ObsoleteAttribute` 로 줄일 수 `Obsolete` 이 컨텍스트에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-110">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="749ab-111">*인수* 특성 유형에 대 한 생성자에는 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-111">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="749ab-112">특성에 있는 경우 기본 생성자를 인수 목록 및 괄호 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-112">If an attribute has a default constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="749ab-113">특성 인수를 위치 인수 및 명명 된 인수를 둘 다 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-113">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="749ab-114">*위치 인수* 나타나는 순서 대로 사용 되는 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-114">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="749ab-115">특성에 public 속성이 있는 경우 명명 된 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-115">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="749ab-116">인수 목록에 다음 구문을 사용 하 여이 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-116">You can set these by using the following syntax in the argument list.</span></span>

```
*property-name* = *property-value*
```

<span data-ttu-id="749ab-117">이러한 속성 초기화 순서에 관계 없이 수 있지만 모든 위치 인수를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-117">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="749ab-118">다음은 인수를 위치 인수 및 속성 초기화를 사용 하는 특성의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-118">Following is an example of an attribute that uses positional arguments and property initializations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="749ab-119">이 예제에서는 특성은 `DllImportAttribute`, 축소 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-119">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="749ab-120">첫 번째 인수가 위치 매개 변수가 고 두 번째 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-120">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="749ab-121">특성은 이라고 하는 개체는.NET 프로그래밍 구문은 *특성* 형식 또는 기타 프로그램 요소의 연결 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-121">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="749ab-122">특성이 적용 되는 프로그램 요소 라고는 *특성 대상*합니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-122">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="749ab-123">특성은 일반적으로 해당 대상에 대 한 메타 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-123">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="749ab-124">이러한 맥락에서 메타 데이터 멤버와 해당 필드 이외의 형식에 대 한 데이터가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-124">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="749ab-125">F #의 특성을 프로그래밍 구문에 적용할 수 있습니다: 함수, 메서드, 어셈블리, 모듈, 형식 (클래스, 레코드, 구조체, 인터페이스, 대리자, 열거형, 공용 구조체 및 등), 생성자, 속성, 필드, 매개 변수 매개 변수를 입력 하 고 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-125">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="749ab-126">특성에서 허용 되지 않습니다 `let` 바인딩 내 클래스, 식 또는 워크플로 식입니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-126">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="749ab-127">일반적으로 특성 선언 특성 대상의 선언 바로 앞에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-127">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="749ab-128">여러 개의 특성 선언은 함께, 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-128">Multiple attribute declarations can be used together, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="749ab-129">런타임 시.NET 리플렉션을 사용 하 여 특성을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-129">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="749ab-130">이전 코드 예제와 같이 개별적으로 특성이 여러 개를 선언 하거나 다음과 같이 개별 특성 및 생성자, 구분 하려면 세미콜론을 사용 하는 경우 대괄호로에 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-130">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="749ab-131">일반적으로 특성은 `Obsolete` 특성, 보안 고려 사항에 대 한 COM 지원, 코드, 소유권과 관련 된 특성 및 특성 형식을 serialize 할 수 있는지 여부를 나타내는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-131">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="749ab-132">다음 예제에서는 `Obsolete` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-132">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="749ab-133">특성 대상 `assembly` 및 `module`, 최상위 수준에 특성을 적용 `do` 어셈블리의 바인딩.</span><span class="sxs-lookup"><span data-stu-id="749ab-133">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="749ab-134">단어를 포함할 수 있습니다 `assembly` 또는 `module` 다음과 같이 특성 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-134">You can include the word `assembly` or `module` in the attribute declaration, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="749ab-135">특성 대상에 적용 되는 특성에 대 한를 생략 하면는 `do` 바인딩, F # 컴파일러에서는 해당 특성에 적합 한 특성 대상을 결정 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-135">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="749ab-136">여러 특성 클래스 형식의 특성에는 `System.AttributeUsageAttribute` 해당 특성에 대해 지원 가능한 대상에 대 한 정보를 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-136">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="749ab-137">경우는 `System.AttributeUsageAttribute` 나타나지만 특성의 대상으로 하는 기능 지원, 프로그램의 주 진입점에 적용할 특성을 구합니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-137">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="749ab-138">경우는 `System.AttributeUsageAttribute` 특성의 어셈블리를 대상으로 지원, 컴파일러는 어셈블리에 적용할 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="749ab-139">대부분의 특성 함수 및 어셈블리 모두에 적용 되지 않지만 수행 하는 경우에는 특성에 대 한 사용 프로그램의 main 함수에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-139">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="749ab-140">특성 대상을 명시적으로 지정 하는 경우 특성은 지정된 된 대상에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-140">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="749ab-141">특성 대상에 대 한 유효한 값 명시적으로 지정 하려면 일반적으로 필요 하지 않으면 있지만 *대상* 특성 함께 사용 예제를 보려면 다음 표에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-141">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.</span></span>

<table>
  <tr>
    <th><span data-ttu-id="749ab-142">특성 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="749ab-142">Attribute target</span></span></td>
    <th><span data-ttu-id="749ab-143">예제</span><span class="sxs-lookup"><span data-stu-id="749ab-143">Example</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="749ab-144">어셈블리</span><span class="sxs-lookup"><span data-stu-id="749ab-144">assembly</span></span></td>
    <td><span data-ttu-id="749ab-145">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span><span class="sxs-lookup"><span data-stu-id="749ab-145">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="749ab-146">return</span><span class="sxs-lookup"><span data-stu-id="749ab-146">return</span></span></td>
    <td><span data-ttu-id="749ab-147">' function1 let x: [<return: Obsolete>] int = x + 1'</span><span class="sxs-lookup"><span data-stu-id="749ab-147">`let function1 x : [<return: Obsolete>] int = x + 1`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="749ab-148">필드(field)</span><span class="sxs-lookup"><span data-stu-id="749ab-148">field</span></span></td>
    <td><span data-ttu-id="749ab-149">' [<field: DefaultValue>] val mutable x: int'</span><span class="sxs-lookup"><span data-stu-id="749ab-149">`[<field: DefaultValue>] val mutable x: int`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="749ab-150">속성</span><span class="sxs-lookup"><span data-stu-id="749ab-150">property</span></span></td>
    <td><span data-ttu-id="749ab-151">' [<property: Obsolete>]이 있습니다. MyProperty = x'</span><span class="sxs-lookup"><span data-stu-id="749ab-151">`[<property: Obsolete>] this.MyProperty = x`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="749ab-152">Param</span><span class="sxs-lookup"><span data-stu-id="749ab-152">param</span></span></td>
    <td><span data-ttu-id="749ab-153">' 멤버가이 있습니다. MyMethod ([<param: Out>] x: ref<int>) = x: = 10'</span><span class="sxs-lookup"><span data-stu-id="749ab-153">`member this.MyMethod([<param: Out>] x : ref<int>) = x := 10`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="749ab-154">type</span><span class="sxs-lookup"><span data-stu-id="749ab-154">type</span></span></td>
    <td><span data-ttu-id="749ab-155">
        ```
        [<type: StructLayout(Sequential)>] MyStruct 입력 구조체 = x: y 바이트: int 끝 ```
    </span><span class="sxs-lookup"><span data-stu-id="749ab-155">
        ```
        [<type: StructLayout(Sequential)>] type MyStruct = struct x : byte y : int end ```
    </span></span></td> 
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="749ab-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="749ab-156">See Also</span></span>

[<span data-ttu-id="749ab-157">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="749ab-157">F# Language Reference</span></span>](index.md)
