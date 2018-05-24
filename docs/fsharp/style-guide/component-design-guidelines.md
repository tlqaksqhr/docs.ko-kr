---
title: 'F # 구성 요소 디자인 지침'
description: '다른 호출자에 의해 사용 하도록 설계 된 F # 구성 요소를 작성 하는 것에 대 한 지침에 알아봅니다.'
ms.date: 05/14/2018
ms.openlocfilehash: 7e71710b1bc2fe3e8d7a5a091513a1432650dc04
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="236c2-103">F # 구성 요소 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="236c2-103">F# component design guidelines</span></span>

<span data-ttu-id="236c2-104">이 문서는 F # 프로그래밍, F # 구성 요소 디자인 지침, v14, Microsoft Research 기반에 대 한 구성 요소 디자인 지침 집합이 고 [다른 버전](https://fsharp.org/specs/component-design-guidelines/) 원래 큐 레이트 하 고 F # Software Foundation에서 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and [another version](https://fsharp.org/specs/component-design-guidelines/) originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="236c2-105">이 문서에서는 F # 프로그래밍에 익숙한 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="236c2-106">F # 커뮤니티의 기여 하 고이 가이드의 다양 한 버전에 대 한 유용한 피드백에 대 한 도움을 주신 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="236c2-107">개요</span><span class="sxs-lookup"><span data-stu-id="236c2-107">Overview</span></span>

<span data-ttu-id="236c2-108">이 문서는 F # 구성 요소 디자인 및 코딩와 관련 된 문제 중 일부를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="236c2-109">구성 요소는 다음 중 하나를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="236c2-110">해당 프로젝트 내에서 외부 소비자가 있는 F # 프로젝트에는 계층입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="236c2-111">다른 어셈블리에서 F # 코드에서 사용 하도록 설계 된 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="236c2-112">다른 어셈블리에서 모든.NET 언어에서 사용 하도록 설계 된 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="236c2-113">와 같은 패키지 리포지토리를 통한 배포용 위한 라이브러리 [NuGet](https://nuget.org)합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="236c2-114">이 문서에서 설명 하는 방법에 따라는 [좋은 F # 코드의 5 개 원칙](index.md#five-principles-of-good-f-code)를 하 고 따라서 활용 기능 둘 다 고 적절 하 게 프로그래밍 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="236c2-115">방법과 상관 없이 구성 요소 및 라이브러리 디자이너 개발자가 쉽게 사용할 수 있는 API를 만들 하려고 할 때 실용적이 고 사용할 수 있는 문제가 많이 직면 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="236c2-116">인식 응용 프로그램은 [.NET 라이브러리 디자인 지침](../../standard/design-guidelines/index.md) 즐겁게 소비할 수 있는 Api의 일관 된 집합을 만들 때 유도 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="236c2-117">일반 지침</span><span class="sxs-lookup"><span data-stu-id="236c2-117">General guidelines</span></span>

<span data-ttu-id="236c2-118">F # 라이브러리에 라이브러리에 대 한 대상에 관계 없이 적용 되는 몇 가지 유니버설 지침 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="236c2-119">.NET 라이브러리 디자인 지침에 알아봅니다</span><span class="sxs-lookup"><span data-stu-id="236c2-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="236c2-120">F # 수행 하는 코딩의 종류에 관계 없이 하는 것이 한 작업 지식을 갖추고는 [.NET 라이브러리 디자인 지침](../../standard/design-guidelines/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="236c2-121">대부분 다른 F # 및.NET 프로그래머에 게 이러한 지침에 잘 알고 되며.NET 코드에 대 한 준수를 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="236c2-122">.NET 라이브러리 디자인 지침 명명, 클래스 및 인터페이스, 멤버 디자인 (속성, 메서드, 이벤트 등) 및 기타를 디자인에 대 한 일반적인 지침을 제공 하며 다양 한 디자인 지침에 대 한 참조에 유용한 첫 번째 지점 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="236c2-123">XML 문서 주석을 코드에 추가</span><span class="sxs-lookup"><span data-stu-id="236c2-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="236c2-124">공용 Api에 XML 문서는 라이브러리에 대 한 파일을 이러한 형식 및 멤버 및 사용 건물 설명서를 사용 하 여 때 유용한 Intellisense 및 요약 정보 사용자가 액세스할 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-124">XML documentation on public APIs ensure that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="236c2-125">참조는 [XML 문서](../language-reference/xml-documentation.md) xmldoc 주석 내 추가 태그에 사용할 수 있는 다양 한 xml 태그에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

