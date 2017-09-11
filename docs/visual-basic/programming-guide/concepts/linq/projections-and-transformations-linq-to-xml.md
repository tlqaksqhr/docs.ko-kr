---
title: "프로젝션 및 변환 (LINQ to XML) (Visual Basic) | Microsoft 문서"
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
ms.assetid: 297de224-b625-44cf-8c00-186b6189aa0e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 723685400aadbf883d7ad939e6a1dd5bdeb7ba09
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="projections-and-transformations-linq-to-xml-visual-basic"></a><span data-ttu-id="cfb22-102">프로젝션 및 변환 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cfb22-102">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="cfb22-103">이 섹션의 예에서는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 프로젝션 및 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb22-103">This section provides examples of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] projections and transformations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cfb22-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="cfb22-104">In This Section</span></span>  
  
|<span data-ttu-id="cfb22-105">항목</span><span class="sxs-lookup"><span data-stu-id="cfb22-105">Topic</span></span>|<span data-ttu-id="cfb22-106">설명</span><span class="sxs-lookup"><span data-stu-id="cfb22-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="cfb22-107">방법: LINQ to XML (Visual Basic)를 사용 하 여 사전 작업</span><span class="sxs-lookup"><span data-stu-id="cfb22-107">How to: Work with Dictionaries Using LINQ to XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-work-with-dictionaries-using-linq-to-xml.md)|<span data-ttu-id="cfb22-108">사전을 XML로 변형하는 방법과 XML을 사전으로 변형하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfb22-108">Shows how to transform dictionaries to XML, and how to transform XML into dictionaries.</span></span>|  
|[<span data-ttu-id="cfb22-109">방법: (Visual Basic) XML 트리의 모양 변환</span><span class="sxs-lookup"><span data-stu-id="cfb22-109">How to: Transform the Shape of an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-transform-the-shape-of-an-xml-tree.md)|<span data-ttu-id="cfb22-110">XML 문서의 모양을 변형하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfb22-110">Shows how to transform the shape of an XML document.</span></span>|  
|[<span data-ttu-id="cfb22-111">방법: 프로젝션 (Visual Basic) 유형 제어</span><span class="sxs-lookup"><span data-stu-id="cfb22-111">How to: Control the Type of a Projection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-control-the-type-of-a-projection.md)|<span data-ttu-id="cfb22-112">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 쿼리의 형식을 제어하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfb22-112">Shows how to control the type of a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="cfb22-113">방법:는 새 형식 프로젝션 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cfb22-113">How to: Project a New Type (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-project-a-new-type-linq-to-xml.md)|<span data-ttu-id="cfb22-114">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 쿼리에서 사용자 정의 형식의 컬렉션을 프로젝션하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfb22-114">Shows how to project a collection of a user-defined type from a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="cfb22-115">방법: (Visual Basic) 개체 그래프 프로젝션</span><span class="sxs-lookup"><span data-stu-id="cfb22-115">How to: Project an Object Graph (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-project-an-object-graph.md)|<span data-ttu-id="cfb22-116">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 쿼리에서 더 복잡한 개체 그래프를 프로젝션하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfb22-116">Shows how to project a more complex object graph from a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="cfb22-117">방법: 익명 형식 (Visual Basic) 프로젝트</span><span class="sxs-lookup"><span data-stu-id="cfb22-117">How to: Project an Anonymous Type (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-project-an-anonymous-type.md)|<span data-ttu-id="cfb22-118">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 쿼리에서 익명 개체의 컬렉션을 프로젝션하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfb22-118">Shows how to project a collection of anonymous objects from a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="cfb22-119">방법: XML (Visual Basic)에서 텍스트 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb22-119">How to: Generate Text Files from XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-generate-text-files-from-xml.md)|<span data-ttu-id="cfb22-120">XML 파일을 XML이 아닌 텍스트 파일로 변형하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfb22-120">Shows how to transform an XML file to a non-XML text file.</span></span>|  
|[<span data-ttu-id="cfb22-121">방법: CSV 파일 (Visual Basic)에서 XML을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb22-121">How to: Generate XML from CSV Files (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-generate-xml-from-csv-files.md)|<span data-ttu-id="cfb22-122">[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]를 사용하여 CSV 파일의 구문을 분석하고 이 파일에서 XML을 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfb22-122">Shows how to use [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] to parse a CSV file and generate XML from it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cfb22-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cfb22-123">See Also</span></span>  
 [<span data-ttu-id="cfb22-124">XML 트리 쿼리 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cfb22-124">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
