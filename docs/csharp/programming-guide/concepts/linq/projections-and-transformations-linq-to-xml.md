---
title: "프로젝션 및 변환(LINQ to XML)(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: bb0457ab-1823-47e6-9d2d-c93c958cc913
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9dc3f97281f2cd13a44e52c441b537e9e2c640a6
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="projections-and-transformations-linq-to-xml-c"></a><span data-ttu-id="0f874-102">프로젝션 및 변환(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="0f874-102">Projections and Transformations (LINQ to XML) (C#)</span></span>
<span data-ttu-id="0f874-103">이 섹션에서는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 프로젝션 및 변환의 예를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f874-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] projections and transformations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0f874-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="0f874-104">In This Section</span></span>  
  
|<span data-ttu-id="0f874-105">항목</span><span class="sxs-lookup"><span data-stu-id="0f874-105">Topic</span></span>|<span data-ttu-id="0f874-106">설명</span><span class="sxs-lookup"><span data-stu-id="0f874-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="0f874-107">작업: LINQ to XML을 사용하여 사전 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="0f874-107">How to: Work with Dictionaries Using LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-work-with-dictionaries-using-linq-to-xml.md)|<span data-ttu-id="0f874-108">사전을 XML로 변환하는 방법과 XML을 사전으로 변환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f874-108">Shows how to transform dictionaries to XML, and how to transform XML into dictionaries.</span></span>|  
|[<span data-ttu-id="0f874-109">방법: XML 트리의 모양 변환(C#)</span><span class="sxs-lookup"><span data-stu-id="0f874-109">How to: Transform the Shape of an XML Tree (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-transform-the-shape-of-an-xml-tree.md)|<span data-ttu-id="0f874-110">XML 문서의 모양을 변환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f874-110">Shows how to transform the shape of an XML document.</span></span>|  
|[<span data-ttu-id="0f874-111">방법: 프로젝션 형식 제어(C#)</span><span class="sxs-lookup"><span data-stu-id="0f874-111">How to: Control the Type of a Projection (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-control-the-type-of-a-projection.md)|<span data-ttu-id="0f874-112">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 쿼리의 형식을 제어하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f874-112">Shows how to control the type of a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="0f874-113">방법: 새 형식 프로젝션(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="0f874-113">How to: Project a New Type (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-project-a-new-type-linq-to-xml.md)|<span data-ttu-id="0f874-114">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 쿼리에서 사용자 정의 형식의 컬렉션을 프로젝션하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f874-114">Shows how to project a collection of a user-defined type from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="0f874-115">방법: 개체 그래프 프로젝션(C#)</span><span class="sxs-lookup"><span data-stu-id="0f874-115">How to: Project an Object Graph (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-project-an-object-graph.md)|<span data-ttu-id="0f874-116">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 쿼리에서 더 복잡한 개체 그래프를 프로젝션하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f874-116">Shows how to project a more complex object graph from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="0f874-117">방법: 무명 형식 프로젝션(C#)</span><span class="sxs-lookup"><span data-stu-id="0f874-117">How to: Project an Anonymous Type (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-project-an-anonymous-type.md)|<span data-ttu-id="0f874-118">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 쿼리에서 익명 개체의 컬렉션을 프로젝션하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f874-118">Shows how to project a collection of anonymous objects from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="0f874-119">방법: XML에서 텍스트 파일 생성(C#)</span><span class="sxs-lookup"><span data-stu-id="0f874-119">How to: Generate Text Files from XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-generate-text-files-from-xml.md)|<span data-ttu-id="0f874-120">XML 파일을 XML이 아닌 텍스트 파일로 변환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f874-120">Shows how to transform an XML file to a non-XML text file.</span></span>|  
|[<span data-ttu-id="0f874-121">방법: CSV 파일에서 XML 생성(C#)</span><span class="sxs-lookup"><span data-stu-id="0f874-121">How to: Generate XML from CSV Files (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-generate-xml-from-csv-files.md)|<span data-ttu-id="0f874-122">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]를 사용하여 CSV 파일의 구문을 분석하고 이 파일에서 XML을 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f874-122">Shows how to use [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to parse a CSV file and generate XML from it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f874-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f874-123">See Also</span></span>  
 [<span data-ttu-id="0f874-124">XML 트리 쿼리(C#)</span><span class="sxs-lookup"><span data-stu-id="0f874-124">Querying XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)

