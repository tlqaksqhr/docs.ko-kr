---
title: XML 문서 리터럴(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 008b5857418a572046797bf061a05f265669d427
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="6c3a5-102">XML 문서 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c3a5-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="6c3a5-103">리터럴 나타내는 <xref:System.Xml.Linq.XDocument> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c3a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="6c3a5-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="6c3a5-105">요소</span><span class="sxs-lookup"><span data-stu-id="6c3a5-105">Parts</span></span>  
  
|<span data-ttu-id="6c3a5-106">용어</span><span class="sxs-lookup"><span data-stu-id="6c3a5-106">Term</span></span>|<span data-ttu-id="6c3a5-107">정의</span><span class="sxs-lookup"><span data-stu-id="6c3a5-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="6c3a5-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-108">Optional.</span></span> <span data-ttu-id="6c3a5-109">문서의 인코딩을 선언 하는 리터럴 텍스트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="6c3a5-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-110">Optional.</span></span> <span data-ttu-id="6c3a5-111">리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-111">Literal text.</span></span> <span data-ttu-id="6c3a5-112">"Yes" 여야 합니다 또는 "no"입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="6c3a5-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-113">Optional.</span></span> <span data-ttu-id="6c3a5-114">XML 처리 명령 및 XML 주석 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="6c3a5-115">다음 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="6c3a5-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="6c3a5-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="6c3a5-117">각 `piComment` 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="6c3a5-118">-   [XML 처리 명령 리터럴](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="6c3a5-119">-   [XML 주석 리터럴](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="6c3a5-120">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-120">Required.</span></span> <span data-ttu-id="6c3a5-121">문서의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-121">Root element of the document.</span></span> <span data-ttu-id="6c3a5-122">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="6c3a5-123">[XML 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="6c3a5-124">형식의 식이 포함 된 `<%=` `elementExp` `%>`합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="6c3a5-125">`elementExp` 다음 중 하나를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="6c3a5-126"><xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="6c3a5-127">하나를 포함 하는 컬렉션 <xref:System.Xml.Linq.XElement> 개체와 임의 개수의 <xref:System.Xml.Linq.XProcessingInstruction> 및 <xref:System.Xml.Linq.XComment> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="6c3a5-128">자세한 내용은 참조 [XML의 포함 식](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="6c3a5-129">반환 값</span><span class="sxs-lookup"><span data-stu-id="6c3a5-129">Return Value</span></span>  
 <span data-ttu-id="6c3a5-130"><xref:System.Xml.Linq.XDocument> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c3a5-131">설명</span><span class="sxs-lookup"><span data-stu-id="6c3a5-131">Remarks</span></span>  
 <span data-ttu-id="6c3a5-132">XML 문서 리터럴의 시작 부분에 리터럴 XML 선언에 의해 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="6c3a5-133">각 XML 문서 리터럴의 정확히 하나의 루트 XML 요소를 사용 해야 하지만 원하는 수의 XML 처리 명령 및 XML 주석 개뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="6c3a5-134">XML 문서 리터럴에 XML 요소에 나타날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c3a5-135">XML 리터럴 줄 연속 문자를 사용 하지 않고 여러 줄을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="6c3a5-136">이렇게 하면 XML 문서에서 콘텐츠를 복사 하 고에 직접 붙여넣을 수 있습니다는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 프로그램.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-136">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 <span data-ttu-id="6c3a5-137">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 리터럴 XML 문서에 대 한 호출으로 변환 하는 컴파일러는 <xref:System.Xml.Linq.XDocument.%23ctor%2A> 및 <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-137">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c3a5-138">예제</span><span class="sxs-lookup"><span data-stu-id="6c3a5-138">Example</span></span>  
 <span data-ttu-id="6c3a5-139">다음 예에서는 XML 선언, 처리 명령, 설명 및 다른 요소를 포함 하는 요소에 있는 XML 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c3a5-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6c3a5-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c3a5-140">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 <xref:System.Xml.Linq.XComment>  
 <xref:System.Xml.Linq.XDocument>  
 [<span data-ttu-id="6c3a5-141">XML 처리 명령 리터럴</span><span class="sxs-lookup"><span data-stu-id="6c3a5-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)  
 [<span data-ttu-id="6c3a5-142">XML 주석 리터럴</span><span class="sxs-lookup"><span data-stu-id="6c3a5-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [<span data-ttu-id="6c3a5-143">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="6c3a5-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="6c3a5-144">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="6c3a5-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="6c3a5-145">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="6c3a5-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="6c3a5-146">XML의 포함 식</span><span class="sxs-lookup"><span data-stu-id="6c3a5-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
