---
title: NET Framework의 문자열 조작
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- strings [.NET Framework], manipulating
- manipulating strings
ms.assetid: d4568ff3-9f83-4549-acd8-47aec2194ac0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca4e24cb882daf7efd14da83011d50d05a85232b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567590"
---
# <a name="manipulating-strings-in-net"></a><span data-ttu-id="f608e-102">.NET에서 문자열 조작</span><span class="sxs-lookup"><span data-stu-id="f608e-102">Manipulating Strings in .NET</span></span>
<span data-ttu-id="f608e-103">.NET에서는 효율적으로 문자열을 생성, 비교 및 수정하고 대량 텍스트와 데이터를 빠르게 구문 분석하여 텍스트 패턴을 검색, 제거 및 바꿀 수 있도록 하는 광범위한 루틴 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f608e-103">.NET provides an extensive set of routines that enable you to efficiently create, compare, and modify strings as well as rapidly parse large amounts of text and data to search for, remove, and replace text patterns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f608e-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f608e-104">In This Section</span></span>  
 [<span data-ttu-id="f608e-105">문자열 사용에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="f608e-105">Best Practices for Using Strings</span></span>](../../../docs/standard/base-types/best-practices-strings.md)  
 <span data-ttu-id="f608e-106">.NET의 문자열 정렬, 비교 및 대/소문자 구분 방법을 살펴보고, 문자열 처리 방법 선택을 위한 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f608e-106">Examines string-sorting, comparison, and casing methods in .NET, and provides recommendations for selecting a string-handling method .</span></span>  
  
 [<span data-ttu-id="f608e-107">.NET 정규식</span><span class="sxs-lookup"><span data-stu-id="f608e-107">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)  
 <span data-ttu-id="f608e-108">언어 요소, 정규식 동작 및 예제를 포함하여 .NET 정규식에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f608e-108">Provides detailed information about .NET regular expressions, including language elements, regular expression behavior, and examples.</span></span>  
  
 [<span data-ttu-id="f608e-109">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="f608e-109">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)  
 <span data-ttu-id="f608e-110">바이트 배열에서 새 문자열 생성, 문자열 값 비교 및 기존 문자열 수정을 비롯하여 <xref:System.String?displayProperty=nameWithType> 및 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 클래스에서 제공하는 문자열 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f608e-110">Describes string operations provided by the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes, including creating new strings from arrays of bytes, comparing string values, and modifying existing strings.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f608e-111">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f608e-111">Related Sections</span></span>  
 [<span data-ttu-id="f608e-112">.NET에서 형식 변환</span><span class="sxs-lookup"><span data-stu-id="f608e-112">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="f608e-113">.NET을 사용하여 형식을 변환하는 데 사용하는 기법 및 규칙을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f608e-113">Explains the techniques and rules used to convert types using .NET.</span></span>  
  
 [<span data-ttu-id="f608e-114">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="f608e-114">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="f608e-115">기본 클래스 라이브러리를 사용하여 서식 지정을 구현하는 방법, 숫자 형식의 서식을 지정하는 방법, 문자열 형식의 서식을 지정하는 방법 및 특정 문화권에 대한 서식을 지정하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f608e-115">Provides how to use the base class library to implement formatting, how to format numeric types, how to format string types, and how to format for a specific culture.</span></span>  
  
 [<span data-ttu-id="f608e-116">Parsing Strings</span><span class="sxs-lookup"><span data-stu-id="f608e-116">Parsing Strings</span></span>](../../../docs/standard/base-types/parsing-strings.md)  
 <span data-ttu-id="f608e-117">개체를 해당 개체의 문자열 표현으로 표시되는 값으로 초기화하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f608e-117">Describes how to initialize objects to the values described by string representations of those objects.</span></span> <span data-ttu-id="f608e-118">구문 분석은 형식 지정의 역순으로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f608e-118">Parsing is the inverse operation of formatting.</span></span>
