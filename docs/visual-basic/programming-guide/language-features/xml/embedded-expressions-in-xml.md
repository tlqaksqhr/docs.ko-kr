---
title: "XML (Visual Basic)에 포함 되는 식이 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.XmlEmbeddedExpression
dev_langs:
- VB
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
caps.latest.revision: 22
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
ms.openlocfilehash: d24a49f2fa6fd66fe6e4c7724bd4298d65fb7a59
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="c58ab-102">XML의 포함 식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c58ab-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="c58ab-103">포함된 식을 사용 하는 런타임 시 계산 되는 식을 포함 하는 XML 리터럴을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="c58ab-104">포함된 된 식의 구문은 `<%=` `expression` `%>`, 같습니다 구문에서 사용 되는 [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].</span></span>  
  
 <span data-ttu-id="c58ab-105">예를 들어 만들면 XML 요소 리터럴, 리터럴 텍스트 내용으로 포함 된 식을 결합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 <span data-ttu-id="c58ab-106">[!code-vb[VbXMLSamples #&27;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c58ab-106">[!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]</span></span>  
  
 <span data-ttu-id="c58ab-107">경우 `isbnNumber` 12345 정수가 포함 되어 있는 및 `modifiedDate` 날짜에 3/5/2006 때이 코드가 실행 되 면 값 `book` 은:</span><span class="sxs-lookup"><span data-stu-id="c58ab-107">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="c58ab-108">포함된 식 위치 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="c58ab-108">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="c58ab-109">포함된 식 XML 리터럴 식에서 특정 위치에만 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-109">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="c58ab-110">반환할 수 있는 식 형식과 식 위치 컨트롤 및 방법을 `Nothing` 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-110">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="c58ab-111">다음 표에서에 허용 되는 위치 및 포함 된 식의 형식에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-111">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="c58ab-112">리터럴에서의 위치</span><span class="sxs-lookup"><span data-stu-id="c58ab-112">Location in literal</span></span>|<span data-ttu-id="c58ab-113">식의 형식</span><span class="sxs-lookup"><span data-stu-id="c58ab-113">Type of expression</span></span>|<span data-ttu-id="c58ab-114">처리`Nothing`</span><span class="sxs-lookup"><span data-stu-id="c58ab-114">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="c58ab-115">XML 요소 이름</span><span class="sxs-lookup"><span data-stu-id="c58ab-115">XML element name</span></span>|<span data-ttu-id="c58ab-116"><xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="c58ab-116"><xref:System.Xml.Linq.XName></span></span>|<span data-ttu-id="c58ab-117">오류</span><span class="sxs-lookup"><span data-stu-id="c58ab-117">Error</span></span>|  
|<span data-ttu-id="c58ab-118">XML 요소 내용</span><span class="sxs-lookup"><span data-stu-id="c58ab-118">XML element content</span></span>|<span data-ttu-id="c58ab-119">`Object`또는의 배열`Object`</span><span class="sxs-lookup"><span data-stu-id="c58ab-119">`Object` or array of `Object`</span></span>|<span data-ttu-id="c58ab-120">무시됨</span><span class="sxs-lookup"><span data-stu-id="c58ab-120">Ignored</span></span>|  
|<span data-ttu-id="c58ab-121">XML 요소 특성 이름</span><span class="sxs-lookup"><span data-stu-id="c58ab-121">XML element attribute name</span></span>|<span data-ttu-id="c58ab-122"><xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="c58ab-122"><xref:System.Xml.Linq.XName></span></span>|<span data-ttu-id="c58ab-123">오류를 특성 값이 될`Nothing`</span><span class="sxs-lookup"><span data-stu-id="c58ab-123">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="c58ab-124">XML 요소 특성 값</span><span class="sxs-lookup"><span data-stu-id="c58ab-124">XML element attribute value</span></span>|`Object`|<span data-ttu-id="c58ab-125">특성 선언 무시 됨</span><span class="sxs-lookup"><span data-stu-id="c58ab-125">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="c58ab-126">XML 요소 특성</span><span class="sxs-lookup"><span data-stu-id="c58ab-126">XML element attribute</span></span>|<span data-ttu-id="c58ab-127"><xref:System.Xml.Linq.XAttribute>또는의 컬렉션<xref:System.Xml.Linq.XAttribute></xref:System.Xml.Linq.XAttribute></xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="c58ab-127"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="c58ab-128">무시됨</span><span class="sxs-lookup"><span data-stu-id="c58ab-128">Ignored</span></span>|  
|<span data-ttu-id="c58ab-129">XML 문서 루트 요소</span><span class="sxs-lookup"><span data-stu-id="c58ab-129">XML document root element</span></span>|<span data-ttu-id="c58ab-130"><xref:System.Xml.Linq.XElement>또는 한 <xref:System.Xml.Linq.XElement>개체와 임의 개수의 <xref:System.Xml.Linq.XProcessingInstruction>및 <xref:System.Xml.Linq.XComment>개체</xref:System.Xml.Linq.XComment> </xref:System.Xml.Linq.XProcessingInstruction> </xref:System.Xml.Linq.XElement> 의 컬렉션</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="c58ab-130"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="c58ab-131">무시됨</span><span class="sxs-lookup"><span data-stu-id="c58ab-131">Ignored</span></span>|  
  
-   <span data-ttu-id="c58ab-132">XML 요소 이름에 포함 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="c58ab-132">Example of an embedded expression in an XML element name:</span></span>  
  
     <span data-ttu-id="c58ab-133">[!code-vb[VbXMLSamples #&32;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c58ab-133">[!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]</span></span>  
  
-   <span data-ttu-id="c58ab-134">XML 요소의 내용에 포함 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="c58ab-134">Example of an embedded expression in the content of an XML element:</span></span>  
  
     <span data-ttu-id="c58ab-135">[!code-vb[VbXMLSamples #&33;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="c58ab-135">[!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]</span></span>  
  
-   <span data-ttu-id="c58ab-136">XML 요소 특성 이름에 포함 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="c58ab-136">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     <span data-ttu-id="c58ab-137">[!code-vb[VbXMLSamples #&34;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="c58ab-137">[!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]</span></span>  
  
-   <span data-ttu-id="c58ab-138">XML 요소 특성 값에 포함된 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="c58ab-138">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     <span data-ttu-id="c58ab-139">[!code-vb[VbXMLSamples #&35;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="c58ab-139">[!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]</span></span>  
  
-   <span data-ttu-id="c58ab-140">XML 요소 특성에 포함 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="c58ab-140">Example of an embedded expression in an XML element attribute:</span></span>  
  
     <span data-ttu-id="c58ab-141">[!code-vb[VbXMLSamples #&36;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="c58ab-141">[!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]</span></span>  
  
-   <span data-ttu-id="c58ab-142">XML 문서 루트 요소에 포함된 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="c58ab-142">Example of an embedded expression in an XML document root element:</span></span>  
  
     <span data-ttu-id="c58ab-143">[!code-vb[VbXMLSamples #&37;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="c58ab-143">[!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]</span></span>  
  
 <span data-ttu-id="c58ab-144">사용 하도록 설정 하면 `Option Strict`, 컴파일러는 각 포함 된 식의 형식이 필요한 형식으로 확대 변환 되 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-144">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="c58ab-145">유일한 예외는 코드를 실행할 때 확인 되는 XML 문서의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-145">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="c58ab-146">없이 컴파일하면 `Option Strict`, 형식의 식을 포함할 수 `Object` 해당 형식이 런타임에 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-146">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="c58ab-147">콘텐츠는 선택적 위치에 포함 된 식을 포함 `Nothing` 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-147">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="c58ab-148">즉, 특성 값, 해당 요소 콘텐츠를 확인 해야 하 고 배열 요소는 없으면 `Nothing` 는 XML 리터럴을 사용 하기 전에 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-148">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="c58ab-149">요소 및 특성 이름과 같은 값 야 하는 데 필요한 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-149">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="c58ab-150">특정 유형의 리터럴에서 포함된 식을 사용 하는 방법에 대 한 자세한 내용은 참조 [XML 문서 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-150">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="c58ab-151">범위 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="c58ab-151">Scoping Rules</span></span>  
 <span data-ttu-id="c58ab-152">컴파일러는 각 XML 리터럴을 적절 한 리터럴 형식에 대 한 생성자 호출으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-152">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="c58ab-153">리터럴 콘텐츠 및 포함된 식에서 XML 리터럴의 생성자에 인수로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-153">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="c58ab-154">즉, 모든 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그래밍 요소에는 XML 리터럴을 사용할 수 있는 해당 포함된 식에 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-154">This means that all [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="c58ab-155">XML 리터럴 내에서 선언 된 접두사는 XML 네임 스페이스에 액세스할 수 있습니다는 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-155">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="c58ab-156">새 XML 네임 스페이스 접두사를 선언 하거나 요소를 사용 하 여 기존 XML 네임 스페이스 접두사를 숨길 수는 `xmlns` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-156">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="c58ab-157">새 네임 스페이스는 포함된 식에서 XML 리터럴의 아니라 해당 요소의 자식 노드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-157">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c58ab-158">사용 하 여는 XML 네임 스페이스 접두사를 선언 하는 `xmlns` 네임 스페이스 특성을 특성 값에는 상수 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-158">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="c58ab-159">이런 면에서 사용 하 여는 `xmlns` 특성은 사용 하 여 원하는 `Imports` XML 네임 스페이스를 선언 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-159">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="c58ab-160">XML 네임 스페이스 값을 지정 하려면 포함된 식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c58ab-160">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c58ab-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c58ab-161">See Also</span></span>  
 <span data-ttu-id="c58ab-162">[Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="c58ab-162">[Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="c58ab-163"> [XML 문서 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) </span><span class="sxs-lookup"><span data-stu-id="c58ab-163"> [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) </span></span>  
<span data-ttu-id="c58ab-164"> [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="c58ab-164"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="c58ab-165"> [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c58ab-165"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="c58ab-166"> [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="c58ab-166"> [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="c58ab-167"> [XML 리터럴 개요](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c58ab-167"> [XML Literals Overview](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)</span></span>
