---
title: "Date 데이터 형식(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Date
helpviewer_keywords:
- Date data type
- dates [Visual Basic], Visual Basic data types
- times [Visual Basic], Date data type
- Date literals [Visual Basic]
- data values [Visual Basic]
- times [Visual Basic], Visual Basic data types
- dates [Visual Basic], Date data type
- data types [Visual Basic], assigning
- literals [Visual Basic], Date
- '# specifier for Date literals'
ms.assetid: d9edf5b0-e85e-438b-a1cf-1f321e7c831b
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 190b40888dc4a42075b7b6b27bdb1bd403a7efb5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="date-data-type-visual-basic"></a><span data-ttu-id="5f26a-102">Date 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f26a-102">Date Data Type (Visual Basic)</span></span>
<span data-ttu-id="5f26a-103">0001년 1월 1일부터 9999년 12월 31일까지의 날짜와 오전 12:00:00(자정)부터 오후 11:59:59.9999999까지의 시간을 나타내는 IEEE 64비트(8비트) 값을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-103">Holds IEEE 64-bit (8-byte) values that represent dates ranging from January 1 of the year 0001 through December 31 of the year 9999, and times from 12:00:00 AM (midnight) through 11:59:59.9999999 PM.</span></span> <span data-ttu-id="5f26a-104">각 증분은 일반 달력에서 1년 1월 1일 시작 이후 경과된 시간의 100나노초를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-104">Each increment represents 100 nanoseconds of elapsed time since the beginning of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="5f26a-105">최대값은 10000년 1월 1일 시작 이전 100나노초를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-105">The maximum value represents 100 nanoseconds before the beginning of January 1 of the year 10000.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f26a-106">설명</span><span class="sxs-lookup"><span data-stu-id="5f26a-106">Remarks</span></span>  
 <span data-ttu-id="5f26a-107">`Date` 데이터 형식을 사용하여 날짜 값, 시간 값 또는 날짜 및 시간 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-107">Use the `Date` data type to contain date values, time values, or date and time values.</span></span>  
  
 <span data-ttu-id="5f26a-108">`Date`의 기본값은 0001년 1월 1일 0:00:00(자정)입니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-108">The default value of `Date` is 0:00:00 (midnight) on January 1, 0001.</span></span>  
  
 <span data-ttu-id="5f26a-109"><xref:Microsoft.VisualBasic.DateAndTime> 클래스에서 현재 날짜와 시간을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-109">You can get the current date and time from the <xref:Microsoft.VisualBasic.DateAndTime> class.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="5f26a-110">형식 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f26a-110">Format Requirements</span></span>  
 <span data-ttu-id="5f26a-111">숫자 기호(`# #`) 내의 `Date` 리터럴을 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-111">You must enclose a `Date` literal within number signs (`# #`).</span></span> <span data-ttu-id="5f26a-112">M/d/yyyy(예: `#5/31/1993#`) 또는 yyyy-MM-dd(예: `#1993-5-31#`) 형식으로 날짜 값을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-112">You must specify the date value in the format M/d/yyyy, for example `#5/31/1993#`, or yyyy-MM-dd, for example `#1993-5-31#`.</span></span> <span data-ttu-id="5f26a-113">연도를 먼저 지정하는 경우 슬래시를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-113">You can use slashes when specifying the year first.</span></span>  <span data-ttu-id="5f26a-114">이 요구 사항은 사용자 로캘과 컴퓨터의 날짜 및 시간 형식 설정에 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-114">This requirement is independent of your locale and your computer's date and time format settings.</span></span>  
  
 <span data-ttu-id="5f26a-115">이러한 제한 이유는 응용 프로그램을 실행하는 로캘에 따라 코드의 의미가 변경되면 안 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-115">The reason for this restriction is that the meaning of your code should never change depending on the locale in which your application is running.</span></span> <span data-ttu-id="5f26a-116">`#3/4/1998#`의 `Date` 리터럴을 하드 코딩하고 1998년 3월 4로 지정한다고 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="5f26a-116">Suppose you hard-code a `Date` literal of `#3/4/1998#` and intend it to mean March 4, 1998.</span></span> <span data-ttu-id="5f26a-117">mm/dd/yyyy를 사용하는 로캘에서는 3/4/1998이 의도한 대로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-117">In a locale that uses mm/dd/yyyy, 3/4/1998 compiles as you intend.</span></span> <span data-ttu-id="5f26a-118">그러나 여러 국가에 응용 프로그램을 배포한다고 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="5f26a-118">But suppose you deploy your application in many countries.</span></span> <span data-ttu-id="5f26a-119">dd/mm/yyyy를 사용하는 로캘에서는 하드 코딩된 리터럴이 1998년 4월 3일로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-119">In a locale that uses dd/mm/yyyy, your hard-coded literal would compile to April 3, 1998.</span></span> <span data-ttu-id="5f26a-120">yyyy/mm/dd를 사용하는 로캘에서는 리터럴이 잘못 지정되며(0003년 4월 1998일) 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-120">In a locale that uses yyyy/mm/dd, the literal would be invalid (April 1998, 0003) and cause a compiler error.</span></span>  
  
