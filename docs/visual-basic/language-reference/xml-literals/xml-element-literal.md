---
title: "XML 요소 리터럴 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralElement
dev_langs:
- VB
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
caps.latest.revision: 32
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
ms.openlocfilehash: d5cf769a1e3f668652d1eb4551058deba38a8acf
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="eba9b-102">XML 요소 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eba9b-102">XML Element Literal (Visual Basic)</span></span>
<span data-ttu-id="eba9b-103">나타내는 리터럴입니다는 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="eba9b-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eba9b-104">구문</span><span class="sxs-lookup"><span data-stu-id="eba9b-104">Syntax</span></span>  
  
```  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a><span data-ttu-id="eba9b-105">요소</span><span class="sxs-lookup"><span data-stu-id="eba9b-105">Parts</span></span>  
  
-   `<`  
  
     <span data-ttu-id="eba9b-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="eba9b-106">Required.</span></span> <span data-ttu-id="eba9b-107">시작 요소 태그를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-107">Opens the starting element tag.</span></span>  
  
-   `name`  
  
     <span data-ttu-id="eba9b-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="eba9b-108">Required.</span></span> <span data-ttu-id="eba9b-109">요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-109">Name of the element.</span></span> <span data-ttu-id="eba9b-110">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-110">The format is one of the following:</span></span>  
  
    -   <span data-ttu-id="eba9b-111">폼의 요소 이름에 대 한 리터럴 텍스트 [`ePrefix``:`]`eName`, 위치:</span><span class="sxs-lookup"><span data-stu-id="eba9b-111">Literal text for the element name, of the form [`ePrefix``:`]`eName`, where:</span></span>  
  
        |<span data-ttu-id="eba9b-112">파트</span><span class="sxs-lookup"><span data-stu-id="eba9b-112">Part</span></span>|<span data-ttu-id="eba9b-113">설명</span><span class="sxs-lookup"><span data-stu-id="eba9b-113">Description</span></span>|  
        |---|---|  
        |`ePrefix`|<span data-ttu-id="eba9b-114">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="eba9b-114">Optional.</span></span> <span data-ttu-id="eba9b-115">요소에 대 한 XML 네임 스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="eba9b-116">전역으로 정의 된 XML 네임 스페이스 여야는 `Imports` 파일 또는 프로젝트 수준 또는 로컬이 요소 또는 부모 요소에 정의 된 XML 네임 스페이스에서 문입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`eName`|<span data-ttu-id="eba9b-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="eba9b-117">Required.</span></span> <span data-ttu-id="eba9b-118">요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-118">Name of the element.</span></span> <span data-ttu-id="eba9b-119">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="eba9b-120">-리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-120">-   Literal text.</span></span> <span data-ttu-id="eba9b-121">참조 [선언 된 XML 요소 및 특성의 이름을](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="eba9b-122">포함 형식의 식이 `<%=` e`NameExp` `%>`합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-122">-   Embedded expression of the form `<%=` e`NameExp` `%>`.</span></span> <span data-ttu-id="eba9b-123">유형의 `eNameExp` 해야 `String` 이거나 <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> 암시적으로 변환할 수 있는 유형</span><span class="sxs-lookup"><span data-stu-id="eba9b-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
  
    -   <span data-ttu-id="eba9b-124">형식의 식이 포함 된 `<%=` `nameExp` `%>`합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-124">Embedded expression of the form `<%=` `nameExp` `%>`.</span></span> <span data-ttu-id="eba9b-125">유형의 `nameExp` 해야 `String` 또는 <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> 암시적으로 변환할 수 있는 유형</span><span class="sxs-lookup"><span data-stu-id="eba9b-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="eba9b-126">요소의 닫는 태그에서 포함된 식을 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-126">An embedded expression is not allowed in a closing tag of an element.</span></span>  
  
-   `attributeList`  
  
     <span data-ttu-id="eba9b-127">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="eba9b-127">Optional.</span></span> <span data-ttu-id="eba9b-128">리터럴에서 선언 된 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-128">List of attributes declared in the literal.</span></span>  
  
     `attribute [ attribute ... ]`  
  
     <span data-ttu-id="eba9b-129">각 `attribute` 에 다음 구문 중 하나:</span><span class="sxs-lookup"><span data-stu-id="eba9b-129">Each `attribute` has one of the following syntaxes:</span></span>  
  
    -   <span data-ttu-id="eba9b-130">특성 형식의 할당 [`aPrefix``:`]`aName``=``aValue`, 위치:</span><span class="sxs-lookup"><span data-stu-id="eba9b-130">Attribute assignment, of the form [`aPrefix``:`]`aName``=``aValue`, where:</span></span>  
  
        |<span data-ttu-id="eba9b-131">파트</span><span class="sxs-lookup"><span data-stu-id="eba9b-131">Part</span></span>|<span data-ttu-id="eba9b-132">설명</span><span class="sxs-lookup"><span data-stu-id="eba9b-132">Description</span></span>|  
        |---|---|  
        |`aPrefix`|<span data-ttu-id="eba9b-133">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="eba9b-133">Optional.</span></span> <span data-ttu-id="eba9b-134">특성에 대 한 XML 네임 스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="eba9b-135">전역으로 정의 된 XML 네임 스페이스 여야는 `Imports` 문 또는이 요소 또는 부모 요소에 정의 된 로컬 XML 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`aName`|<span data-ttu-id="eba9b-136">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="eba9b-136">Required.</span></span> <span data-ttu-id="eba9b-137">특성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-137">Name of the attribute.</span></span> <span data-ttu-id="eba9b-138">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="eba9b-139">-리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-139">-   Literal text.</span></span> <span data-ttu-id="eba9b-140">참조 [선언 된 XML 요소 및 특성의 이름을](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="eba9b-141">포함 형식의 식이 `<%=` `aNameExp` `%>`합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-141">-   Embedded expression of the form `<%=` `aNameExp` `%>`.</span></span> <span data-ttu-id="eba9b-142">유형의 `aNameExp` 해야 `String` 이거나 <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> 암시적으로 변환할 수 있는 유형</span><span class="sxs-lookup"><span data-stu-id="eba9b-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
        |`aValue`|<span data-ttu-id="eba9b-143">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="eba9b-143">Optional.</span></span> <span data-ttu-id="eba9b-144">특성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-144">Value of the attribute.</span></span> <span data-ttu-id="eba9b-145">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="eba9b-146">-따옴표로 묶인 리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-146">-   Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="eba9b-147">포함 형식의 식이 `<%=` `aValueExp` `%>`합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-147">-   Embedded expression of the form `<%=` `aValueExp` `%>`.</span></span> <span data-ttu-id="eba9b-148">모든 형식이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-148">Any type is allowed.</span></span>|  
  
    -   <span data-ttu-id="eba9b-149">형식의 식이 포함 된 `<%=` `aExp` `%>`합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-149">Embedded expression of the form `<%=` `aExp` `%>`.</span></span>  
  
-   `/>`  
  
     <span data-ttu-id="eba9b-150">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="eba9b-150">Optional.</span></span> <span data-ttu-id="eba9b-151">요소 콘텐츠가 없는 빈 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-151">Indicates that the element is an empty element, without content.</span></span>  
  
-   `>`  
  
     <span data-ttu-id="eba9b-152">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="eba9b-152">Required.</span></span> <span data-ttu-id="eba9b-153">이상 버전 또는 빈 요소 태그를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-153">Ends the beginning or empty element tag.</span></span>  
  
-   `elementContents`  
  
     <span data-ttu-id="eba9b-154">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="eba9b-154">Optional.</span></span> <span data-ttu-id="eba9b-155">요소 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-155">Content of the element.</span></span>  
  
     `content [ content ... ]`  
  
     <span data-ttu-id="eba9b-156">각 `content` 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-156">Each `content` can be one of the following:</span></span>  
  
    -   <span data-ttu-id="eba9b-157">리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-157">Literal text.</span></span> <span data-ttu-id="eba9b-158">에 있는 모든 공백을 `elementContents` 리터럴 텍스트가 있으면 의미를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>  
  
    -   <span data-ttu-id="eba9b-159">형식의 식이 포함 된 `<%=` `contentExp` `%>`합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-159">Embedded expression of the form `<%=` `contentExp` `%>`.</span></span>  
  
    -   <span data-ttu-id="eba9b-160">XML 요소 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-160">XML element literal.</span></span>  
  
    -   <span data-ttu-id="eba9b-161">XML 주석 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-161">XML comment literal.</span></span> <span data-ttu-id="eba9b-162">참조 [XML 주석 리터럴](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>  
  
    -   <span data-ttu-id="eba9b-163">XML 처리 명령 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-163">XML processing instruction literal.</span></span> <span data-ttu-id="eba9b-164">참조 [XML 처리 명령 리터럴](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>  
  
    -   <span data-ttu-id="eba9b-165">XML CDATA 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-165">XML CDATA literal.</span></span> <span data-ttu-id="eba9b-166">참조 [XML CDATA 리터럴](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>  
  
-   <span data-ttu-id="eba9b-167">`</`[`name`]`>`</span><span class="sxs-lookup"><span data-stu-id="eba9b-167">`</`[`name`]`>`</span></span>  
  
     <span data-ttu-id="eba9b-168">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-168">Optional.</span></span> <span data-ttu-id="eba9b-169">닫는 태그를 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-169">Represents the closing tag for the element.</span></span> <span data-ttu-id="eba9b-170">선택적 `name` 포함된 된 식의 결과 경우에 매개 변수가 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-170">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eba9b-171">반환 값</span><span class="sxs-lookup"><span data-stu-id="eba9b-171">Return Value</span></span>  
 <span data-ttu-id="eba9b-172"><xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="eba9b-172">An <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eba9b-173">주의</span><span class="sxs-lookup"><span data-stu-id="eba9b-173">Remarks</span></span>  
 <span data-ttu-id="eba9b-174">XML 요소 리터럴 구문을 사용 하 여 만들려는 <xref:System.Xml.Linq.XElement>코드에서 개체.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="eba9b-174">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eba9b-175">XML 리터럴 줄 연속 문자를 사용 하지 않고 여러 줄을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-175">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="eba9b-176">이 기능을 사용 하는 XML 문서에서 콘텐츠를 복사 하 고에 직접 붙여넣을 수는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-176">This feature enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="eba9b-177">포함 형식의 식이 `<%=` `exp` `%>` 리터럴 XML 요소에 동적 정보를 추가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-177">Embedded expressions of the form `<%=` `exp` `%>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="eba9b-178">자세한 내용은 참조 [XML의 포함 식](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-178">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="eba9b-179">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러 호출으로 XML 요소 리터럴 변환는 <xref:System.Xml.Linq.XElement.%23ctor%2A>생성자 및 필요한 경우는 <xref:System.Xml.Linq.XAttribute.%23ctor%2A>생성자.</xref:System.Xml.Linq.XAttribute.%23ctor%2A> </xref:System.Xml.Linq.XElement.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="eba9b-179">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="eba9b-180">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="eba9b-180">XML Namespaces</span></span>  
 <span data-ttu-id="eba9b-181">XML 네임 스페이스 접두사는 XML 리터럴을 여러 번 코드에서에서 동일한 네임 스페이스의에서 요소를 만들 수 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-181">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="eba9b-182">사용 하 여 정의 하는 전역 XML 네임 스페이스 접두사를 사용할 수는 `Imports` 문 또는 로컬 접두사를 사용 하 여 정의 `xmlns:``xmlPrefix`= "`xmlNamespace`" 특성 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-182">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:``xmlPrefix`="`xmlNamespace`" attribute syntax.</span></span> <span data-ttu-id="eba9b-183">자세한 내용은 참조 [Imports 문 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-183">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
 <span data-ttu-id="eba9b-184">XML 네임 스페이스에 대 한 범위 지정 규칙에 따라 로컬 접두사 전역 접두사 보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-184">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="eba9b-185">그러나 XML 리터럴과 XML 네임 스페이스를 정의 하는 경우 해당 네임 스페이스 사용할 수 없는 경우 포함된 된 식에 표시 되는 식</span><span class="sxs-lookup"><span data-stu-id="eba9b-185">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="eba9b-186">포함된 식에 전역 XML 네임 스페이스에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-186">The embedded expression can access only the global XML namespace.</span></span>  
  
 <span data-ttu-id="eba9b-187">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 변환 하는 XML 리터럴을에서 생성된 된 코드에서 하나의 로컬 네임 스페이스 정의로 사용 되는 각 글로벌 XML 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-187">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="eba9b-188">사용 되지 않는 전역 XML 네임 스페이스는 생성된 된 코드에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-188">Global XML namespaces that are not used do not appear in the generated code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eba9b-189">예제</span><span class="sxs-lookup"><span data-stu-id="eba9b-189">Example</span></span>  
 <span data-ttu-id="eba9b-190">다음 예제에서는 두 개의 중첩 된 빈 요소가 포함 된 간단한 XML 요소를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-190">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>  
  
 <span data-ttu-id="eba9b-191">[!code-vb[VbXMLSamples #&20;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="eba9b-191">[!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]</span></span>  
  
 <span data-ttu-id="eba9b-192">다음 텍스트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-192">The example displays the following text.</span></span> <span data-ttu-id="eba9b-193">공지 리터럴 빈 요소의 구조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-193">Notice that the literal preserves the structure of the empty elements.</span></span>  
  
```  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a><span data-ttu-id="eba9b-194">예제</span><span class="sxs-lookup"><span data-stu-id="eba9b-194">Example</span></span>  
 <span data-ttu-id="eba9b-195">다음 예제에서는 포함된 식을 사용 하 여 요소 이름을 지정 하 고 속성을 작성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-195">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>  
  
 <span data-ttu-id="eba9b-196">[!code-vb[VbXMLSamples #&21;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="eba9b-196">[!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]</span></span>  
  
 <span data-ttu-id="eba9b-197">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-197">This code displays the following text:</span></span>  
  
```  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a><span data-ttu-id="eba9b-198">예제</span><span class="sxs-lookup"><span data-stu-id="eba9b-198">Example</span></span>  
 <span data-ttu-id="eba9b-199">다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="eba9b-199">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="eba9b-200">그런 다음 XML 리터럴을 만드는 데 네임 스페이스의 접두사 값을 사용 하 고 요소의 최종 폼이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-200">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>  
  
 <span data-ttu-id="eba9b-201">[!code-vb[VbXMLSamples #&22;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="eba9b-201">[!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]</span></span>  
  
 <span data-ttu-id="eba9b-202">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-202">This code displays the following text:</span></span>  
  
```  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="eba9b-203">컴파일러 전역 XML 네임 스페이스의 접두사는 XML 네임 스페이스에 대 한 접두사 정의로 변환 함을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-203">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="eba9b-204">\<ns:middle > 요소에 대 한 XML 네임 스페이스 접두사를 다시 정의 \<ns:inner1 > 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-204">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="eba9b-205">그러나는 \<ns:inner2 >에 정의 된 네임 스페이스를 사용 하는 요소는 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="eba9b-205">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eba9b-206">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eba9b-206">See Also</span></span>  
 <span data-ttu-id="eba9b-207"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="eba9b-207"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="eba9b-208"> [선언 된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="eba9b-208"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md) </span></span>  
<span data-ttu-id="eba9b-209"> [XML 주석 리터럴](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span><span class="sxs-lookup"><span data-stu-id="eba9b-209"> [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span></span>  
<span data-ttu-id="eba9b-210"> [XML CDATA 리터럴](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md) </span><span class="sxs-lookup"><span data-stu-id="eba9b-210"> [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md) </span></span>  
<span data-ttu-id="eba9b-211"> [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="eba9b-211"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="eba9b-212"> [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="eba9b-212"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="eba9b-213"> [XML의 포함된 식](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span><span class="sxs-lookup"><span data-stu-id="eba9b-213"> [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span></span>  
<span data-ttu-id="eba9b-214"> [Imports 문(XML 네임스페이스)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)</span><span class="sxs-lookup"><span data-stu-id="eba9b-214"> [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)</span></span>
