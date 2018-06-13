---
title: '방법: XML 리터럴 만들기(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: e5f8429b3ff02678bf8bf3e9e32bef6eb1a56831
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652872"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="e19cb-102">방법: XML 리터럴 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e19cb-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="e19cb-103">코드에서 직접 XML 리터럴을 사용 하 여 XML 문서, 조각 또는 요소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e19cb-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="e19cb-104">이 항목의 예제 XML 문서를 만드는 방법과 세 개의 자식 요소를 포함 하는 XML 요소를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e19cb-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="e19cb-105">사용할 수도 있습니다는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 만들려는 Api [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e19cb-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="e19cb-106">자세한 내용은 <xref:System.Xml.Linq.XElement>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e19cb-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="e19cb-107">XML 요소를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e19cb-107">To create an XML element</span></span>  
  
-   <span data-ttu-id="e19cb-108">실제 XML 구문으로 동일한 XML 리터럴 구문을 사용 하 여 XML 인라인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e19cb-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]  
  
     <span data-ttu-id="e19cb-109">코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e19cb-109">Run the code.</span></span> <span data-ttu-id="e19cb-110">이 코드의 출력은입니다.</span><span class="sxs-lookup"><span data-stu-id="e19cb-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="e19cb-111">XML 문서를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e19cb-111">To create an XML document</span></span>  
  
-   <span data-ttu-id="e19cb-112">XML 문서 인라인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e19cb-112">Create the XML document inline.</span></span> <span data-ttu-id="e19cb-113">다음 코드는 XML 문서를 리터럴 구문, XML 선언, 처리 명령, 설명 및 다른 요소를 포함 하는 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e19cb-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]  
  
     <span data-ttu-id="e19cb-114">코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e19cb-114">Run the code.</span></span> <span data-ttu-id="e19cb-115">이 코드의 출력은입니다.</span><span class="sxs-lookup"><span data-stu-id="e19cb-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="e19cb-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e19cb-116">See Also</span></span>  
 [<span data-ttu-id="e19cb-117">XML</span><span class="sxs-lookup"><span data-stu-id="e19cb-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="e19cb-118">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="e19cb-118">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="e19cb-119">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="e19cb-119">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="e19cb-120">XML 문서 리터럴</span><span class="sxs-lookup"><span data-stu-id="e19cb-120">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
