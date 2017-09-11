---
title: "XML 주석 리터럴 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralComment
dev_langs:
- VB
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: 19
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
ms.openlocfilehash: ab896399b664c658710c24d9799218ff3d81aecc
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="8108d-102">XML 주석 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8108d-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="8108d-103">리터럴 나타내는 <xref:System.Xml.Linq.XComment>개체.</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="8108d-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8108d-104">구문</span><span class="sxs-lookup"><span data-stu-id="8108d-104">Syntax</span></span>  
  
```  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="8108d-105">요소</span><span class="sxs-lookup"><span data-stu-id="8108d-105">Parts</span></span>  
  
|<span data-ttu-id="8108d-106">용어</span><span class="sxs-lookup"><span data-stu-id="8108d-106">Term</span></span>|<span data-ttu-id="8108d-107">정의</span><span class="sxs-lookup"><span data-stu-id="8108d-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="8108d-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8108d-108">Required.</span></span> <span data-ttu-id="8108d-109">XML 주석 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8108d-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="8108d-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8108d-110">Required.</span></span> <span data-ttu-id="8108d-111">XML 설명에 표시할 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="8108d-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="8108d-112">일련의 두 개의 하이픈 (-) 또는 닫는 태그에 인접 한 하이픈으로 끝날을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8108d-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="8108d-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8108d-113">Required.</span></span> <span data-ttu-id="8108d-114">XML 주석 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8108d-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="8108d-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="8108d-115">Return Value</span></span>  
 <span data-ttu-id="8108d-116"><xref:System.Xml.Linq.XComment>개체.</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="8108d-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8108d-117">주의</span><span class="sxs-lookup"><span data-stu-id="8108d-117">Remarks</span></span>  
 <span data-ttu-id="8108d-118">XML 주석 리터럴 문서 콘텐츠가; 포함 되어 있지 않습니다. 문서에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8108d-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="8108d-119">XML 주석 섹션 시퀀스 "-->"로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="8108d-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="8108d-120">이 다음 사항을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8108d-120">This implies the following points:</span></span>  
  
-   <span data-ttu-id="8108d-121">포함된 식 구분 기호는 유효한 XML 주석 내용 때문에 XML 주석 리터럴 포함된 식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8108d-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
-   <span data-ttu-id="8108d-122">XML 주석 섹션 중첩 될 수 없으므로 때문에 `content` "-->" 값을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8108d-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="8108d-123">XML 주석 리터럴를 변수에 할당할 수 있습니다 또는 리터럴 XML 요소에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8108d-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8108d-124">XML 리터럴 줄 연속 문자를 사용 하지 않고 여러 줄을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8108d-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="8108d-125">이 기능을 사용 하는 XML 문서에서 콘텐츠를 복사 하 고에 직접 붙여넣을 수는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="8108d-125">This feature enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="8108d-126">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 호출을 XML 주석 리터럴 변환 하는 <xref:System.Xml.Linq.XComment.%23ctor%2A>생성자.</xref:System.Xml.Linq.XComment.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="8108d-126">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8108d-127">예제</span><span class="sxs-lookup"><span data-stu-id="8108d-127">Example</span></span>  
 <span data-ttu-id="8108d-128">다음 예제에서는 "This is a comment" 텍스트를 포함 하는 XML 주석을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8108d-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 <span data-ttu-id="8108d-129">[!code-vb[VbXMLSamples #&9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8108d-129">[!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8108d-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8108d-130">See Also</span></span>  
 <span data-ttu-id="8108d-131"><xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="8108d-131"><xref:System.Xml.Linq.XComment></span></span>   
<span data-ttu-id="8108d-132"> [XML 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="8108d-132"> [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="8108d-133"> [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="8108d-133"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="8108d-134"> [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span><span class="sxs-lookup"><span data-stu-id="8108d-134"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span></span>
