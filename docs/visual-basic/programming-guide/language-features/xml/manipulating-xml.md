---
title: "Visual Basic에서 XML 조작"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- LINQ to XML [Visual Basic], manipulating XML
- Visual Basic code, XML
- XML [Visual Basic], manipulating
ms.assetid: da32cffb-198d-41b1-9af3-260fe32e3b7d
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 061617524659ac2f8793e2030f26a2d6b2724a64
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="manipulating-xml-in-visual-basic"></a><span data-ttu-id="35873-102">Visual Basic에서 XML 조작</span><span class="sxs-lookup"><span data-stu-id="35873-102">Manipulating XML in Visual Basic</span></span>
<span data-ttu-id="35873-103">사용할 수 있습니다 *XML 리터럴을* 를 문자열, 파일 또는 스트림을 같은 외부 소스에서 XML을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="35873-103">You can use *XML literals* to load XML from an external source such as a string, file, or stream.</span></span> <span data-ttu-id="35873-104">사용할 수 있습니다 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] XML을 조작 하 여 사용할 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] XML을 쿼리하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35873-104">You can then use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to manipulate the XML and use [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] to query the XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35873-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="35873-105">In This Section</span></span>  
 [<span data-ttu-id="35873-106">방법: 파일, 문자열 또는 스트림에서 XML 로드</span><span class="sxs-lookup"><span data-stu-id="35873-106">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 <span data-ttu-id="35873-107">XML을 로드 하는 방법을 보여 줍니다.는 <xref:System.Xml.Linq.XDocument> 또는 <xref:System.Xml.Linq.XElement> 텍스트 파일, 문자열 또는 스트림에 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="35873-107">Demonstrates how to load XML into an <xref:System.Xml.Linq.XDocument> or <xref:System.Xml.Linq.XElement> object from a text file, string, or stream.</span></span>  
  
 [<span data-ttu-id="35873-108">방법: LINQ를 사용하여 XML 변형</span><span class="sxs-lookup"><span data-stu-id="35873-108">How to: Transform XML by Using LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-transform-xml-by-using-linq.md)  
 <span data-ttu-id="35873-109">콘텐츠를 변환 하는 방법을 보여 줍니다.는 <xref:System.Xml.Linq.XDocument> 새 XML 문서에는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="35873-109">Demonstrates how to transform the contents of an <xref:System.Xml.Linq.XDocument> object into a new XML document.</span></span>  
  
 [<span data-ttu-id="35873-110">방법: XML 리터럴 수정</span><span class="sxs-lookup"><span data-stu-id="35873-110">How to: Modify XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-modify-xml-literals.md)  
 <span data-ttu-id="35873-111">요소, 특성 및 XML 리터럴에서 값을 수정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35873-111">Demonstrates how to modify the elements, attributes, and values in an XML literal.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="35873-112">관련 단원</span><span class="sxs-lookup"><span data-stu-id="35873-112">Related Sections</span></span>  
 [<span data-ttu-id="35873-113">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="35873-113">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 <span data-ttu-id="35873-114">다양 한 XML 액세스 속성을 설명 하는 섹션에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="35873-114">Provides links to sections that describe the various XML access properties.</span></span>  
  
 [<span data-ttu-id="35873-115">Visual Basic의 LINQ to XML 개요</span><span class="sxs-lookup"><span data-stu-id="35873-115">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="35873-116">사용 하 여 소개 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Visual Basic의 합니다.</span><span class="sxs-lookup"><span data-stu-id="35873-116">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="35873-117">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="35873-117">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="35873-118">Visual Basic의 XML 리터럴을 사용 하 여에 대 한 소개를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="35873-118">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="35873-119">Visual Basic에서 XML에 액세스</span><span class="sxs-lookup"><span data-stu-id="35873-119">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 <span data-ttu-id="35873-120">XML 요소 또는 Visual Basic의 문서의 일부를 액세스 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35873-120">Demonstrates how to access parts of an XML element or document in Visual Basic.</span></span>  
  
 [<span data-ttu-id="35873-121">XML</span><span class="sxs-lookup"><span data-stu-id="35873-121">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="35873-122">링크를 사용 하는 방법을 설명 하는 절 제공 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Visual Basic의 합니다.</span><span class="sxs-lookup"><span data-stu-id="35873-122">Provides links to sections that describe how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35873-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35873-123">See Also</span></span>  
 [<span data-ttu-id="35873-124">XML</span><span class="sxs-lookup"><span data-stu-id="35873-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="35873-125">LINQ</span><span class="sxs-lookup"><span data-stu-id="35873-125">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="35873-126">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="35873-126">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
