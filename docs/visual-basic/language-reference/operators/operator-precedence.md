---
title: "Visual Basic의 연산자 우선 순위 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- arithmetic operators, precedence
- operator precedence
- logical operators, precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators
- operators [Visual Basic], precedence
- precedence, of operators
- comparison operators, precedence
- math operators
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f653dd83c9778dddfe0e52db27065f7d73866e37
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="6114b-102">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="6114b-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="6114b-103">각 부분 평가 되 고 호출 하는 미리 결정 된 순서로 해결 식에서 몇 가지 작업이 발생할 때 *연산자 우선 순위*합니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>  
  
## <a name="precedence-rules"></a><span data-ttu-id="6114b-104">우선 순위 규칙</span><span class="sxs-lookup"><span data-stu-id="6114b-104">Precedence Rules</span></span>  
 <span data-ttu-id="6114b-105">식 연산자에서 둘 이상의 범주를 포함 하는 경우 다음 규칙에 따라 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>  
  
-   <span data-ttu-id="6114b-106">산술 및 연결 연산자는 다음 섹션에서 설명 하는 우선 순위를 있고 모든 비교, 논리 보다 높은 우선 순위 및 비트 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>  
  
-   <span data-ttu-id="6114b-107">모든 비교 연산자 있고 우선 순위가 동일한 연산자는 논리 및 비트 연산자 보다 우선 순위가 높은 있으며 산술 및 연결 연산자 보다 우선 순위가 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>  
  
-   <span data-ttu-id="6114b-108">논리 및 비트 연산자는 다음 섹션에서 설명 하는 우선 순위를 있고 모든 산술, 연결 및 비교 연산자 보다 우선 순위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>  
  
-   <span data-ttu-id="6114b-109">우선 순위가 같은 연산자는 왼쪽에서 오른쪽 계산 식에 나타나는 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>  
  
## <a name="precedence-order"></a><span data-ttu-id="6114b-110">우선 순위</span><span class="sxs-lookup"><span data-stu-id="6114b-110">Precedence Order</span></span>  
 <span data-ttu-id="6114b-111">연산자의 우선 순위는 다음과 같은 순서로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-111">Operators are evaluated in the following order of precedence:</span></span>  
  
### <a name="await-operator"></a><span data-ttu-id="6114b-112">Await 연산자</span><span class="sxs-lookup"><span data-stu-id="6114b-112">Await Operator</span></span>  
 <span data-ttu-id="6114b-113">대기</span><span class="sxs-lookup"><span data-stu-id="6114b-113">Await</span></span>  
  
### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="6114b-114">산술 및 연결 연산자</span><span class="sxs-lookup"><span data-stu-id="6114b-114">Arithmetic and Concatenation Operators</span></span>  
 <span data-ttu-id="6114b-115">지 수 (`^`)</span><span class="sxs-lookup"><span data-stu-id="6114b-115">Exponentiation (`^`)</span></span>  
  
 <span data-ttu-id="6114b-116">단항 같음 및 부정 (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="6114b-116">Unary identity and negation (`+`, `–`)</span></span>  
  
 <span data-ttu-id="6114b-117">곱하기 및 부동 소수점 나누기 (`*`, `/`)</span><span class="sxs-lookup"><span data-stu-id="6114b-117">Multiplication and floating-point division (`*`, `/`)</span></span>  
  
 <span data-ttu-id="6114b-118">정수 나누기 (`\`)</span><span class="sxs-lookup"><span data-stu-id="6114b-118">Integer division (`\`)</span></span>  
  
 <span data-ttu-id="6114b-119">산술 나머지 (`Mod`)</span><span class="sxs-lookup"><span data-stu-id="6114b-119">Modulus arithmetic (`Mod`)</span></span>  
  
 <span data-ttu-id="6114b-120">더하기와 빼기 (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="6114b-120">Addition and subtraction (`+`, `–`)</span></span>  
  
 <span data-ttu-id="6114b-121">문자열 연결 (`&`)</span><span class="sxs-lookup"><span data-stu-id="6114b-121">String concatenation (`&`)</span></span>  
  
 <span data-ttu-id="6114b-122">산술 비트 시프트 (`<<`, `>>`)</span><span class="sxs-lookup"><span data-stu-id="6114b-122">Arithmetic bit shift (`<<`, `>>`)</span></span>  
  
### <a name="comparison-operators"></a><span data-ttu-id="6114b-123">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="6114b-123">Comparison Operators</span></span>  
 <span data-ttu-id="6114b-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)</span><span class="sxs-lookup"><span data-stu-id="6114b-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>  
  
### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="6114b-125">논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="6114b-125">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="6114b-126">부정 (`Not`)</span><span class="sxs-lookup"><span data-stu-id="6114b-126">Negation (`Not`)</span></span>  
  
 <span data-ttu-id="6114b-127">함께 (`And`, `AndAlso`)</span><span class="sxs-lookup"><span data-stu-id="6114b-127">Conjunction (`And`, `AndAlso`)</span></span>  
  
 <span data-ttu-id="6114b-128">포함 논리합 (`Or`, `OrElse`)</span><span class="sxs-lookup"><span data-stu-id="6114b-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>  
  
 <span data-ttu-id="6114b-129">배타적 논리합 (`Xor`)</span><span class="sxs-lookup"><span data-stu-id="6114b-129">Exclusive disjunction (`Xor`)</span></span>  
  
### <a name="comments"></a><span data-ttu-id="6114b-130">설명</span><span class="sxs-lookup"><span data-stu-id="6114b-130">Comments</span></span>  
 <span data-ttu-id="6114b-131">`=` 연산자는 같음 비교 연산자만, 대입 연산자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="6114b-132">문자열 연결 연산자 (`&`)는 산술 연산자가 산술 연산자와 그룹화는 우선 순위에 따라 하지만 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>  
  
 <span data-ttu-id="6114b-133">`Is` 및 `IsNot` 연산자는 개체 참조 비교 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="6114b-134">두 개체의 값을 비교 하지 않습니다. 이러한 두 개체 변수가 동일한 개체 인스턴스를 참조 하는지 여부 확인에 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>  
  
## <a name="associativity"></a><span data-ttu-id="6114b-135">결합성</span><span class="sxs-lookup"><span data-stu-id="6114b-135">Associativity</span></span>  
 <span data-ttu-id="6114b-136">동일한 우선 순위의 연산자는 식, 곱하기 및 나누기, 예를 들어에 함께 표시 하는 경우 컴파일러도 왼쪽에서 오른쪽으로 각 작업을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="6114b-137">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-137">The following example illustrates this.</span></span>  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 <span data-ttu-id="6114b-138">첫 번째 식이 96 나누기 / 8 (함 결과 12) 및 나누기 12 / 4 결과 3입니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="6114b-139">에 대 한 작업으로 계산 하므로 `n1` 왼쪽에서 오른쪽으로 평가 동일한에 대 한이 순서를 명시적으로 지정 하는 경우 `n2`합니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="6114b-140">둘 다 `n1` 및 `n2` 결과는&3;입니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="6114b-141">반면, `n3` 48의 결과 괄호 8을 평가 하는 컴파일러가 / 4 첫 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>  
  
 <span data-ttu-id="6114b-142">이 동작으로 인해 연산자에 있다고 *왼쪽 결합형* 에서 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-142">Because of this behavior, operators are said to be *left associative* in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="6114b-143">우선 순위 및 결합성 재정의</span><span class="sxs-lookup"><span data-stu-id="6114b-143">Overriding Precedence and Associativity</span></span>  
 <span data-ttu-id="6114b-144">다른 사용자 보다 먼저 계산 하는 식의 일부분에 괄호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="6114b-145">이 우선 순위와 왼쪽된 결합성 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-145">This can override both the order of precedence and the left associativity.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="6114b-146">항상 외부 보다 먼저 괄호로 묶여 있는 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-146"> always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="6114b-147">그러나 괄호 안에 유지 일반 우선 순위와 결합성 괄호 안에서 괄호를 사용 하지 않으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="6114b-148">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6114b-148">The following example illustrates this.</span></span>  
  
```  
Dim a, b, c, d, e, f, g As Double  
a = 8.0  
b = 3.0  
c = 4.0  
d = 2.0  
e = 1.0  
f = a - b + c / d * e  
' The preceding line sets f to 7.0. Because of natural operator   
' precedence and associativity, it is exactly equivalent to the   
' following line.  
f = (a - b) + ((c / d) * e)  
' The following line overrides the natural operator precedence   
' and left associativity.  
g = (a - (b + c)) / (d * e)  
' The preceding line sets g to 0.5.  
```  
  
## <a name="see-also"></a><span data-ttu-id="6114b-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6114b-149">See Also</span></span>  
 <span data-ttu-id="6114b-150">[= 연산자](../../../visual-basic/language-reference/operators/assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="6114b-150">[= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) </span></span>  
<span data-ttu-id="6114b-151"> [Is 연산자](../../../visual-basic/language-reference/operators/is-operator.md) </span><span class="sxs-lookup"><span data-stu-id="6114b-151"> [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md) </span></span>  
<span data-ttu-id="6114b-152"> [IsNot 연산자](../../../visual-basic/language-reference/operators/isnot-operator.md) </span><span class="sxs-lookup"><span data-stu-id="6114b-152"> [IsNot Operator](../../../visual-basic/language-reference/operators/isnot-operator.md) </span></span>  
<span data-ttu-id="6114b-153"> [Like 연산자](../../../visual-basic/language-reference/operators/like-operator.md) </span><span class="sxs-lookup"><span data-stu-id="6114b-153"> [Like Operator](../../../visual-basic/language-reference/operators/like-operator.md) </span></span>  
<span data-ttu-id="6114b-154"> [TypeOf 연산자](../../../visual-basic/language-reference/operators/typeof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="6114b-154"> [TypeOf Operator](../../../visual-basic/language-reference/operators/typeof-operator.md) </span></span>  
<span data-ttu-id="6114b-155"> [Await 연산자](../../../visual-basic/language-reference/operators/await-operator.md) </span><span class="sxs-lookup"><span data-stu-id="6114b-155"> [Await Operator](../../../visual-basic/language-reference/operators/await-operator.md) </span></span>  
<span data-ttu-id="6114b-156"> [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="6114b-156"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="6114b-157"> [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)</span><span class="sxs-lookup"><span data-stu-id="6114b-157"> [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)</span></span>
