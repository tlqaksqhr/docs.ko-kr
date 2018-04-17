---
title: Visual Basic의 튜플
ms.custom: ''
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68c82e75ce4a438381bc9c60ce8c992565eb31cb
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="tuples-visual-basic"></a><span data-ttu-id="b4b96-102">튜플 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4b96-102">Tuples (Visual Basic)</span></span>

<span data-ttu-id="b4b96-103">Visual Basic 2017 부터는 Visual Basic 언어는 기본 제공 하는 튜플 지원 튜플 만들고 튜플 쉽게 요소에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-103">Starting with Visual Basic 2017, the Visual Basic language offers built-in support for tuples that makes creating tuples and accessing the elements of tuples easier.</span></span> <span data-ttu-id="b4b96-104">튜플은 특정 수 및 값의 시퀀스를 포함 하는 간단한 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-104">A tuple is a light-weight data structure that has a specific number and sequence of values.</span></span> <span data-ttu-id="b4b96-105">튜플의 인스턴스화할 때 수 및 각 값 (또는 요소)의 데이터 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-105">When you instantiate the tuple, you define the number and the data type of each value (or element).</span></span> <span data-ttu-id="b4b96-106">예를 들어 2-튜플 (또는 쌍)에 두 개의 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-106">For example, a 2-tuple (or pair) has two elements.</span></span> <span data-ttu-id="b4b96-107">첫 번째 수는 `Boolean` 값을 고 두 번째는는 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-107">The first might be a `Boolean` value, while the second is a `String`.</span></span> <span data-ttu-id="b4b96-108">튜플 쉽게 단일 개체에 여러 값을 저장할 수 있도록, 때문에 종종 메서드에서 여러 값을 반환 하는 간단한 방법으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-108">Because tuples make it easy to store multiple values in a single object, they are often used as a lightweight way to return multiple values from a method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4b96-109">튜플 지원 하려면는 <xref:System.ValueTuple> 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-109">Tuple support requires the <xref:System.ValueTuple> type.</span></span> <span data-ttu-id="b4b96-110">NuGet 패키지를 추가 해야.NET Framework 4.7 설치 되어 있지 않으면 `System.ValueTuple`은 NuGet 갤러리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-110">If the .NET Framework 4.7 is not installed, you must add the NuGet package `System.ValueTuple`, which is available on the NuGet Gallery.</span></span> <span data-ttu-id="b4b96-111">이 패키지 없이 오류가 발생할 수 있습니다는 컴파일, "미리 정의 된 형식과 비슷한 'ValueTuple(Of,,,)'가 정의 하지 않았거나 가져오지 하지 않습니다."</span><span class="sxs-lookup"><span data-stu-id="b4b96-111">Without this package, you may get a compilation error similar to, "Predefined type 'ValueTuple(Of,,,)' is not defined or imported."</span></span>

## <a name="instantiating-and-using-a-tuple"></a><span data-ttu-id="b4b96-112">인스턴스화 및 튜플을 사용</span><span class="sxs-lookup"><span data-stu-id="b4b96-112">Instantiating and using a tuple</span></span>

<span data-ttu-id="b4b96-113">쉼표로 구분 된 값 im 괄호를 포함 하 여 튜플을 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-113">You instantiate a tuple by enclosing its comma-delimited values im parentheses.</span></span> <span data-ttu-id="b4b96-114">각 값 튜플의 필드가 다음 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-114">Each of those values then becomes a field of the tuple.</span></span> <span data-ttu-id="b4b96-115">다음 코드를 세 번 (또는 3-튜플)을 정의 예를 들어 한 `Date` 해당 첫 번째 값으로는 `String` 를 두 번째 및 `Boolean` 세 번째도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-115">For example, the following code defines a triple (or 3-tuple) with a `Date` as its first value, a `String` as its second, and a `Boolean` as its third.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

