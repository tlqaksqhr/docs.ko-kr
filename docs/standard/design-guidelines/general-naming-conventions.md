---
title: 일반 명명 규칙
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], conflicts
- type names, conflicts
- language-specific type names
- names [.NET Framework], about naming guidelines
- names [.NET Framework], abbreviations
- abbreviation naming guidelines
- acronym naming guidelines
- Hungarian notation
- names [.NET Framework], type names
- names [.NET Framework], acronyms
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 207227b3e5c52b7c6e0f704543379874f3708c03
ms.sourcegitcommit: ceca5a1c027627abcca2767567703c3879f33325
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2018
ms.locfileid: "36338106"
---
# <a name="general-naming-conventions"></a><span data-ttu-id="8f9a2-102">일반 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="8f9a2-102">General Naming Conventions</span></span>
<span data-ttu-id="8f9a2-103">이 섹션에서는 일반 명명 규칙 단어 선택 관련 된 약어 및 머리글자어 및 권장 사항을 사용 하 여 언어별 이름을 사용 하지 않도록 하는 방법에 대 한 지침을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-103">This section describes general naming conventions that relate to word choice, guidelines on using abbreviations and acronyms, and recommendations on how to avoid using language-specific names.</span></span>  
  
## <a name="word-choice"></a><span data-ttu-id="8f9a2-104">단어 선택</span><span class="sxs-lookup"><span data-stu-id="8f9a2-104">Word Choice</span></span>  
 <span data-ttu-id="8f9a2-105">**✓ DO** 쉽게 읽을 수 있는 식별자 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-105">**✓ DO** choose easily readable identifier names.</span></span>  
  
 <span data-ttu-id="8f9a2-106">예를 들어 라는 속성이 `HorizontalAlignment` 는 영어-읽기 쉬운 `AlignmentHorizontal`합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-106">For example, a property named `HorizontalAlignment` is more English-readable than `AlignmentHorizontal`.</span></span>  
  
 <span data-ttu-id="8f9a2-107">**✓ DO** 가독성 간결한 설명을 위해 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-107">**✓ DO** favor readability over brevity.</span></span>  
  
 <span data-ttu-id="8f9a2-108">속성 이름 `CanScrollHorizontally` 더 좋은 것은 `ScrollableX` (x 축에는 그 보다 모호해 참조).</span><span class="sxs-lookup"><span data-stu-id="8f9a2-108">The property name `CanScrollHorizontally` is better than `ScrollableX` (an obscure reference to the X-axis).</span></span>  
  
 <span data-ttu-id="8f9a2-109">**X DO NOT** 밑줄, 하이픈 또는 기타 영숫자가 아닌 문자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-109">**X DO NOT** use underscores, hyphens, or any other nonalphanumeric characters.</span></span>  
  
 <span data-ttu-id="8f9a2-110">**X DO NOT** 헝가리 식 표기법을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-110">**X DO NOT** use Hungarian notation.</span></span>  
  
 <span data-ttu-id="8f9a2-111">**X AVOID** 널리의 키워드와 충돌 하는 식별자를 사용 하 여 프로그래밍 언어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-111">**X AVOID** using identifiers that conflict with keywords of widely used programming languages.</span></span>  
  
 <span data-ttu-id="8f9a2-112">규칙 4의는 CLS 공용 언어 사양 ()에 따라 규정을 준수 하는 모든 언어는 해당 언어의 키워드를 식별자로 사용 하는 명명 된 항목에 액세스할 수 있는 메커니즘을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-112">According to Rule 4 of the Common Language Specification (CLS), all compliant languages must provide a mechanism that allows access to named items that use a keyword of that language as an identifier.</span></span> <span data-ttu-id="8f9a2-113">C#, 예를 들어, 사용 하는 @ 기호가 경우에서 이스케이프 메커니즘으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-113">C#, for example, uses the @ sign as an escape mechanism in this case.</span></span> <span data-ttu-id="8f9a2-114">그러나 메서드를 사용 하는 이스케이프 시퀀스 없이 1 보다 훨씬 더 어렵기 때문에 일반적인 키워드를 방지 하는 여전히 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-114">However, it is still a good idea to avoid common keywords because it is much more difficult to use a method with the escape sequence than one without it.</span></span>  
  
