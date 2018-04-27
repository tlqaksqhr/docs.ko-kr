---
title: XML 요소 리터럴(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
caps.latest.revision: 32
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 58b11c61253b199bdeeb2f373eed5f6a358b9e0e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="48e9b-102">XML 요소 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48e9b-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="48e9b-103">나타내는 리터럴입니다는 <xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48e9b-104">구문</span><span class="sxs-lookup"><span data-stu-id="48e9b-104">Syntax</span></span>  
  
```xml  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a><span data-ttu-id="48e9b-105">요소</span><span class="sxs-lookup"><span data-stu-id="48e9b-105">Parts</span></span>  
  
-   `<`  
  
     <span data-ttu-id="48e9b-106">필수.</span><span class="sxs-lookup"><span data-stu-id="48e9b-106">Required.</span></span> <span data-ttu-id="48e9b-107">시작 요소 태그를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-107">Opens the starting element tag.</span></span>  
  
-   `name`  
  
     <span data-ttu-id="48e9b-108">필수.</span><span class="sxs-lookup"><span data-stu-id="48e9b-108">Required.</span></span> <span data-ttu-id="48e9b-109">요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-109">Name of the element.</span></span> <span data-ttu-id="48e9b-110">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-110">The format is one of the following:</span></span>  
  
    -   <span data-ttu-id="48e9b-111">형식 요소 이름에 대 한 리터럴 텍스트 `[ePrefix:]eName`, 여기서:</span><span class="sxs-lookup"><span data-stu-id="48e9b-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>  
  
        |<span data-ttu-id="48e9b-112">파트</span><span class="sxs-lookup"><span data-stu-id="48e9b-112">Part</span></span>|<span data-ttu-id="48e9b-113">설명</span><span class="sxs-lookup"><span data-stu-id="48e9b-113">Description</span></span>|  
        |---|---|  
        |`ePrefix`|<span data-ttu-id="48e9b-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-114">Optional.</span></span> <span data-ttu-id="48e9b-115">요소에 대 한 XML 네임 스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="48e9b-116">전역으로 정의 된 XML 네임 스페이스 여야 합니다는 `Imports` 문 파일에서 또는 프로젝트 수준 또는 로컬이 요소 또는 부모 요소에 정의 된 XML 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`eName`|<span data-ttu-id="48e9b-117">필수.</span><span class="sxs-lookup"><span data-stu-id="48e9b-117">Required.</span></span> <span data-ttu-id="48e9b-118">요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-118">Name of the element.</span></span> <span data-ttu-id="48e9b-119">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="48e9b-120">-리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-120">-   Literal text.</span></span> <span data-ttu-id="48e9b-121">참조 [선언 된 XML 요소 및 특성의 이름을](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="48e9b-122">포함 형식의 식이 `<%= eNameExp %>`합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-122">-   Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="48e9b-123">유형의 `eNameExp` 해야 `String` 또는 형식으로 암시적으로 변환할 수 있는 <xref:System.Xml.Linq.XName>합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
  
    -   <span data-ttu-id="48e9b-124">형식의 식이 포함 된 `<%= nameExp %>`합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="48e9b-125">유형의 `nameExp` 해야 `String` 또는 형식으로 암시적으로 변환할 <xref:System.Xml.Linq.XName>합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="48e9b-126">요소의 닫는 태그에서 포함된 식을 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-126">An embedded expression is not allowed in a closing tag of an element.</span></span>  
  
-   `attributeList`  
  
     <span data-ttu-id="48e9b-127">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-127">Optional.</span></span> <span data-ttu-id="48e9b-128">리터럴에서 선언 된 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-128">List of attributes declared in the literal.</span></span>  
  
     `attribute [ attribute ... ]`  
  
     <span data-ttu-id="48e9b-129">각 `attribute` 다음 구문 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-129">Each `attribute` has one of the following syntaxes:</span></span>  
  
    -   <span data-ttu-id="48e9b-130">특성 형식 할당 `[aPrefix:]aName=aValue`, 여기서:</span><span class="sxs-lookup"><span data-stu-id="48e9b-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>  
  
        |<span data-ttu-id="48e9b-131">파트</span><span class="sxs-lookup"><span data-stu-id="48e9b-131">Part</span></span>|<span data-ttu-id="48e9b-132">설명</span><span class="sxs-lookup"><span data-stu-id="48e9b-132">Description</span></span>|  
        |---|---|  
        |`aPrefix`|<span data-ttu-id="48e9b-133">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-133">Optional.</span></span> <span data-ttu-id="48e9b-134">특성에 대 한 XML 네임 스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="48e9b-135">전역으로 정의 된 XML 네임 스페이스 여야 합니다는 `Imports` 문이나이 요소 또는 부모 요소에 정의 된 로컬 XML 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`aName`|<span data-ttu-id="48e9b-136">필수.</span><span class="sxs-lookup"><span data-stu-id="48e9b-136">Required.</span></span> <span data-ttu-id="48e9b-137">특성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-137">Name of the attribute.</span></span> <span data-ttu-id="48e9b-138">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="48e9b-139">-리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-139">-   Literal text.</span></span> <span data-ttu-id="48e9b-140">참조 [선언 된 XML 요소 및 특성의 이름을](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="48e9b-141">포함 형식의 식이 `<%= aNameExp %>`합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-141">-   Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="48e9b-142">유형의 `aNameExp` 해야 `String` 또는 형식으로 암시적으로 변환할 수 있는 <xref:System.Xml.Linq.XName>합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
        |`aValue`|<span data-ttu-id="48e9b-143">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-143">Optional.</span></span> <span data-ttu-id="48e9b-144">특성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-144">Value of the attribute.</span></span> <span data-ttu-id="48e9b-145">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="48e9b-146">-따옴표로 묶인 리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-146">-   Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="48e9b-147">포함 형식의 식이 `<%= aValueExp %>`합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-147">-   Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="48e9b-148">모든 형식이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-148">Any type is allowed.</span></span>|  
  
    -   <span data-ttu-id="48e9b-149">형식의 식이 포함 된 `<%= aExp %>`합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-149">Embedded expression of the form `<%= aExp %>`.</span></span>  
  
-   `/>`  
  
     <span data-ttu-id="48e9b-150">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-150">Optional.</span></span> <span data-ttu-id="48e9b-151">요소 콘텐츠가 없는 빈 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-151">Indicates that the element is an empty element, without content.</span></span>  
  
-   `>`  
  
     <span data-ttu-id="48e9b-152">필수.</span><span class="sxs-lookup"><span data-stu-id="48e9b-152">Required.</span></span> <span data-ttu-id="48e9b-153">초보 또는 빈 요소 태그를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-153">Ends the beginning or empty element tag.</span></span>  
  
-   `elementContents`  
  
     <span data-ttu-id="48e9b-154">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-154">Optional.</span></span> <span data-ttu-id="48e9b-155">콘텐츠 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-155">Content of the element.</span></span>  
  
     `content [ content ... ]`  
  
     <span data-ttu-id="48e9b-156">각 `content` 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-156">Each `content` can be one of the following:</span></span>  
  
    -   <span data-ttu-id="48e9b-157">리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-157">Literal text.</span></span> <span data-ttu-id="48e9b-158">모든 공백을 `elementContents` 리터럴 모든 텍스트가 있는 경우 의미를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>  
  
    -   <span data-ttu-id="48e9b-159">형식의 식이 포함 된 `<%= contentExp %>`합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-159">Embedded expression of the form `<%= contentExp %>`.</span></span>  
  
    -   <span data-ttu-id="48e9b-160">XML 요소 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-160">XML element literal.</span></span>  
  
    -   <span data-ttu-id="48e9b-161">XML 주석 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-161">XML comment literal.</span></span> <span data-ttu-id="48e9b-162">참조 [XML 주석 리터럴](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>  
  
    -   <span data-ttu-id="48e9b-163">XML 처리 명령 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-163">XML processing instruction literal.</span></span> <span data-ttu-id="48e9b-164">참조 [XML 처리 명령 리터럴](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>  
  
    -   <span data-ttu-id="48e9b-165">XML CDATA 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-165">XML CDATA literal.</span></span> <span data-ttu-id="48e9b-166">참조 [XML CDATA 리터럴](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>  
  
-   `</[name]>`  
  
     <span data-ttu-id="48e9b-167">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-167">Optional.</span></span> <span data-ttu-id="48e9b-168">요소의 닫는 태그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="48e9b-169">선택적 `name` 포함 된 식의 결과 되었을 때 매개 변수는 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48e9b-170">반환 값</span><span class="sxs-lookup"><span data-stu-id="48e9b-170">Return Value</span></span>  
 <span data-ttu-id="48e9b-171"><xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-171">An <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48e9b-172">설명</span><span class="sxs-lookup"><span data-stu-id="48e9b-172">Remarks</span></span>  
 <span data-ttu-id="48e9b-173">XML 요소 리터럴 구문을 사용 하 여 만들려는 <xref:System.Xml.Linq.XElement> 코드에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48e9b-174">XML 리터럴 줄 연속 문자를 사용 하지 않고 여러 줄을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="48e9b-175">이 기능을 사용 하면 XML 문서에서 콘텐츠를 복사 하 고 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="48e9b-176">포함 형식의 식이 `<%= exp %>` XML 요소 리터럴에에 동적 정보를 추가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="48e9b-177">자세한 내용은 참조 [XML의 포함 식](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="48e9b-178">Visual Basic 컴파일러는 XML 요소 리터럴에 대 한 호출으로 변환 된 <xref:System.Xml.Linq.XElement.%23ctor%2A> 생성자 및 필요한 경우는 <xref:System.Xml.Linq.XAttribute.%23ctor%2A> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="48e9b-179">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="48e9b-179">XML Namespaces</span></span>  
 <span data-ttu-id="48e9b-180">XML 네임 스페이스 접두사는 코드에서 여러 번 같은 네임 스페이스에서 요소와 XML 리터럴을 만들 수 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="48e9b-181">사용 하 여 정의 하는 전역 XML 네임 스페이스 접두사를 사용할 수는 `Imports` 문이나 로컬 접두사를 사용 하 여 정의 `xmlns:xmlPrefix="xmlNamespace"` 특성 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="48e9b-182">자세한 내용은 참조 [Imports 문 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
 <span data-ttu-id="48e9b-183">XML 네임 스페이스에 대 한 범위 지정 규칙에 따라 로컬 접두사가 글로벌 접두사 보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="48e9b-184">그러나 XML 리터럴의 XML 네임 스페이스를 정의 하는 경우 해당 네임 스페이스를 사용할 수 없으면 포함된 된 식에 표시 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="48e9b-185">포함된 식에는 전역 XML 네임 스페이스만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-185">The embedded expression can access only the global XML namespace.</span></span>  
  
 <span data-ttu-id="48e9b-186">Visual Basic 컴파일러는 XML 리터럴에 의해 생성된 된 코드에서 하나를 로컬 네임 스페이스 정의로 사용 되는 각 전역 XML 네임 스페이스를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="48e9b-187">사용 되지 않는 전역 XML 네임 스페이스는 생성된 된 코드에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48e9b-188">예제</span><span class="sxs-lookup"><span data-stu-id="48e9b-188">Example</span></span>  
 <span data-ttu-id="48e9b-189">다음 예제에서는 두 개의 중첩 된 빈 요소가 포함 된 간단한 XML 요소를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>  
  
 [!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]  
  
 <span data-ttu-id="48e9b-190">다음 텍스트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-190">The example displays the following text.</span></span> <span data-ttu-id="48e9b-191">빈 요소의 구조 리터럴 유지 됨을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-191">Notice that the literal preserves the structure of the empty elements.</span></span>  
  
```xml  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a><span data-ttu-id="48e9b-192">예제</span><span class="sxs-lookup"><span data-stu-id="48e9b-192">Example</span></span>  
 <span data-ttu-id="48e9b-193">다음 예제에서는 포함된 식을 사용 하 여 요소 이름을 지정 하 고 속성을 작성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>  
  
 [!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]  
  
 <span data-ttu-id="48e9b-194">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-194">This code displays the following text:</span></span>  
  
```xml  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a><span data-ttu-id="48e9b-195">예제</span><span class="sxs-lookup"><span data-stu-id="48e9b-195">Example</span></span>  
 <span data-ttu-id="48e9b-196">다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="48e9b-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="48e9b-197">그런 다음 네임 스페이스의 접두사를 사용 하 여 XML 리터럴을 만들고를 하 고 요소의 최종 폼이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]  
  
 <span data-ttu-id="48e9b-198">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-198">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="48e9b-199">컴파일러는 XML 네임 스페이스에 대 한 접두사 정의로 전역 XML 네임 스페이스 접두사를 변환 주의 하십시오.</span><span class="sxs-lookup"><span data-stu-id="48e9b-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="48e9b-200">\<ns:middle >에 대 한 XML 네임 스페이스 접두사를 재정의 하는 요소는 \<ns:inner1 > 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="48e9b-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="48e9b-201">그러나는 \<ns:inner2 > 요소에 정의 된 네임 스페이스를 사용 하 여는 `Imports` 문.</span><span class="sxs-lookup"><span data-stu-id="48e9b-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48e9b-202">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48e9b-202">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="48e9b-203">선언된 XML 요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="48e9b-203">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [<span data-ttu-id="48e9b-204">XML 주석 리터럴</span><span class="sxs-lookup"><span data-stu-id="48e9b-204">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [<span data-ttu-id="48e9b-205">XML CDATA 리터럴</span><span class="sxs-lookup"><span data-stu-id="48e9b-205">XML CDATA Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)  
 [<span data-ttu-id="48e9b-206">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="48e9b-206">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="48e9b-207">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="48e9b-207">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="48e9b-208">XML의 포함 식</span><span class="sxs-lookup"><span data-stu-id="48e9b-208">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [<span data-ttu-id="48e9b-209">Imports 문(XML 네임스페이스)</span><span class="sxs-lookup"><span data-stu-id="48e9b-209">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