<span data-ttu-id="b4b96-116">기본적으로 문자열의 튜플의 각 필드의 이름이 구성 `Item` 튜플의 필드의 1-시작 위치와 함께 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-116">By default, the name of each field in a tuple consists of the string `Item` along with the field's one-based position in the tuple.</span></span> <span data-ttu-id="b4b96-117">이 3-튜플에 대 한는 `Date` 필드는 `Item1`, `String` 필드는 `Item2`, 및 `Boolean` 필드는 `Item3`합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-117">For this 3-tuple, the `Date` field is `Item1`, the `String` field is `Item2`, and the `Boolean` field is `Item3`.</span></span> <span data-ttu-id="b4b96-118">다음 예제에서는 코드의 이전 줄에서 인스턴스화된 튜플의 필드의 값 표시</span><span class="sxs-lookup"><span data-stu-id="b4b96-118">The following example displays the values of fields of the tuple instantiated in the previous line of code</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

<span data-ttu-id="b4b96-119">Visual Basic 튜플의 필드는 읽기 / 쓰기; 튜플을 인스턴스화한 한 후 해당 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-119">The fields of a Visual Basic tuple are read-write; after you've instantiated a tuple, you can modify its values.</span></span> <span data-ttu-id="b4b96-120">다음 예제에서는 두 개의 이전 예제에서 만든 튜플의 세 개의 필드를 수정 하 고 결과 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-120">The following example modifies two of the three fields of the tuple created in the previous example and displays the result.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a><span data-ttu-id="b4b96-121">인스턴스화 및 명명 된 튜플을 사용</span><span class="sxs-lookup"><span data-stu-id="b4b96-121">Instantiating and using a named tuple</span></span>

<span data-ttu-id="b4b96-122">튜플의 필드에 대 한 기본 이름을 사용 하는 대신 인스턴스화할 수 있습니다는 *라는 튜플* 튜플의 요소에 고유한 이름을 지정 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-122">Rather than using default names for a tuple's fields, you can instantiate a *named tuple* by assigning your own names to the tuple's elements.</span></span> <span data-ttu-id="b4b96-123">튜플의 필드에 할당 된 이름으로 액세스할 수 있습니다 *또는* 기본 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-123">The tuple's fields can then be accessed by their assigned names *or* by their default names.</span></span> <span data-ttu-id="b4b96-124">다음 예제에서는 첫 번째 필드 이름을 명시적으로 지정 한다는 점을 제외 하면 앞에서 동일한 3-튜플 인스턴스화합니다 `EventDate`, 두 번째 `Name`, 세 번째 `IsHoliday`합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-124">The following example instantiates the same 3-tuple as previously, except that it explicitly names the first field `EventDate`, the second `Name`, and the third `IsHoliday`.</span></span> <span data-ttu-id="b4b96-125">필드 값을 표시,를 수정 하 고 다시 필드 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-125">It then displays the field values, modifies them, and displays the field values again.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="b4b96-126">유추 된 튜플 요소 이름</span><span class="sxs-lookup"><span data-stu-id="b4b96-126">Inferred tuple element names</span></span>

<span data-ttu-id="b4b96-127">Visual Basic 15.3 부터는 Visual Basic 유추할 수; 여 튜플 요소 이름 명시적으로 할당 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-127">Starting with Visual Basic 15.3, Visual Basic can infer the names of tuple elements; you do not have to assign them explicitly.</span></span> <span data-ttu-id="b4b96-128">유추 된 튜플 이름은 변수 집합에서 튜플을 초기화 하 고 변수 이름으로 동일 하 게 튜플 요소 이름을 사용 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-128">Inferred tuple names are useful when you initialize a tuple from a set of variables, and you want the tuple element name to be the same as the variable name.</span></span> 

<span data-ttu-id="b4b96-129">다음 예제에서는 한 `stateInfo` 명명 된 요소를 명시적으로 3 개 포함 된 튜플을 `state`, `stateName`, 및 `capital`합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-129">The following example creates a `stateInfo` tuple that contains three explicitly named elements, `state`, `stateName`, and `capital`.</span></span> <span data-ttu-id="b4b96-130">유의 요소 이름 지정 시에, 튜플 초기화 문 지정 명명 된 요소는 동일 하 게 명명 된 변수의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-130">Note that, in naming the elements, the tuple initialization statement simply assigns the named elements the values of the identically named variables.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
<span data-ttu-id="b4b96-131">요소 및 변수의 이름이 동일 하기 때문에 Visual Basic 컴파일러는 다음 예제와 같이 필드의 이름이 추론할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-131">Because elements and variables have the same name, the Visual Basic compiler can infer the names of the fields, as the following example shows.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

