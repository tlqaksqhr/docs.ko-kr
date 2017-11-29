---
title: "XML 처리 명령 리터럴(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9ce0f2d0dff80072beefdb4f84643ea28e2cf165
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="3fb47-102">XML 처리 명령 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3fb47-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="3fb47-103">리터럴 나타내는 <xref:System.Xml.Linq.XProcessingInstruction> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fb47-104">구문</span><span class="sxs-lookup"><span data-stu-id="3fb47-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="3fb47-105">요소</span><span class="sxs-lookup"><span data-stu-id="3fb47-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="3fb47-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="3fb47-106">Required.</span></span> <span data-ttu-id="3fb47-107">XML 처리 명령 리터럴의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="3fb47-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="3fb47-108">Required.</span></span> <span data-ttu-id="3fb47-109">이름을 응용 프로그램을 나타내는 처리 명령의 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="3fb47-110">"Xml" 또는 "XML"로 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="3fb47-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-111">Optional.</span></span> <span data-ttu-id="3fb47-112">응용 프로그램이 대상으로 지정 하는 방법을 나타내는 문자열 `piName` XML 문서를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="3fb47-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="3fb47-113">Required.</span></span> <span data-ttu-id="3fb47-114">처리 명령의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fb47-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="3fb47-115">Return Value</span></span>  
 <span data-ttu-id="3fb47-116"><xref:System.Xml.Linq.XProcessingInstruction> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fb47-117">설명</span><span class="sxs-lookup"><span data-stu-id="3fb47-117">Remarks</span></span>  
 <span data-ttu-id="3fb47-118">XML 처리 명령 리터럴 응용 프로그램은 XML 문서를 처리 하는 방법을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="3fb47-119">응용 프로그램에 XML 문서 로드 되 면 문서를 처리할 방법을 결정 하기 위해 XML 처리 명령을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="3fb47-120">응용 프로그램의 의미를 해석 `piName` 및 `piData`합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="3fb47-121">XML 문서 리터럴의 XML 처리 명령 유사한 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="3fb47-122">자세한 내용은 참조 [XML 문서 리터럴](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fb47-123">`piName` 요소는 XML 1.0 사양에 이러한 식별자는 예약 때문에 문자열 "xml" 또는 "XML"로 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="3fb47-124">XML 처리 명령 리터럴을 변수에 할당 하거나 XML 문서 리터럴의에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fb47-125">XML 리터럴은 줄 연속 문자 필요 없이 여러 줄으로 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="3fb47-126">이렇게 하면 XML 문서에서 콘텐츠를 복사 하 고에 직접 붙여넣을 수 있습니다는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 프로그램.</span><span class="sxs-lookup"><span data-stu-id="3fb47-126">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 <span data-ttu-id="3fb47-127">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러에 대 한 호출을 XML 처리 명령 리터럴의 변환는 <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-127">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fb47-128">예제</span><span class="sxs-lookup"><span data-stu-id="3fb47-128">Example</span></span>  
 <span data-ttu-id="3fb47-129">다음 예제에서는 XML 문서에 대 한 스타일 시트를 식별 하는 처리 명령을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3fb47-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3fb47-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3fb47-130">See Also</span></span>  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 [<span data-ttu-id="3fb47-131">XML 문서 리터럴</span><span class="sxs-lookup"><span data-stu-id="3fb47-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [<span data-ttu-id="3fb47-132">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="3fb47-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="3fb47-133">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="3fb47-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
