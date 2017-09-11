---
title: ".NET에서 문자열 구문 분석"
description: ".NET에서 문자열 구문 분석"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/22/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 8103c0a6-61d3-40dd-a3e9-2a32ba6a4c05
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: c741ae793d491f691a355df6ad064b81d609c7e5
ms.contentlocale: ko-kr
ms.lasthandoff: 03/03/2017

---

# <a name="parsing-strings-in-net"></a><span data-ttu-id="e99f2-104">.NET에서 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="e99f2-104">Parsing strings in .NET</span></span>

<span data-ttu-id="e99f2-105">구문 분석 작업은 .NET 기본 형식을 나타내는 문자열을 해당 기본 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="e99f2-105">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="e99f2-106">구문 분석 작업을 사용하여 문자열을 부동 소수점 숫자나 날짜 및 시간 값으로 변환하는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e99f2-106">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="e99f2-107">구문 분석 작업을 수행하는 데 가장 일반적으로 사용되는 메서드는 `Parse` 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="e99f2-107">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="e99f2-108">구문 분석은 서식 지정(기본 형식을 문자열 표현으로 변환하는 작업 포함)의 반대 작업으로 많은 동일한 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e99f2-108">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="e99f2-109">서식 지정이 [IFormatProvider](xref:System.IFormatProvider) 인터페이스를 구현하는 개체를 사용하여 문화권을 구분하는 서식 지정 정보를 제공하는 것과 마찬가지로 구문 분석은 [IFormatProvider](xref:System.IFormatProvider) 인터페이스를 구현하는 개체를 사용하여 문자열 표현을 해석하는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e99f2-109">Just as formatting uses an object that implements the [IFormatProvider](xref:System.IFormatProvider) interface to provide culture-sensitive formatting information, parsing also uses an object that implements the [IFormatProvider](xref:System.IFormatProvider) interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="e99f2-110">자세한 내용은 [.NET에서 서식 지정 형식](formatting-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e99f2-110">For more information, see [Formatting Types in .NET](formatting-types.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e99f2-111">단원 내용</span><span class="sxs-lookup"><span data-stu-id="e99f2-111">In This Section</span></span>

<span data-ttu-id="e99f2-112">[.NET에서 숫자 문자열 구문 분석](parsing-numeric.md) - 문자열을 .NET 숫자 형식으로 변환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e99f2-112">[Parsing Numeric Strings in .NET](parsing-numeric.md) - Describes how to convert strings into .NET numeric types.</span></span>

<span data-ttu-id="e99f2-113">[.NET에서 날짜 및 시간 문자열 구문 분석](parsing-datetime.md) - 문자열을 .NET `DateTime` 형식으로 변환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e99f2-113">[Parsing Date and Time Strings in .NET](parsing-datetime.md) - Describes how to convert strings into .NET `DateTime` types.</span></span>

<span data-ttu-id="e99f2-114">[.NET에서 기타 문자열 구문 분석](parsing-other.md) - 문자열을 [Char](xref:System.Char), [부울](xref:System.Boolean), 및 [Enum](xref:System.Enum) 형식으로 변환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e99f2-114">[Parsing Other Strings in .NET](parsing-other.md) - Describes how to convert strings into [Char](xref:System.Char), [Boolean](xref:System.Boolean), and [Enum](xref:System.Enum) types.</span></span>

<span data-ttu-id="e99f2-115">[.NET에서 서식 지정 형식](formatting-types.md) - 서식 지정자 및 서식 공급자와 같은 기본 서식 지정 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e99f2-115">[Formatting Types in .NET](formatting-types.md) - Describes basic formatting concepts like format specifiers and format providers.</span></span>

<span data-ttu-id="e99f2-116">[.NET에서 형식 변환](type-conversion.md) - 형식을 변환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e99f2-116">[Type Conversion in .NET](type-conversion.md) - Describes how to convert types.</span></span>

<span data-ttu-id="e99f2-117">[.NET에서 기본 형식 사용](index.md) - .NET 기본 형식에서 수행할 수 있는 일반적인 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e99f2-117">[Working with Base Types in .NET](index.md) - Describes common operations that you can perform on .NET base types.</span></span>