## <a name="using-abbreviations-and-acronyms"></a><span data-ttu-id="8f9a2-115">머리 글자어와 약어를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="8f9a2-115">Using Abbreviations and Acronyms</span></span>  
 <span data-ttu-id="8f9a2-116">**X DO NOT** 식별자 이름의 일부로 약어 또는 축약을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-116">**X DO NOT** use abbreviations or contractions as part of identifier names.</span></span>  
  
 <span data-ttu-id="8f9a2-117">사용 예를 들어 `GetWindow` 대신 `GetWin`합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-117">For example, use `GetWindow` rather than `GetWin`.</span></span>  
  
 <span data-ttu-id="8f9a2-118">**X DO NOT** 폭넓게 활용 되 고 필요한 경우에 있는 경우에 하지 않은 머리글자어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-118">**X DO NOT** use any acronyms that are not widely accepted, and even if they are, only when necessary.</span></span>  
  
## <a name="avoiding-language-specific-names"></a><span data-ttu-id="8f9a2-119">언어 관련 이름 방지</span><span class="sxs-lookup"><span data-stu-id="8f9a2-119">Avoiding Language-Specific Names</span></span>  
 <span data-ttu-id="8f9a2-120">**✓ DO** 형식 이름에 대 한 언어별 키워드 보다는 특별 한 의미가 있는 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-120">**✓ DO** use semantically interesting names rather than language-specific keywords for type names.</span></span>  
  
 <span data-ttu-id="8f9a2-121">예를 들어 `GetLength` 보다 더 나은 이름인 `GetInt`합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-121">For example, `GetLength` is a better name than `GetInt`.</span></span>  
  
 <span data-ttu-id="8f9a2-122">**✓ DO** 드문 경우 식별자 의미가 없는 해당 형식 이상의 때의 언어 관련 이름 대신 일반 CLR 형식 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-122">**✓ DO** use a generic CLR type name, rather than a language-specific name, in the rare cases when an identifier has no semantic meaning beyond its type.</span></span>  
  
 <span data-ttu-id="8f9a2-123">예를 들어를 변환 하는 메서드 <xref:System.Int64> 명명할 `ToInt64`이 아니라 `ToLong` (때문에 <xref:System.Int64> C#에 대 한 CLR 이름이-특정 별칭 `long`).</span><span class="sxs-lookup"><span data-stu-id="8f9a2-123">For example, a method converting to <xref:System.Int64> should be named `ToInt64`, not `ToLong` (because <xref:System.Int64> is a CLR name for the C#-specific alias `long`).</span></span> <span data-ttu-id="8f9a2-124">다음 표에서 CLR 형식 이름 (뿐만 아니라 해당 하는 유형 이름을 C#, Visual Basic 및 c + +)를 사용 하 여 몇 가지 기본 데이터 형식을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-124">The following table presents several base data types using the CLR type names (as well as the corresponding type names for C#, Visual Basic, and C++).</span></span>  
  
|<span data-ttu-id="8f9a2-125">C#</span><span class="sxs-lookup"><span data-stu-id="8f9a2-125">C#</span></span>|<span data-ttu-id="8f9a2-126">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8f9a2-126">Visual Basic</span></span>|<span data-ttu-id="8f9a2-127">C++</span><span class="sxs-lookup"><span data-stu-id="8f9a2-127">C++</span></span>|<span data-ttu-id="8f9a2-128">CLR</span><span class="sxs-lookup"><span data-stu-id="8f9a2-128">CLR</span></span>|  
|---------|------------------|-----------|---------|  
|<span data-ttu-id="8f9a2-129">**sbyte**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-129">**sbyte**</span></span>|<span data-ttu-id="8f9a2-130">**SByte**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-130">**SByte**</span></span>|<span data-ttu-id="8f9a2-131">**char**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-131">**char**</span></span>|<span data-ttu-id="8f9a2-132">**SByte**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-132">**SByte**</span></span>|  
|<span data-ttu-id="8f9a2-133">**byte**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-133">**byte**</span></span>|<span data-ttu-id="8f9a2-134">**Byte**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-134">**Byte**</span></span>|<span data-ttu-id="8f9a2-135">**unsigned char**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-135">**unsigned char**</span></span>|<span data-ttu-id="8f9a2-136">**Byte**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-136">**Byte**</span></span>|  
|<span data-ttu-id="8f9a2-137">**short**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-137">**short**</span></span>|<span data-ttu-id="8f9a2-138">**Short**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-138">**Short**</span></span>|<span data-ttu-id="8f9a2-139">**short**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-139">**short**</span></span>|<span data-ttu-id="8f9a2-140">**Int16**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-140">**Int16**</span></span>|  
|<span data-ttu-id="8f9a2-141">**ushort**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-141">**ushort**</span></span>|<span data-ttu-id="8f9a2-142">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-142">**UInt16**</span></span>|<span data-ttu-id="8f9a2-143">**unsigned short**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-143">**unsigned short**</span></span>|<span data-ttu-id="8f9a2-144">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-144">**UInt16**</span></span>|  
|<span data-ttu-id="8f9a2-145">**int**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-145">**int**</span></span>|<span data-ttu-id="8f9a2-146">**Integer**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-146">**Integer**</span></span>|<span data-ttu-id="8f9a2-147">**int**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-147">**int**</span></span>|<span data-ttu-id="8f9a2-148">**Int32**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-148">**Int32**</span></span>|  
|<span data-ttu-id="8f9a2-149">**uint**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-149">**uint**</span></span>|<span data-ttu-id="8f9a2-150">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-150">**UInt32**</span></span>|<span data-ttu-id="8f9a2-151">**unsigned int**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-151">**unsigned int**</span></span>|<span data-ttu-id="8f9a2-152">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-152">**UInt32**</span></span>|  
|<span data-ttu-id="8f9a2-153">**long**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-153">**long**</span></span>|<span data-ttu-id="8f9a2-154">**Long**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-154">**Long**</span></span>|<span data-ttu-id="8f9a2-155">**__int64**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-155">**__int64**</span></span>|<span data-ttu-id="8f9a2-156">**Int64**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-156">**Int64**</span></span>|  
|<span data-ttu-id="8f9a2-157">**ulong**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-157">**ulong**</span></span>|<span data-ttu-id="8f9a2-158">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-158">**UInt64**</span></span>|<span data-ttu-id="8f9a2-159">**unsigned __int64**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-159">**unsigned __int64**</span></span>|<span data-ttu-id="8f9a2-160">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-160">**UInt64**</span></span>|  
|<span data-ttu-id="8f9a2-161">**float**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-161">**float**</span></span>|<span data-ttu-id="8f9a2-162">**Single**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-162">**Single**</span></span>|<span data-ttu-id="8f9a2-163">**float**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-163">**float**</span></span>|<span data-ttu-id="8f9a2-164">**Single**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-164">**Single**</span></span>|  
|<span data-ttu-id="8f9a2-165">**double**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-165">**double**</span></span>|<span data-ttu-id="8f9a2-166">**Double**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-166">**Double**</span></span>|<span data-ttu-id="8f9a2-167">**double**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-167">**double**</span></span>|<span data-ttu-id="8f9a2-168">**Double**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-168">**Double**</span></span>|  
|<span data-ttu-id="8f9a2-169">**bool**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-169">**bool**</span></span>|<span data-ttu-id="8f9a2-170">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-170">**Boolean**</span></span>|<span data-ttu-id="8f9a2-171">**bool**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-171">**bool**</span></span>|<span data-ttu-id="8f9a2-172">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-172">**Boolean**</span></span>|  
|<span data-ttu-id="8f9a2-173">**char**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-173">**char**</span></span>|<span data-ttu-id="8f9a2-174">**Char**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-174">**Char**</span></span>|<span data-ttu-id="8f9a2-175">**wchar_t**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-175">**wchar_t**</span></span>|<span data-ttu-id="8f9a2-176">**Char**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-176">**Char**</span></span>|  
|<span data-ttu-id="8f9a2-177">**string**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-177">**string**</span></span>|<span data-ttu-id="8f9a2-178">**String**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-178">**String**</span></span>|<span data-ttu-id="8f9a2-179">**String**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-179">**String**</span></span>|<span data-ttu-id="8f9a2-180">**String**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-180">**String**</span></span>|  
|<span data-ttu-id="8f9a2-181">**object**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-181">**object**</span></span>|<span data-ttu-id="8f9a2-182">**개체**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-182">**Object**</span></span>|<span data-ttu-id="8f9a2-183">**개체**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-183">**Object**</span></span>|<span data-ttu-id="8f9a2-184">**개체**</span><span class="sxs-lookup"><span data-stu-id="8f9a2-184">**Object**</span></span>|  
  
 <span data-ttu-id="8f9a2-185">**✓ DO** 와 같은 일반 이름을 사용 하 여 `value` 또는 `item`, 형식 이름 식별자 의미가 없는 및 매개 변수의 형식이 중요 하지 않은 경우 드문 경우에서를 반복할 필요 없이 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-185">**✓ DO**  use a common name, such as `value` or `item`, rather than repeating the type name, in the rare cases when an identifier has no semantic meaning and the type of the parameter is not important.</span></span>  
  
## <a name="naming-new-versions-of-existing-apis"></a><span data-ttu-id="8f9a2-186">새 버전 기존 Api의 이름 지정</span><span class="sxs-lookup"><span data-stu-id="8f9a2-186">Naming New Versions of Existing APIs</span></span>  
 <span data-ttu-id="8f9a2-187">**✓ DO** 기존 API의 새 버전을 만들 때 기존 API와 유사한 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-187">**✓ DO** use a name similar to the old API when creating new versions of an existing API.</span></span>  
  
 <span data-ttu-id="8f9a2-188">이렇게 하면 Api 간의 관계를 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-188">This helps to highlight the relationship between the APIs.</span></span>  
  
 <span data-ttu-id="8f9a2-189">**✓ DO** 선호 기존 API의 새 버전을 나타내는 접두사 보다는 접미사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-189">**✓ DO** prefer adding a suffix rather than a prefix to indicate a new version of an existing API.</span></span>  
  
 <span data-ttu-id="8f9a2-190">이 설명서를 검색할 때 검색 도움이 또는 IntelliSense를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-190">This will assist discovery when browsing documentation, or using IntelliSense.</span></span> <span data-ttu-id="8f9a2-191">대부분의 브라우저와 IntelliSense 식별자 사전순으로 표시 되므로 새로운 Api에 가까운 이전 버전의 API 구성할 수 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-191">The old version of the API will be organized close to the new APIs, because most browsers and IntelliSense show identifiers in alphabetical order.</span></span>  
  
 <span data-ttu-id="8f9a2-192">**✓ CONSIDER** 접두사 또는 접미사를 추가 하는 대신 새로운, 하지만 의미 있는 식별자를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-192">**✓ CONSIDER** using a brand new, but meaningful identifier, instead of adding a suffix or a prefix.</span></span>  
  
 <span data-ttu-id="8f9a2-193">**✓ DO** 특히 API의 기존 이름이 경우 (즉,이 산업 표준) 쉽게 알아볼 수 있는 유일한 이름이 어떤 의미 있는 추가 하는 경우 접미사 (또는 이름을 변경) 되지 않은 경우 응용 프로그램에 기존 API의 새 버전을 나타내기 위해 숫자 접미사를 사용 합니다. ropriate 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-193">**✓ DO** use a numeric suffix to indicate a new version of an existing API, particularly if the existing name of the API is the only name that makes sense (i.e., if it is an industry standard) and if adding any meaningful suffix (or changing the name) is not an appropriate option.</span></span>  
  
 <span data-ttu-id="8f9a2-194">**X DO NOT** "Ex" (또는 유사한)를 사용 하 여 이전 버전의 동일한 API와 구분 식별자에 대 한 접미사입니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-194">**X DO NOT** use the "Ex" (or a similar) suffix for an identifier to distinguish it from an earlier version of the same API.</span></span>  
  
 <span data-ttu-id="8f9a2-195">**✓ DO** 32 비트 정수 대신 64 비트 정수 (long 정수)에서 작동 하는 Api의 버전을 도입할 때 "64" 접미사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-195">**✓ DO** use the "64" suffix when introducing versions of APIs that operate on a 64-bit integer (a long integer) instead of a 32-bit integer.</span></span> <span data-ttu-id="8f9a2-196">기존 32 비트 API 있으면;이 접근 해야 64 비트 버전을 사용 하 여 새 Api에 대 한 수행 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8f9a2-196">You only need to take this approach when the existing 32-bit API exists; don’t do it for brand new APIs with only a 64-bit version.</span></span>  
  
 <span data-ttu-id="8f9a2-197">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="8f9a2-197">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8f9a2-198">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="8f9a2-198">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f9a2-199">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f9a2-199">See Also</span></span>  
 [<span data-ttu-id="8f9a2-200">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="8f9a2-200">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="8f9a2-201">명명 지침</span><span class="sxs-lookup"><span data-stu-id="8f9a2-201">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
