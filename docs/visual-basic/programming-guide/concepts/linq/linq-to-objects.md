---
title: "LINQ to Objects (Visual Basic) | Microsoft 문서"
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
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 82094ee6232ef5b1884f1b4b15eacb635be758aa
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="linq-to-objects-visual-basic"></a><span data-ttu-id="f287d-102">LINQ to Objects(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f287d-102">LINQ to Objects (Visual Basic)</span></span>
<span data-ttu-id="f287d-103">LINQ 사용 하는 "LINQ 개체"를 의미를 사용 하 여 쿼리 <xref:System.Collections.IEnumerable>또는 <xref:System.Collections.Generic.IEnumerable%601>컬렉션의 중간 LINQ 공급자 또는와 같은 API를 사용 하지 않고 직접 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) 또는 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="f287d-103">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) or [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span> <span data-ttu-id="f287d-104">LINQ를 사용 하 여 모든 열거 가능 컬렉션을 같은 쿼리를 <xref:System.Collections.Generic.List%601>, <xref:System.Array>, 또는 <xref:System.Collections.Generic.Dictionary%602>.</xref:System.Collections.Generic.Dictionary%602> </xref:System.Array> </xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="f287d-104">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="f287d-105">컬렉션은 사용자 지정 중이거나.NET Framework API에서 반환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f287d-105">The collection may be user-defined or may be returned by a .NET Framework API.</span></span>  
  
 <span data-ttu-id="f287d-106">기본적으로 LINQ to Objects 컬렉션에는 새로운 방법을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f287d-106">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="f287d-107">이전에는 컬렉션에서 데이터를 검색하는 방법을 지정하는 복잡한 `For Each` 루프를 작성해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f287d-107">In the old way, you had to write complex `For Each` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="f287d-108">LINQ 사용 하 여 검색을 설명 하는 선언적 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f287d-108">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="f287d-109">LINQ 쿼리 기존의 비해 세 가지 주요 이점을 제공 하는 또한 `For Each` 루프:</span><span class="sxs-lookup"><span data-stu-id="f287d-109">In addition, LINQ queries offer three main advantages over traditional `For Each` loops:</span></span>  
  
1.  <span data-ttu-id="f287d-110">보다 간결하며 쉽게 읽을 수 있습니다(특히 여러 조건을 필터링하는 경우).</span><span class="sxs-lookup"><span data-stu-id="f287d-110">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
2.  <span data-ttu-id="f287d-111">최소한의 응용 프로그램 코드로도 강력한 필터링, 순서 지정 및 그룹화 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f287d-111">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
3.  <span data-ttu-id="f287d-112">거의 또는 전혀 수정하지 않고도 다른 데이터 소스에 이식할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f287d-112">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="f287d-113">일반적으로 복잡할수록 기존의 반복 기술 대신 LINQ를 사용 하 여 얻게 될 더 큰 이점을, 데이터에 대해 수행 하려는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="f287d-113">In general, the more complex the operation you want to perform on the data, the more benefit you will realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="f287d-114">이 섹션의 목적은 몇 가지 예제를 통해 LINQ를 사용을 보여 주는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f287d-114">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="f287d-115">여기서 설명하는 방식 외에도 다양한 방식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f287d-115">It is not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f287d-116">단원 내용</span><span class="sxs-lookup"><span data-stu-id="f287d-116">In This Section</span></span>  
 [<span data-ttu-id="f287d-117">LINQ 및 문자열 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f287d-117">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 <span data-ttu-id="f287d-118">문자열 및 문자열 컬렉션을 쿼리하고 변환에 LINQ를 사용할 수 있는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f287d-118">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="f287d-119">또한 이러한 원칙을 설명하는 항목의 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f287d-119">Also includes links to topics that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="f287d-120">LINQ 및 리플렉션 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f287d-120">LINQ and Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-reflection.md)  
 <span data-ttu-id="f287d-121">LINQ에 리플렉션을 사용 하는 방법을 보여 주는 샘플에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f287d-121">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 [<span data-ttu-id="f287d-122">LINQ 및 파일 디렉터리 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f287d-122">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)  
 <span data-ttu-id="f287d-123">파일 시스템과 상호 작용 하도록 LINQ를 사용할 수 있는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f287d-123">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="f287d-124">또한 이러한 개념을 설명하는 항목의 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f287d-124">Also includes links to topics that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="f287d-125">방법: LINQ (Visual Basic)를 사용 하 여 ArrayList 쿼리</span><span class="sxs-lookup"><span data-stu-id="f287d-125">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="f287d-126">C#에서 ArrayList를 쿼리 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f287d-126">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="f287d-127">방법: LINQ 쿼리 (Visual Basic)에 대 한 사용자 지정 메서드 추가</span><span class="sxs-lookup"><span data-stu-id="f287d-127">How to: Add Custom Methods for LINQ Queries (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="f287d-128">확장 메서드를 추가 하 여 LINQ 쿼리에 사용할 수 있는 메서드 집합을 확장 하는 방법에 설명 된 <xref:System.Collections.Generic.IEnumerable%601>인터페이스.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="f287d-128">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="f287d-129">언어 통합 쿼리 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f287d-129">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="f287d-130">LINQ를 설명 하 고 쿼리를 수행 하는 코드 예제를 제공 하는 항목에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f287d-130">Provides links to topics that explain LINQ and provide examples of code that perform queries.</span></span>