## <a name="workarounds"></a><span data-ttu-id="5f26a-121">해결 방법</span><span class="sxs-lookup"><span data-stu-id="5f26a-121">Workarounds</span></span>  
 <span data-ttu-id="5f26a-122">`Date` 리터럴을 해당 로캘 형식이나 사용자 지정 형식으로 변환하려면 <xref:Microsoft.VisualBasic.Strings.Format%2A> 함수에 리터럴을 제공하고 미리 정의된 날짜 형식이나 사용자 정의 날짜 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-122">To convert a `Date` literal to the format of your locale, or to a custom format, supply the literal to the <xref:Microsoft.VisualBasic.Strings.Format%2A> function, specifying either a predefined or user-defined date format.</span></span> <span data-ttu-id="5f26a-123">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-123">The following example demonstrates this.</span></span>  
  
```  
MsgBox("The formatted date is " & Format(#5/31/1993#, "dddd, d MMM yyyy"))  
```  
  
 <span data-ttu-id="5f26a-124">또는 <xref:System.DateTime> 구조체의 오버로드된 생성자 중 하나를 사용하여 날짜 및 시간 값을 어셈블할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-124">Alternatively, you can use one of the overloaded constructors of the <xref:System.DateTime> structure to assemble a date and time value.</span></span> <span data-ttu-id="5f26a-125">다음 예제에서는 1993년 5월 31일 오후 12:14를 나타내는 값을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-125">The following example creates a value to represent May 31, 1993 at 12:14 in the afternoon.</span></span>  
  
```  
Dim dateInMay As New System.DateTime(1993, 5, 31, 12, 14, 0)  
```  
  
## <a name="hour-format"></a><span data-ttu-id="5f26a-126">시간 형식</span><span class="sxs-lookup"><span data-stu-id="5f26a-126">Hour Format</span></span>  
 <span data-ttu-id="5f26a-127">12시간제 또는 24시간제 형식으로 시간 값을 지정할 수 있습니다(예: `#1:15:30 PM#` 또는 `#13:15:30#`).</span><span class="sxs-lookup"><span data-stu-id="5f26a-127">You can specify the time value in either 12-hour or 24-hour format, for example `#1:15:30 PM#` or `#13:15:30#`.</span></span> <span data-ttu-id="5f26a-128">그러나 분 또는 초를 지정하지 않는 경우 AM 또는 PM을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-128">However, if you do not specify either the minutes or the seconds, you must specify AM or PM.</span></span>  
  
