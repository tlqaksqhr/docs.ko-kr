---
title: '방법: String.Split(C# Guide)를 사용하여 문자열 구문 분석'
description: String.Split은 구분 기호 집합에서 분리된 문자열 배열을 반환합니다. 문자열을 구문 분석하는 쉬운 방법입니다.
ms.date: 01/03/2018
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
ms.custom: mvc
ms.openlocfilehash: e2d788b27f54ac068922f0ebe558a2aea8a475ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-parse-strings-using-stringsplit-c-guide"></a><span data-ttu-id="7150d-104">방법: String.Split(C# Guide)를 사용하여 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="7150d-104">How to: Parse Strings Using String.Split (C# Guide)</span></span>

<span data-ttu-id="7150d-105"><xref:System.String.Split%2A?displayProperty=nameWithType> 메서드는 하나 이상의 구분 기호를 기준으로 입력 문자열을 분할하여 부분 문자열 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-105">The <xref:System.String.Split%2A?displayProperty=nameWithType> method creates an array of substrings by splitting the input string based on one or more delimiters.</span></span> <span data-ttu-id="7150d-106">종종 단어 경계에서 문자열을 분리하는 가장 쉬운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-106">It is often the easiest way to separate a string on word boundaries.</span></span> <span data-ttu-id="7150d-107">다른 특정 문자 또는 문자열에서 문자열을 분할하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-107">It is also used to split strings on other specific characters or strings.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="7150d-108">다음 코드는 공통 어구를 각 단어에 대한 문자열의 배열로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-108">The following code splits a common phrase into an array of strings for each word.</span></span>

[!code-csharp-interactive[split strings on word boundaries](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#1)]

<span data-ttu-id="7150d-109">구분 문자의 모든 인스턴스는 반환된 배열에 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-109">Every instance of a separator character produces a value in the returned array.</span></span> <span data-ttu-id="7150d-110">연속된 구분 문자는 반환된 배열의 값으로 빈 문자열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-110">Consecutive separator characters produce the empty string as a value in the returned array.</span></span>  <span data-ttu-id="7150d-111">다음 예제에서 공백을 구분 기호로 사용하여 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-111">You can see this in the following example, which uses space as a separator:</span></span>

[!code-csharp-interactive[split strings with repeated separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#2)]

<span data-ttu-id="7150d-112">이 동작은 표 형식 데이터를 나타내는 쉼표로 구분된 값(CSV) 파일과 같은 형식을 더 쉽게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-112">This behavior makes it easier for formats like comma separated values (CSV) files representing tabular data.</span></span> <span data-ttu-id="7150d-113">연속된 쉼표는 빈 열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-113">Consecutive commas represent a blank column.</span></span>

<span data-ttu-id="7150d-114">반환된 배열에 빈 문자열을 제외하기 위해 선택적인 <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> 매개 변수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-114">You can pass an optional <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> parameter to exclude any empty strings in the returned array.</span></span> <span data-ttu-id="7150d-115">반환된 컬렉션의 더 복잡한 처리를 위해 [LINQ](../programming-guide/concepts/linq/index.md)를 사용하여 결과 시퀀스를 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-115">For more complicated processing of the returned collection, you can use [LINQ](../programming-guide/concepts/linq/index.md) to manipulate the result sequence.</span></span>    

<span data-ttu-id="7150d-116"><xref:System.String.Split%2A?displayProperty=nameWithType>은 다중 구분 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-116"><xref:System.String.Split%2A?displayProperty=nameWithType> can use multiple separator characters.</span></span> <span data-ttu-id="7150d-117">다음 예제에서는 공백, 쉼표, 마침표, 콜론 및 탭을 사용하며, 모두 이러한 구분 문자를 포함하는 배열에서 <xref:System.String.Split%2A>로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-117">The following example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters, to <xref:System.String.Split%2A>.</span></span>  <span data-ttu-id="7150d-118">코드 맨 아래의 루프는 반환된 배열의 각 단어를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-118">The loop at the bottom of the code displays each of the words in the returned array.</span></span>  

[!code-csharp-interactive[split strings using multiple separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#3)]

<span data-ttu-id="7150d-119">연속되는 모든 구분 기호의 인스턴스는 출력 배열에 빈 문자열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-119">Consecutive instances of any separator produce the empty string in the output array:</span></span>

[!code-csharp-interactive[split strings using multiple consecutive separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#4)]

<span data-ttu-id="7150d-120"><xref:System.String.Split%2A?displayProperty=nameWithType>은 문자열 배열(단일 문자 대신 대상 문자열을 구문 분석하는 구분 기호 역할을 하는 문자 시퀀스)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-120"><xref:System.String.Split%2A?displayProperty=nameWithType> can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>  
  
[!code-csharp-interactive[split strings using strings as separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#5)]

<span data-ttu-id="7150d-121">[GitHub 리포지토리](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings)의 코드를 확인하여 이러한 샘플을 시험해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-121">You can try these samples by looking at the code in our [GitHub repository](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings).</span></span> <span data-ttu-id="7150d-122">또는 샘플을 [zip 파일로](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip) 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7150d-122">Or you can download the samples [as a zip file](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip).</span></span>

## <a name="see-also"></a><span data-ttu-id="7150d-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7150d-123">See Also</span></span>  
 [<span data-ttu-id="7150d-124">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7150d-124">C# Programming Guide</span></span>](../programming-guide/index.md)  
 [<span data-ttu-id="7150d-125">문자열</span><span class="sxs-lookup"><span data-stu-id="7150d-125">Strings</span></span>](../programming-guide/strings/index.md)  
 [<span data-ttu-id="7150d-126">.NET 정규식</span><span class="sxs-lookup"><span data-stu-id="7150d-126">.NET Regular Expressions</span></span>](../../standard/base-types/regular-expressions.md)
