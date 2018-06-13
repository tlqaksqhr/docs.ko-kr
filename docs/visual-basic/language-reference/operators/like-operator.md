---
title: Like 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Like
- vb.Like
helpviewer_keywords:
- similar to
- pattern matching
- Like operator [Visual Basic]
- '? symbol, wildcard character'
- string comparison [Visual Basic], Like operator
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- symbols, wildcard
- wildcards, Like operator
- strings [Visual Basic], matching
- string comparison [Visual Basic], sorting data
- data [Visual Basic], sorting
- text [Visual Basic], comparing
- operators [Visual Basic], pattern-matching
- data [Visual Basic], string comparisons
- string comparison [Visual Basic], Like operators
ms.assetid: 966283ec-80e2-4294-baa8-c75baff804f9
ms.openlocfilehash: a9c672a397510c69c9ee67358689feff80d8831a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605422"
---
# <a name="like-operator-visual-basic"></a><span data-ttu-id="a03fb-102">Like 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a03fb-102">Like Operator (Visual Basic)</span></span>
<span data-ttu-id="a03fb-103">문자열을 패턴과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-103">Compares a string against a pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a03fb-104">구문</span><span class="sxs-lookup"><span data-stu-id="a03fb-104">Syntax</span></span>  
  
```  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="a03fb-105">요소</span><span class="sxs-lookup"><span data-stu-id="a03fb-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="a03fb-106">필수.</span><span class="sxs-lookup"><span data-stu-id="a03fb-106">Required.</span></span> <span data-ttu-id="a03fb-107">모든 `Boolean` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-107">Any `Boolean` variable.</span></span> <span data-ttu-id="a03fb-108">결과 한 `Boolean` 나타내는 값 여부는 `string` 충족는 `pattern`합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-108">The result is a `Boolean` value indicating whether or not the `string` satisfies the `pattern`.</span></span>  
  
 `string`  
 <span data-ttu-id="a03fb-109">필수.</span><span class="sxs-lookup"><span data-stu-id="a03fb-109">Required.</span></span> <span data-ttu-id="a03fb-110">임의의 `String` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-110">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="a03fb-111">필수.</span><span class="sxs-lookup"><span data-stu-id="a03fb-111">Required.</span></span> <span data-ttu-id="a03fb-112">모든 `String` "주의"에 설명 된 패턴 일치 규칙에 맞는 식</span><span class="sxs-lookup"><span data-stu-id="a03fb-112">Any `String` expression conforming to the pattern-matching conventions described in "Remarks."</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a03fb-113">설명</span><span class="sxs-lookup"><span data-stu-id="a03fb-113">Remarks</span></span>  
 <span data-ttu-id="a03fb-114">경우에 값 `string` 에 포함 된 패턴을 충족 `pattern`, `result` 은 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-114">If the value in `string` satisfies the pattern contained in `pattern`, `result` is `True`.</span></span> <span data-ttu-id="a03fb-115">문자열 패턴을 충족 하지 못하는 경우 `result` 은 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-115">If the string does not satisfy the pattern, `result` is `False`.</span></span> <span data-ttu-id="a03fb-116">두 `string` 및 `pattern` 빈 문자열이 결과 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-116">If both `string` and `pattern` are empty strings, the result is `True`.</span></span>  
  
## <a name="comparison-method"></a><span data-ttu-id="a03fb-117">비교 메서드</span><span class="sxs-lookup"><span data-stu-id="a03fb-117">Comparison Method</span></span>  
 <span data-ttu-id="a03fb-118">동작은 `Like` 연산자에 따라 달라 집니다는 [옵션 비교 문](../../../visual-basic/language-reference/statements/option-compare-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-118">The behavior of the `Like` operator depends on the [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span> <span data-ttu-id="a03fb-119">각 소스 파일에 대 한 기본 문자열 비교 메서드는 `Option Compare Binary`합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-119">The default string comparison method for each source file is `Option Compare Binary`.</span></span>  
  
## <a name="pattern-options"></a><span data-ttu-id="a03fb-120">패턴 옵션</span><span class="sxs-lookup"><span data-stu-id="a03fb-120">Pattern Options</span></span>  
 <span data-ttu-id="a03fb-121">기본 제공 패턴 일치 문자열 비교에 유용한 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-121">Built-in pattern matching provides a versatile tool for string comparisons.</span></span> <span data-ttu-id="a03fb-122">패턴 일치 기능을 사용 하면 각 문자에 맞게 `string` 특정 문자, 와일드 카드 문자, 문자 목록, 또는 문자 범위에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-122">The pattern-matching features allow you to match each character in `string` against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="a03fb-123">다음 표에서 허용 되는 문자를 보여 줍니다. `pattern` 일치 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-123">The following table shows the characters allowed in `pattern` and what they match.</span></span>  
  
|<span data-ttu-id="a03fb-124">문자 `pattern`</span><span class="sxs-lookup"><span data-stu-id="a03fb-124">Characters in `pattern`</span></span>|<span data-ttu-id="a03fb-125">에 일치 하는 `string`</span><span class="sxs-lookup"><span data-stu-id="a03fb-125">Matches in `string`</span></span>|  
|-----------------------------|-------------------------|  
|`?`|<span data-ttu-id="a03fb-126">단일 문자</span><span class="sxs-lookup"><span data-stu-id="a03fb-126">Any single character</span></span>|  
|`*`|<span data-ttu-id="a03fb-127">0 개 이상의 문자</span><span class="sxs-lookup"><span data-stu-id="a03fb-127">Zero or more characters</span></span>|  
|`#`|<span data-ttu-id="a03fb-128">임의의 단일 숫자 (0-9)</span><span class="sxs-lookup"><span data-stu-id="a03fb-128">Any single digit (0–9)</span></span>|  
|`[charlist]`|<span data-ttu-id="a03fb-129">단일 문자 `charlist`</span><span class="sxs-lookup"><span data-stu-id="a03fb-129">Any single character in `charlist`</span></span>|  
|`[!charlist]`|<span data-ttu-id="a03fb-130">에 없는 모든 단일 문자 `charlist`</span><span class="sxs-lookup"><span data-stu-id="a03fb-130">Any single character not in `charlist`</span></span>|  
  
