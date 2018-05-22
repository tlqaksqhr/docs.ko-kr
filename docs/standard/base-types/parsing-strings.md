---
title: .NET에서 문자열 구문 분석
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a6e0e7e69affd93320ec3f3d73e6254befaf6ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="parsing-strings-in-net"></a><span data-ttu-id="08322-102">.NET에서 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="08322-102">Parsing Strings in .NET</span></span>
<span data-ttu-id="08322-103">구문 분석 작업은 .NET 기본 형식을 나타내는 문자열을 해당 기본 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="08322-103">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="08322-104">구문 분석 작업을 사용하여 문자열을 부동 소수점 숫자나 날짜 및 시간 값으로 변환하는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08322-104">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="08322-105">구문 분석 작업을 수행하는 데 가장 일반적으로 사용되는 메서드는 `Parse` 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="08322-105">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="08322-106">구문 분석은 서식 지정(기본 형식을 문자열 표현으로 변환하는 작업 포함)의 반대 작업으로 많은 동일한 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08322-106">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="08322-107">서식 지정이 <xref:System.IFormatProvider> 인터페이스를 구현하는 개체를 사용하여 문화권을 구분하는 서식 지정 정보를 제공하는 것과 마찬가지로 구문 분석은 <xref:System.IFormatProvider> 인터페이스를 구현하는 개체를 사용하여 문자열 표현을 해석하는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="08322-107">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="08322-108">자세한 내용은 [서식 지정 형식](../../../docs/standard/base-types/formatting-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08322-108">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="08322-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="08322-109">In This Section</span></span>  
 [<span data-ttu-id="08322-110">숫자 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="08322-110">Parsing Numeric Strings</span></span>](../../../docs/standard/base-types/parsing-numeric.md)  
 <span data-ttu-id="08322-111">문자열을 .NET 숫자 형식으로 변환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08322-111">Describes how to convert strings into .NET numeric types.</span></span>  
  
 [<span data-ttu-id="08322-112">날짜 및 시간 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="08322-112">Parsing Date and Time Strings</span></span>](../../../docs/standard/base-types/parsing-datetime.md)  
 <span data-ttu-id="08322-113">문자열을 .NET **DateTime** 형식으로 변환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08322-113">Describes how to convert strings into .NET **DateTime** types.</span></span>  
  
 [<span data-ttu-id="08322-114">기타 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="08322-114">Parsing Other Strings</span></span>](../../../docs/standard/base-types/parsing-other.md)  
 <span data-ttu-id="08322-115">문자열을 **Char**, **부울** 및 **열거형** 형식으로 변환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08322-115">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="08322-116">관련 단원</span><span class="sxs-lookup"><span data-stu-id="08322-116">Related Sections</span></span>  
 [<span data-ttu-id="08322-117">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="08322-117">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="08322-118">형식 지정자 및 형식 공급자와 같은 기본 서식 지정 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08322-118">Describes basic formatting concepts like format specifiers and format providers.</span></span>  
  
 [<span data-ttu-id="08322-119">.NET에서 형식 변환</span><span class="sxs-lookup"><span data-stu-id="08322-119">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="08322-120">형식을 변환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08322-120">Describes how to convert types.</span></span>  
  
 [<span data-ttu-id="08322-121">기본 형식</span><span class="sxs-lookup"><span data-stu-id="08322-121">Base Types</span></span>](../../../docs/standard/base-types/index.md)  
 <span data-ttu-id="08322-122">.NET 기본 형식에 대해 수행할 수 있는 일반적인 작업에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08322-122">Describes common operations that you can perform on .NET base types.</span></span>
