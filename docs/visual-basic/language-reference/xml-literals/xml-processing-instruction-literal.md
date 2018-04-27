---
title: XML 처리 명령 리터럴(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d2df93a46d426358988b3ad7f3161c7ae0c7b9e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="46e03-102">XML 처리 명령 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46e03-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="46e03-103">리터럴 나타내는 <xref:System.Xml.Linq.XProcessingInstruction> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46e03-104">구문</span><span class="sxs-lookup"><span data-stu-id="46e03-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="46e03-105">요소</span><span class="sxs-lookup"><span data-stu-id="46e03-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="46e03-106">필수.</span><span class="sxs-lookup"><span data-stu-id="46e03-106">Required.</span></span> <span data-ttu-id="46e03-107">XML 처리 명령 리터럴의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="46e03-108">필수.</span><span class="sxs-lookup"><span data-stu-id="46e03-108">Required.</span></span> <span data-ttu-id="46e03-109">이름을 응용 프로그램을 나타내는 처리 명령의 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="46e03-110">"Xml" 또는 "XML"로 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="46e03-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-111">Optional.</span></span> <span data-ttu-id="46e03-112">응용 프로그램이 대상으로 지정 하는 방법을 나타내는 문자열 `piName` XML 문서를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="46e03-113">필수.</span><span class="sxs-lookup"><span data-stu-id="46e03-113">Required.</span></span> <span data-ttu-id="46e03-114">처리 명령의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46e03-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="46e03-115">Return Value</span></span>  
 <span data-ttu-id="46e03-116"><xref:System.Xml.Linq.XProcessingInstruction> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46e03-117">설명</span><span class="sxs-lookup"><span data-stu-id="46e03-117">Remarks</span></span>  
 <span data-ttu-id="46e03-118">XML 처리 명령 리터럴 응용 프로그램은 XML 문서를 처리 하는 방법을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="46e03-119">응용 프로그램에 XML 문서 로드 되 면 문서를 처리할 방법을 결정 하기 위해 XML 처리 명령을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="46e03-120">응용 프로그램의 의미를 해석 `piName` 및 `piData`합니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="46e03-121">XML 문서 리터럴의 XML 처리 명령 유사한 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="46e03-122">자세한 내용은 참조 [XML 문서 리터럴](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46e03-123">`piName` 요소는 XML 1.0 사양에 이러한 식별자는 예약 때문에 문자열 "xml" 또는 "XML"로 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="46e03-124">XML 처리 명령 리터럴을 변수에 할당 하거나 XML 문서 리터럴의에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46e03-125">XML 리터럴은 줄 연속 문자 필요 없이 여러 줄으로 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="46e03-126">따라서 XML 문서에서 콘텐츠를 복사 하 고 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="46e03-127">Visual Basic 컴파일러를 호출 하는 XML 처리 명령 리터럴를 변환의 <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46e03-128">예제</span><span class="sxs-lookup"><span data-stu-id="46e03-128">Example</span></span>  
 <span data-ttu-id="46e03-129">다음 예제에서는 XML 문서에 대 한 스타일 시트를 식별 하는 처리 명령을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="46e03-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46e03-130">See Also</span></span>  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 [<span data-ttu-id="46e03-131">XML 문서 리터럴</span><span class="sxs-lookup"><span data-stu-id="46e03-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [<span data-ttu-id="46e03-132">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="46e03-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="46e03-133">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="46e03-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
