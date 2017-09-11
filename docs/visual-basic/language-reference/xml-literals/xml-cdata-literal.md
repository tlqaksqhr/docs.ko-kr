---
title: "XML CDATA 리터럴 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralCdata
dev_langs:
- VB
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
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
ms.openlocfilehash: 6bf12a5dd5b24b0a915cb15f41cb8947c33e94b0
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="a7299-102">XML CDATA 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7299-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="a7299-103">리터럴 나타내는 <xref:System.Xml.Linq.XCData>개체.</xref:System.Xml.Linq.XCData></span><span class="sxs-lookup"><span data-stu-id="a7299-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7299-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7299-104">Syntax</span></span>  
  
```  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="a7299-105">요소</span><span class="sxs-lookup"><span data-stu-id="a7299-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="a7299-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a7299-106">Required.</span></span> <span data-ttu-id="a7299-107">XML CDATA 섹션의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a7299-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="a7299-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a7299-108">Required.</span></span> <span data-ttu-id="a7299-109">XML CDATA 섹션에 표시할 텍스트 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="a7299-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="a7299-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a7299-110">Required.</span></span> <span data-ttu-id="a7299-111">섹션의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a7299-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7299-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="a7299-112">Return Value</span></span>  
 <span data-ttu-id="a7299-113"><xref:System.Xml.Linq.XCData>개체.</xref:System.Xml.Linq.XCData></span><span class="sxs-lookup"><span data-stu-id="a7299-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7299-114">주의</span><span class="sxs-lookup"><span data-stu-id="a7299-114">Remarks</span></span>  
 <span data-ttu-id="a7299-115">XML CDATA 섹션이 포함 되어 있기는 하지만 구문 분석 되지 포함 된 XML로 해야 하는 원시 텍스트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7299-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="a7299-116">XML CDATA 섹션에는 모든 텍스트 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7299-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="a7299-117">예약 된 XML 문자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7299-117">This includes reserved XML characters.</span></span> <span data-ttu-id="a7299-118">XML CDATA 섹션 순서와 함께 종료 "]] >"입니다.</span><span class="sxs-lookup"><span data-stu-id="a7299-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="a7299-119">이 다음 사항을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="a7299-119">This implies the following points:</span></span>  
  
-   <span data-ttu-id="a7299-120">포함된 식 구분 기호는 유효한 XML CDATA 내용 때문에 XML 주석 리터럴 포함된 식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7299-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
-   <span data-ttu-id="a7299-121">XML CDATA 섹션 중첩 될 수 없으므로 때문에 `content` 값을 포함할 수 없습니다 "]] >"입니다.</span><span class="sxs-lookup"><span data-stu-id="a7299-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="a7299-122">XML 주석 리터럴를 변수에 할당 하거나 리터럴 XML 요소에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7299-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7299-123">XML 리터럴 여러 줄으로 나누어 입력할 수 있지만 줄 연속 문자를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7299-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="a7299-124">이렇게 하면 XML 문서에서 콘텐츠를 복사 하 고에 직접 붙여넣을 수 있습니다는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="a7299-124">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="a7299-125">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 변환에 대 한 호출 하는 XML CDATA 리터럴는 <xref:System.Xml.Linq.XCData.%23ctor%2A>생성자.</xref:System.Xml.Linq.XCData.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="a7299-125">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7299-126">예제</span><span class="sxs-lookup"><span data-stu-id="a7299-126">Example</span></span>  
 <span data-ttu-id="a7299-127">다음 예제에서는 텍스트를 포함 하는 CDATA 섹션 "리터럴을 포함 될 수 있습니다 \<XML > 태그"입니다.</span><span class="sxs-lookup"><span data-stu-id="a7299-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 <span data-ttu-id="a7299-128">[!code-vb[VbXMLSamples&23;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a7299-128">[!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7299-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7299-129">See Also</span></span>  
 <span data-ttu-id="a7299-130"><xref:System.Xml.Linq.XCData></xref:System.Xml.Linq.XCData></span><span class="sxs-lookup"><span data-stu-id="a7299-130"><xref:System.Xml.Linq.XCData></span></span>   
<span data-ttu-id="a7299-131"> [XML 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="a7299-131"> [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="a7299-132"> [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="a7299-132"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="a7299-133"> [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span><span class="sxs-lookup"><span data-stu-id="a7299-133"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span></span>
