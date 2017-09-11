---
title: "방법: XML 리터럴 만들기 (Visual Basic) | Microsoft 문서"
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
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
caps.latest.revision: 17
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
ms.openlocfilehash: 3a7b5dc692317067290b48222ba056d765a449f3
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="d9187-102">방법: XML 리터럴 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9187-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="d9187-103">코드에서 직접 XML 리터럴을 사용 하 여 XML 문서, 조각 또는 요소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9187-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="d9187-104">이 항목의 예제에는 세 개의 자식 요소를 포함 하는 XML 요소를 만드는 방법 및 XML 문서를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9187-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="d9187-105">사용할 수도 있습니다는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Api를 만드는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d9187-105">You can also use the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] APIs to create [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objects.</span></span> <span data-ttu-id="d9187-106">자세한 내용은 <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d9187-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="d9187-107">XML 요소를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d9187-107">To create an XML element</span></span>  
  
-   <span data-ttu-id="d9187-108">실제 XML 구문으로 동일한 XML 리터럴 구문을 사용 하 여 XML 인라인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9187-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     <span data-ttu-id="d9187-109">[!code-vb[VbXMLSamples #&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="d9187-109">[!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]</span></span>  
  
     <span data-ttu-id="d9187-110">코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9187-110">Run the code.</span></span> <span data-ttu-id="d9187-111">이 코드의 출력이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9187-111">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="d9187-112">XML 문서를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d9187-112">To create an XML document</span></span>  
  
-   <span data-ttu-id="d9187-113">XML 문서 인라인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9187-113">Create the XML document inline.</span></span> <span data-ttu-id="d9187-114">다음 코드는 리터럴 구문, XML 선언, 처리 명령, 주석 및 다른 요소를 포함 하는 요소를 가진 XML 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9187-114">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     <span data-ttu-id="d9187-115">[!code-vb[VbXMLSamples #&30;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="d9187-115">[!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]</span></span>  
  
     <span data-ttu-id="d9187-116">코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9187-116">Run the code.</span></span> <span data-ttu-id="d9187-117">이 코드의 출력이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9187-117">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="d9187-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9187-118">See Also</span></span>  
 <span data-ttu-id="d9187-119">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="d9187-119">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="d9187-120"> [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="d9187-120"> [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="d9187-121"> [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="d9187-121"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="d9187-122"> [XML 문서 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)</span><span class="sxs-lookup"><span data-stu-id="d9187-122"> [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)</span></span>