<span data-ttu-id="b4b96-132">Visual Basic 프로젝트에서 사용 하는 Visual Basic 컴파일러의 버전을 정의 해야 수감 되어 튜플 요소 이름을 사용 하려면 (\*.vbproj) 파일:</span><span class="sxs-lookup"><span data-stu-id="b4b96-132">To enable interred tuple element names, you must define the version of the Visual Basic compiler to use in your Visual Basic project (\*.vbproj) file:</span></span> 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 
```

<span data-ttu-id="b4b96-133">버전 번호는 15.3 부터는 Visual Basic 컴파일러의 모든 버전일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-133">The version number can be any version of the Visual Basic compiler starting with 15.3.</span></span> <span data-ttu-id="b4b96-134">하드 코딩 특정 컴파일러 버전을 대신 지정할 수도 있습니다 "최신"의 값으로 `LangVersion` 를 시스템에 설치 하는 Visual Basic 컴파일러의 가장 최신 버전을 사용 하 여 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-134">Rather than hard-coding a specific compiler version, you can also specify "Latest" as the value of `LangVersion` to compile with the most recent version of the Visual Basic compiler installed on your system.</span></span>

<span data-ttu-id="b4b96-135">Visual Basic 컴파일러에 따라서는 후보 이름에서 튜플 요소 이름을 유추할 수 없습니다 및와 같은 기본 이름으로 사용 하 여 튜플 필드 참조만 수 `Item1`, `Item2`등입니다. 여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-135">In some cases, the Visual Basic compiler cannot infer the tuple element name from the candidate name, and the tuple field can only be referenced using its default name, such as `Item1`, `Item2`, etc. These include:</span></span>

- <span data-ttu-id="b4b96-136">후보 이름은 튜플 멤버의 이름과 같은 `Item3`, `Rest`, 또는 `ToString`합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-136">The candidate name is the same as the name of a tuple member, such as `Item3`, `Rest`, or `ToString`.</span></span>

- <span data-ttu-id="b4b96-137">튜플의 후보 이름이 중복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-137">The candidate name is duplicated in the tuple.</span></span>
 
<span data-ttu-id="b4b96-138">필드 이름 유추가 실패 한 경우 Visual Basic 컴파일러 오류가 발생 하지 않습니다 없거나 이러한 속성이 런타임 시 발생 하는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-138">When field name inference fails, Visual Basic does not generate a compiler error, nor is an exception thrown at runtime.</span></span> <span data-ttu-id="b4b96-139">대신, 튜플 필드 참조 해야의 미리 정의 된 이름이 같은 `Item1` 및 `Item2`합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-139">Instead, tuple fields must be referenced by their predefined names, such as `Item1` and `Item2`.</span></span> 
  
## <a name="tuples-versus-structures"></a><span data-ttu-id="b4b96-140">구조 및 튜플</span><span class="sxs-lookup"><span data-stu-id="b4b96-140">Tuples versus structures</span></span>

<span data-ttu-id="b4b96-141">Visual Basic 튜플 값 형식이 중 하나의 인스턴스가는 **System.ValueTuple** 제네릭 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-141">A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types.</span></span> <span data-ttu-id="b4b96-142">예를 들어는 `holiday` 의 인스턴스가 이전 예제에서 정의 된 튜플을 <xref:System.ValueTuple%603> 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-142">For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure.</span></span> <span data-ttu-id="b4b96-143">데이터에 대 한 간단한 컨테이너 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-143">It is designed to be a lightweight container for data.</span></span> <span data-ttu-id="b4b96-144">튜플의 쉽게 여러 데이터 항목이 있는 개체를 만들 수 있도록 목표, 이후 사용자 정의 구조를 가질 수 있는 기능 중 일부는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-144">Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have.</span></span> <span data-ttu-id="b4b96-145">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-145">These include:</span></span>

- <span data-ttu-id="b4b96-146">사용자 지정 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-146">Custom members.</span></span> <span data-ttu-id="b4b96-147">사용자 고유의 속성, 메서드 또는 튜플의 대 한 이벤트를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-147">You cannot define your own properties, methods, or events for a tuple.</span></span>

- <span data-ttu-id="b4b96-148">유효성 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-148">Validation.</span></span> <span data-ttu-id="b4b96-149">필드에 할당 된 데이터를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-149">You cannot validate the data assigned to fields.</span></span>

- <span data-ttu-id="b4b96-150">변경 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-150">Immutability.</span></span> <span data-ttu-id="b4b96-151">Visual Basic 튜플은 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-151">Visual Basic tuples are mutable.</span></span> <span data-ttu-id="b4b96-152">반면, 사용자 정의 구조를 제어할 수 있습니다 인지 인스턴스 변경할 수 있는 변경 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-152">In contrast, a custom structure allows you to control whether an instance is mutable or immutable.</span></span>

<span data-ttu-id="b4b96-153">사용자 지정 멤버, 속성 및 필드 유효성 검사 또는 불변성 중요 한 경우에 Visual Basic을 사용 해야 [구조](../../../language-reference/statements/structure-statement.md) 을 사용자 지정 값 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-153">If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.</span></span>

<span data-ttu-id="b4b96-154">Visual Basic 튜플 멤버의 상속지 않습니다 해당 **ValueTuple** 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-154">A Visual Basic tuple does inherit the members of its **ValueTuple** type.</span></span> <span data-ttu-id="b4b96-155">해당 필드와 함께 다음 메서드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-155">In addition to its fields, these include the following methods:</span></span>

| <span data-ttu-id="b4b96-156">멤버</span><span class="sxs-lookup"><span data-stu-id="b4b96-156">Member</span></span> | <span data-ttu-id="b4b96-157">설명</span><span class="sxs-lookup"><span data-stu-id="b4b96-157">Description</span></span> |
| ---|---|
| <span data-ttu-id="b4b96-158">CompareTo</span><span class="sxs-lookup"><span data-stu-id="b4b96-158">CompareTo</span></span> | <span data-ttu-id="b4b96-159">현재 튜플을 다른 튜플에 동일한 수의 요소를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-159">Compares the current tuple to another tuple with the same number of elements.</span></span> |
| <span data-ttu-id="b4b96-160">같음</span><span class="sxs-lookup"><span data-stu-id="b4b96-160">Equals</span></span> | <span data-ttu-id="b4b96-161">현재 튜플을 다른 튜플 또는 개체와 같은지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-161">Determines whether the current tuple is equal to another tuple or object.</span></span> |
| <span data-ttu-id="b4b96-162">GetHashCode</span><span class="sxs-lookup"><span data-stu-id="b4b96-162">GetHashCode</span></span> | <span data-ttu-id="b4b96-163">현재 인스턴스에 대 한 해시 코드를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-163">Calculates the hash code for the current instance.</span></span> |
| <span data-ttu-id="b4b96-164">ToString</span><span class="sxs-lookup"><span data-stu-id="b4b96-164">ToString</span></span> | <span data-ttu-id="b4b96-165">형식은이 튜플의 문자열 표현을 반환 `(Item1, Item2...)`여기서 `Item1` 및 `Item2` 튜플의 필드의 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-165">Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields.</span></span> |

<span data-ttu-id="b4b96-166">또한는 **ValueTuple** 형식은 구현 <xref:System.Collections.IStructuralComparable> 및 <xref:System.Collections.IStructuralEquatable> 인터페이스는 고객 비교자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-166">In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.</span></span>

## <a name="assignment-and-tuples"></a><span data-ttu-id="b4b96-167">할당 및 튜플</span><span class="sxs-lookup"><span data-stu-id="b4b96-167">Assignment and tuples</span></span>

<span data-ttu-id="b4b96-168">Visual Basic에서는 동일한 필드 수 있는 튜플 형식 사이 할당을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-168">Visual Basic supports assignment between tuple types that have the same number of fields.</span></span> <span data-ttu-id="b4b96-169">다음 중 하나 이면 필드 유형을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-169">The field types can be converted if one of the following is true:</span></span>

- <span data-ttu-id="b4b96-170">원본 및 대상 필드는 같은 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-170">The source and target field are of the same type.</span></span>

- <span data-ttu-id="b4b96-171">확대 (또는 암시적) 변환 원본 유형 대상 유형으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-171">A widening (or implicit) conversion of the source type to the target type is defined.</span></span> 

- <span data-ttu-id="b4b96-172">`Option Strict` `On`, 축소 (또는 명시적) 변환 원본 유형 대상 유형으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-172">`Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined.</span></span> <span data-ttu-id="b4b96-173">이 변환은 원본 값이 대상 형식의 범위 밖에 있는 경우 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-173">This conversion can throw an exception if the source value is outside the range of the target type.</span></span>

