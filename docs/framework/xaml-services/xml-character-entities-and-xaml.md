---
title: XML 문자 엔터티 및 XAML
ms.date: 03/30/2017
f1_keywords:
- '&'
- '&amp'
- '&gt'
- '&lt'
helpviewer_keywords:
- XAML [XAML Services], special characters
- ampersand (&) [XAML Services]
- special characters [XAML Services]
- apostrophe (') [XAML Services]
- greater-than (>) character [XAML Services]
- XAML [XAML Services], quotation mark (")
- XAML [XAML Services], apostrophe (')
- '& (ampersand) [XAML Services]'
- XAML [XAML Services], & (ampersand)
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- less-than (<) character [XAML Services]
ms.assetid: 6896d0ce-74f7-420a-9ab4-de9bbf390e8d
ms.openlocfilehash: 5ef489498cdc8716f7599124138f9ecf8945ac9a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564773"
---
# <a name="xml-character-entities-and-xaml"></a><span data-ttu-id="1e567-102">XML 문자 엔터티 및 XAML</span><span class="sxs-lookup"><span data-stu-id="1e567-102">XML Character Entities and XAML</span></span>
<span data-ttu-id="1e567-103">XAML은 특수 문자를 위해 XML에 정의된 문자 엔터티를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-103">XAML uses character entities defined in XML for special characters.</span></span> <span data-ttu-id="1e567-104">이 항목에서는 일부 특정 문자 엔터티 및 XAML의 다른 XML 개념에 대한 일반적인 고려 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-104">This topic describes some specific character entities and general considerations for other XML concepts in XAML.</span></span>  
  
<a name="character_entities_and_escaping_issues_that_are_unique_to_xaml"></a>   
## <a name="character-entities-and-escaping-issues-that-are-unique-to-xaml"></a><span data-ttu-id="1e567-105">XAML에 고유한 문자 엔터티 및 이스케이프 문제</span><span class="sxs-lookup"><span data-stu-id="1e567-105">Character Entities and Escaping Issues That Are Unique to XAML</span></span>  
 <span data-ttu-id="1e567-106">XAML 태그는 일반적으로 XML에 정의된 것과 동일한 문자 엔터티 및 이스케이프 시퀀스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-106">XAML markup typically uses the same character entities and escape sequences that are defined in XML.</span></span>  
  
 <span data-ttu-id="1e567-107">가장 큰 차이점은, 중괄호({ })는 중괄호로 묶인 문자 시퀀스를 태그 확장으로 해석해야 한다고 XAML 프로세서에 알리기 때문에 XAML에서는 중괄호가 상당한 의미를 가진다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-107">The main exception is that braces ({ and }) have significance in XAML because these characters inform a XAML processor that a character sequence enclosed by braces must be interpreted as a markup extension.</span></span> <span data-ttu-id="1e567-108">태그 확장에 대한 자세한 내용은 [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e567-108">For more information about markup extensions, see [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span></span>  
  
 <span data-ttu-id="1e567-109">하지만 XML이 아니라 XAML에 특정한 이스케이프 시퀀스를 사용하여 중괄호를 리터럴 문자로 표시할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-109">However, you can still display the braces as literal characters by using an escape sequence that is particular to XAML instead of XML.</span></span> <span data-ttu-id="1e567-110">자세한 내용은 참조 [ {} 이스케이프 시퀀스-태그 확장](escape-sequence-markup-extension.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-110">For more information, see [{} Escape Sequence - Markup Extension](escape-sequence-markup-extension.md).</span></span>  
  
 <span data-ttu-id="1e567-111">백슬래시 (\\) 문자열로 처리 되는 이스케이프 시퀀스 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-111">Note that a backslash (\\) does not require an escape sequence when it is handled as a string.</span></span>  
  
<a name="xml_character_entities"></a>   
## <a name="xml-character-entities"></a><span data-ttu-id="1e567-112">XML 문자 엔터티</span><span class="sxs-lookup"><span data-stu-id="1e567-112">XML Character Entities</span></span>  
 <span data-ttu-id="1e567-113">앞서 언급했듯이, 대부분의 문자 엔터티 및 XAML 태그 작성에 일반적으로 사용되는 이스케이프 시퀀스는 XML에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-113">As mentioned previously, most character entities and escape sequences that are typically used to write XAML markup are defined by XML.</span></span> <span data-ttu-id="1e567-114">이 항목에서는 이러한 엔터티의 전체 목록을 제공하지는 않습니다. 이 엔터티에 대한 자세한 참조 정보는 외부 설명서(예: XML 사양)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-114">This topic does not provide the complete list of these entities; a detailed reference for the entities can be found in external documentation, such as in XML specifications.</span></span> <span data-ttu-id="1e567-115">그러나 편의상, 이 항목에서는 XAML 태그에 일반적으로 사용되는 특정 XML 문자 엔터티 중 일부를 제시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-115">However, for convenience, this topic lists some of the specific XML character entities that are typically used in XAML markup.</span></span>  
  
|<span data-ttu-id="1e567-116">문자</span><span class="sxs-lookup"><span data-stu-id="1e567-116">Character</span></span>|<span data-ttu-id="1e567-117">엔터티</span><span class="sxs-lookup"><span data-stu-id="1e567-117">Entity</span></span>|<span data-ttu-id="1e567-118">노트</span><span class="sxs-lookup"><span data-stu-id="1e567-118">Notes</span></span>|  
|---------------|------------|-----------|  
|<span data-ttu-id="1e567-119">&(앰퍼샌드)</span><span class="sxs-lookup"><span data-stu-id="1e567-119">& (ampersand)</span></span>|<span data-ttu-id="1e567-120">\&amp;</span><span class="sxs-lookup"><span data-stu-id="1e567-120">\&amp;</span></span>|<span data-ttu-id="1e567-121">특성 값 및 요소의 콘텐츠에 대해 모두 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-121">Must be used both for attribute values and for content of an element.</span></span>|  
|<span data-ttu-id="1e567-122">>(보다 큼 문자)</span><span class="sxs-lookup"><span data-stu-id="1e567-122">> (greater-than character)</span></span>|<span data-ttu-id="1e567-123">\&gt;</span><span class="sxs-lookup"><span data-stu-id="1e567-123">\&gt;</span></span>|<span data-ttu-id="1e567-124">특성 값에 대해 사용해야 하지만 > 문자는 앞에 < 문자가 오지 않을 때만 요소의 콘텐츠로 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-124">Must be used for an attribute value, but > is acceptable as the content of an element as long as < does not precede it.</span></span>|  
|<span data-ttu-id="1e567-125"><(보다 작음 문자)</span><span class="sxs-lookup"><span data-stu-id="1e567-125">< (less-than character)</span></span>|<span data-ttu-id="1e567-126">\&lt;</span><span class="sxs-lookup"><span data-stu-id="1e567-126">\&lt;</span></span>|<span data-ttu-id="1e567-127">특성 값에 사용 해야 하지만 \< 는 그 앞에 > 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-127">Must be used for an attribute value, but \< is acceptable as the content of an element as long as > does not follow it.</span></span>|  
|<span data-ttu-id="1e567-128">"(곧은 따옴표)</span><span class="sxs-lookup"><span data-stu-id="1e567-128">" (straight quotation mark)</span></span>|<span data-ttu-id="1e567-129">\&quot;</span><span class="sxs-lookup"><span data-stu-id="1e567-129">\&quot;</span></span>|<span data-ttu-id="1e567-130">특성 값에 대해 사용해야 하지만 곧은 따옴표(")는 요소의 콘텐츠로 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-130">Must be used for an attribute value, but a straight quotation mark (") is acceptable as the content of an element.</span></span> <span data-ttu-id="1e567-131">특성 값을 곧은 작은따옴표(')나 곧은 큰따옴표(")로 묶을 수 있습니다. 둘 중 어느 것이 먼저 나오든 이들 문자는 특성 값 포함을 정의하며, 대체 따옴표를 값 내부 리터럴로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-131">Note that attribute values may be enclosed either by a single straight quotation mark (') or by a straight quotation mark ("); whichever character appears first defines the attribute value enclosure, and the alternative quote can then be used as a literal within the value.</span></span>|  
|<span data-ttu-id="1e567-132">'(곧은 작은따옴표)</span><span class="sxs-lookup"><span data-stu-id="1e567-132">' (single straight quotation mark)</span></span>|<span data-ttu-id="1e567-133">\&apos;</span><span class="sxs-lookup"><span data-stu-id="1e567-133">\&apos;</span></span>|<span data-ttu-id="1e567-134">특성 값에 대해 사용해야 하지만 곧은 작은따옴표(')는 요소의 콘텐츠로 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-134">Must be used for an attribute value, but a single straight quotation mark (') is acceptable as the content of an element.</span></span> <span data-ttu-id="1e567-135">특성 값을 곧은 작은따옴표(')나 곧은 큰따옴표(")로 묶을 수 있습니다. 둘 중 어느 것이 먼저 나오든 이들 문자는 특성 값 포함을 정의하며, 대체 따옴표를 값 내부 리터럴로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-135">Note that attribute values may be enclosed either by a single straight quotation mark (') or by a straight quotation mark ("); whichever character appears first defines the attribute value enclosure, and the alternative quote can then be used as a literal within the value.</span></span>|  
|<span data-ttu-id="1e567-136">(숫자 매핑)</span><span class="sxs-lookup"><span data-stu-id="1e567-136">(numeric character mappings)</span></span>|<span data-ttu-id="1e567-137">&#*[정수]* ; 또는 & #x *[16 진수]*;</span><span class="sxs-lookup"><span data-stu-id="1e567-137">&#*[integer]*; or &#x *[hex]*;</span></span>|<span data-ttu-id="1e567-138">XAML은 활성화된 인코딩에 대한 숫자 매핑을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-138">XAML supports numeric character mappings into the encoding that is active.</span></span>|  
|<span data-ttu-id="1e567-139">(줄 바꿈하지 않는 공백)</span><span class="sxs-lookup"><span data-stu-id="1e567-139">(nonbreaking space)</span></span>|<span data-ttu-id="1e567-140">&\#160; (utf-8 인코딩을 가정함)</span><span class="sxs-lookup"><span data-stu-id="1e567-140">&\#160; (assuming UTF-8 encoding)</span></span>|<span data-ttu-id="1e567-141">유동 문서 요소 또는 WPF <xref:System.Windows.Controls.TextBox> 등의 텍스트를 사용하는 요소의 경우, 줄 바꿈하지 않는 공백은 `xml:space="default"`의 경우에도 태그 외부에서 정규화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-141">For flow document elements, or elements that take text such as the WPF <xref:System.Windows.Controls.TextBox>, nonbreaking spaces are not normalized out of the markup, even for `xml:space="default"`.</span></span> <span data-ttu-id="1e567-142">(자세한 내용은 참조 [XAML의 공백 처리](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).)</span><span class="sxs-lookup"><span data-stu-id="1e567-142">(For more information, see [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).)</span></span>|  
  
<a name="xml_comment_format"></a>   
## <a name="xml-comment-format"></a><span data-ttu-id="1e567-143">XML 주석 형식</span><span class="sxs-lookup"><span data-stu-id="1e567-143">XML Comment Format</span></span>  
 <span data-ttu-id="1e567-144">XAML은 XML 주석 형식을 사용합니다. 즉, 주석의 시작은 `<!--`이고 주석의 끝은 `-->,`이며 주석 내에서 `--` 시퀀스가 발생해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-144">XAML uses the XML comment format: the start of the comment is `<!--`, the end of comment is `-->,` and the sequence `--` must not occur within the comment.</span></span>  
  
<a name="xml_processing_instructions"></a>   
## <a name="xml-processing-instructions"></a><span data-ttu-id="1e567-145">XML 처리 명령</span><span class="sxs-lookup"><span data-stu-id="1e567-145">XML Processing Instructions</span></span>  
 <span data-ttu-id="1e567-146">XAML은 XML 처리 명령을 XML 사양에 따라 처리합니다. 이 사양에서는 이 명령을 거쳐야 한다고 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-146">XAML handles XML processing instructions according to XML specifications, which state that the instructions must be passed through.</span></span> <span data-ttu-id="1e567-147">.NET Framework XAML 서비스에서 처리 하는 XAML 처리 명령을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-147">XAML processing in .NET Framework XAML Services  does not use any processing instructions.</span></span> <span data-ttu-id="1e567-148">XAML을 사용하는 다른 기존 프레임워크에서도 XAML의 처리 명령을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e567-148">Other existing frameworks that use XAML also do not use processing instructions from XAML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e567-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e567-149">See Also</span></span>  
 [<span data-ttu-id="1e567-150">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="1e567-150">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="1e567-151">태그 확장 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="1e567-151">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="1e567-152">XamlName 문법</span><span class="sxs-lookup"><span data-stu-id="1e567-152">XamlName Grammar</span></span>](../../../docs/framework/xaml-services/xamlname-grammar.md)  
 [<span data-ttu-id="1e567-153">XAML의 공백 처리</span><span class="sxs-lookup"><span data-stu-id="1e567-153">Whitespace Processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)
