---
title: "LINQ 및 문자열 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 75ddb201-d97a-4f98-8cdf-4ad51714529a
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 94e9627efb183c08bbb67a7e6e82df9132ebdef2
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="linq-and-strings-visual-basic"></a><span data-ttu-id="03124-102">LINQ 및 문자열 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03124-102">LINQ and Strings (Visual Basic)</span></span>
<span data-ttu-id="03124-103">LINQ는 문자열 및 문자열 컬렉션을 쿼리하고 변환에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03124-103">LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="03124-104">반 구조화 된 데이터를 텍스트 파일에에서 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="03124-104">It can be especially useful with semi-structured data in text files.</span></span> <span data-ttu-id="03124-105">기존의 문자열 함수 및 정규식 LINQ 쿼리를 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03124-105">LINQ queries can be combined with traditional string functions and regular expressions.</span></span> <span data-ttu-id="03124-106">예를 들어, 사용할 수는 <xref:System.String.Split%2A>또는 <xref:System.Text.RegularExpressions.Regex.Split%2A>있습니다 후 쿼리 또는 수정할 수 있는 LINQ를 사용 하 여 문자열의 배열을 만드는 메서드를.</xref:System.Text.RegularExpressions.Regex.Split%2A> </xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="03124-106">For example, you can use the <xref:System.String.Split%2A> or <xref:System.Text.RegularExpressions.Regex.Split%2A> method to create an array of strings that you can then query or modify by using LINQ.</span></span> <span data-ttu-id="03124-107">사용할 수는 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>에서 메서드는 `where` LINQ 쿼리 절.</xref:System.Text.RegularExpressions.Regex.IsMatch%2A></span><span class="sxs-lookup"><span data-stu-id="03124-107">You can use the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method in the `where` clause of a LINQ query.</span></span> <span data-ttu-id="03124-108">LINQ를 사용 하 여를 쿼리하거나 수정 하는 <xref:System.Text.RegularExpressions.MatchCollection>정규식에 의해 반환 된 결과입니다.</xref:System.Text.RegularExpressions.MatchCollection></span><span class="sxs-lookup"><span data-stu-id="03124-108">And you can use LINQ to query or modify the <xref:System.Text.RegularExpressions.MatchCollection> results returned by a regular expression.</span></span>  
  
 <span data-ttu-id="03124-109">또한 반 구조화 된 텍스트 데이터를 XML로 변환 하이 섹션에 설명 된 기법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03124-109">You can also use the techniques described in this section to transform semi-structured text data to XML.</span></span> <span data-ttu-id="03124-110">자세한 내용은 참조 [하는 방법: CSV 파일에서 XML 생성](how-to-generate-xml-from-csv-files.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03124-110">For more information, see [How to: Generate XML from CSV Files](how-to-generate-xml-from-csv-files.md).</span></span>  
  
 <span data-ttu-id="03124-111">이 섹션의 예에서는 두 가지 범주로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03124-111">The examples in this section fall into two categories:</span></span>  
  
