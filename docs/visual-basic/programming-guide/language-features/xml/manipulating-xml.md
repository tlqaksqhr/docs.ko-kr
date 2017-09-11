---
title: "Visual Basic에서 XML 조작 | Microsoft 문서"
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
helpviewer_keywords:
- LINQ to XML [Visual Basic], manipulating XML
- Visual Basic code, XML
- XML [Visual Basic], manipulating
ms.assetid: da32cffb-198d-41b1-9af3-260fe32e3b7d
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 62b955d78eb507aab4c786e84f3044ba54a38ebc
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="manipulating-xml-in-visual-basic"></a><span data-ttu-id="c93e6-102">Visual Basic에서 XML 조작</span><span class="sxs-lookup"><span data-stu-id="c93e6-102">Manipulating XML in Visual Basic</span></span>
<span data-ttu-id="c93e6-103">사용할 수 있습니다 *XML 리터럴을* 문자열, 파일, 또는 스트림과 같은 외부 소스에서 XML을 로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93e6-103">You can use *XML literals* to load XML from an external source such as a string, file, or stream.</span></span> <span data-ttu-id="c93e6-104">사용할 수 있습니다 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] XML을 조작 하 여 사용 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] XML을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c93e6-104">You can then use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] to manipulate the XML and use [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] to query the XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c93e6-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="c93e6-105">In This Section</span></span>  
 [<span data-ttu-id="c93e6-106">방법: 파일, 문자열 또는 스트림에서 XML 로드</span><span class="sxs-lookup"><span data-stu-id="c93e6-106">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 <span data-ttu-id="c93e6-107">에 XML을 로드 하는 방법을 보여 줍니다는 <xref:System.Xml.Linq.XDocument>또는 <xref:System.Xml.Linq.XElement>텍스트 파일, 문자열 또는 스트림에 개체.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="c93e6-107">Demonstrates how to load XML into an <xref:System.Xml.Linq.XDocument> or <xref:System.Xml.Linq.XElement> object from a text file, string, or stream.</span></span>  
  
 [<span data-ttu-id="c93e6-108">방법: LINQ를 사용하여 XML 변형</span><span class="sxs-lookup"><span data-stu-id="c93e6-108">How to: Transform XML by Using LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-transform-xml-by-using-linq.md)  
 <span data-ttu-id="c93e6-109">콘텐츠를 변환 하는 방법을 보여 줍니다는 <xref:System.Xml.Linq.XDocument>새 XML 문서에는 개체입니다.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="c93e6-109">Demonstrates how to transform the contents of an <xref:System.Xml.Linq.XDocument> object into a new XML document.</span></span>  
  
 [<span data-ttu-id="c93e6-110">방법: XML 리터럴 수정</span><span class="sxs-lookup"><span data-stu-id="c93e6-110">How to: Modify XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-modify-xml-literals.md)  
 <span data-ttu-id="c93e6-111">요소, 특성 및 XML 리터럴에 대 한 값을 수정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c93e6-111">Demonstrates how to modify the elements, attributes, and values in an XML literal.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c93e6-112">관련 단원</span><span class="sxs-lookup"><span data-stu-id="c93e6-112">Related Sections</span></span>  
 [<span data-ttu-id="c93e6-113">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="c93e6-113">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 <span data-ttu-id="c93e6-114">다양 한 XML 액세스 속성을 설명 하는 단원의 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93e6-114">Provides links to sections that describe the various XML access properties.</span></span>  
  
 [<span data-ttu-id="c93e6-115">Visual Basic의 LINQ to XML 개요</span><span class="sxs-lookup"><span data-stu-id="c93e6-115">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="c93e6-116">사용 하 여 소개 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Visual Basic의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93e6-116">Provides an introduction to using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c93e6-117">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="c93e6-117">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="c93e6-118">Visual Basic에서 XML 리터럴을 사용 하 여 소개를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93e6-118">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c93e6-119">Visual Basic의 XML에 액세스</span><span class="sxs-lookup"><span data-stu-id="c93e6-119">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 <span data-ttu-id="c93e6-120">XML 요소 또는 Visual Basic의 문서의 부분에 액세스 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c93e6-120">Demonstrates how to access parts of an XML element or document in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c93e6-121">XML</span><span class="sxs-lookup"><span data-stu-id="c93e6-121">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="c93e6-122">링크를 사용 하는 방법을 설명 하는 섹션이 제공 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Visual Basic의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93e6-122">Provides links to sections that describe how to use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c93e6-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c93e6-123">See Also</span></span>  
 <span data-ttu-id="c93e6-124">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="c93e6-124">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="c93e6-125"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="c93e6-125"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="c93e6-126"> [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="c93e6-126"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
