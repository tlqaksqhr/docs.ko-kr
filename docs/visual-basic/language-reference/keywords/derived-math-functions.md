---
title: 파생된 수학 함수(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operations, derived math functions
- cosecant function
- arcsecant function
- arccotangent function
- functions [Visual Basic], derived math functions
- inverse functions
- math functions, derived
- derived math functions
- cotangent function
- angles
- secant function
- trigonometric functions
- logarithms
- arccosecant function
- hyperbolic functions
- arcsine function
- degrees
- arccosine function
ms.assetid: 63e449d8-9444-44fb-8db1-6d9cf346e2aa
ms.openlocfilehash: 87faa623f5b145eec8b88e350fce4171125324dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596810"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="9fd95-102">파생된 수학 함수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9fd95-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="9fd95-103">다음 표에의 내장 수학 함수에서 파생 될 수 있는 비 내장 수치 연산 함수는 <xref:System.Math?displayProperty=nameWithType> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9fd95-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="9fd95-104">추가 하 여 기본 수치 연산 함수에 액세스할 수 있습니다 `Imports System.Math` 를 파일이 나 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="9fd95-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="9fd95-105">함수</span><span class="sxs-lookup"><span data-stu-id="9fd95-105">Function</span></span>|<span data-ttu-id="9fd95-106">파생된 형식</span><span class="sxs-lookup"><span data-stu-id="9fd95-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="9fd95-107">시 컨 트 (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-107">Secant (Sec(x))</span></span>|<span data-ttu-id="9fd95-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="9fd95-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="9fd95-109">코시 컨 트 (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="9fd95-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="9fd95-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="9fd95-111">코탄젠트 (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="9fd95-112">1 / Tan(x)</span><span class="sxs-lookup"><span data-stu-id="9fd95-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="9fd95-113">역 사인 (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="9fd95-114">Atan (x / Sqrt (-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="9fd95-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="9fd95-115">역 코사인 (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="9fd95-116">Atan (-x / Sqrt (-x * x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="9fd95-116">Atan(-x / Sqrt(-x * x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="9fd95-117">역 시 컨 트 (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="9fd95-118">2 * Atan(1) – Atan(Sign(x) / Sqrt (x \* x-1))</span><span class="sxs-lookup"><span data-stu-id="9fd95-118">2 * Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="9fd95-119">역 코시 컨 트 (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="9fd95-120">Atan(Sign(x) / Sqrt (x \* x-1))</span><span class="sxs-lookup"><span data-stu-id="9fd95-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="9fd95-121">역 코탄젠트 (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="9fd95-122">2 \* Atan(1)-Atan(x)</span><span class="sxs-lookup"><span data-stu-id="9fd95-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="9fd95-123">쌍 곡 사인 (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="9fd95-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="9fd95-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="9fd95-125">쌍 곡 코사인 (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="9fd95-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="9fd95-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="9fd95-127">쌍 곡 탄젠트 (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="9fd95-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="9fd95-129">쌍 곡 시 컨 트 (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="9fd95-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="9fd95-131">쌍 곡 코시 컨 트 (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="9fd95-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="9fd95-133">쌍 곡 코탄젠트 (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="9fd95-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="9fd95-135">역 쌍 곡 사인 (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="9fd95-136">로그 (x + Sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="9fd95-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="9fd95-137">역 쌍 곡 코사인 (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="9fd95-138">로그 (x + Sqrt (x \* x-1))</span><span class="sxs-lookup"><span data-stu-id="9fd95-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="9fd95-139">역 쌍 곡 탄젠트 (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="9fd95-140">로그 ((1 + x) / (1-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="9fd95-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="9fd95-141">역 쌍 곡 시 컨 트 (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="9fd95-142">로그 ((Sqrt (-x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="9fd95-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="9fd95-143">역 쌍 곡 코시 컨 트 (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="9fd95-144">Log((Sign(x) * Sqrt (x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="9fd95-144">Log((Sign(x) * Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="9fd95-145">역 쌍 곡 코탄젠트 (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="9fd95-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="9fd95-146">로그 ((x + 1) / (x-1)) / 2</span><span class="sxs-lookup"><span data-stu-id="9fd95-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9fd95-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9fd95-147">See Also</span></span>  
 [<span data-ttu-id="9fd95-148">수학 함수</span><span class="sxs-lookup"><span data-stu-id="9fd95-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