<span data-ttu-id="b4b96-174">다른 변환은 할당에 고려되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-174">Other conversions are not considered for assignments.</span></span> <span data-ttu-id="b4b96-175">튜플 형식 간에 허용되는 할당 종류를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-175">Let's look at the kinds of assignments that are allowed between tuple types.</span></span>

<span data-ttu-id="b4b96-176">다음 예제에서 사용되는 이러한 변수를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="b4b96-176">Consider these variables used in the following examples:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

<span data-ttu-id="b4b96-177">처음 두 개의 변수 `unnamed` 및 `anonymous`는 필드에 대해 제공 된 의미 체계 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-177">The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields.</span></span> <span data-ttu-id="b4b96-178">필드 이름 요소가 기본 `Item1` 및 `Item2`합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-178">Their field names are the default `Item1` and `Item2`.</span></span> <span data-ttu-id="b4b96-179">마지막 두 개의 변수 `named` 및 `differentName` 의미 체계 필드 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-179">The last two variables, `named` and `differentName` have semantic field names.</span></span> <span data-ttu-id="b4b96-180">이러한 두 튜플의 필드 이름은 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-180">Note that these two tuples have different names for the fields.</span></span>

<span data-ttu-id="b4b96-181">이러한 튜플의 네 필드 (라고도 함 '인자 수가'), 동일한 수 있고 해당 필드의 형식이 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-181">All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical.</span></span> <span data-ttu-id="b4b96-182">따라서 다음 할당이 모든 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-182">Therefore, all of these assignments work:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

