---
title: 문화권을 구분하지 않는 문자열 작업
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture, culture-insensitive string operations
- case-sensitive comparisons
- globalization [.NET Framework], culture-insensitive string operations
- strings [.NET Framework], culture-insensitive string operations
- localization [.NET Framework], culture-insensitive string operations
- world-ready applications, culture-insensitive string operations
- culture-sensitive string operations
- culture-insensitive string operations
ms.assetid: e6e2bb94-a95d-44e2-b68c-cfdd1db77784
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 212aa3f00967c04631b80305289c46d818106c44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="culture-insensitive-string-operations"></a><span data-ttu-id="0b904-102">문화권을 구분하지 않는 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="0b904-102">Culture-Insensitive String Operations</span></span>
<span data-ttu-id="0b904-103">문화권 구분 문자열 작업은 문화권별로 사용자에게 결과를 표시하도록 디자인된 응용 프로그램을 만드는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b904-103">Culture-sensitive string operations can be an advantage if you are creating applications designed to display results to users on a per-culture basis.</span></span> <span data-ttu-id="0b904-104">기본적으로 문화권 구분 메서드는 사용할 문화권을 현재 스레드의 <xref:System.Globalization.CultureInfo.CurrentCulture%2A> 속성에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b904-104">By default, culture-sensitive methods obtain the culture to use from the <xref:System.Globalization.CultureInfo.CurrentCulture%2A> property for the current thread.</span></span>  
  
 <span data-ttu-id="0b904-105">문화권 구분 문자열 작업이 항상 필요한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0b904-105">Note that culture-sensitive string operations are not always the desired behavior.</span></span> <span data-ttu-id="0b904-106">결과가 문화권의 영향을 받지 않아야 하는 경우 문화권 구분 작업을 사용하면, 사용자 지정 연결과 정렬 규칙을 포함한 지정된 문화권에서의 응용 프로그램 코드가 제대로 실행되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b904-106">Using culture-sensitive operations when results should be independent of culture can cause application code to fail on cultures with custom case mappings and sorting rules.</span></span> <span data-ttu-id="0b904-107">예제는 [문자열 사용에 대한 모범 사례](../../../docs/standard/base-types/best-practices-strings.md) 문서에서 “현재 문화권을 사용하는 문자열 비교” 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b904-107">For an example, see the "String Comparisons that Use the Current Culture" section in the [Best Practices for Using Strings](../../../docs/standard/base-types/best-practices-strings.md) article.</span></span>  
  
 <span data-ttu-id="0b904-108">문자열 작업의 문화권 구분 여부는 응용 프로그램에서 작업 결과를 사용하는 방식에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b904-108">Whether string operations should be culture-sensitive or culture-insensitive depends on how your application uses the results.</span></span> <span data-ttu-id="0b904-109">사용자에게 결과를 표시하는 문자열 작업은 일반적으로 문화권을 구분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b904-109">String operations that display results to the user should typically be culture-sensitive.</span></span> <span data-ttu-id="0b904-110">예를 들어 응용 프로그램에서 지역화된 문자열 목록을 정렬하여 목록 상자에 표시하는 경우 응용 프로그램에서 문화권 구분 정렬을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b904-110">For example, if an application displays a sorted list of localized strings in a list box, the application should perform a culture-sensitive sort.</span></span>  
  
 <span data-ttu-id="0b904-111">내부적으로 사용되는 문자열 작업의 결과는 일반적으로 문화권을 구분하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b904-111">Results of string operations that are used internally should typically be culture-insensitive.</span></span> <span data-ttu-id="0b904-112">일반적으로 응용 프로그램에서 사용자에게 표시되지 않는 파일 이름, 지속성 형식 또는 기호화된 정보로 작업하는 경우 문자열 작업의 결과가 문화권의 영향을 받지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b904-112">In general, if the application is working with file names, persistence formats, or symbolic information that is not displayed to the user, results of string operations should not vary by culture.</span></span> <span data-ttu-id="0b904-113">예를 들어, 응용 프로그램이 문자열을 비교하여 인식되는 XML 태그인지 여부를 결정하는 경우 비교 작업은 문화권을 구분하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b904-113">For example, if an application compares a string to determine whether it is a recognized XML tag, the comparison should not be culture-sensitive.</span></span> <span data-ttu-id="0b904-114">또한 문자열 비교 또는 대/소문자 변경 작업의 결과에 따라 보안 결정을 수행하는 경우 <xref:System.Globalization.CultureInfo.CurrentCulture%2A> 값의 영향을 받지 않는 결과를 얻기 위해 문화권을 구분하지 않고 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b904-114">In addition, if a security decision is based on the result of a string comparison or case change operation, the operation should be culture-insensitive to ensure that the result is not affected by the value of <xref:System.Globalization.CultureInfo.CurrentCulture%2A>.</span></span>  
  
 <span data-ttu-id="0b904-115">지역화 및 전역화 문제를 처리하는 코드가 포함된 응용 프로그램을 개발하는지 여부에 관계없이 기본적으로 문화권 구분 결과를 검색하는 .NET Framework 메서드를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b904-115">Whether or not you are developing an application that includes code to handle localization and globalization issues, you should be aware of the .NET Framework methods that retrieve culture-sensitive results by default.</span></span> <span data-ttu-id="0b904-116">이 항목의 목표는 응용 프로그램에서 이러한 메서드를 사용하여 문화권을 구분하지 않는 결과를 얻는 올바른 방법을 보여 주기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0b904-116">The purpose of this topic is to illustrate the correct way for your applications to use these methods to obtain culture-insensitive results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b904-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b904-117">See Also</span></span>  
 [<span data-ttu-id="0b904-118">전역화 및 지역화</span><span class="sxs-lookup"><span data-stu-id="0b904-118">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)
