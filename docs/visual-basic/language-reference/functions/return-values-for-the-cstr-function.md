---
title: CStr 함수의 반환 값(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
ms.openlocfilehash: 5312734633eea12aacd7e61afba616d31e06cd71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598526"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="9d0ef-102">CStr 함수의 반환 값(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d0ef-102">Return Values for the CStr Function (Visual Basic)</span></span>
<span data-ttu-id="9d0ef-103">다음 표에서 반환 값에 대 한 설명 `CStr` 의 서로 다른 데이터 형식에 대 한 `expression`합니다.</span><span class="sxs-lookup"><span data-stu-id="9d0ef-103">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="9d0ef-104">경우 `expression` 형식이</span><span class="sxs-lookup"><span data-stu-id="9d0ef-104">If `expression` type is</span></span>|<span data-ttu-id="9d0ef-105">`CStr` return</span><span class="sxs-lookup"><span data-stu-id="9d0ef-105">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="9d0ef-106">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9d0ef-106">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="9d0ef-107">"True"를 포함 하는 문자열 또는 "False"입니다.</span><span class="sxs-lookup"><span data-stu-id="9d0ef-107">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="9d0ef-108">Date 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9d0ef-108">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="9d0ef-109">포함 하는 문자열을 `Date` 시스템의 간단한 날짜 형식 값 (날짜 및 시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="9d0ef-109">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="9d0ef-110">숫자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9d0ef-110">Numeric Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="9d0ef-111">수를 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9d0ef-111">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="9d0ef-112">CStr 및 날짜</span><span class="sxs-lookup"><span data-stu-id="9d0ef-112">CStr and Date</span></span>  
 <span data-ttu-id="9d0ef-113">`Date` 형식이 항상 날짜와 시간 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d0ef-113">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="9d0ef-114">형식 변환을 위해 Visual Basic 간주 1/1/0001 (1 1 년 1 월)는 *기본값으로* 시간에 대 한 기본값으로 간주 00시: 00 (자정) 및 날짜,입니다.</span><span class="sxs-lookup"><span data-stu-id="9d0ef-114">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="9d0ef-115">`CStr` 결과 문자열에는 기본값이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d0ef-115">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="9d0ef-116">예를 들어, 변환 하면 `#January 1, 0001 9:30:00#` 문자열로 결과 "오전 9시 30분: 00" 하 고 날짜 정보는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d0ef-116">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="9d0ef-117">그러나 날짜 정보에에서는 아직 있는 원래 `Date` 값 및와 같은 함수를 사용 하 여 복구할 수 수 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="9d0ef-117">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d0ef-118">`CStr` 함수 응용 프로그램에 대 한 현재 문화권 설정에 따라으로 변환을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d0ef-118">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="9d0ef-119">숫자의를 사용 하 여 숫자의 문자열 표현을 특정 문화권을 가져오려면 `ToString(IFormatProvider)` 메서드.</span><span class="sxs-lookup"><span data-stu-id="9d0ef-119">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="9d0ef-120">사용 예를 들어 <xref:System.Double.ToString%2A?displayProperty=nameWithType> 형식의 값을 변환할 때 `Double` 에 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="9d0ef-120">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d0ef-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d0ef-121">See Also</span></span>  
 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>  
 [<span data-ttu-id="9d0ef-122">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="9d0ef-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="9d0ef-123">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9d0ef-123">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [<span data-ttu-id="9d0ef-124">Date 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9d0ef-124">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)