<span data-ttu-id="b4b96-183">튜플 이름은 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-183">Notice that the names of the tuples are not assigned.</span></span> <span data-ttu-id="b4b96-184">필드 값은 튜플의 필드 순서에 따라 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-184">The values of the fields are assigned following the order of the fields in the tuple.</span></span>

<span data-ttu-id="b4b96-185">마지막으로 할당할 수 있습니다 알는 `named` 에 튜플을 `conversion` 튜플 경우에의 첫 번째 필드로 `named` 은 `Integer`, 및의 첫 번째 필드 `conversion` 는 `Long`합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-185">Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`.</span></span> <span data-ttu-id="b4b96-186">변환 있기 때문에이 할당 성공는 `Integer` 에 `Long` 확대 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-186">This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

<span data-ttu-id="b4b96-187">필드의 수를 다르게 하 여 튜플은 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-187">Tuples with different numbers of fields are not assignable:</span></span>

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a><span data-ttu-id="b4b96-188">메서드 반환 값으로의 튜플</span><span class="sxs-lookup"><span data-stu-id="b4b96-188">Tuples as method return values</span></span>

<span data-ttu-id="b4b96-189">메서드는 단일 값만 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-189">A method can return only a single value.</span></span> <span data-ttu-id="b4b96-190">대부분의 경우 하지만 원하는 여러 값을 반환 하는 메서드 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-190">Frequently, though, you'd like a method call to return multiple values.</span></span> <span data-ttu-id="b4b96-191">여러 가지 방법을 사용 하 여이 제한을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-191">There are several ways to work around this limitation:</span></span>