## <a name="character-lists"></a><span data-ttu-id="a03fb-131">문자 목록</span><span class="sxs-lookup"><span data-stu-id="a03fb-131">Character Lists</span></span>  
 <span data-ttu-id="a03fb-132">하나 이상의 문자 그룹 (`charlist`) 대괄호로 묶은 (`[ ]`)는 내 임의의 단일 문자와 일치 하는 데 사용할 수 `string` 숫자를 포함 하 여 거의 모든 문자 코드를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-132">A group of one or more characters (`charlist`) enclosed in brackets (`[ ]`) can be used to match any single character in `string` and can include almost any character code, including digits.</span></span>  
  
 <span data-ttu-id="a03fb-133">느낌표 (`!`) 맨 앞에 `charlist` 경우의 문자를 제외한 모든 문자는 일치 하는 내용을 의미 `charlist` 에 `string`합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-133">An exclamation point (`!`) at the beginning of `charlist` means that a match is made if any character except the characters in `charlist` is found in `string`.</span></span> <span data-ttu-id="a03fb-134">를 대괄호 외부에서 사용 하는 경우 자체에서 느낌표를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-134">When used outside brackets, the exclamation point matches itself.</span></span>  
  
## <a name="special-characters"></a><span data-ttu-id="a03fb-135">특수 문자</span><span class="sxs-lookup"><span data-stu-id="a03fb-135">Special Characters</span></span>  
 <span data-ttu-id="a03fb-136">특수 문자 왼쪽된 대괄호에 맞게 (`[`), 물음표 (`?`), 숫자 기호 (`#`), 별표 (`*`), 대괄호로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-136">To match the special characters left bracket (`[`), question mark (`?`), number sign (`#`), and asterisk (`*`), enclose them in brackets.</span></span> <span data-ttu-id="a03fb-137">오른쪽 대괄호 (`]`) 자신과 일치 하는 그룹 내에서 사용할 수 없습니다 되지만 개별 문자로 그룹 외부에 있는 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-137">The right bracket (`]`) cannot be used within a group to match itself, but it can be used outside a group as an individual character.</span></span>  
  
 <span data-ttu-id="a03fb-138">문자 시퀀스 `[]` 길이가 0 인 문자열로 간주 됩니다 (`""`).</span><span class="sxs-lookup"><span data-stu-id="a03fb-138">The character sequence `[]` is considered a zero-length string (`""`).</span></span> <span data-ttu-id="a03fb-139">그러나 대괄호로 묶은 문자 목록의 일부가 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-139">However, it cannot be part of a character list enclosed in brackets.</span></span> <span data-ttu-id="a03fb-140">에 위치 하는지 여부를 확인 하려는 경우 `string` 하나가 포함 된 문자 또는 모두에 문자가 그룹에서 사용할 수 있습니다 `Like` 두 번입니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-140">If you want to check whether a position in `string` contains one of a group of characters or no character at all, you can use `Like` twice.</span></span> <span data-ttu-id="a03fb-141">예를 들어 참조 [하는 방법: 패턴에 대해 문자열](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-141">For an example, see [How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span></span>  
  
## <a name="character-ranges"></a><span data-ttu-id="a03fb-142">문자 범위</span><span class="sxs-lookup"><span data-stu-id="a03fb-142">Character Ranges</span></span>  
 <span data-ttu-id="a03fb-143">하이픈을 사용 하 여 (`–`)를 하 한과 상한을 범위를 구분 하려면 `charlist` 문자 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-143">By using a hyphen (`–`) to separate the lower and upper bounds of the range, `charlist` can specify a range of characters.</span></span> <span data-ttu-id="a03fb-144">예를 들어 `[A–Z]` 해당 문자에 위치 하는 경우 일치 결과가 `string` 범위 내 모든 문자를 포함 `A`–`Z`, 및 `[!H–L]` 해당 문자 위치 하는 경우에 일치 하는 항목에 발생 합니다. 범위 밖에 있는 경우 모든 문자를 포함 `H`–`L`합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-144">For example, `[A–Z]` results in a match if the corresponding character position in `string` contains any character within the range `A`–`Z`, and `[!H–L]` results in a match if the corresponding character position contains any character outside the range `H`–`L`.</span></span>  
  
 <span data-ttu-id="a03fb-145">문자 범위를 지정 하면 오름차순 정렬 순서, 즉, 오름차순으로 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-145">When you specify a range of characters, they must appear in ascending sort order, that is, from lowest to highest.</span></span> <span data-ttu-id="a03fb-146">따라서 `[A–Z]` 올바른 패턴은 있지만 `[Z–A]` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-146">Thus, `[A–Z]` is a valid pattern, but `[Z–A]` is not.</span></span>  
  
### <a name="multiple-character-ranges"></a><span data-ttu-id="a03fb-147">여러 문자 범위</span><span class="sxs-lookup"><span data-stu-id="a03fb-147">Multiple Character Ranges</span></span>  
 <span data-ttu-id="a03fb-148">동일한 문자 위치에 대 한 여러 범위를 지정 하려면 대괄호 구분 기호 없이 내에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-148">To specify multiple ranges for the same character position, put them within the same brackets without delimiters.</span></span> <span data-ttu-id="a03fb-149">예를 들어 `[A–CX–Z]` 해당 문자에 위치 하는 경우 일치 결과가 `string` 중 하나가 범위 내 모든 문자를 포함 `A`–`C` 또는 범위의 `X`–`Z`합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-149">For example, `[A–CX–Z]` results in a match if the corresponding character position in `string` contains any character within either the range `A`–`C` or the range `X`–`Z`.</span></span>  
  
### <a name="usage-of-the-hyphen"></a><span data-ttu-id="a03fb-150">하이픈 사용</span><span class="sxs-lookup"><span data-stu-id="a03fb-150">Usage of the Hyphen</span></span>  
 <span data-ttu-id="a03fb-151">하이픈 (`–`) (느낌표, 있는 경우) 한 후 시작 또는 끝날 때 나타날 수 있습니다 `charlist` 자체와 일치 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-151">A hyphen (`–`) can appear either at the beginning (after an exclamation point, if any) or at the end of `charlist` to match itself.</span></span> <span data-ttu-id="a03fb-152">다른 위치에 있는 하이픈 문자를 하이픈의 어느 쪽에 있는 문자의 범위를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-152">In any other location, the hyphen identifies a range of characters delimited by the characters on either side of the hyphen.</span></span>  
  
## <a name="collating-sequence"></a><span data-ttu-id="a03fb-153">데이터 정렬 순서</span><span class="sxs-lookup"><span data-stu-id="a03fb-153">Collating Sequence</span></span>  
 <span data-ttu-id="a03fb-154">지정 된 범위의 의미 문자에서 런타임에 의해 결정 된 순서에 따라 달라 집니다 `Option``Compare` 시스템의 로캘 설정 코드에서 실행 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-154">The meaning of a specified range depends on the character ordering at run time, as determined by `Option``Compare` and the locale setting of the system the code is running on.</span></span> <span data-ttu-id="a03fb-155">와 `Option``Compare``Binary`, 범위 `[A–E]` 일치 `A`, `B`, `C`, `D`, 및 `E`합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-155">With `Option``Compare``Binary`, the range `[A–E]` matches `A`, `B`, `C`, `D`, and `E`.</span></span> <span data-ttu-id="a03fb-156">와 `Option``Compare``Text`, `[A–E]` 일치 `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, 및 `e`합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-156">With `Option``Compare``Text`, `[A–E]` matches `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, and `e`.</span></span> <span data-ttu-id="a03fb-157">범위 일치 하지 않습니다. `Ê` 또는 `ê` 악센트 문자 악센트가 없는 문자 정렬 순서에서 다음 collate 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-157">The range does not match `Ê` or `ê` because accented characters collate after unaccented characters in the sort order.</span></span>  
  
## <a name="digraph-characters"></a><span data-ttu-id="a03fb-158">Digraph 문자</span><span class="sxs-lookup"><span data-stu-id="a03fb-158">Digraph Characters</span></span>  
 <span data-ttu-id="a03fb-159">일부 언어에서 두 개의 별도 문자를 나타내는 알파벳 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-159">In some languages, there are alphabetic characters that represent two separate characters.</span></span> <span data-ttu-id="a03fb-160">여러 언어 문자를 사용 하는 예를 들어 `æ` 문자를 나타내는 `a` 및 `e` 함께 표시 되는 경우.</span><span class="sxs-lookup"><span data-stu-id="a03fb-160">For example, several languages use the character `æ` to represent the characters `a` and `e` when they appear together.</span></span> <span data-ttu-id="a03fb-161">`Like` 연산자 인식 digraph 문자 및 두 개의 개별 문자는 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-161">The `Like` operator recognizes that the single digraph character and the two individual characters are equivalent.</span></span>  
  
 <span data-ttu-id="a03fb-162">Digraph 문자 중 하나에 있는 경우, digraph 문자를 사용 하는 언어 시스템 로캘 설정에 지정 된 경우 `pattern` 또는 `string` 다른 문자열에 해당 하는 두 문자 시퀀스와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-162">When a language that uses a digraph character is specified in the system locale settings, an occurrence of the single digraph character in either `pattern` or `string` matches the equivalent two-character sequence in the other string.</span></span> <span data-ttu-id="a03fb-163">마찬가지로,의 digraph 문자 `pattern` 대괄호로 묶은 자체적으로, 목록, 또는 범위에 해당 하는 두 문자 시퀀스와 일치 `string`합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-163">Similarly, a digraph character in `pattern` enclosed in brackets (by itself, in a list, or in a range) matches the equivalent two-character sequence in `string`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a03fb-164">오버로딩</span><span class="sxs-lookup"><span data-stu-id="a03fb-164">Overloading</span></span>  
 <span data-ttu-id="a03fb-165">`Like` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-165">The `Like` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a03fb-166">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-166">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a03fb-167">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-167">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a03fb-168">예제</span><span class="sxs-lookup"><span data-stu-id="a03fb-168">Example</span></span>  
 <span data-ttu-id="a03fb-169">사용 하 여이 예제는 `Like` 다양 한 패턴 문자열을 비교 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-169">This example uses the `Like` operator to compare strings to various patterns.</span></span> <span data-ttu-id="a03fb-170">결과 다루지는 `Boolean` 각 문자열 패턴을 충족 하는지 여부를 나타내는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a03fb-170">The results go into a `Boolean` variable indicating whether each string satisfies the pattern.</span></span>  
  
 [!code-vb[VbVbalrOperators#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/like-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a03fb-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a03fb-171">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>  
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>  
 [<span data-ttu-id="a03fb-172">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="a03fb-172">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="a03fb-173">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="a03fb-173">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="a03fb-174">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="a03fb-174">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="a03fb-175">Option Compare 문</span><span class="sxs-lookup"><span data-stu-id="a03fb-175">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="a03fb-176">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="a03fb-176">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="a03fb-177">방법: 패턴에 대해 문자열 비교</span><span class="sxs-lookup"><span data-stu-id="a03fb-177">How to: Match a String against a Pattern</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