<span data-ttu-id="236c2-126">약식 XML 주석을 사용할 수 있습니다 (`/// comment`), 또는 표준 XML 주석 (`///<summary>comment</summary>`).</span><span class="sxs-lookup"><span data-stu-id="236c2-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="236c2-127">안정적인 라이브러리 및 Api 구성 요소에 대 한 명시적 서명 파일 (.fsi)를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="236c2-128">이 두 가지 있는지 하면 라이브러리의 전체 공개 화면 알고으로 확실 하 게 구분 내부 및 공용 설명서 간의 제공 되도록 공용 API의 간단한 요약을 제공 명시적 서명 파일을 사용 하 여 F # 라이브러리의 구현 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which both helps to ensure that you know the full public surface of your library, as well as provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="236c2-129">Note 서명 파일 구현 및 서명 파일에 대해 적용할 변경 사항을 요구 하 여 공용 API를 변화 하는 마찰을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-129">Note that signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="236c2-130">결과적으로, 서명 파일이 일반적으로 소개 해야 API 그 되 고는 더 이상 크게 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="236c2-131">항상 문자열을 사용 하 여.NET에 대 한 모범 사례를 따르십시오</span><span class="sxs-lookup"><span data-stu-id="236c2-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="236c2-132">에 따라 [.NET에서 문자열 사용에 대 한 유용한](../../standard/base-types/best-practices-strings.md) 지침.</span><span class="sxs-lookup"><span data-stu-id="236c2-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="236c2-133">특히, 항상 명시적으로 지정할 *문화적 의도* 변환 및 문자열의 비교에서 (있는 경우).</span><span class="sxs-lookup"><span data-stu-id="236c2-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="236c2-134">F #에 대 한 지침-라이브러리를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="236c2-135">이 섹션에서는 공용 F #을 개발 하기 위한 권장 사항을-라이브러리; 연결 즉, 라이브러리를 F # 개발자가 사용 하기 위한 공용 Api를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="236c2-136">적용할 특히 F # 라이브러리 디자인 권장 구성의 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="236c2-137">에 나오는 특정 권장 사항은 없을 경우.NET 라이브러리 디자인 지침은 대체 (fallback)의 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="236c2-138">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="236c2-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="236c2-139">.NET 이름 지정 및 대/소문자 규칙을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="236c2-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="236c2-140">다음 표에서.NET 이름 지정 및 대/소문자 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="236c2-141">F # 구문을 포함에 대 한 작은 추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="236c2-142">구문</span><span class="sxs-lookup"><span data-stu-id="236c2-142">Construct</span></span> | <span data-ttu-id="236c2-143">Case</span><span class="sxs-lookup"><span data-stu-id="236c2-143">Case</span></span> | <span data-ttu-id="236c2-144">파트</span><span class="sxs-lookup"><span data-stu-id="236c2-144">Part</span></span> | <span data-ttu-id="236c2-145">예제</span><span class="sxs-lookup"><span data-stu-id="236c2-145">Examples</span></span> | <span data-ttu-id="236c2-146">노트</span><span class="sxs-lookup"><span data-stu-id="236c2-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="236c2-147">구체적인 형식</span><span class="sxs-lookup"><span data-stu-id="236c2-147">Concrete types</span></span> | <span data-ttu-id="236c2-148">표시 방법이 PascalCase</span><span class="sxs-lookup"><span data-stu-id="236c2-148">PascalCase</span></span> | <span data-ttu-id="236c2-149">명사 형용사 /</span><span class="sxs-lookup"><span data-stu-id="236c2-149">Noun/ adjective</span></span> | <span data-ttu-id="236c2-150">목록, Double, 복잡 한</span><span class="sxs-lookup"><span data-stu-id="236c2-150">List, Double, Complex</span></span> | <span data-ttu-id="236c2-151">구체적인 유형은 구조체, 클래스, 열거형, 대리자, 레코드 및 공용 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="236c2-152">형식 이름은 OCaml에 일반적으로 소문자로, F #는 채택 했습니다 형식에 대 한.NET 이름 지정 체계를입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="236c2-153">DLL</span><span class="sxs-lookup"><span data-stu-id="236c2-153">DLLs</span></span>           | <span data-ttu-id="236c2-154">표시 방법이 PascalCase</span><span class="sxs-lookup"><span data-stu-id="236c2-154">PascalCase</span></span> |                 | <span data-ttu-id="236c2-155">Fabrikam.Core.dll</span><span class="sxs-lookup"><span data-stu-id="236c2-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="236c2-156">공용 구조체 태그</span><span class="sxs-lookup"><span data-stu-id="236c2-156">Union tags</span></span>     | <span data-ttu-id="236c2-157">표시 방법이 PascalCase</span><span class="sxs-lookup"><span data-stu-id="236c2-157">PascalCase</span></span> | <span data-ttu-id="236c2-158">명사</span><span class="sxs-lookup"><span data-stu-id="236c2-158">Noun</span></span> | <span data-ttu-id="236c2-159">일부 추가, 성공</span><span class="sxs-lookup"><span data-stu-id="236c2-159">Some, Add, Success</span></span> | <span data-ttu-id="236c2-160">공용 Api에서 접두사를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="236c2-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="236c2-161">필요에 따라 내부와 같은 접두사를 사용 하 여 ' ' 팀 입력 TAlpha =</span><span class="sxs-lookup"><span data-stu-id="236c2-161">Optionally use a prefix when internal, such as \`\`\`type Teams = TAlpha</span></span> | <span data-ttu-id="236c2-162">TBeta</span><span class="sxs-lookup"><span data-stu-id="236c2-162">TBeta</span></span> | <span data-ttu-id="236c2-163">TDelta. ' '</span><span class="sxs-lookup"><span data-stu-id="236c2-163">TDelta.\`\`\`</span></span> |
| <span data-ttu-id="236c2-164">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="236c2-164">Event</span></span>          | <span data-ttu-id="236c2-165">표시 방법이 PascalCase</span><span class="sxs-lookup"><span data-stu-id="236c2-165">PascalCase</span></span> | <span data-ttu-id="236c2-166">동사</span><span class="sxs-lookup"><span data-stu-id="236c2-166">Verb</span></span> | <span data-ttu-id="236c2-167">재정의 / ValueChanging</span><span class="sxs-lookup"><span data-stu-id="236c2-167">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="236c2-168">예외</span><span class="sxs-lookup"><span data-stu-id="236c2-168">Exceptions</span></span>     | <span data-ttu-id="236c2-169">표시 방법이 PascalCase</span><span class="sxs-lookup"><span data-stu-id="236c2-169">PascalCase</span></span> |      | <span data-ttu-id="236c2-170">WebException</span><span class="sxs-lookup"><span data-stu-id="236c2-170">WebException</span></span> | <span data-ttu-id="236c2-171">이름 "예외"로 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-171">Name should end with “Exception”.</span></span> |
| <span data-ttu-id="236c2-172">필드</span><span class="sxs-lookup"><span data-stu-id="236c2-172">Field</span></span>          | <span data-ttu-id="236c2-173">표시 방법이 PascalCase</span><span class="sxs-lookup"><span data-stu-id="236c2-173">PascalCase</span></span> | <span data-ttu-id="236c2-174">명사</span><span class="sxs-lookup"><span data-stu-id="236c2-174">Noun</span></span> | <span data-ttu-id="236c2-175">CurrentName</span><span class="sxs-lookup"><span data-stu-id="236c2-175">CurrentName</span></span>  | |
| <span data-ttu-id="236c2-176">인터페이스 형식</span><span class="sxs-lookup"><span data-stu-id="236c2-176">Interface types</span></span> |  <span data-ttu-id="236c2-177">표시 방법이 PascalCase</span><span class="sxs-lookup"><span data-stu-id="236c2-177">PascalCase</span></span> | <span data-ttu-id="236c2-178">명사 형용사 /</span><span class="sxs-lookup"><span data-stu-id="236c2-178">Noun/ adjective</span></span> | <span data-ttu-id="236c2-179">IDisposable</span><span class="sxs-lookup"><span data-stu-id="236c2-179">IDisposable</span></span> | <span data-ttu-id="236c2-180">이름은 "I"로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-180">Name should start with “I”.</span></span> |
| <span data-ttu-id="236c2-181">메서드</span><span class="sxs-lookup"><span data-stu-id="236c2-181">Method</span></span> |  <span data-ttu-id="236c2-182">표시 방법이 PascalCase</span><span class="sxs-lookup"><span data-stu-id="236c2-182">PascalCase</span></span> |  <span data-ttu-id="236c2-183">동사</span><span class="sxs-lookup"><span data-stu-id="236c2-183">Verb</span></span> | <span data-ttu-id="236c2-184">ToString</span><span class="sxs-lookup"><span data-stu-id="236c2-184">ToString</span></span> | |
| <span data-ttu-id="236c2-185">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="236c2-185">Namespace</span></span> | <span data-ttu-id="236c2-186">표시 방법이 PascalCase</span><span class="sxs-lookup"><span data-stu-id="236c2-186">PascalCase</span></span> | | <span data-ttu-id="236c2-187">Microsoft.FSharp.Core</span><span class="sxs-lookup"><span data-stu-id="236c2-187">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="236c2-188">일반적으로 사용 하 여 `<Organization>.<Technology>[.<Subnamespace>]`, 기술이 조직 으로부터 독립적인 경우 하지만 조직을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-188">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="236c2-189">매개 변수</span><span class="sxs-lookup"><span data-stu-id="236c2-189">Parameters</span></span> | <span data-ttu-id="236c2-190">camelCase</span><span class="sxs-lookup"><span data-stu-id="236c2-190">camelCase</span></span> | <span data-ttu-id="236c2-191">명사</span><span class="sxs-lookup"><span data-stu-id="236c2-191">Noun</span></span> |  <span data-ttu-id="236c2-192">typeName, 변환, 범위</span><span class="sxs-lookup"><span data-stu-id="236c2-192">typeName, transform, range</span></span> | |
| <span data-ttu-id="236c2-193">값 (내부)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-193">let values (internal)</span></span> | <span data-ttu-id="236c2-194">camelCase 또는 표시 방법이 PascalCase</span><span class="sxs-lookup"><span data-stu-id="236c2-194">camelCase or PascalCase</span></span> | <span data-ttu-id="236c2-195">명사 / 동사</span><span class="sxs-lookup"><span data-stu-id="236c2-195">Noun/ verb</span></span> |  <span data-ttu-id="236c2-196">getValue, myTable</span><span class="sxs-lookup"><span data-stu-id="236c2-196">getValue, myTable</span></span> |
| <span data-ttu-id="236c2-197">값 (외부)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-197">let values (external)</span></span> | <span data-ttu-id="236c2-198">camelCase 또는 표시 방법이 PascalCase</span><span class="sxs-lookup"><span data-stu-id="236c2-198">camelCase or PascalCase</span></span> | <span data-ttu-id="236c2-199">명사/동사</span><span class="sxs-lookup"><span data-stu-id="236c2-199">Noun/verb</span></span>  | <span data-ttu-id="236c2-200">List.map Dates.Today</span><span class="sxs-lookup"><span data-stu-id="236c2-200">List.map, Dates.Today</span></span> | <span data-ttu-id="236c2-201">let 바인딩 값 기존의 기능 디자인 패턴을 수행할 때 공용 많습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-201">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="236c2-202">그러나 일반적으로 사용 하 여 표시 방법이 PascalCase 식별자는 다른.NET 언어에서 사용할 수 있을 때.</span><span class="sxs-lookup"><span data-stu-id="236c2-202">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="236c2-203">속성</span><span class="sxs-lookup"><span data-stu-id="236c2-203">Property</span></span>  | <span data-ttu-id="236c2-204">표시 방법이 PascalCase</span><span class="sxs-lookup"><span data-stu-id="236c2-204">PascalCase</span></span>  | <span data-ttu-id="236c2-205">명사 형용사 /</span><span class="sxs-lookup"><span data-stu-id="236c2-205">Noun/ adjective</span></span>  | <span data-ttu-id="236c2-206">IsEndOfFile, BackColor</span><span class="sxs-lookup"><span data-stu-id="236c2-206">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="236c2-207">부울 속성 일반적으로 사용 되 고 수 IsEndOfFile, 하지 IsNotEndOfFile 에서처럼 찬성 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-207">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="236c2-208">약어를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-208">Avoid abbreviations</span></span>

