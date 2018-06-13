---
title: 상수는 클래스, 구조체, 형식 매개 변수 또는 배열 형식이 아닌 내장 또는 열거 형식이어야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: 9039376fc4d1f67ca9b526e46eaf28a0b1a3943c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587484"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="1adb4-102">상수는 클래스, 구조체, 형식 매개 변수 또는 배열 형식이 아닌 내장 또는 열거 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1adb4-102">Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>
<span data-ttu-id="1adb4-103">형식 매개 변수를 포함 하는 제네릭 형식에 정의 된 또는 클래스, 구조체 또는 배열 형식으로 상수를 선언 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1adb4-103">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>  
  
 <span data-ttu-id="1adb4-104">상수는 내장 형식 이어야 합니다 (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, 또는 `UShort`), 또는 `Enum` 형식 정수 계열 형식 중 하나에 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="1adb4-104">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>  
  
 <span data-ttu-id="1adb4-105">**오류 ID:** BC30424</span><span class="sxs-lookup"><span data-stu-id="1adb4-105">**Error ID:** BC30424</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1adb4-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="1adb4-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="1adb4-107">내장 상수 선언 또는 `Enum` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="1adb4-107">Declare the constant as an intrinsic or `Enum` type.</span></span>  
  
2.  <span data-ttu-id="1adb4-108">상수 수와 같은 특수 값이 될 수도 `True`, `False`, 또는 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="1adb4-108">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="1adb4-109">컴파일러는 이러한 미리 정의 된 값이 적절 한 기본 유형일 수 있다고 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="1adb4-109">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1adb4-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1adb4-110">See Also</span></span>  
 [<span data-ttu-id="1adb4-111">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="1adb4-111">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [<span data-ttu-id="1adb4-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1adb4-112">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="1adb4-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1adb4-113">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)
