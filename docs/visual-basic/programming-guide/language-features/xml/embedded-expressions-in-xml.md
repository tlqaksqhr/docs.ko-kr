---
title: XML의 포함 식(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b1cdba0a39a932f143ac98c2514240e1696a8fe0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="5e992-102">XML의 포함 식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e992-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="5e992-103">포함 된 식을 사용 하면 런타임 시 계산 되는 식을 포함 하는 XML 리터럴을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="5e992-104">포함 식 구문은 `<%=` `expression` `%>`, 같습니다 구문에서 사용 되는 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span></span>  
  
 <span data-ttu-id="5e992-105">예를 들어 만들 수 있습니다는 XML 요소 리터럴 리터럴 텍스트 콘텐츠로 포함된 식을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 [!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]  
  
 <span data-ttu-id="5e992-106">경우 `isbnNumber` 12345 정수가 포함 되어 있는 및 `modifiedDate` 날짜에 3/5/2006 때이 코드가 실행 되는 값의 `book` 은:</span><span class="sxs-lookup"><span data-stu-id="5e992-106">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="5e992-107">포함된 식 위치 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="5e992-107">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="5e992-108">포함된 식은 XML 리터럴 식에서 특정 위치에만 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-108">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="5e992-109">식 형식 되는 식 위치 제어를 반환할 수 있습니다 및 방법을 `Nothing` 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-109">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="5e992-110">다음 표에서 허용 되는 위치 및 포함 된 식의 형식에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-110">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="5e992-111">리터럴에 위치</span><span class="sxs-lookup"><span data-stu-id="5e992-111">Location in literal</span></span>|<span data-ttu-id="5e992-112">식의 형식</span><span class="sxs-lookup"><span data-stu-id="5e992-112">Type of expression</span></span>|<span data-ttu-id="5e992-113">처리`Nothing`</span><span class="sxs-lookup"><span data-stu-id="5e992-113">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="5e992-114">XML 요소 이름</span><span class="sxs-lookup"><span data-stu-id="5e992-114">XML element name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="5e992-115">오류</span><span class="sxs-lookup"><span data-stu-id="5e992-115">Error</span></span>|  
|<span data-ttu-id="5e992-116">XML 요소 내용</span><span class="sxs-lookup"><span data-stu-id="5e992-116">XML element content</span></span>|<span data-ttu-id="5e992-117">`Object`배열 또는`Object`</span><span class="sxs-lookup"><span data-stu-id="5e992-117">`Object` or array of `Object`</span></span>|<span data-ttu-id="5e992-118">무시됨</span><span class="sxs-lookup"><span data-stu-id="5e992-118">Ignored</span></span>|  
|<span data-ttu-id="5e992-119">XML 요소 특성 이름</span><span class="sxs-lookup"><span data-stu-id="5e992-119">XML element attribute name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="5e992-120">오류, 아니면 특성 값`Nothing`</span><span class="sxs-lookup"><span data-stu-id="5e992-120">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="5e992-121">XML 요소 특성 값</span><span class="sxs-lookup"><span data-stu-id="5e992-121">XML element attribute value</span></span>|`Object`|<span data-ttu-id="5e992-122">특성 선언이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-122">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="5e992-123">XML 요소 특성</span><span class="sxs-lookup"><span data-stu-id="5e992-123">XML element attribute</span></span>|<span data-ttu-id="5e992-124"><xref:System.Xml.Linq.XAttribute>또는 컬렉션<xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="5e992-124"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="5e992-125">무시됨</span><span class="sxs-lookup"><span data-stu-id="5e992-125">Ignored</span></span>|  
|<span data-ttu-id="5e992-126">XML 문서 루트 요소</span><span class="sxs-lookup"><span data-stu-id="5e992-126">XML document root element</span></span>|<span data-ttu-id="5e992-127"><xref:System.Xml.Linq.XElement>하나의 컬렉션 또는 <xref:System.Xml.Linq.XElement> 개체와 임의 개수의 <xref:System.Xml.Linq.XProcessingInstruction> 및 <xref:System.Xml.Linq.XComment> 개체</span><span class="sxs-lookup"><span data-stu-id="5e992-127"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="5e992-128">무시됨</span><span class="sxs-lookup"><span data-stu-id="5e992-128">Ignored</span></span>|  
  
-   <span data-ttu-id="5e992-129">XML 요소 이름에 포함 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="5e992-129">Example of an embedded expression in an XML element name:</span></span>  
  
     [!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]  
  
-   <span data-ttu-id="5e992-130">XML 요소의 내용에 포함 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="5e992-130">Example of an embedded expression in the content of an XML element:</span></span>  
  
     [!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]  
  
-   <span data-ttu-id="5e992-131">XML 요소 특성 이름에 포함 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="5e992-131">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     [!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]  
  
-   <span data-ttu-id="5e992-132">XML 요소 특성 값에 포함된 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="5e992-132">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     [!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]  
  
-   <span data-ttu-id="5e992-133">XML 요소 특성에 포함 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="5e992-133">Example of an embedded expression in an XML element attribute:</span></span>  
  
     [!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]  
  
-   <span data-ttu-id="5e992-134">XML 문서 루트 요소에 포함된 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="5e992-134">Example of an embedded expression in an XML document root element:</span></span>  
  
     [!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]  
  
 <span data-ttu-id="5e992-135">사용 하도록 설정 하면 `Option Strict`, 컴파일러는 각 포함 된 식의 형식이 필요한 형식으로 확장 되는지를 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-135">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="5e992-136">코드를 실행할 때 확인할 수 있는 XML 문서의 루트 요소에 대 한 유일한 예외는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-136">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="5e992-137">없이 컴파일하면 `Option Strict`, 유형의 식을 포함할 수 `Object` 형식별이 런타임에 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-137">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="5e992-138">콘텐츠는 선택 사항이 위치에 포함 된 식을 포함 `Nothing` 은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-138">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="5e992-139">즉, 특성 값, 해당 요소 콘텐츠를 확인 해야 하 고 배열 요소에는 없는 `Nothing` 는 XML 리터럴을 사용 하기 전에.</span><span class="sxs-lookup"><span data-stu-id="5e992-139">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="5e992-140">요소 및 특성 이름과 같은 값이 될 수 없습니다 필요한 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-140">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="5e992-141">특정 유형의 리터럴 포함된 식을 사용 하는 방법에 대 한 자세한 내용은 참조 [XML 문서 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-141">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="5e992-142">범위 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="5e992-142">Scoping Rules</span></span>  
 <span data-ttu-id="5e992-143">컴파일러가 각 XML 리터럴을 적절 한 리터럴 형식에 대 한 생성자 호출을 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-143">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="5e992-144">리터럴 내용과 XML 리터럴의의 포함된 식 생성자에 인수로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-144">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="5e992-145">즉, 모든 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 프로그래밍 요소는 XML 리터럴을 사용할 수 있는 해당 포함된 식을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-145">This means that all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="5e992-146">XML 리터럴 내에서 사용 하 여 접두사를 선언 하는 XML 네임 스페이스에 액세스할 수 있습니다는 `Imports` 문.</span><span class="sxs-lookup"><span data-stu-id="5e992-146">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="5e992-147">새 XML 네임 스페이스 접두사를 선언 하거나 사용 하 여 요소에서 기존 XML 네임 스페이스 접두사를 숨길 수 있습니다는 `xmlns` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-147">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="5e992-148">새 네임 스페이스는 포함된 식에서 XML 리터럴의 아니라 해당 요소의 자식 노드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-148">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e992-149">사용 하 여는 XML 네임 스페이스 접두사를 선언 하는 `xmlns` 네임 스페이스 특성을 특성 값에는 상수 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-149">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="5e992-150">이런 점에서 사용 하는 `xmlns` 사용과 같은 특성은는 `Imports` XML 네임 스페이스를 선언 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-150">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="5e992-151">XML 네임 스페이스 값을 지정 하려면 포함된 식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e992-151">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e992-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e992-152">See Also</span></span>  
 [<span data-ttu-id="5e992-153">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="5e992-153">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="5e992-154">XML 문서 리터럴</span><span class="sxs-lookup"><span data-stu-id="5e992-154">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [<span data-ttu-id="5e992-155">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="5e992-155">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="5e992-156">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="5e992-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="5e992-157">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="5e992-157">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="5e992-158">XML 리터럴 개요</span><span class="sxs-lookup"><span data-stu-id="5e992-158">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
