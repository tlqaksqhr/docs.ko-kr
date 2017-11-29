---
title: "LINQ 및 문자열 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75ddb201-d97a-4f98-8cdf-4ad51714529a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b615f3dc76d72e7f73146498e0143f88c52278a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="linq-and-strings-visual-basic"></a><span data-ttu-id="35934-102">LINQ 및 문자열 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35934-102">LINQ and Strings (Visual Basic)</span></span>
<span data-ttu-id="35934-103">LINQ를 사용하여 문자열 및 문자열 컬렉션을 쿼리하고 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35934-103">LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="35934-104">텍스트 파일의 반구조적 데이터에 특히 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35934-104">It can be especially useful with semi-structured data in text files.</span></span> <span data-ttu-id="35934-105">LINQ 쿼리에 기존의 문자열 함수 및 정규식을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35934-105">LINQ queries can be combined with traditional string functions and regular expressions.</span></span> <span data-ttu-id="35934-106">예를 들어 <xref:System.String.Split%2A> 또는 <xref:System.Text.RegularExpressions.Regex.Split%2A> 메서드를 사용하여 문자열 배열을 만든 다음 LINQ를 사용하여 쿼리하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35934-106">For example, you can use the <xref:System.String.Split%2A> or <xref:System.Text.RegularExpressions.Regex.Split%2A> method to create an array of strings that you can then query or modify by using LINQ.</span></span> <span data-ttu-id="35934-107">LINQ 쿼리의 `where` 절에 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35934-107">You can use the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method in the `where` clause of a LINQ query.</span></span> <span data-ttu-id="35934-108">또한 LINQ를 사용하여 정규식에서 반환된 <xref:System.Text.RegularExpressions.MatchCollection> 결과를 쿼리하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35934-108">And you can use LINQ to query or modify the <xref:System.Text.RegularExpressions.MatchCollection> results returned by a regular expression.</span></span>  
  
 <span data-ttu-id="35934-109">이 섹션에 설명된 기법을 사용하여 반구조적 텍스트 데이터를 XML로 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35934-109">You can also use the techniques described in this section to transform semi-structured text data to XML.</span></span> <span data-ttu-id="35934-110">자세한 내용은 [방법: CSV 파일에서 XML 생성](how-to-generate-xml-from-csv-files.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35934-110">For more information, see [How to: Generate XML from CSV Files](how-to-generate-xml-from-csv-files.md).</span></span>  
  
 <span data-ttu-id="35934-111">이 섹션의 예제는 다음 두 가지 범주로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="35934-111">The examples in this section fall into two categories:</span></span>  
  
