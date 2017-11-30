---
title: "방법: XML 리터럴에 식 포함(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bef4662d69ca7ceddeb2641cbe265d93712c5d16
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="ef651-102">방법: XML 리터럴에 식 포함(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef651-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="ef651-103">XML 리터럴의 XML 문서, 조각 또는 런타임 시 생성 된 콘텐츠가 포함 된 요소를 만드는 포함된 식과 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef651-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="ef651-104">다음 예제에서는 포함된 식을 사용 하 여 런타임에 요소 내용, 특성 및 요소 이름이 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ef651-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="ef651-105">포함 식 구문은 `<%=` `exp` `%>`, 동일한 구문이 되는 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef651-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] uses.</span></span> <span data-ttu-id="ef651-106">자세한 내용은 참조 [XML의 포함 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ef651-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="ef651-107">사용할 수도 있습니다는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 만들려는 Api [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ef651-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="ef651-108">자세한 내용은 <xref:System.Xml.Linq.XElement>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ef651-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="ef651-109">절차</span><span class="sxs-lookup"><span data-stu-id="ef651-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="ef651-110">요소 내용으로 텍스트를 삽입 하려면</span><span class="sxs-lookup"><span data-stu-id="ef651-110">To insert text as element content</span></span>  
  
-   <span data-ttu-id="ef651-111">에 포함 된 텍스트를 삽입 하는 방법을 보여 주는 다음 예제는 `contactName` 열기 및 닫기 이름 요소 간의 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ef651-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     <span data-ttu-id="ef651-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ef651-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="ef651-113">특성 값으로 텍스트를 삽입 하려면</span><span class="sxs-lookup"><span data-stu-id="ef651-113">To insert text as an attribute value</span></span>  
  
-   <span data-ttu-id="ef651-114">에 포함 된 텍스트를 삽입 하는 방법을 보여 주는 다음 예제는 `phoneType` 변수 값으로는 `type` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ef651-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     <span data-ttu-id="ef651-115">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ef651-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="ef651-116">요소 이름에 대 한 텍스트를 삽입 하려면</span><span class="sxs-lookup"><span data-stu-id="ef651-116">To insert text for an element name</span></span>  
  
-   <span data-ttu-id="ef651-117">에 포함 된 텍스트를 삽입 하는 방법을 보여 주는 다음 예제는 `elementName` 요소 이름으로 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ef651-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="ef651-118">사용 하 여 닫아이 방법을 사용 하 여 요소를 만들 때의 \</ > 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="ef651-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     <span data-ttu-id="ef651-119">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ef651-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ef651-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef651-120">See Also</span></span>  
 [<span data-ttu-id="ef651-121">방법: XML 리터럴 만들기</span><span class="sxs-lookup"><span data-stu-id="ef651-121">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)  
 [<span data-ttu-id="ef651-122">XML의 포함 식</span><span class="sxs-lookup"><span data-stu-id="ef651-122">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [<span data-ttu-id="ef651-123">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="ef651-123">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="ef651-124">XML</span><span class="sxs-lookup"><span data-stu-id="ef651-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
