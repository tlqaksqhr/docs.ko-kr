---
title: "Visual Basic에서의 연산자 우선 순위"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arithmetic operators [Visual Basic], precedence
- operator precedence
- logical operators [Visual Basic], precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators [Visual Basic]
- operators [Visual Basic], precedence
- precedence [Visual Basic], of operators
- comparison operators [Visual Basic], precedence
- math operators [Visual Basic]
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6c0fb466b404cafdd4b91d061971fd683375c715
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="375b0-102">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="375b0-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="375b0-103">각 부분 평가 되 고 호출 미리 결정 된 순서 대로 확인 식에서 여러 작업이 발생 하는 경우 *연산자 우선 순위*합니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>  
  
## <a name="precedence-rules"></a><span data-ttu-id="375b0-104">선행 규칙</span><span class="sxs-lookup"><span data-stu-id="375b0-104">Precedence Rules</span></span>  
 <span data-ttu-id="375b0-105">식에 포함 될 연산자는 둘 이상의 범주에서 다음 규칙에 따라 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>  
  
-   <span data-ttu-id="375b0-106">산술 연산, 연결 연산자의 다음 섹션에서 설명 하는 우선 순위 있고 모든 비교, 논리 보다 높은 우선 순위 및 비트 연산자.</span><span class="sxs-lookup"><span data-stu-id="375b0-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>  
  
-   <span data-ttu-id="375b0-107">같은 우선 순위와는 논리 및 비트 연산자 보다 높은 우선 순위 있지만 순위 연산자 보다 우선 순위가 있는 모든 포함 된 모든 비교 연산자.</span><span class="sxs-lookup"><span data-stu-id="375b0-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>  
  
-   <span data-ttu-id="375b0-108">논리 및 비트 연산자의 다음 섹션에서 설명 하는 우선 순위 있고 모든 산술 연산, 연결 및 비교 연산자 보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>  
  
-   <span data-ttu-id="375b0-109">우선 순위가 같은 연산자는 오른쪽으로 계산 왼쪽 식에 나타나는 순서.</span><span class="sxs-lookup"><span data-stu-id="375b0-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>  
  
## <a name="precedence-order"></a><span data-ttu-id="375b0-110">우선 순위</span><span class="sxs-lookup"><span data-stu-id="375b0-110">Precedence Order</span></span>  
 <span data-ttu-id="375b0-111">연산자 우선 순위는 다음 순서 대로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-111">Operators are evaluated in the following order of precedence:</span></span>  
  
### <a name="await-operator"></a><span data-ttu-id="375b0-112">Await 연산자</span><span class="sxs-lookup"><span data-stu-id="375b0-112">Await Operator</span></span>  
 <span data-ttu-id="375b0-113">await</span><span class="sxs-lookup"><span data-stu-id="375b0-113">Await</span></span>  
  
### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="375b0-114">산술 및 연결 연산자</span><span class="sxs-lookup"><span data-stu-id="375b0-114">Arithmetic and Concatenation Operators</span></span>  
 <span data-ttu-id="375b0-115">지 수 (`^`)</span><span class="sxs-lookup"><span data-stu-id="375b0-115">Exponentiation (`^`)</span></span>  
  
 <span data-ttu-id="375b0-116">단항 id 및 부정 (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="375b0-116">Unary identity and negation (`+`, `–`)</span></span>  
  
 <span data-ttu-id="375b0-117">곱하기와 나누기 부동 소수점 (`*`, `/`)</span><span class="sxs-lookup"><span data-stu-id="375b0-117">Multiplication and floating-point division (`*`, `/`)</span></span>  
  
 <span data-ttu-id="375b0-118">정수 나누기 (`\`)</span><span class="sxs-lookup"><span data-stu-id="375b0-118">Integer division (`\`)</span></span>  
  
 <span data-ttu-id="375b0-119">모듈러스 산술 (`Mod`)</span><span class="sxs-lookup"><span data-stu-id="375b0-119">Modulus arithmetic (`Mod`)</span></span>  
  
 <span data-ttu-id="375b0-120">더하기와 빼기 (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="375b0-120">Addition and subtraction (`+`, `–`)</span></span>  
  
 <span data-ttu-id="375b0-121">문자열 연결 (`&`)</span><span class="sxs-lookup"><span data-stu-id="375b0-121">String concatenation (`&`)</span></span>  
  
 <span data-ttu-id="375b0-122">산술 비트 시프트 (`<<`, `>>`)</span><span class="sxs-lookup"><span data-stu-id="375b0-122">Arithmetic bit shift (`<<`, `>>`)</span></span>  
  
### <a name="comparison-operators"></a><span data-ttu-id="375b0-123">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="375b0-123">Comparison Operators</span></span>  
 <span data-ttu-id="375b0-124">모든 비교 연산자 (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)</span><span class="sxs-lookup"><span data-stu-id="375b0-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>  
  
### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="375b0-125">논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="375b0-125">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="375b0-126">부정 (`Not`)</span><span class="sxs-lookup"><span data-stu-id="375b0-126">Negation (`Not`)</span></span>  
  
 <span data-ttu-id="375b0-127">함께 (`And`, `AndAlso`)</span><span class="sxs-lookup"><span data-stu-id="375b0-127">Conjunction (`And`, `AndAlso`)</span></span>  
  
 <span data-ttu-id="375b0-128">포함 논리합 (`Or`, `OrElse`)</span><span class="sxs-lookup"><span data-stu-id="375b0-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>  
  
 <span data-ttu-id="375b0-129">배타적 논리합 (`Xor`)</span><span class="sxs-lookup"><span data-stu-id="375b0-129">Exclusive disjunction (`Xor`)</span></span>  
  
### <a name="comments"></a><span data-ttu-id="375b0-130">설명</span><span class="sxs-lookup"><span data-stu-id="375b0-130">Comments</span></span>  
 <span data-ttu-id="375b0-131">`=` 연산자는만 같음 비교 연산자, 대입 연산자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="375b0-132">문자열 연결 연산자 (`&`)는 산술 연산자가 있지만 산술 연산자와 그룹화가 우선에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>  
  
 <span data-ttu-id="375b0-133">`Is` 및 `IsNot` 연산자는 개체 참조 비교 연산자.</span><span class="sxs-lookup"><span data-stu-id="375b0-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="375b0-134">두 개체;의 값을 비교 하지 않습니다. 이러한 두 개체 변수가 동일한 개체 인스턴스를 나타내는지 확인에 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>  
  
## <a name="associativity"></a><span data-ttu-id="375b0-135">결합성</span><span class="sxs-lookup"><span data-stu-id="375b0-135">Associativity</span></span>  
 <span data-ttu-id="375b0-136">동일한 우선 순위의 연산자를 식, 곱하기 및 나누기, 예를 들어에 함께 나타납니다. 컴파일러도 왼쪽에서 오른쪽으로 각 작업을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="375b0-137">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-137">The following example illustrates this.</span></span>  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 <span data-ttu-id="375b0-138">첫 번째 식이 96 나누기 / 8 (있음 결과 12) 및 나누기 12 / 결과 3 4입니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="375b0-139">에 대 한 작업으로 계산 하므로 `n1` 왼쪽에서 오른쪽으로 계산 같습니다에 대 한 해당 순서를 명시적으로 지정 하는 경우 `n2`합니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="375b0-140">둘 다 `n1` 및 `n2` 결과는 3입니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="375b0-141">반면, `n3` 괄호는 컴파일러가 8 평가 때문에 48의 결과가 / 4 첫 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>  
  
 <span data-ttu-id="375b0-142">이러한 동작으로 인해 연산자에 있다고 *왼쪽 결합형* 에서 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-142">Because of this behavior, operators are said to be *left associative* in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="375b0-143">재정의 우선 순위 및 결합성</span><span class="sxs-lookup"><span data-stu-id="375b0-143">Overriding Precedence and Associativity</span></span>  
 <span data-ttu-id="375b0-144">다른 대체 이전 평가할 식의 일부분에 괄호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="375b0-145">우선 순위와 왼쪽된 결합성을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-145">This can override both the order of precedence and the left associativity.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="375b0-146">항상 외부 보다 먼저 괄호로 묶여 있는 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-146"> always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="375b0-147">그러나 괄호 안에 유지 일반 우선 순위와 결합성 괄호 안에 괄호를 사용 하지 않는 한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="375b0-148">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="375b0-148">The following example illustrates this.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="375b0-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="375b0-149">See Also</span></span>  
 [<span data-ttu-id="375b0-150">= 연산자</span><span class="sxs-lookup"><span data-stu-id="375b0-150">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [<span data-ttu-id="375b0-151">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="375b0-151">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="375b0-152">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="375b0-152">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="375b0-153">Like 연산자</span><span class="sxs-lookup"><span data-stu-id="375b0-153">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="375b0-154">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="375b0-154">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="375b0-155">Await 연산자</span><span class="sxs-lookup"><span data-stu-id="375b0-155">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)  
 [<span data-ttu-id="375b0-156">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="375b0-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="375b0-157">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="375b0-157">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