- <span data-ttu-id="b4b96-192">사용자 지정 클래스 또는 구조체 속성을 가진 만들거나 필드 메서드에 의해 반환 되는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-192">You can create a custom class or structure whose properties or fields represent values returned by the method.</span></span> <span data-ttu-id="b4b96-193">따라서는 중량 솔루션입니다. 유일한 목적인 메서드 호출에서 값을 검색 하는 사용자 지정 형식을 정의 하는 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-193">Thus is a heavyweight solution; it requires that you define a custom type whose only purpose is to retrieve values from a method call.</span></span>

- <span data-ttu-id="b4b96-194">단일 값은 메서드에서 돌아오기 있고 메서드에 대 한 참조를 전달 하 여 나머지 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-194">You can return a single value from the method, and return the remaining values by passing them by reference to the method.</span></span> <span data-ttu-id="b4b96-195">변수 및 참조로 전달 하는 변수의 값을 덮어쓰는 위험을 인스턴스화하는 오버 헤드 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-195">This involves the overhead of instantiating a variable and risks inadvertently overwriting the value of the variable that you pass by reference.</span></span>

- <span data-ttu-id="b4b96-196">여러 개의 반환 값을 검색 하는 간단한 솔루션을 제공 하는 튜플을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-196">You can use a tuple, which provides a lightweight solution to retrieving multiple return values.</span></span>

<span data-ttu-id="b4b96-197">예를 들어는 **TryParse** .NET 리턴으로 메서드는 `Boolean` 구문 분석 작업이 성공 했는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-197">For example, the **TryParse** methods in .NET return a `Boolean` value that indicates whether the parsing operation succeeded.</span></span> <span data-ttu-id="b4b96-198">구문 분석 작업의 결과 메서드에 참조로 전달 되는 변수에 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-198">The result of the parsing operation is returned in a variable passed by reference to the method.</span></span> <span data-ttu-id="b4b96-199">에 대 한 호출 일반적으로와 같은 구문 분석 방법을 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-199">Normally, a call to the a parsing method such as <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> looks like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

<span data-ttu-id="b4b96-200">문자열을 반환할 수 튜플을 구문 분석 작업에서 호출을 래핑할 하는 경우는 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 고유한 메서드에서 메서드.</span><span class="sxs-lookup"><span data-stu-id="b4b96-200">We can return a tuple from the parsing operation if we wrap the call to the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method in our own method.</span></span> <span data-ttu-id="b4b96-201">다음 예에서 `NumericLibrary.ParseInteger` 호출은 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 메서드 및 두 개의 요소가 있는 명명 된 튜플을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-201">In the following example, `NumericLibrary.ParseInteger` calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method and returns a named tuple with two elements.</span></span> 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

<span data-ttu-id="b4b96-202">다음과 같은 코드를 사용 하 여 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-202">You can then call the method with code like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a><span data-ttu-id="b4b96-203">Visual Basic 튜플 및.NET Framework의 튜플</span><span class="sxs-lookup"><span data-stu-id="b4b96-203">Visual Basic tuples and tuples in the .NET Framework</span></span>

<span data-ttu-id="b4b96-204">Visual Basic 튜플은 중 하나의 인스턴스는 **System.ValueTuple** 제네릭 형식.NET Framework 4.7에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-204">A Visual Basic tuple is an instance of one of the **System.ValueTuple** generic types, which were introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="b4b96-205">.NET Framework 제네릭 집합이 포함 되어 **System.Tuple** 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-205">The .NET Framework also includes a set of generic **System.Tuple** classes.</span></span> <span data-ttu-id="b4b96-206">그러나 Visual Basic 튜플에서와 다 이러한 클래스와 **System.ValueTuple** 다양 한 방법으로의 제네릭 형식:</span><span class="sxs-lookup"><span data-stu-id="b4b96-206">These classes, however, differ from Visual Basic tuples and the **System.ValueTuple** generic types in a number of ways:</span></span>

