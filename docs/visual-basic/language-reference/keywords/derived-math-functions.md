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
---
# <a name="derived-math-functions-visual-basic"></a>파생된 수학 함수(Visual Basic)
다음 표에의 내장 수학 함수에서 파생 될 수 있는 비 내장 수치 연산 함수는 <xref:System.Math?displayProperty=nameWithType> 개체입니다. 추가 하 여 기본 수치 연산 함수에 액세스할 수 있습니다 `Imports System.Math` 를 파일이 나 프로젝트입니다.  
  
|함수|파생된 형식|  
|--------------|-------------------------|  
|시 컨 트 (Sec(x))|1 / Cos(x)|  
|코시 컨 트 (Csc(x))|1 / Sin(x)|  
|코탄젠트 (Ctan(x))|1 / Tan(x)|  
|역 사인 (Asin(x))|Atan (x / Sqrt (-x * x + 1))|  
|역 코사인 (Acos(x))|Atan (-x / Sqrt (-x * x + 1)) + 2 \* Atan(1)|  
|역 시 컨 트 (Asec(x))|2 * Atan(1) – Atan(Sign(x) / Sqrt (x \* x-1))|  
|역 코시 컨 트 (Acsc(x))|Atan(Sign(x) / Sqrt (x * x-1))|  
|역 코탄젠트 (Acot(x))|2 * Atan(1)-Atan(x)|  
|쌍 곡 사인 (Sinh(x))|(Exp(x) – Exp(-x)) / 2|  
|쌍 곡 코사인 (Cosh(x))|(Exp(x) + Exp(-x)) / 2|  
|쌍 곡 탄젠트 (Tanh(x))|(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))|  
|쌍 곡 시 컨 트 (Sech(x))|2 / (Exp(x) + Exp(-x))|  
|쌍 곡 코시 컨 트 (Csch(x))|2 / (Exp(x) – Exp(-x))|  
|쌍 곡 코탄젠트 (Coth(x))|(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))|  
|역 쌍 곡 사인 (Asinh(x))|로그 (x + Sqrt (x * x + 1))|  
|역 쌍 곡 코사인 (Acosh(x))|로그 (x + Sqrt (x * x-1))|  
|역 쌍 곡 탄젠트 (Atanh(x))|로그 ((1 + x) / (1-x)) / 2|  
|역 쌍 곡 시 컨 트 (AsecH(x))|로그 ((Sqrt (-x * x + 1) + 1) / x)|  
|역 쌍 곡 코시 컨 트 (Acsch(x))|Log((Sign(x) * Sqrt (x \* x + 1) + 1) / x)|  
|역 쌍 곡 코탄젠트 (Acoth(x))|로그 ((x + 1) / (x-1)) / 2|  
  
## <a name="see-also"></a>참고 항목  
 [수학 함수](../../../visual-basic/language-reference/functions/math-functions.md)
