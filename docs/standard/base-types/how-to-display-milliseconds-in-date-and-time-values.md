---
title: '방법: 날짜 및 시간 값의 밀리초 표시'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DateTime.ToString method
- displaying date and time data
- time [.NET Framework], milliseconds
- dates [.NET Framework], milliseconds
- milliseconds [.NET Framework]
ms.assetid: ae1a0610-90b9-4877-8eb6-4e30bc5e00cf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7bf73920d10ff825396e61a3ca4e9efd622d9c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568006"
---
# <a name="how-to-display-milliseconds-in-date-and-time-values"></a><span data-ttu-id="4ba61-102">방법: 날짜 및 시간 값의 밀리초 표시</span><span class="sxs-lookup"><span data-stu-id="4ba61-102">How to: Display Milliseconds in Date and Time Values</span></span>
<span data-ttu-id="4ba61-103"><xref:System.DateTime.ToString?displayProperty=nameWithType>과 같은 기본 날짜 및 시간 서식 지정 메서드에는 시간 값의 시, 분, 초가 포함되지만 밀리초 구성 요소는 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-103">The default date and time formatting methods, such as <xref:System.DateTime.ToString?displayProperty=nameWithType>, include the hours, minutes, and seconds of a time value but exclude its milliseconds component.</span></span> <span data-ttu-id="4ba61-104">이 항목에서는 형식이 지정된 날짜 및 시간 문자열에 날짜 및 시간의 밀리초 구성 요소를 포함하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-104">This topic shows how to include a date and time's millisecond component in formatted date and time strings.</span></span>  
  
### <a name="to-display-the-millisecond-component-of-a-datetime-value"></a><span data-ttu-id="4ba61-105">DateTime 값의 밀리초 구성 요소를 표시하려면</span><span class="sxs-lookup"><span data-stu-id="4ba61-105">To display the millisecond component of a DateTime value</span></span>  
  