- <span data-ttu-id="b4b96-207">요소는 **튜플** 클래스는 명명 된 속성 `Item1`, `Item2`등입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-207">The elements of the **Tuple** classes are properties named `Item1`, `Item2`, and so on.</span></span> <span data-ttu-id="b4b96-208">Visual Basic 튜플에 및 **ValueTuple** 형식, 튜플 요소는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-208">In Visual Basic tuples and the **ValueTuple** types, tuple elements are fields.</span></span>

- <span data-ttu-id="b4b96-209">요소에 의미 있는 이름을 할당할 수 없습니다는 **튜플** 인스턴스 또는 **ValueTuple** 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="b4b96-209">You cannot assign meaningful names to the elements of a **Tuple** instance or of a **ValueTuple** instance.</span></span> <span data-ttu-id="b4b96-210">Visual Basic을 사용 하는 필드의 의미를 전달 하는 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-210">Visual Basic allows you to assign names that communicate the meaning of the fields.</span></span>

- <span data-ttu-id="b4b96-211">속성은 **튜플** 인스턴스는 읽기 전용; 튜플을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-211">The properties of a **Tuple** instance are read-only; the tuples are immutable.</span></span> <span data-ttu-id="b4b96-212">Visual Basic 튜플에 및 **ValueTuple** 형식, 튜플 필드는 읽기 / 쓰기; 튜플에 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-212">In Visual Basic tuples and the **ValueTuple** types, tuple fields are read-write; the tuples are mutable.</span></span>

- <span data-ttu-id="b4b96-213">제네릭 **튜플** 형식은 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-213">The generic **Tuple** types are reference types.</span></span> <span data-ttu-id="b4b96-214">이 사용 하 여 **튜플** 개체 할당 의미를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-214">Using these **Tuple** types means allocating objects.</span></span> <span data-ttu-id="b4b96-215">실행 부하 과다 경로에서는 이로 인해 응용 프로그램 성능이 크게 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-215">On hot paths, this can have a measurable impact on your application's performance.</span></span> <span data-ttu-id="b4b96-216">Visual Basic 튜플 및 **ValueTuple** 유형은 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-216">Visual Basic tuples and the **ValueTuple** types are value types.</span></span>

<span data-ttu-id="b4b96-217">확장 메서드는 <xref:System.TupleExtensions> 클래스 쉽게 튜플 Visual Basic 및.NET 사이 변환할 **튜플** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-217">Extension methods in the <xref:System.TupleExtensions> class make it easy to convert between Visual Basic tuples and .NET **Tuple** objects.</span></span> <span data-ttu-id="b4b96-218">**ToTuple** 메서드는.NET Visual Basic 튜플 변환 **튜플** 개체 및 **ToValueTuple** 메서드 변환.NET **튜플** Visual Basic 튜플 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-218">The **ToTuple** method converts a Visual Basic tuple to a .NET **Tuple** object, and the **ToValueTuple** method converts a .NET **Tuple** object to a Visual Basic tuple.</span></span>

<span data-ttu-id="b4b96-219">다음 예제는 튜플을 만듭니다을 하는.NET 변환 **튜플** 개체 및 Visual Basic 튜플에 다시 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-219">The following example creates a tuple, converts it to a .NET **Tuple** object, and converts it back to a Visual Basic tuple.</span></span> <span data-ttu-id="b4b96-220">그런 다음 원래 같은지 확인에 있는이 튜플을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b96-220">The example then compares this tuple with the original one to ensure that they are equal.</span></span>

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a><span data-ttu-id="b4b96-221">참고자료</span><span class="sxs-lookup"><span data-stu-id="b4b96-221">See also</span></span>

[<span data-ttu-id="b4b96-222">Visual Basic 언어 참조</span><span class="sxs-lookup"><span data-stu-id="b4b96-222">Visual Basic Language Reference</span></span>](index.md)  