## <a name="querying-a-block-of-text"></a><span data-ttu-id="35934-112">텍스트 블록 쿼리</span><span class="sxs-lookup"><span data-stu-id="35934-112">Querying a Block of Text</span></span>  
 <span data-ttu-id="35934-113"><xref:System.String.Split%2A> 메서드 또는 <xref:System.Text.RegularExpressions.Regex.Split%2A> 메서드를 사용하여 더 작은 문자열의 쿼리 가능 배열로 분할하면 텍스트 블록을 쿼리, 분석, 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35934-113">You can query, analyze, and modify text blocks by splitting them into a queryable array of smaller strings by using the <xref:System.String.Split%2A> method or the <xref:System.Text.RegularExpressions.Regex.Split%2A> method.</span></span> <span data-ttu-id="35934-114">소스 텍스트를 단어, 문장, 단락, 페이지 또는 기타 기준으로 분할한 다음 쿼리에 필요한 경우 추가 분할을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35934-114">You can split the source text into words, sentences, paragraphs, pages, or any other criteria, and then perform additional splits if they are required in your query.</span></span>  
  
 [<span data-ttu-id="35934-115">방법: LINQ () (Visual Basic) 문자열에서 단어의 개수</span><span class="sxs-lookup"><span data-stu-id="35934-115">How to: Count Occurrences of a Word in a String (LINQ) (Visual Basic)</span></span>](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 <span data-ttu-id="35934-116">간단한 텍스트 쿼리를 위해 LINQ를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35934-116">Shows how to use LINQ for simple querying over text.</span></span>  
  
 [<span data-ttu-id="35934-117">방법: 지정된 된 단어 (LINQ) (Visual Basic) 집합이 들어 있는 문장 쿼리</span><span class="sxs-lookup"><span data-stu-id="35934-117">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)

 <span data-ttu-id="35934-118">임의의 경계에서 텍스트 파일을 분할하는 방법 및 각 부분에 대해 쿼리를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35934-118">Shows how to split text files on arbitrary boundaries and how to perform queries against each part.</span></span>  
  
 [<span data-ttu-id="35934-119">방법: 문자열 (LINQ) (Visual Basic)에 있는 문자에 대 한 쿼리</span><span class="sxs-lookup"><span data-stu-id="35934-119">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>](how-to-query-for-characters-in-a-string-linq.md)  
 <span data-ttu-id="35934-120">문자열이 쿼리 가능한 형식인지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35934-120">Demonstrates that a string is a queryable type.</span></span>  
  
 [<span data-ttu-id="35934-121">방법: LINQ 쿼리와 정규식 (Visual Basic)를 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="35934-121">How to: Combine LINQ Queries with Regular Expressions (Visual Basic)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)  
 <span data-ttu-id="35934-122">필터링된 쿼리 결과에 대한 복잡한 패턴 일치를 위해 LINQ 쿼리에서 정규식을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35934-122">Shows how to use regular expressions in LINQ queries for complex pattern matching on filtered query results.</span></span>  
  
## <a name="querying-semi-structured-data-in-text-format"></a><span data-ttu-id="35934-123">텍스트 형식의 반구조적 데이터 쿼리</span><span class="sxs-lookup"><span data-stu-id="35934-123">Querying Semi-Structured Data in Text Format</span></span>  
 <span data-ttu-id="35934-124">다양한 형식의 텍스트 파일은 대체로 탭 또는 쉼표로 구분된 파일 또는 고정 길이 줄과 같은 유사한 형식을 가진 일련의 줄로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35934-124">Many different types of text files consist of a series of lines, often with similar formatting, such as tab- or comma-delimited files or fixed-length lines.</span></span> <span data-ttu-id="35934-125">이러한 텍스트 파일을 메모리로 읽어온 후 LINQ를 사용하여 줄을 쿼리 및/또는 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35934-125">After you read such a text file into memory, you can use LINQ to query and/or modify the lines.</span></span> <span data-ttu-id="35934-126">또한 LINQ 쿼리는 여러 소스의 데이터를 결합하는 작업을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="35934-126">LINQ queries also simplify the task of combining data from multiple sources.</span></span>  
  
 [<span data-ttu-id="35934-127">방법: 두 목록 (Visual Basic) (LINQ) 간의 차집합 구하기</span><span class="sxs-lookup"><span data-stu-id="35934-127">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)  
 <span data-ttu-id="35934-128">한 목록에는 있지만 다른 목록에는 없는 모든 문자열을 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35934-128">Shows how to find all the strings that are present in one list but not the other.</span></span>  
  
 [<span data-ttu-id="35934-129">방법: 정렬 또는 필터 텍스트 데이터에서 단어 또는 필드 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35934-129">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 <span data-ttu-id="35934-130">단어 또는 필드에 따라 텍스트 줄을 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35934-130">Shows how to sort text lines based on any word or field.</span></span>  
  
 [<span data-ttu-id="35934-131">방법: 구분 기호로 분리 된 파일 (LINQ) (Visual Basic)의 필드 순서</span><span class="sxs-lookup"><span data-stu-id="35934-131">How to: Reorder the Fields of a Delimited File (LINQ) (Visual Basic)</span></span>](how-to-reorder-the-fields-of-a-delimited-file.md)  
 <span data-ttu-id="35934-132">.csv 파일에서 줄의 필드 순서를 변경하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35934-132">Shows how to reorder fields in a line in a .csv file.</span></span>  
  
 [<span data-ttu-id="35934-133">방법: LINQ () (Visual Basic) 문자열 컬렉션 결합 및 비교</span><span class="sxs-lookup"><span data-stu-id="35934-133">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](how-to-combine-and-compare-string-collections-linq.md)  
 <span data-ttu-id="35934-134">다양한 방법으로 문자열 목록을 조합하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35934-134">Shows how to combine string lists in various ways.</span></span>  
  
 [<span data-ttu-id="35934-135">방법: 여러 원본 (LINQ) (Visual Basic)에서 개체 컬렉션 채우기</span><span class="sxs-lookup"><span data-stu-id="35934-135">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)  
 <span data-ttu-id="35934-136">여러 텍스트 파일을 데이터 소스로 사용하여 개체 컬렉션을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35934-136">Shows how to create object collections by using multiple text files as data sources.</span></span>  
  
 [<span data-ttu-id="35934-137">방법: 서로 다른 파일 (LINQ) (Visual Basic)의 콘텐츠 조인</span><span class="sxs-lookup"><span data-stu-id="35934-137">How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)</span></span>](how-to-join-content-from-dissimilar-files-linq.md)  
 <span data-ttu-id="35934-138">일치하는 키를 사용하여 두 목록의 문자열을 단일 문자열로 결합하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35934-138">Shows how to combine strings in two lists into a single string by using a matching key.</span></span>  
  
 [<span data-ttu-id="35934-139">방법: 한 파일 그룹 (LINQ) (Visual Basic)를 사용 하 여 여러 파일로 분할</span><span class="sxs-lookup"><span data-stu-id="35934-139">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 <span data-ttu-id="35934-140">단일 파일을 데이터 소스로 사용하여 새 파일을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35934-140">Shows how to create new files by using a single file as a data source.</span></span>  
  
 [<span data-ttu-id="35934-141">방법: CSV 텍스트 파일 (LINQ) (Visual Basic)의 열 값 계산</span><span class="sxs-lookup"><span data-stu-id="35934-141">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 <span data-ttu-id="35934-142">.csv 파일의 텍스트 데이터에 대해 수학적 계산을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35934-142">Shows how to perform mathematical computations on text data in .csv files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35934-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35934-143">See Also</span></span>  
 [<span data-ttu-id="35934-144">LINQ(Language-Integrated Query)(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35934-144">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](index.md)  
 [<span data-ttu-id="35934-145">방법: CSV 파일에서 XML 생성</span><span class="sxs-lookup"><span data-stu-id="35934-145">How to: Generate XML from CSV Files</span></span>](how-to-generate-xml-from-csv-files.md)