1.  <span data-ttu-id="4ba61-106">날짜의 문자열 표현에 대한 작업을 하는 경우에는 정적 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 메서드를 사용하여 해당 표현을 <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> 또는 <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType> 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-106">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="4ba61-107">시간 밀리초 구성 요소의 문자열 표현을 추출하려면 날짜 및 시간 값의 <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> 또는 <xref:System.DateTimeOffset.ToString%2A> 메서드를 호출하고 `fff` 또는 `FFF` 사용자 지정 형식 패턴을 단독으로 또는 다른 사용자 지정 형식 지정자와 함께 `format` 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-107">To extract the string representation of a time's millisecond component, call the date and time value's <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%2A> method, and pass the `fff` or `FFF` custom format pattern either alone or with other custom format specifiers as the `format` parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ba61-108">예</span><span class="sxs-lookup"><span data-stu-id="4ba61-108">Example</span></span>  
 <span data-ttu-id="4ba61-109">이 예제에서는 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 값의 밀리초 구성 요소를 단독으로 그리고 긴 날짜 및 시간 문자열에 포함하여 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-109">The example displays the millisecond component of a <xref:System.DateTime> and a <xref:System.DateTimeOffset> value to the console, both alone and included in a longer date and time string.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#1)]
 [!code-vb[Formatting.HowTo.Millisecond#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#1)]  
  
 <span data-ttu-id="4ba61-110">`fff` 형식 패턴에서는 밀리초 값의 뒤에 0이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-110">The `fff` format pattern includes any trailing zeros in the millisecond value.</span></span> <span data-ttu-id="4ba61-111">`FFF` 형식 패턴에서는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-111">The `FFF` format pattern suppresses them.</span></span> <span data-ttu-id="4ba61-112">다음 예제에서 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-112">The difference is illustrated in the following example.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#2)]
 [!code-vb[Formatting.HowTo.Millisecond#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#2)]  
  
 <span data-ttu-id="4ba61-113">날짜 및 시간의 밀리초 구성 요소를 포함하는 전체 사용자 지정 형식 지정자를 정의할 때 발생하는 문제는 응용 프로그램의 현재 문화권에서 사용되는 시간 요소의 정렬과 일치하지 않는 하드 코드된 형식이 정의될 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-113">A problem with defining a complete custom format specifier that includes the millisecond component of a date and time is that it defines a hard-coded format that may not correspond to the arrangement of time elements in the application's current culture.</span></span> <span data-ttu-id="4ba61-114">더 나은 방법은 현재 문화권의 <xref:System.Globalization.DateTimeFormatInfo> 개체로 정의된 날짜 및 시간 표시 패턴 중 하나를 검색한 후 밀리초를 포함하도록 수정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-114">A better alternative is to retrieve one of the date and time display patterns defined by the current culture's <xref:System.Globalization.DateTimeFormatInfo> object and modify it to include milliseconds.</span></span> <span data-ttu-id="4ba61-115">이 방법도 예제에서 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-115">The example also illustrates this approach.</span></span> <span data-ttu-id="4ba61-116"><xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> 속성에서 현재 문화권의 전체 날짜 및 시간 패턴을 검색한 후 해당 초 패턴 뒤에 사용자 지정 패턴 `.ffff`를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-116">It retrieves the current culture's full date and time pattern from the <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> property, and then inserts the custom pattern `.ffff` after its seconds pattern.</span></span> <span data-ttu-id="4ba61-117">예제에서는 정규식을 사용하여 이 작업을 단일 메서드 호출에서 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-117">Note that the example uses a regular expression to perform this operation in a single method call.</span></span>  
  
 <span data-ttu-id="4ba61-118">사용자 지정 형식 지정자를 사용하여 밀리초가 아닌 초의 소수 자릿수를 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-118">You can also use a custom format specifier to display a fractional part of seconds other than milliseconds.</span></span> <span data-ttu-id="4ba61-119">예를 들어 `f` 또는 `F` 사용자 지정 형식 지정자는 1/10초, `ff` 또는 `FF` 사용자 지정 형식 지정자는 1/100초, `ffff` 또는 `FFFF` 사용자 지정 형식 지정자는 1/10000초를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-119">For example, the `f` or `F` custom format specifier displays tenths of a second, the `ff` or `FF` custom format specifier displays hundredths of a second, and the `ffff` or `FFFF` custom format specifier displays ten thousandths of a second.</span></span> <span data-ttu-id="4ba61-120">반환된 문자열에서 밀리초의 소수 자릿수가 반올림되지 않고 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-120">Fractional parts of a millisecond are truncated instead of rounded in the returned string.</span></span> <span data-ttu-id="4ba61-121">이 형식 지정자는 다음 예제에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-121">These format specifiers are used in the following example.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#3)]
 [!code-vb[Formatting.HowTo.Millisecond#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#3)]  
  
> [!NOTE]
>  <span data-ttu-id="4ba61-122">1/10000초, 1/100000초 등 1초의 매우 작은 소수 단위를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-122">It is possible to display very small fractional units of a second, such as ten thousandths of a second or hundred-thousandths of a second.</span></span> <span data-ttu-id="4ba61-123">그러나 이러한 값은 의미가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-123">However, these values may not be meaningful.</span></span> <span data-ttu-id="4ba61-124">날짜 및 시간 값의 자릿수는 시스템 시계의 정밀도에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-124">The precision of date and time values depends on the resolution of the system clock.</span></span> <span data-ttu-id="4ba61-125">Windows NT 3.5 이상 버전과 [!INCLUDE[windowsver](../../../includes/windowsver-md.md)] 운영 체제의 경우 시계의 정밀도는 약 10-15밀리초입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-125">On Windows NT 3.5 and later, and [!INCLUDE[windowsver](../../../includes/windowsver-md.md)] operating systems, the clock's resolution is approximately 10-15 milliseconds.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4ba61-126">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="4ba61-126">Compiling the Code</span></span>  
 <span data-ttu-id="4ba61-127">csc.exe 또는 vb.exe를 사용하여 명령줄에서 코드를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-127">Compile the code at the command line using csc.exe or vb.exe.</span></span> <span data-ttu-id="4ba61-128">Visual Studio에서 코드를 컴파일하려면 해당 코드를 콘솔 응용 프로그램 프로젝트 템플릿에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba61-128">To compile the code in Visual Studio, put it in a console application project template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ba61-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ba61-129">See Also</span></span>  
 <xref:System.Globalization.DateTimeFormatInfo>  
 [<span data-ttu-id="4ba61-130">사용자 지정 날짜 및 시간 형식 문자열</span><span class="sxs-lookup"><span data-stu-id="4ba61-130">Custom Date and Time Format Strings</span></span>](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)
