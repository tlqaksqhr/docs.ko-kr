---
title: "방법: XML 리터럴 (Visual Basic) 식 포함 | Microsoft 문서"
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
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: 16
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
ms.openlocfilehash: e4f086b06575cb8300bd65d450cda6b9893bb692
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="15d74-102">방법: XML 리터럴에 식 포함(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15d74-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="15d74-103">XML 리터럴 XML 문서, 조각 또는 런타임 시 생성 된 콘텐츠가 포함 된 요소를 만드는 포함 된 식으로 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d74-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="15d74-104">다음 예제에 포함 된 식을 사용 하 여 런타임에 요소 내용, 특성 및 요소 이름이 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15d74-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="15d74-105">포함된 된 식의 구문은 `<%=` `exp` `%>`, 즉 동일한 구문을 [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d74-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] uses.</span></span> <span data-ttu-id="15d74-106">자세한 내용은 참조 [XML의 포함 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="15d74-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="15d74-107">사용할 수도 있습니다는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Api를 만드는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="15d74-107">You can also use the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] APIs to create [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objects.</span></span> <span data-ttu-id="15d74-108">자세한 내용은 <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15d74-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="15d74-109">절차</span><span class="sxs-lookup"><span data-stu-id="15d74-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="15d74-110">요소 내용으로 텍스트를 삽입 하려면</span><span class="sxs-lookup"><span data-stu-id="15d74-110">To insert text as element content</span></span>  
  
-   <span data-ttu-id="15d74-111">다음 예제에 포함 된 텍스트를 삽입 하는 방법을 보여 줍니다는 `contactName` 열기 및 닫기 이름 요소 간의 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="15d74-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     <span data-ttu-id="15d74-112">[!code-vb[VbXMLSamples #&39;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="15d74-112">[!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]</span></span>  
  
     <span data-ttu-id="15d74-113">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="15d74-113">This example produces the following output:</span></span>  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="15d74-114">특성 값으로 텍스트를 삽입 하려면</span><span class="sxs-lookup"><span data-stu-id="15d74-114">To insert text as an attribute value</span></span>  
  
-   <span data-ttu-id="15d74-115">다음 예제에 포함 된 텍스트를 삽입 하는 방법을 보여 줍니다는 `phoneType` 의 값으로 변수는 `type` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="15d74-115">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     <span data-ttu-id="15d74-116">[!code-vb[VbXMLSamples #&40;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="15d74-116">[!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]</span></span>  
  
     <span data-ttu-id="15d74-117">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="15d74-117">This example produces the following output:</span></span>  
  
    ```  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="15d74-118">요소 이름에 대 한 텍스트를 삽입 하려면</span><span class="sxs-lookup"><span data-stu-id="15d74-118">To insert text for an element name</span></span>  
  
-   <span data-ttu-id="15d74-119">다음 예제에 포함 된 텍스트를 삽입 하는 방법을 보여 줍니다는 `elementName` 요소 이름으로 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="15d74-119">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="15d74-120">이 기술을 사용 하 여 요소를 만들 때 닫아야를 사용 하 여는 \</ > 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="15d74-120">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     <span data-ttu-id="15d74-121">[!code-vb[VbXMLSamples #&41;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="15d74-121">[!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]</span></span>  
  
     <span data-ttu-id="15d74-122">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="15d74-122">This example produces the following output:</span></span>  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="15d74-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15d74-123">See Also</span></span>  
 <span data-ttu-id="15d74-124">[방법: XML 리터럴 만들기](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md) </span><span class="sxs-lookup"><span data-stu-id="15d74-124">[How to: Create XML Literals](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md) </span></span>  
<span data-ttu-id="15d74-125"> [XML의 포함된 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span><span class="sxs-lookup"><span data-stu-id="15d74-125"> [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span></span>  
<span data-ttu-id="15d74-126"> [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="15d74-126"> [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="15d74-127"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)</span><span class="sxs-lookup"><span data-stu-id="15d74-127"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)</span></span>