<span data-ttu-id="236c2-209">.NET 지침 약어를 사용 하지 못하도록 (예를 들어 "사용 `OnButtonClick` 대신 `OnBtnClick`").</span><span class="sxs-lookup"><span data-stu-id="236c2-209">The .NET guidelines discourage the use of abbreviations (for example, “use `OnButtonClick` rather than `OnBtnClick`”).</span></span> <span data-ttu-id="236c2-210">일반적인 약어와 같은 `Async` 트랜잭션당 "비동기"에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-210">Common abbreviations, such as `Async` for “Asynchronous”, are tolerated.</span></span> <span data-ttu-id="236c2-211">이 지침 함수형 프로그래밍;에 대 한 경우에 따라 무시 됩니다. 예를 들어 `List.iter` "반복"에 대 한 약어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-211">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for “iterate”.</span></span> <span data-ttu-id="236c2-212">이러한 이유로 약어를 사용 하는 경향이 F #에 보다 심층적 허용 될-에-F # 프로그래밍 있지만 공용 구성 요소 디자인에서 여전히 일반적으로 사용 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-212">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="236c2-213">이름 충돌을 대/소문자 구분 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="236c2-213">Avoid casing name collisions</span></span>

<span data-ttu-id="236c2-214">.NET 지침 예를 들어 일부 클라이언트 언어 (예를 들어 Visual Basic)은 대/소문자 구분 이름 충돌을 명확 하 게 대/소문자 구분 단독 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-214">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="236c2-215">적합 한 머리글자어 사용</span><span class="sxs-lookup"><span data-stu-id="236c2-215">Use acronyms where appropriate</span></span>

<span data-ttu-id="236c2-216">XML과 같은 머리글자어 약어 않으며 소문자로 시작된 양식 (Xml)에.NET 라이브러리에 널리 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-216">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="236c2-217">만 널리 인정, 잘 알려진 약어를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-217">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="236c2-218">제네릭 매개 변수 이름에 대 한 표시 방법이 PascalCase를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="236c2-218">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="236c2-219">F #에 대 한 포함 하는 공용 Api에서 제네릭 매개 변수 이름에 표시 방법이 PascalCase 사용-라이브러리를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-219">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="236c2-220">특히,와 같은 이름을 사용 하 여 `T`, `U`, `T1`, `T2` 임의의 제네릭 매개 변수에 대 한 및 특정 이름이 의미가 다음 F #에 대 한-마주보 라이브러리와 같은 이름을 사용 하 여 `Key`, `Value`, `Arg`(하지만 하지 예를 들어 `TKey`).</span><span class="sxs-lookup"><span data-stu-id="236c2-220">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="236c2-221">공용 함수 및 F # 모듈의 값에 대 한 표시 방법이 PascalCase 또는 camelCase 중 하나를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="236c2-221">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="236c2-222">camelCase 공용 함수를 사용할 수 있도록 설계에 사용 되 정규화 되지 않은 (예를 들어 `invalidArg`), 및 (예: List.map) "표준 컬렉션 함수"에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-222">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the “standard collection functions” (for example, List.map).</span></span> <span data-ttu-id="236c2-223">두이 경우 모두에서 함수 이름을 훨씬 언어의 키워드에에서 처럼 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-223">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="236c2-224">개체, 형식 및 모듈 디자인</span><span class="sxs-lookup"><span data-stu-id="236c2-224">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="236c2-225">네임 스페이스 또는 모듈을 사용 하 여 형식 및 모듈을 포함 하도록</span><span class="sxs-lookup"><span data-stu-id="236c2-225">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="236c2-226">각 F # 파일에서 구성 요소에서 네임 스페이스 선언 또는 모듈 선언으로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-226">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="236c2-227">또는</span><span class="sxs-lookup"><span data-stu-id="236c2-227">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="236c2-228">최상위 수준에서 코드를 구성 모듈 및 네임 스페이스를 사용 하 여 간의 차이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-228">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="236c2-229">네임 스페이스는 여러 파일을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-229">Namespaces can span multiple files</span></span>
* <span data-ttu-id="236c2-230">네임 스페이스는 내부 모듈 내에서 아니면 F # 함수를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-230">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="236c2-231">지정 된 모든 모듈에 대 한 코드는 단일 파일에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-231">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="236c2-232">최상위 모듈에는 F # 함수 내부 모듈에 대 한 필요 없이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-232">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="236c2-233">최상위 네임 스페이스 또는 모듈 간의 선택 코드의 컴파일된 형태에 영향을 줍니다 따라서 영향을 미칩니다 다른.NET 언어에서 보기 사용 해야 하 여 API 결국 F # 코드 외부에서.</span><span class="sxs-lookup"><span data-stu-id="236c2-233">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="236c2-234">개체 형식에 내장 된 작업에 대 한 메서드 및 속성 사용</span><span class="sxs-lookup"><span data-stu-id="236c2-234">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="236c2-235">개체를 사용할 때 사용 될 기능 메서드 및 해당 형식에 대 한 속성으로 구현 됨을 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-235">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="236c2-236">지정된 된 멤버에 대 한 기능 대량의 필요 하지 반드시 구현할 수 해당 멤버에 있지만 해당 기능에서 사용 될 수 있습니다 항목 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-236">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="236c2-237">클래스를 사용 하 여 변경 가능 상태를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-237">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="236c2-238">F #에서이 수행 해야 여기서 상태 클로저, 시퀀스 식에서 비동기 계산 등의 다른 언어 구문이 이미 캡슐화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-238">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="236c2-239">그룹화 할 인터페이스를 사용 하 여 관련 작업</span><span class="sxs-lookup"><span data-stu-id="236c2-239">Use interfaces to group related operations</span></span>

<span data-ttu-id="236c2-240">일련의 작업을 나타내는 인터페이스 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-240">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="236c2-241">이 함수는 튜플 또는 함수의 레코드 등의 다른 옵션에 선호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-241">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="236c2-242">우선적으로:</span><span class="sxs-lookup"><span data-stu-id="236c2-242">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

<span data-ttu-id="236c2-243">인터페이스는 어떤 함수는 일반적으로 사용 하면 달성 하기 위해 사용할 수 있는.NET에 대 한 주요 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-243">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="236c2-244">또한 함수의 레코드 수 없습니다. 프로그램에 존재 하는 형식을 인코딩하는 데 사용할 수 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-244">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a><span data-ttu-id="236c2-245">컬렉션에 대해 작동 하는 그룹 함수에는 모듈을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="236c2-245">Use a module to group functions which act on collections</span></span>

