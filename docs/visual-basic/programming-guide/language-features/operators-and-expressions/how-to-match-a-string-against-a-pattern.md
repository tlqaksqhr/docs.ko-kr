---
title: "방법: 패턴에 대해 문자열 비교(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- pattern matching
- strings [Visual Basic], comparing
- string comparison [Visual Basic], operators
- Visual Basic code, operators
- pattern matching [Visual Basic], string comparison
- string comparison [Visual Basic]
- Like operator [Visual Basic], pattern matching
- pattern matching, empty strings
- operators [Visual Basic], comparison
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83433bdb41df0ce40d0979f3f44603f10ba1c7d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="c09f7-102">방법: 패턴에 대해 문자열 비교(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c09f7-102">How to: Match a String against a Pattern (Visual Basic)</span></span>
<span data-ttu-id="c09f7-103">식을 확인 하려는 경우는 [문자열 데이터 형식](../../../../visual-basic/language-reference/data-types/string-data-type.md) 사용 하 여 패턴을 만족는 [Like 연산자](../../../../visual-basic/language-reference/operators/like-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
 <span data-ttu-id="c09f7-104">`Like`두 개의 피연산자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-104">`Like` takes two operands.</span></span> <span data-ttu-id="c09f7-105">왼쪽된 피연산자가 문자열 식 및 오른쪽 피연산자는 일치 하는 데 사용할 패턴을 포함 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="c09f7-106">`Like`반환 된 `Boolean` 문자열 식의 패턴을 충족 하는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>  
  
 <span data-ttu-id="c09f7-107">특정 문자, 와일드 카드 문자, 문자 목록, 또는 문자 범위에서 문자열 식의 각 문자를 일치 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="c09f7-108">패턴 문자열에 지정 된 위치는 문자열 식에 일치 시킬 문자 위치에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="c09f7-109">특정 문자는 문자열 식의 문자를 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="c09f7-109">To match a character in the string expression against a specific character</span></span>  
  
-   <span data-ttu-id="c09f7-110">직접 패턴 문자열에에서 특정 문자를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="c09f7-111">특수 문자를 대괄호로 묶어야 합니다 (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="c09f7-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="c09f7-112">자세한 내용은 참조 [Like 연산자](../../../../visual-basic/language-reference/operators/like-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
     <span data-ttu-id="c09f7-113">다음 예에서는 테스트 여부 `myString` 단일 문자를 정확 하 게 이루어져 `H`합니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>  
  
     [!code-vb[VbVbalrOperators#70](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_1.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="c09f7-114">와일드 카드 문자는 문자열 식의 문자를 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="c09f7-114">To match a character in the string expression against a wildcard character</span></span>  
  
-   <span data-ttu-id="c09f7-115">물음표 (`?`) 패턴 문자열에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="c09f7-116">이 위치에 있는 유효한 문자가 일치를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-116">Any valid character in this position makes a successful match.</span></span>  
  
     <span data-ttu-id="c09f7-117">다음 예제에서는 테스트 여부 `myString` 단일 문자 `W` 모든 값에 정확히 두 개의 문자로 이어지는 합니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>  
  
     [!code-vb[VbVbalrOperators#71](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_2.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="c09f7-118">문자 목록에서 문자열 식의 문자를 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="c09f7-118">To match a character in the string expression against a list of characters</span></span>  
  
-   <span data-ttu-id="c09f7-119">대괄호 (`[ ]`) 패턴 문자열에서 한 문자 목록을 추가 대괄호 안에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="c09f7-120">쉼표 또는 다른 구분 기호 문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="c09f7-121">목록에 있는 한 문자 일치를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-121">Any single character in the list makes a successful match.</span></span>  
  
     <span data-ttu-id="c09f7-122">다음 예에서는 테스트 여부 `myString` 모든 유효한 문자는 문자 하나에 의해 뒤 `A`, `C`, 또는 `E`합니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>  
  
     [!code-vb[VbVbalrOperators#72](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_3.vb)]  
  
     <span data-ttu-id="c09f7-123">이 일치는 대/소문자 구분을 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-123">Note that this match is case-sensitive.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="c09f7-124">문자 범위에서 문자열 식의 문자를 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="c09f7-124">To match a character in the string expression against a range of characters</span></span>  
  
-   <span data-ttu-id="c09f7-125">대괄호 (`[ ]`) 하이픈으로 구분 된 패턴 문자열 및 최저 및 최고 문자 범위를 넣을 대괄호 안에 (`–`).</span><span class="sxs-lookup"><span data-stu-id="c09f7-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="c09f7-126">범위 내 임의의 단일 문자와 일치를 하면 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-126">Any single character within the range makes a successful match.</span></span>  
  
     <span data-ttu-id="c09f7-127">다음 예제에서는 테스트 여부 `myString` 문자로 구성 `num` 뒤에 문자 중 하나에 의해 `i`, `j`, `k`, `l`, `m`, 또는 `n`합니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>  
  
     [!code-vb[VbVbalrOperators#73](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_4.vb)]  
  
     <span data-ttu-id="c09f7-128">이 일치는 대/소문자 구분을 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-128">Note that this match is case-sensitive.</span></span>  
  
## <a name="matching-empty-strings"></a><span data-ttu-id="c09f7-129">일치 하는 빈 문자열</span><span class="sxs-lookup"><span data-stu-id="c09f7-129">Matching Empty Strings</span></span>  
 <span data-ttu-id="c09f7-130">`Like`시퀀스는 처리 `[]` 길이가 0 인 문자열 (`""`).</span><span class="sxs-lookup"><span data-stu-id="c09f7-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="c09f7-131">사용할 수 있습니다 `[]` 전체 문자열 식이 비어 있지만 문자열 식에서 특정 위치가 비어 있는지를 테스트 하려면 사용할 수 없습니다 있는지 여부를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="c09f7-132">사용할 수 있습니다에 대 한 테스트 해야 하는 빈 위치를 사용 하는 옵션 중 하나인 경우 `Like` 두 번 이상.</span><span class="sxs-lookup"><span data-stu-id="c09f7-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="c09f7-133">문자 또는 문자가 없는 목록에서 문자열 식의 문자를 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="c09f7-133">To match a character in the string expression against a list of characters or no character</span></span>  
  
1.  <span data-ttu-id="c09f7-134">호출 된 `Like` 연산자에 동일한 두 번 문자열 식, 및 중 하나를 사용 하 여 두 번 호출 연결는 [또는 연산자](../../../../visual-basic/language-reference/operators/or-operator.md) 또는 [OrElse 연산자](../../../../visual-basic/language-reference/operators/orelse-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
2.  <span data-ttu-id="c09f7-135">첫 번째에 대 한 패턴 문자열에 `Like` 절 대괄호로 묶은 문자 목록을 포함 (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="c09f7-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>  
  
3.  <span data-ttu-id="c09f7-136">두 번째 패턴 문자열에 `Like` 절을 배치 하지 않는 모든 문자 위치에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>  
  
     <span data-ttu-id="c09f7-137">다음 예제에서는 테스트 7 자리 전화 번호 `phoneNum` 정확히 3 자리 숫자, 공백, 하이픈 뒤에 (`–`), 마침표 (`.`), 또는 숫자와 전혀 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c09f7-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>  
  
     [!code-vb[VbVbalrOperators#74](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c09f7-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c09f7-138">See Also</span></span>  
 [<span data-ttu-id="c09f7-139">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="c09f7-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="c09f7-140">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="c09f7-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="c09f7-141">Like 연산자</span><span class="sxs-lookup"><span data-stu-id="c09f7-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="c09f7-142">String 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c09f7-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