## <a name="date-and-time-defaults"></a><span data-ttu-id="5f26a-129">날짜 및 시간 기본값</span><span class="sxs-lookup"><span data-stu-id="5f26a-129">Date and Time Defaults</span></span>  
 <span data-ttu-id="5f26a-130">날짜/시간 리터럴에 날짜를 포함하지 않으면 Visual Basic에서 값의 날짜 부분을 0001년 1월 1일로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-130">If you do not include a date in a date/time literal, Visual Basic sets the date part of the value to January 1, 0001.</span></span> <span data-ttu-id="5f26a-131">날짜/시간 리터럴에 시간을 포함하지 않으면 Visual Basic에서 값의 시간 부분을 그 날의 시작, 즉 자정(0:00:00)으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-131">If you do not include a time in a date/time literal, Visual Basic sets the time part of the value to the start of the day, that is, midnight (0:00:00).</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="5f26a-132">형식 변환</span><span class="sxs-lookup"><span data-stu-id="5f26a-132">Type Conversions</span></span>  
 <span data-ttu-id="5f26a-133">`Date` 값을 `String` 형식으로 변환하는 경우 Visual Basic에서 런타임 로캘에 지정된 약식 날짜 형식에 따라 날짜를 렌더링하고 런타임 로캘에 지정된 시간 형식(12시간제 또는 24시간제)에 따라 시간을 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-133">If you convert a `Date` value to the `String` type, Visual Basic renders the date according to the short date format specified by the run-time locale, and it renders the time according to the time format (either 12-hour or 24-hour) specified by the run-time locale.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="5f26a-134">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="5f26a-134">Programming Tips</span></span>  
  
-   <span data-ttu-id="5f26a-135">**Interop 고려 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="5f26a-135">**Interop Considerations.**</span></span> <span data-ttu-id="5f26a-136">자동화 개체나 COM 개체와 같이 .NET Framework용으로 작성되지 않은 구성 요소를 조작하는 경우 다른 환경의 날짜/시간 형식이 Visual Basic `Date` 형식과 호환되지 않는 것에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="5f26a-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that date/time types in other environments are not compatible with the Visual Basic `Date` type.</span></span> <span data-ttu-id="5f26a-137">이러한 구성 요소에 날짜/시간 인수를 전달하는 경우 새로운 Visual Basic 코드에서 이 인수를 `Date` 대신 `Double`로 선언하고 변환 메서드 <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> 및 <xref:System.DateTime.ToOADate%2A?displayProperty=nameWithType>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-137">If you are passing a date/time argument to such a component, declare it as `Double` instead of `Date` in your new Visual Basic code, and use the conversion methods <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> and <xref:System.DateTime.ToOADate%2A?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="5f26a-138">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="5f26a-138">**Type Characters.**</span></span> <span data-ttu-id="5f26a-139">`Date`에 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-139">`Date` has no literal type character or identifier type character.</span></span> <span data-ttu-id="5f26a-140">그러나 컴파일러가 숫자 기호(`# #`)로 묶인 리터럴을 `Date`로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-140">However, the compiler treats literals enclosed within number signs (`# #`) as `Date`.</span></span>  
  
-   <span data-ttu-id="5f26a-141">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="5f26a-141">**Framework Type.**</span></span> <span data-ttu-id="5f26a-142">.NET Framework에서 해당하는 형식은 <xref:System.DateTime?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-142">The corresponding type in the .NET Framework is the <xref:System.DateTime?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f26a-143">예제</span><span class="sxs-lookup"><span data-stu-id="5f26a-143">Example</span></span>  
 <span data-ttu-id="5f26a-144">`Date` 데이터 형식의 변수 또는 상수는 날짜와 시간을 모두 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-144">A variable or constant of the `Date` data type holds both the date and the time.</span></span> <span data-ttu-id="5f26a-145">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5f26a-145">The following example illustrates this.</span></span>  
  
```  
Dim someDateAndTime As Date = #8/13/2002 12:14 PM#  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f26a-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f26a-146">See Also</span></span>  
 <xref:System.DateTime?displayProperty=nameWithType>  
 [<span data-ttu-id="5f26a-147">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5f26a-147">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="5f26a-148">표준 날짜 및 시간 형식 문자열</span><span class="sxs-lookup"><span data-stu-id="5f26a-148">Standard Date and Time Format Strings</span></span>](../../../standard/base-types/standard-date-and-time-format-strings.md)  
 [<span data-ttu-id="5f26a-149">사용자 지정 날짜 및 시간 형식 문자열</span><span class="sxs-lookup"><span data-stu-id="5f26a-149">Custom Date and Time Format Strings</span></span>](../../../standard/base-types/custom-date-and-time-format-strings.md)  
 [<span data-ttu-id="5f26a-150">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="5f26a-150">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="5f26a-151">변환 요약</span><span class="sxs-lookup"><span data-stu-id="5f26a-151">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="5f26a-152">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="5f26a-152">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