<span data-ttu-id="236c2-246">컬렉션 형식을 정의 하는 경우와 같은 표준 작업 집합이 제공 하십시오 `CollectionType.map` 및 `CollectionType.iter`)에 대 한 새 컬렉션 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-246">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="236c2-247">이러한 모듈을 포함 하는 경우 FSharp.Core에서 찾을 수 함수에 대 한 표준 명명 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-247">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="236c2-248">특히 수학 및 DSL 라이브러리에서 일반적으로 정식 함수에 대 한 모듈 그룹 기능을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="236c2-248">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="236c2-249">예를 들어 `Microsoft.FSharp.Core.Operators` 은 자동으로 열리는 컬렉션 최상위 함수 (같은 `abs` 및 `sin`) FSharp.Core.dll에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-249">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="236c2-250">마찬가지로, 통계 라이브러리 함수를 사용 하 여 모듈을 포함할 수 있습니다 `erf` 및 `erfc`여기서이 모듈은 디자인 된 명시적으로 또는 자동으로 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-250">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="236c2-251">신중 하 게 AutoOpen 특성을 적용 및 RequireQualifiedAccess를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-251">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="236c2-252">추가 `[<RequireQualifiedAccess>]` 특성을 모듈에 모듈을 열 수 있습니다 하며 액세스를 한정 된 모듈의 요소에 대 한 참조가 필요 명시적 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-252">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="236c2-253">예를 들어는 `Microsoft.FSharp.Collections.List` 모듈에는이 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-253">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="236c2-254">함수 및 모듈의 값에는 이름이 다른 모듈의 있는 이름과 충돌 가능성이 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-254">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="236c2-255">정규화 된 액세스가 필요한 장기적인 유지 관리 및 라이브러리의 evolvability 크게 향상 시켜 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-255">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="236c2-256">추가 `[<AutoOpen>]` 특성 모듈을 포함 하는 네임 스페이스를 열 때 모듈을 열 수는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-256">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="236c2-257">`[<AutoOpen>]` 특성이 어셈블리를 참조할 때 자동으로 열려 있는 모듈을 표시 하기 위해 어셈블리에도 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-257">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="236c2-258">예를 들어 통계 라이브러리 **MathsHeaven.Statistics** 포함 될 수 있습니다는 `module MathsHeaven.Statistics.Operators` 함수가 포함 된 `erf` 및 `erfc`합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-258">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="236c2-259">이 모듈을 표시 하려면이 `[<AutoOpen>]`합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-259">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="236c2-260">즉, `open MathsHeaven.Statistics` 이 모듈을 열고 및 이름을 상태로 `erf` 및 `erfc` 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-260">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="236c2-261">사용 된 다른 `[<AutoOpen>]` 확장 메서드를 포함 하는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-261">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="236c2-262">과 용 `[<AutoOpen>]` 주의 하 여 잠재 고객 오염된 네임 스페이스 및 특성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-262">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="236c2-263">특정 도메인에 적절 하 게 사용할 특정 라이브러리에 대 한 `[<AutoOpen>]` 성이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-263">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="236c2-264">잘 알려진 연산자를 사용 하는 적절 한 클래스에서 연산자 멤버를 정의 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-264">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="236c2-265">경우에 따라 클래스 벡터와 같은 수학적 구문을 모델링 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-265">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="236c2-266">모델링 되는 도메인에 잘 알려진 연산자가 있을 때 유용 내장 함수는 클래스를 구성원으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-266">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="236c2-267">이 가이드는 이러한 형식에 대 한 일반적인.NET 지침에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-267">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="236c2-268">그러나 F #을 함께 F # 함수 및 메서드에서 List.sumBy 같은 멤버 제약 조건과 함께 사용할 이러한 형식에 허용이 코딩 또한 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-268">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="236c2-269">CompiledName를 사용 하 여 제공 하는 합니다. 다른.NET 언어 소비자에 NET 이름</span><span class="sxs-lookup"><span data-stu-id="236c2-269">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="236c2-270">경우에 따라 있습니다 이름을 지정할 수 하나의 스타일에 F # 소비자에 대 한 (소문자로 표시 되도록 정적 멤버와 같은 모듈 바인딩된 함수 처럼)를 설치 했지만 다른 스타일 이름에 대 한 어셈블리로 컴파일할 때 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-270">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="236c2-271">사용할 수는 `[<CompiledName>]` 특성을 비 F # 코드 어셈블리 사용에 대 한 다른 스타일을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-271">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="236c2-272">사용 하 여 `[<CompiledName>]`, 비 F # 어셈블리 소비자에 대 한.NET 명명 규칙을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-272">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="236c2-273">이렇게 하면 더 간단 하는 API를 제공 하는 경우 멤버 함수에 대 한 메서드 오버 로드 사용</span><span class="sxs-lookup"><span data-stu-id="236c2-273">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="236c2-274">메서드 오버 로드는 다양 한 옵션 또는 인수 하면서도 유사한 기능을 수행 해야 할 수 있는 API를 단순화 하기 위한 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-274">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="236c2-275">이 F #에서 인수의 형식 보다는 수의 인수에 오버 로드를 더 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-275">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="236c2-276">레코드 및 공용 구조체 형식의 표현의 숨기는 이러한 종류의 디자인은 변경 될 수 있으므로</span><span class="sxs-lookup"><span data-stu-id="236c2-276">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="236c2-277">개체의 구체적인 표현을 노출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="236c2-277">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="236c2-278">예를 들어 구체적인 표현의 <xref:System.DateTime> 값이.NET 라이브러리 디자인의 외부, 공용 API에서 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-278">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="236c2-279">런타임 시 공용 언어 런타임 실행 전체에서 사용 하는 커밋된 구현을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-279">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="236c2-280">그러나 컴파일된 코드 자체는 선택 하지 않습니다 구체적인 표현에 대 한 종속성입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-280">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="236c2-281">확장성에 대 한 구현 상속을 사용 하지 않도록</span><span class="sxs-lookup"><span data-stu-id="236c2-281">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="236c2-282">F #에서 구현 상속은 거의 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-282">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="236c2-283">또한 상속 계층 구조는 종종 복잡 하 고 새 요구 사항을 도착할 때 변경 하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-283">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="236c2-284">상속 구현 드문 경우에는 문제에 가장 적합 한 솔루션 하지만 사용할 다른 방법을 찾아야 할 F # 프로그램에서 같은 인터페이스 구현 다형성을 위해 설계할 때의 호환성 및 F #에서 여전히 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-284">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="236c2-285">함수 및 구성원 서명</span><span class="sxs-lookup"><span data-stu-id="236c2-285">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="236c2-286">적은 수의 여러 관련 없는 값을 반환 하는 경우 반환 값에 대 한 튜플을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="236c2-286">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="236c2-287">반환 형식에 튜플을 사용의 좋은 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-287">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="236c2-288">에 대 한 여러 구성 요소를 포함 하는 형식을 반환 하거나 구성 요소 식별이 가능한 엔터티는 관련 된, 튜플을 대신 명명 된 형식을 사용 하 여 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-288">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="236c2-289">사용 하 여 `Async<T>` F # API 경계에서 비동기 프로그래밍에 대 한</span><span class="sxs-lookup"><span data-stu-id="236c2-289">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="236c2-290">라는 해당 동기 작업 인지 `Operation` 반환 하는 `T`, 비동기 작업 이름을 지정 해야 하는 다음 `AsyncOperation` 반환 하는 경우 `Async<T>` 또는 `OperationAsync` 반환 하는 경우 `Task<T>`합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-290">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="236c2-291">사용 하는 것이 좋습니다 Begin/End 메서드를 노출 하는 일반적으로 사용 되는.NET 형식에 대 한 `Async.FromBeginEnd` 확장 메서드는.NET Api에 F # 비동기 프로그래밍 모델을 제공 하려면 외관으로 씁니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-291">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