## <a name="querying-a-block-of-text"></a><span data-ttu-id="03124-112">텍스트 블록을 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="03124-112">Querying a Block of Text</span></span>  
 <span data-ttu-id="03124-113">쿼리, 분석 및 사용 하 여 쿼리 가능한 작은 문자열 배열로 분할 하 여 텍스트 블록을 수정할 수는 <xref:System.String.Split%2A>메서드 또는 <xref:System.Text.RegularExpressions.Regex.Split%2A>메서드.</xref:System.Text.RegularExpressions.Regex.Split%2A> </xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="03124-113">You can query, analyze, and modify text blocks by splitting them into a queryable array of smaller strings by using the <xref:System.String.Split%2A> method or the <xref:System.Text.RegularExpressions.Regex.Split%2A> method.</span></span> <span data-ttu-id="03124-114">단어, 문장, 단락, 페이지 또는 기타 기준으로 소스 텍스트를 분할 하 고 쿼리에 요구 하는 경우 추가 분할을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03124-114">You can split the source text into words, sentences, paragraphs, pages, or any other criteria, and then perform additional splits if they are required in your query.</span></span>  
  
 [<span data-ttu-id="03124-115">방법: 문자열 (LINQ) (Visual Basic)에서 단어 수 계산</span><span class="sxs-lookup"><span data-stu-id="03124-115">How to: Count Occurrences of a Word in a String (LINQ) (Visual Basic)</span></span>](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 <span data-ttu-id="03124-116">간단 하 게 쿼리 텍스트에 대 한 LINQ를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03124-116">Shows how to use LINQ for simple querying over text.</span></span>  
  
 [<span data-ttu-id="03124-117">방법: 지정된 된 단어 (LINQ) (Visual Basic) 집합이 들어 있는 문장 쿼리</span><span class="sxs-lookup"><span data-stu-id="03124-117">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)

 <span data-ttu-id="03124-118">임의의 경계에서 텍스트 파일을 분할 하는 방법과 각 부분에 대해 쿼리를 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03124-118">Shows how to split text files on arbitrary boundaries and how to perform queries against each part.</span></span>  
  
 [<span data-ttu-id="03124-119">방법: 문자열 (Visual Basic) (LINQ)의 문자에 대 한 쿼리</span><span class="sxs-lookup"><span data-stu-id="03124-119">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>](how-to-query-for-characters-in-a-string-linq.md)  
 <span data-ttu-id="03124-120">문자열이 쿼리 가능한 형식 인지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03124-120">Demonstrates that a string is a queryable type.</span></span>  
  
 [<span data-ttu-id="03124-121">방법: LINQ 쿼리와 정규식 (Visual Basic)를 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="03124-121">How to: Combine LINQ Queries with Regular Expressions (Visual Basic)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)  
 <span data-ttu-id="03124-122">필터링 된 쿼리 결과 대해 일치 하는 복잡 한 패턴에 대 한 LINQ 쿼리에서 정규식을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03124-122">Shows how to use regular expressions in LINQ queries for complex pattern matching on filtered query results.</span></span>  
  
## <a name="querying-semi-structured-data-in-text-format"></a><span data-ttu-id="03124-123">텍스트 형식으로 반 구조화 된 데이터 쿼리</span><span class="sxs-lookup"><span data-stu-id="03124-123">Querying Semi-Structured Data in Text Format</span></span>  
 <span data-ttu-id="03124-124">다양 한 유형의 텍스트 파일 일련의 탭 또는 쉼표로 구분 된 파일 또는 고정 길이 줄과 같은 유사한 형식을 함께 줄으로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03124-124">Many different types of text files consist of a series of lines, often with similar formatting, such as tab- or comma-delimited files or fixed-length lines.</span></span> <span data-ttu-id="03124-125">이러한 텍스트 파일을 메모리로 읽어 들인 후 쿼리 및/또는 줄을 수정 하려면 LINQ를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03124-125">After you read such a text file into memory, you can use LINQ to query and/or modify the lines.</span></span> <span data-ttu-id="03124-126">LINQ 쿼리는 또한 여러 원본의 데이터를 결합 하 여 작업을 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="03124-126">LINQ queries also simplify the task of combining data from multiple sources.</span></span>  
  
 [<span data-ttu-id="03124-127">방법: 두 목록 (Visual Basic) (LINQ) 간의 차집합 구하기</span><span class="sxs-lookup"><span data-stu-id="03124-127">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)  
 <span data-ttu-id="03124-128">다른 리소스는 제외 목록에 있는 모든 문자열을 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03124-128">Shows how to find all the strings that are present in one list but not the other.</span></span>  
  
 [<span data-ttu-id="03124-129">방법: 데이터 정렬 또는 필터링 텍스트에서 단어 또는 필드 (Visual Basic) (LINQ)</span><span class="sxs-lookup"><span data-stu-id="03124-129">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 <span data-ttu-id="03124-130">단어 또는 필드에 따라 텍스트 줄을 정렬 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03124-130">Shows how to sort text lines based on any word or field.</span></span>  
  
 [<span data-ttu-id="03124-131">방법: 구분된 된 파일 (Visual Basic) (LINQ)의 필드 다시 정렬</span><span class="sxs-lookup"><span data-stu-id="03124-131">How to: Reorder the Fields of a Delimited File (LINQ) (Visual Basic)</span></span>](how-to-reorder-the-fields-of-a-delimited-file.md)  
 <span data-ttu-id="03124-132">.Csv 파일의 줄의 필드 순서를 변경 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03124-132">Shows how to reorder fields in a line in a .csv file.</span></span>  
  
 [<span data-ttu-id="03124-133">방법: 문자열 컬렉션 (Visual Basic) (LINQ) 결합 및 비교</span><span class="sxs-lookup"><span data-stu-id="03124-133">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](how-to-combine-and-compare-string-collections-linq.md)  
 <span data-ttu-id="03124-134">다양 한 방법으로 문자열 목록을 조합 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03124-134">Shows how to combine string lists in various ways.</span></span>  
  
 [<span data-ttu-id="03124-135">방법: 개체 컬렉션 (Visual Basic) (LINQ) 여러 소스에서 채우기</span><span class="sxs-lookup"><span data-stu-id="03124-135">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)  
 <span data-ttu-id="03124-136">데이터 원본으로 여러 텍스트 파일을 사용 하 여 개체 컬렉션을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03124-136">Shows how to create object collections by using multiple text files as data sources.</span></span>  
  
 [<span data-ttu-id="03124-137">방법: 서로 다른 파일 (Visual Basic) (LINQ)의 콘텐츠 조인</span><span class="sxs-lookup"><span data-stu-id="03124-137">How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)</span></span>](how-to-join-content-from-dissimilar-files-linq.md)  
 <span data-ttu-id="03124-138">일치 하는 키를 사용 하 여 두 목록에서 문자열을 단일 문자열로 결합 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03124-138">Shows how to combine strings in two lists into a single string by using a matching key.</span></span>  
  
 [<span data-ttu-id="03124-139">방법: 그룹 (LINQ) (Visual Basic)를 사용 하 여 파일을 여러 파일로 분할</span><span class="sxs-lookup"><span data-stu-id="03124-139">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 <span data-ttu-id="03124-140">단일 파일을 데이터 원본으로 사용 하 여 새 파일을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03124-140">Shows how to create new files by using a single file as a data source.</span></span>  
  
 [<span data-ttu-id="03124-141">방법: CSV 텍스트 파일 (Visual Basic) (LINQ)의 열 값 계산</span><span class="sxs-lookup"><span data-stu-id="03124-141">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 <span data-ttu-id="03124-142">.Csv 파일에서 텍스트 데이터에 대해 수학적 계산을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03124-142">Shows how to perform mathematical computations on text data in .csv files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03124-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03124-143">See Also</span></span>  
 <span data-ttu-id="03124-144">[언어 통합 쿼리 (LINQ) (Visual Basic)](index.md) </span><span class="sxs-lookup"><span data-stu-id="03124-144">[Language-Integrated Query (LINQ) (Visual Basic)](index.md) </span></span>  
<span data-ttu-id="03124-145"> [방법: CSV 파일에서 XML 생성](how-to-generate-xml-from-csv-files.md)</span><span class="sxs-lookup"><span data-stu-id="03124-145"> [How to: Generate XML from CSV Files](how-to-generate-xml-from-csv-files.md)</span></span>