```fsharp
type SomeType =
    member this.Compute(x:int) : int =
        ...
    member this.AsyncCompute(x:int) : Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a><span data-ttu-id="236c2-292">예외</span><span class="sxs-lookup"><span data-stu-id="236c2-292">Exceptions</span></span>

<span data-ttu-id="236c2-293">예외는.net; 예외 즉, 이러한 발생 하지 않습니다 자주 런타임 시.</span><span class="sxs-lookup"><span data-stu-id="236c2-293">Exceptions are exceptional in .NET; that is, they should not occur frequently at runtime.</span></span> <span data-ttu-id="236c2-294">그럴 경우 포함 된 정보 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-294">When they do, the information they contain is valuable.</span></span> <span data-ttu-id="236c2-295">예외는 핵심.NET;의 최고 수준의 개념 응용 프로그램의 예외를 적절 한 다음 구성 요소 인터페이스의 디자인의 일환으로 쓰일 수 있으므로 it 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-295">Exceptions are a core first class concept of .NET; it hence follows that appropriate application of the Exceptions should be used as part of the design of the interface of a component.</span></span>

#### <a name="follow-the-net-guidelines-for-exceptions"></a><span data-ttu-id="236c2-296">예외에 대 한.NET 지침에 따라</span><span class="sxs-lookup"><span data-stu-id="236c2-296">Follow the .NET guidelines for exceptions</span></span>

<span data-ttu-id="236c2-297">[.NET 라이브러리 디자인 지침](../../standard/design-guidelines/exceptions.md) 모든.NET 프로그래밍의 컨텍스트에서 예외 사용에 뛰어난 도움말을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-297">The [.NET Library Design Guidelines](../../standard/design-guidelines/exceptions.md) give excellent advice on the use of exceptions in the context of all .NET programming.</span></span> <span data-ttu-id="236c2-298">이러한 지침 중 일부는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-298">Some of these guidelines are as follows:</span></span>

* <span data-ttu-id="236c2-299">정상적인 제어 흐름에 대 한 예외를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="236c2-299">Do not use exceptions for normal flow of control.</span></span> <span data-ttu-id="236c2-300">이 기술은 OCaml 등의 언어에는 대개, 하지만 버그 발생 하기 쉽습니다 및.NET에서 비효율적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-300">Although this technique is often used in languages such as OCaml, it is bug-prone and can be inefficient on .NET.</span></span> <span data-ttu-id="236c2-301">대신, 반환 해 보십시오는 `None` 옵션에 공용 또는 예상 발생 한 실패를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-301">Instead, consider returning a `None` option value to indicate a failure that is a common or expected occurrence.</span></span>

* <span data-ttu-id="236c2-302">함수를 잘못 사용 하면 구성 요소에서 발생 한 예외를 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-302">Document exceptions thrown by your components when a function is used incorrectly.</span></span>

* <span data-ttu-id="236c2-303">가능한 경우, 기존 예외는 시스템 네임 스페이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-303">Where possible, employ existing exceptions from the System namespaces.</span></span> <span data-ttu-id="236c2-304">방지 <xref:System.ApplicationException>되지만, 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-304">Avoid <xref:System.ApplicationException>, though.</span></span>

* <span data-ttu-id="236c2-305">throw 하지 않습니다 <xref:System.Exception> 는 사용자 코드로 이스케이프 되는 경우.</span><span class="sxs-lookup"><span data-stu-id="236c2-305">Do not throw <xref:System.Exception> when it will escape to user code.</span></span> <span data-ttu-id="236c2-306">여기에 사용 하지 `failwith`, `failwithf`, 스크립트에서 사용 하기 위해 및 개발 중인 코드에 대 한 유용한 함수는 있지만 F # 라이브러리 코드를 더 구체적인 예외 형식 발생 하기 위해에서 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-306">This includes avoiding the use of `failwith`, `failwithf`, which are handy functions for use in scripting and for code under development, but should be removed from F# library code in favor of throwing a more specific exception type.</span></span>

* <span data-ttu-id="236c2-307">사용 하 여 `nullArg`, `invalidArg`, 및 `invalidOp` 시키려면 메커니즘으로 <xref:System.ArgumentNullException>, <xref:System.ArgumentException>, 및 <xref:System.InvalidOperationException> 적절 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-307">Use `nullArg`, `invalidArg`, and `invalidOp` as the mechanism to throw <xref:System.ArgumentNullException>, <xref:System.ArgumentException>, and <xref:System.InvalidOperationException> when appropriate.</span></span>

#### <a name="consider-using-option-values-for-return-types-when-failure-is-not-an-exceptional-scenario"></a><span data-ttu-id="236c2-308">실패 예외 시나리오는 아닌 경우 반환 형식에 대 한 옵션 값을 사용 하는 것이 좋습니다</span><span class="sxs-lookup"><span data-stu-id="236c2-308">Consider using option values for return types when failure is not an exceptional scenario</span></span>

<span data-ttu-id="236c2-309">"예외"; 수 있어야 하는 예외에 대 한.NET 접근이입니다. 즉, 비교적 자주 발생 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-309">The .NET approach to exceptions is that they should be “exceptional”; that is, they should occur relatively infrequently.</span></span> <span data-ttu-id="236c2-310">그러나 일부 작업 (예: 테이블 검색)이 자주 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-310">However, some operations (for example, searching a table) may fail frequently.</span></span> <span data-ttu-id="236c2-311">F # 옵션 값은 이러한 작업의 반환 형식을 나타낼 수 있는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-311">F# option values are an excellent way to represent the return types of these operations.</span></span> <span data-ttu-id="236c2-312">이러한 작업은 일반적으로 "try" 이름 접두사로 시작:</span><span class="sxs-lookup"><span data-stu-id="236c2-312">These operations conventionally start with the name prefix “try”:</span></span>

```fsharp
// bad: throws exception if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// bad: returns -1 if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// good: returns None if no element meets criteria
member this.TryFindFirstIndex(pred : 'T -> bool) : int option =
    ...
```

### <a name="extension-members"></a><span data-ttu-id="236c2-313">확장 멤버</span><span class="sxs-lookup"><span data-stu-id="236c2-313">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="236c2-314">F #에서 F # 확장 멤버를 신중 하 게 적용-에-F # 구성 요소</span><span class="sxs-lookup"><span data-stu-id="236c2-314">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="236c2-315">일반적으로 대부분의 모드를 사용 하 여의 형식과 연관 내장 연산의 클로저에 있는 작업에 대해 F # 확장 멤버에만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-315">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="236c2-316">일반적으로 사용 F #에 다양 한.NET 형식의 관용구 더 있는 Api를 제공 하는 것:</span><span class="sxs-lookup"><span data-stu-id="236c2-316">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="236c2-317">공용 구조체 유형</span><span class="sxs-lookup"><span data-stu-id="236c2-317">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="236c2-318">구분 된 공용 구조체를 사용 하 여 트리 구조의 데이터에 대 한 클래스 계층 구조 대신</span><span class="sxs-lookup"><span data-stu-id="236c2-318">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="236c2-319">트리 형식 구조는 재귀적으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-319">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="236c2-320">이것은 상속을 잘못 된 구문이 구별 된 결합 된 세련 된입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-320">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="236c2-321">또한 구별 된 공용 구조체를 사용 하 여 트리 형식 데이터를 나타내는 패턴 일치에서 exhaustiveness에서 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-321">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="236c2-322">사용 하 여 `[<RequireQualifiedAccess>]` 사례 이름이 충분히 고유 하지 않습니다. 공용 구조체 형식에 대해</span><span class="sxs-lookup"><span data-stu-id="236c2-322">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="236c2-323">직접 있는 도메인 이름이 같은 구별 된 공용 구조체 케이스와 같은 다른 작업에 가장 적합 한 이름을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-323">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="236c2-324">사용할 수 있습니다 `[<RequireQualifiedAccess>]` 혼동 인 한 오류 숨기기 종속의 순서를 트리거하지 않도록 하기 위해 case 이름을 명확 하 게 `open` 문</span><span class="sxs-lookup"><span data-stu-id="236c2-324">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="236c2-325">이진 호환 Api에 대 한 구별 된 공용 구조체의 표현의 숨기는 이러한 종류의 디자인은 변경 될 수 있으므로</span><span class="sxs-lookup"><span data-stu-id="236c2-325">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="236c2-326">F # 패턴 일치 forms 간결한 프로그래밍 모델에 대 한 공용 구조체 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-326">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="236c2-327">앞에서 설명한 대로 이러한 형식의 디자인은 변경 될 수 있으므로 하는 경우 구체적인 데이터 표현을 노출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="236c2-327">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="236c2-328">예를 들어 구별된 된 공용 구조체의 표현을 숨길 수 있는 private 또는 internal 선언을 사용 하 여 또는 서명 파일을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-328">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="236c2-329">구별 된 공용 구조체를 무차별적으로 표시 하는 경우 알 수 있습니다이 버전으로 하드 라이브러리 사용자 코드를 중단시 키 지 않고도.</span><span class="sxs-lookup"><span data-stu-id="236c2-329">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="236c2-330">대신, 해당 형식의 값에 대 한 패턴 일치를 허용 하기 위해 하나 이상의 활성 패턴을 노출 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-330">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="236c2-331">활성 패턴에는 F # 공용 구조체 형식에 직접 노출 방지 하는 동안 일치 하는 패턴으로 F # 소비자가 제공 하는 다른 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-331">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="236c2-332">인라인 함수와 멤버 제약 조건</span><span class="sxs-lookup"><span data-stu-id="236c2-332">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="236c2-333">인라인 함수를 사용 하 여 암시적된 멤버 제약 조건, 정적으로 확인 된 제네릭 형식이 일반 숫자 알고리즘을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-333">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="236c2-334">산술 멤버 제약 조건 및 F # 비교 제약 F # 프로그래밍에 대 한 표준은입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-334">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="236c2-335">예를 들어, 다음 코드를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="236c2-335">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="236c2-336">이 함수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-336">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="236c2-337">이것이 수학 라이브러리의 공용 API에 대 한 적절 한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-337">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="236c2-338">형식 클래스 및 덕 시뮬레이션 하기 멤버 제약 조건을 사용 하지 마십시오</span><span class="sxs-lookup"><span data-stu-id="236c2-338">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="236c2-339">"덕"를 시뮬레이션할 수는 F # 멤버 제약 조건을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-339">It is possible to simulate “duck typing” using F# member constraints.</span></span> <span data-ttu-id="236c2-340">그러나 멤버 하는 사용 하 여이 F #에 속하지 않은 일반을 사용 해야-에-F # 라이브러리 디자인 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-340">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="236c2-341">사용자 코드 고정적인 하 고 하나의 특정 프레임 워크 패턴 제한은를 모르거나 비표준 암시적 제약 조건에 따라 라이브러리 디자인 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-341">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="236c2-342">또한 매우 긴 컴파일 시간 많이 이런이 방식으로 멤버 제약 조건 사용할 때 발생할 수 있는 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-342">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="236c2-343">연산자 정의</span><span class="sxs-lookup"><span data-stu-id="236c2-343">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="236c2-344">기호화 된 사용자 지정 연산자를 정의 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="236c2-344">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="236c2-345">사용자 지정 연산자는 상황에 따라 필수 이며 구현 코드의 큰 본문이 내에 매우 유용한 표기 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-345">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="236c2-346">라이브러리의 새 사용자에 대 한 명명 된 함수는 보다 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-346">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="236c2-347">또한 사용자 지정 기호 연산자는 문서를 하기 어려울 수 있습니다 및 사용자 들이 찾을 IDE 및 검색 엔진에서 기존 제한으로 인해 연산자에 대 한 도움말을 조회 하기가 더 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-347">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="236c2-348">결과적으로, 프로그램 및 기능을 명명 된 함수 멤버를 게시 하 고 또한 표기법 상의 이점을 설명서와 cognitive 비용 있는 것 보다 클 경우에이 기능에 대 한 연산자를 노출 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-348">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="236c2-349">측정 단위</span><span class="sxs-lookup"><span data-stu-id="236c2-349">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="236c2-350">신중 하 게 측정 단위를 사용 하 여 F # 코드에 추가 된 형식 안정성</span><span class="sxs-lookup"><span data-stu-id="236c2-350">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="236c2-351">측정 단위에 대 한 입력 추가 정보는 다른.NET 언어에서 볼 때 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-351">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="236c2-352">주의.NET 구성 요소, 도구 및 리플렉션 단위 san은 형식 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-352">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="236c2-353">예를 들어 C# 소비자가 표시 됩니다 `float` 대신 `float<kg>`합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-353">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="236c2-354">형식 약어</span><span class="sxs-lookup"><span data-stu-id="236c2-354">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="236c2-355">신중 하 게 형식 약어를 사용 하 여 F # 코드를 단순화 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-355">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="236c2-356">.NET 구성 요소, 도구 및 리플렉션 형식에 대 한 약식된 이름이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-356">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="236c2-357">형식 약어의 중요 한 사용량에 나타날 것 보다 복잡 한 실제로, 소비자가 혼동을 줄 수 있는 도메인을 축소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-357">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="236c2-358">해당 멤버 및 속성 형식에서 사용할 수 있는 기본적으로 달라 야 하는 공용 형식에 대 한 형식 약어를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-358">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="236c2-359">이 경우 형식에서 정의 하 고 실제 형식 표현에 대해 자세히 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-359">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="236c2-360">대신, 클래스 유형 또는 단일 대/소문자 구별 된 공용 구조체에는 약어를 배치 하는 것이 좋습니다. 또는, 성능이 필수적인 경우는 약어를 래핑하는 구조체 형식을 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="236c2-360">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="236c2-361">예를 들어 F # 맵의 특별 한 경우로 예를 들어 다중 지도 정의 하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-361">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="236c2-362">그러나이 형식에 대 한 논리 점 표기법 작업 지도 대 한 작업으로 동일 하지 않은-lookup 연산자 매핑할 수 있는지 합리적인 하는 예를 들어 합니다. [키] 반환이 예외를 발생 시키는 대신 사전에 키가 없는 경우에 빈 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-362">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="236c2-363">다른.NET 언어에서 사용 하기 위해 라이브러리에 대 한 지침</span><span class="sxs-lookup"><span data-stu-id="236c2-363">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="236c2-364">다른.NET 언어에서 사용 하기 위해 라이브러리를 디자인할 때이에 맞게 중요는 [.NET 라이브러리 디자인 지침](../../standard/design-guidelines/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-364">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="236c2-365">이 문서에 이러한 라이브러리는 F # 달리 바닐라.NET 라이브러리로 표시 된-제한 없이 생성 F #을 사용 하는 라이브러리를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-365">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="236c2-366">F #의 사용을 최소화 하 여.NET Framework의 나머지 부분과 일치 친숙 하 고 관용구 Api를 제공 하 의미 바닐라.NET 라이브러리 디자인-공용 API에서 특정 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-366">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="236c2-367">규칙은 다음 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-367">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="236c2-368">Namespace 및 형식 디자인 (라이브러리에 대 한 다른.NET 언어에서 사용 하기 위해)</span><span class="sxs-lookup"><span data-stu-id="236c2-368">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="236c2-369">구성 요소의 공용 API에.NET 명명 규칙을 적용</span><span class="sxs-lookup"><span data-stu-id="236c2-369">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="236c2-370">약식된 이름이 및.NET 대/소문자가 지침의 사용에 특별히 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-370">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="236c2-371">구성 요소에 대 한 기본 조직 구조도 네임 스페이스, 형식 및 멤버를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="236c2-371">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="236c2-372">공용 기능을 포함 하는 모든 파일으로 시작 해야는 `namespace` 선언 및 네임 스페이스에만 공용 엔터티 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-372">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="236c2-373">F # 모듈을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="236c2-373">Do not use F# modules.</span></span>

<span data-ttu-id="236c2-374">구현 코드, 형식 유틸리티 및 유틸리티 함수를 보유 하 public이 아닌 모듈을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-374">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="236c2-375">정적 형식은 해야 원하는 모듈을 통해 F # 모듈 내에서 사용할 수 없습니다..NET API 디자인 개념 하 고 다른 오버 로드를 사용 하는 API의 향후 발전을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-375">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="236c2-376">예를 들어 다음 공용 API 대신:</span><span class="sxs-lookup"><span data-stu-id="236c2-376">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="236c2-377">대신 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="236c2-377">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="236c2-378">형식 디자인 하지 발전 하는 경우 F # 레코드 형식을 바닐라.NET Api에서 사용</span><span class="sxs-lookup"><span data-stu-id="236c2-378">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="236c2-379">F # 레코드 종류는 간단한.NET 클래스를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-379">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="236c2-380">이러한 작업은 몇 가지 단순 하 고 안정적인 형식 Api에 대 한 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-380">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="236c2-381">사용을 고려해 야는 `[<NoEquality>]` 및 `[<NoComparison>]` 특성을 인터페이스의 자동 생성을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-381">You should consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="236c2-382">또한 공용 필드 이러한 노출으로 바닐라.NET Api의에서 변경 가능한 레코드 필드를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="236c2-382">Also avoid using mutable record fields in vanilla .NET APIs as these exposes a public field.</span></span> <span data-ttu-id="236c2-383">항상 클래스 API의 미래 변화에 대 한 보다 유연한 옵션을 제공 하는지 여부를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-383">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="236c2-384">예를 들어 다음 F # 코드는 C# 소비자에 게 공용 API를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-384">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="236c2-385">F #의 경우:</span><span class="sxs-lookup"><span data-stu-id="236c2-385">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing : int
        SecondThing : string }
```

<span data-ttu-id="236c2-386">C#: </span><span class="sxs-lookup"><span data-stu-id="236c2-386">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="236c2-387">.NET Api 바닐라에서 F # 공용 구조체 형식의 표현을 숨기기</span><span class="sxs-lookup"><span data-stu-id="236c2-387">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="236c2-388">F # 공용 구조체 형식을 거의 사용 되지 않는 구성 요소 경계를 넘어에 F #-에-F # 코딩 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-388">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="236c2-389">구성 요소 및 라이브러리에서 내부적으로 사용 될 때에 뛰어난 구현 장치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-389">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="236c2-390">바닐라.NET API를 디자인할 때 공용 구조체 형식의 표현을 개인 선언 또는 서명 파일을 사용 하 여 숨기는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-390">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="236c2-391">또한 원하는 제공 하기 내부적으로 멤버와 함께 union 표현을 사용 하는 형식을 보강할 수 있습니다. NET 연결 API입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-391">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True

    /// A public member for use from C#
    member x.Evaluate =
        match x with
        | And(a,b) -> a.Evaluate && b.Evaluate
        | Not a -> not a.Evaluate
        | True -> true

    /// A public member for use from C#
    static member CreateAnd(a,b) = And(a,b)
```

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="236c2-392">디자인 GUI 및 프레임 워크의 디자인 패턴을 사용 하 여 다른 구성 요소</span><span class="sxs-lookup"><span data-stu-id="236c2-392">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="236c2-393">WinForms, WPF 및 ASP.NET 같은.NET에서 사용할 수 있는 다양 한 프레임 워크 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-393">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="236c2-394">이러한 프레임 워크에서 사용 하기 위해 구성 요소를 디자인 하는 경우 각각에 대 한 이름 지정 및 디자인 규칙에 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-394">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="236c2-395">예를 들어 WPF 프로그래밍에 대 한 디자인 하는 클래스에 대 한 WPF 디자인 패턴을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-395">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="236c2-396">사용자 인터페이스 프로그래밍에서 모델에 대 한 이벤트와 같은 디자인 패턴을 사용 하 여 이며 같은 알림 기반 컬렉션에 <xref:System.Collections.ObjectModel>합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-396">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="236c2-397">개체와 멤버 디자인 (라이브러리에 대 한 다른.NET 언어에서 사용 하기 위해)</span><span class="sxs-lookup"><span data-stu-id="236c2-397">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="236c2-398">CLIEvent 특성을 사용 하 여.NET 이벤트를 노출 하려면</span><span class="sxs-lookup"><span data-stu-id="236c2-398">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="236c2-399">생성 한 `DelegateEvent` 대리자 개체를 사용 하는 형식의 특정.net 및 `EventArgs` (아닌 `Event`, 사용 하는 `FSharpHandler` 유형을 기본적으로) 하는 이벤트는 다른.NET 언어에 친숙 한 방식으로 게시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-399">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x:int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a><span data-ttu-id="236c2-400">.NET 작업을 반환 하는 메서드로 비동기 작업 노출</span><span class="sxs-lookup"><span data-stu-id="236c2-400">Expose asynchronous operations as methods which return .NET tasks</span></span>

<span data-ttu-id="236c2-401">작업을 나타내는 활성 비동기 계산.NET에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-401">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="236c2-402">작업은 일반적으로 F # 보다 덜 compositional `Async<T>` 개체의 경우 "이미 실행 중" 작업을 나타내는지과 병렬 컴퍼지션을 수행 하는 하거나 취소 신호 오류 코드 및 기타 전파를 숨기는 함께 구성 될 수 있으므로 컨텍스트 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-402">Tasks are in general less compositional than F# `Async<T>` objects, since they represent “already executing” tasks and can’t be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="236c2-403">그러나, 그럼에도 불구 하 고 작업을 반환 하는 메서드는.NET에서 비동기 프로그래밍의 표준 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-403">However, despite this, methods which return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="236c2-404">자주 됩니다도 명시적 취소 토큰을 수락 하려면:</span><span class="sxs-lookup"><span data-stu-id="236c2-404">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="236c2-405">F # 함수 형식 대신.NET 대리자 형식을 사용합니다</span><span class="sxs-lookup"><span data-stu-id="236c2-405">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="236c2-406">와 같은 "화살표" 형식 "F # 함수 형식"을 의미 하는 여기 `int -> int`합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-406">Here “F# function types” mean “arrow” types like `int -> int`.</span></span>

<span data-ttu-id="236c2-407">문장을 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="236c2-407">Instead of this:</span></span>

```fsharp
member this.Transform(f:int->int) =
    ...
```

<span data-ttu-id="236c2-408">방법</span><span class="sxs-lookup"><span data-stu-id="236c2-408">Do this:</span></span>

```fsharp
member this.Transform(f:Func<int,int>) =
    ...
```

<span data-ttu-id="236c2-409">F # 함수 형식으로 나타납니다 `class FSharpFunc<T,U>` 다른.NET 언어 이며 대리자 형식을 이해 하는 언어 기능 및 도구에 대 한 덜 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-409">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understand delegate types.</span></span> <span data-ttu-id="236c2-410">.NET Framework 3.5 이상을 대상으로 하는 상위 기 메서드를 작성할 때는 `System.Func` 및 `System.Action` 대리자는.NET 개발자가 원활한 방식으로 이러한 Api를 사용할 수 있도록 게시 하려면 오른쪽 Api입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-410">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="236c2-411">(.NET Framework 2.0을 대상으로 지정 하는 경우 시스템에서 정의한 대리자 형식이 더 제한적 이며와 같은 미리 정의 된 대리자 유형을 사용 하 여 `System.Converter<T,U>` 하거나 특정 대리자 형식을 정의 합니다.)</span><span class="sxs-lookup"><span data-stu-id="236c2-411">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="236c2-412">긍 적 적인 측면에서.NET의 대리자는 F #에 대 한 자연-라이브러리 연결 (F #에 다음 섹션을 참조 하십시오.-연결 라이브러리)입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-412">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="236c2-413">더 높은 순서 메서드 바닐라.NET 라이브러리를 개발 하는 경우 일반적인 구현 전략을 처리할 수 있도록 모든 F # 함수 형식을 사용 하 여 구현 한 후 실제 F # 위에 씬 외관으로 대리자를 사용 하 여 공용 API를 만드는 결과적으로, 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-413">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="236c2-414">F # 옵션 값을 반환 하는 대신 TryGetValue 패턴을 사용 하 고 F # 옵션 값을 인수로 사용 하도록 메서드 오버 로드 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-414">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="236c2-415">Api에서 F # 옵션 종류를 위한 일반적인 패턴은 더 나은 바닐라에서 구현 된 표준.NET을 사용 하 여.NET Api 디자인 기술을 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-415">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="236c2-416">F # 옵션 값을 반환 하는 대신 bool 반환 형식 및 "TryGetValue" 패턴에서와 같이 out 매개 변수를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-416">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="236c2-417">및 F # 옵션 값을 매개 변수로 수행 하는 대신 메서드 오버 로드 또는 선택적 인수를 사용 하 여 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-417">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal : byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x : int, y : int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x : int) = x

member this.ParamOverload(x : int, y : int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="236c2-418">.NET 컬렉션 인터페이스를 사용 하 여 형식을 IEnumerable\<T\> 및 IDictionary\<키, 값\> 매개 변수 및 반환 값</span><span class="sxs-lookup"><span data-stu-id="236c2-418">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="236c2-419">.NET 배열과 같은 구체적 컬렉션 형식의 사용 하지 않도록 `T[]`, F # 형식 `list<T>`, `Map<Key,Value>` 및 `Set<T>`, 및와 같은.NET 구체적 컬렉션 형식은 `Dictionary<Key,Value>`합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-419">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="236c2-420">.NET 라이브러리 디자인 지침이 같은 다양 한 컬렉션 형식을 사용 하는 경우에 관한 좋은 조언 `IEnumerable<T>`합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-420">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="236c2-421">일부 배열 사용 (`T[]`) 성능 부 지에 따라에서 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-421">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="236c2-422">특히 `seq<T>` 은 방금 F #에 별칭이 `IEnumerable<T>`, 되어 있으므로 seq 종종 바닐라.NET API에 대 한 적절 한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-422">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="236c2-423">F #을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-423">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names : string list) =
    ...
```

<span data-ttu-id="236c2-424">F # 시퀀스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-424">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="236c2-425">0 인수 메서드를 정의 메서드의 유일한 입력된 유형으로의 단위 유형을 사용 하거나 유일한으로 void를 반환 하는 메서드를 정의 하는 형식 반환</span><span class="sxs-lookup"><span data-stu-id="236c2-425">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="236c2-426">단위 형식의 다른 곳에 사용을 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="236c2-426">Avoid other uses of the unit type.</span></span> <span data-ttu-id="236c2-427">다음은 좋은입니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-427">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

<span data-ttu-id="236c2-428">다음은 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-428">This is bad:</span></span>

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="236c2-429">바닐라.NET API 경계에 null 값을 확인</span><span class="sxs-lookup"><span data-stu-id="236c2-429">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="236c2-430">F # 구현 코드를 변경할 수 없는 디자인 패턴 및 F # 형식에 대 한 null 리터럴의 사용에 대 한 제한으로 인해 더 적은 null 값이 있는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-430">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="236c2-431">다른.NET 언어 종종 null 값 훨씬 더 자주 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-431">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="236c2-432">이 인해 바닐라.NET API를 공개 하는 F # 코드 API 경계에서 null에 대 한 매개 변수를 확인 하 고 F # 구현 코드를 더 깊은 흐름에서 이러한 값을 방지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-432">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="236c2-433">`isNull` 함수 또는에 패턴 일치는 `null` 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-433">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="236c2-434">튜플 반환 값으로 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="236c2-434">Avoid using tuples as return values</span></span>

<span data-ttu-id="236c2-435">대신, 데이터를 집계를 보유 하 고 있거나 out 매개 변수를 사용 하 여 여러 값을 반환 하는 명명 된 형식을 반환 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-435">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="236c2-436">한 구조체.NET에 있어도 (튜플 구조체에 대 한 C# 언어 지원과 포함)은 가장 많이 제공 하지 않습니다 이상적인 및 예상 되는 API.NET 개발자를 위한.</span><span class="sxs-lookup"><span data-stu-id="236c2-436">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="236c2-437">변환 매개 변수는 사용 하지</span><span class="sxs-lookup"><span data-stu-id="236c2-437">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="236c2-438">대신,.NET 호출 규칙을 사용 하 여 ``Method(arg1,arg2,…,argN)``합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-438">Instead, use .NET calling conventions ``Method(arg1,arg2,…,argN)``.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="236c2-439">팁: 모든.NET 언어에서 사용 하기 위해 라이브러리를 디자인 하는 경우 없기 맬웨어에 일부 실험적 C# 및 Visual Basic 프로그래밍 라이브러리 "느낌 오른쪽" 이러한 언어에서 충족 되도록 작업을 실제로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-439">Tip: If you’re designing libraries for use from any .NET language, then there’s no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="236c2-440">또한 Reflector.NET 및 Visual Studio 개체 브라우저와 같은 도구를 사용 하 여 라이브러리 및 해당 설명서 개발자에 게 예상 대로 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-440">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="236c2-441">부록</span><span class="sxs-lookup"><span data-stu-id="236c2-441">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="236c2-442">다른.NET 언어에서 사용 하기 위해 F # 코드를 디자인할 때의 종단 간 예제</span><span class="sxs-lookup"><span data-stu-id="236c2-442">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="236c2-443">다음 클래스를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="236c2-443">Consider the following class:</span></span>

```fsharp
open System

type Point1(angle,radius) =
    new() = Point1(angle=0.0, radius=0.0)
    member x.Angle = angle
    member x.Radius = radius
    member x.Stretch(l) = Point1(angle=x.Angle, radius=x.Radius * l)
    member x.Warp(f) = Point1(angle=f(x.Angle), radius=x.Radius)
    static member Circle(n) =
        [ for i in 1..n -> Point1(angle=2.0*Math.PI/float(n), radius=1.0) ]
```

<span data-ttu-id="236c2-444">이 클래스의 유추 된 F # 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-444">The inferred F# type of this class is as follows:</span></span>

```fsharp
type Point1 =
    new : unit -> Point1
    new : angle:double * radius:double -> Point1
    static member Circle : n:int -> Point1 list
    member Stretch : l:double -> Point1
    member Warp : f:(double -> double) -> Point1
    member Angle : double
    member Radius : double
```

<span data-ttu-id="236c2-445">F # 이와 다른.NET 언어를 사용 하 여 프로그래머에 표시 되는 방식을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-445">Let’s take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="236c2-446">예를 들어 대략적인 C# "서명"은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-446">For example, the approximate C# “signature” is as follows:</span></span>

```csharp
// C# signature for the unadjusted Point1 class
public class Point1
{
    public Point1();

    public Point1(double angle, double radius);

    public static Microsoft.FSharp.Collections.List<Point1> Circle(int count);

    public Point1 Stretch(double factor);

    public Point1 Warp(Microsoft.FSharp.Core.FastFunc<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

<span data-ttu-id="236c2-447">F # 나타내는 방법 구문 여기에서 주의 해야 할 몇 가지 중요 한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-447">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="236c2-448">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="236c2-448">For example:</span></span>

* <span data-ttu-id="236c2-449">인수 이름 같은 메타 데이터를 유지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-449">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="236c2-450">두 개의 인수를 사용 하는 F # 메서드로는 두 개의 인수를 사용 하는 C# 메서드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-450">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="236c2-451">함수 및 목록에는 F # 라이브러리 시그니처에 있는 해당 형식에 대 한 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-451">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="236c2-452">다음 코드에서는 이러한 것 들을 고려 하도록 하려면이 코드를 조정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-452">The following code shows how to adjust this code to take these things into account.</span></span>

```fsharp
namespace SuperDuperFSharpLibrary.Types

type RadialPoint(angle:double, radius:double) =

    /// Return a point at the origin
    new() = RadialPoint(angle=0.0, radius=0.0)

    /// The angle to the point, from the x-axis
    member x.Angle = angle

    /// The distance to the point, from the origin
    member x.Radius = radius

    /// Return a new point, with radius multiplied by the given factor
    member x.Stretch(factor) =
        RadialPoint(angle=angle, radius=radius * factor)

    /// Return a new point, with angle transformed by the function
    member x.Warp(transform:Func<_,_>) =
        RadialPoint(angle=transform.Invoke angle, radius=radius)

    /// Return a sequence of points describing an approximate circle using
    /// the given count of points
    static member Circle(count) =
        seq { for i in 1..count ->
                RadialPoint(angle=2.0*Math.PI/float(count), radius=1.0) }
```

<span data-ttu-id="236c2-453">코드의 유추 된 F # 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-453">The inferred F# type of the code is as follows:</span></span>

```fsharp
type RadialPoint =
    new : unit -> RadialPoint
    new : angle:double * radius:double -> RadialPoint
    static member Circle : count:int -> seq<RadialPoint>
    member Stretch : factor:double -> RadialPoint
    member Warp : transform:System.Func<double,double> -> RadialPoint
    member Angle : double
    member Radius : double
```

<span data-ttu-id="236c2-454">C# 시그니처는 이제 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-454">The C# signature is now as follows:</span></span>

```csharp
public class RadialPoint
{
    public RadialPoint();

    public RadialPoint(double angle, double radius);

    public static System.Collections.Generic.IEnumerable<RadialPoint> Circle(int count);

    public RadialPoint Stretch(double factor);

    public RadialPoint Warp(System.Func<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

<span data-ttu-id="236c2-455">바닐라.NET 라이브러리의 일부는 다음과 같이이 형식을 사용 하기 위해 준비 하는 수정 사항은 구성.</span><span class="sxs-lookup"><span data-stu-id="236c2-455">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="236c2-456">여러 개의 이름을 조정: `Point1`, `n`, `l`, 및 `f` 상태가 된 `RadialPoint`, `count`, `factor`, 및 `transform`각각.</span><span class="sxs-lookup"><span data-stu-id="236c2-456">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="236c2-457">반환 형식으로 사용 되는 `seq<RadialPoint>` 대신 `RadialPoint list` 변경 사용 하 여 목록을 생성 하 여 `[ ... ]` 를 사용 하 여 시퀀스 생성 `IEnumerable<RadialPoint>`합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-457">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="236c2-458">.NET 대리자 형식을 사용 `System.Func` F # 함수 형식 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-458">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="236c2-459">따라서 C# 코드에서 사용할 테 훨씬 더 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c2-459">This makes it far nicer to consume in C# code.</span></span>
