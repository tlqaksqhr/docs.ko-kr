---
title: "XML 특성 축 속성 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyAttributeAxis
dev_langs:
- VB
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
caps.latest.revision: 23
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
ms.openlocfilehash: a3c327f4448287bcf6c45b9b6e26a1ef9ba13c16
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="23c76-102">XML 특성 축 속성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23c76-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="23c76-103">에 대 한 특성의 값에 액세스할 수는 <xref:System.Xml.Linq.XElement>개체 또는 컬렉션의 첫 번째 요소를 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="23c76-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23c76-104">구문</span><span class="sxs-lookup"><span data-stu-id="23c76-104">Syntax</span></span>  
  
```  
  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="23c76-105">요소</span><span class="sxs-lookup"><span data-stu-id="23c76-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="23c76-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="23c76-106">Required.</span></span> <span data-ttu-id="23c76-107"><xref:System.Xml.Linq.XElement>개체 또는 컬렉션을 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="23c76-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="23c76-108">.@</span><span class="sxs-lookup"><span data-stu-id="23c76-108">.@</span></span>  
 <span data-ttu-id="23c76-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="23c76-109">Required.</span></span> <span data-ttu-id="23c76-110">특성 축 속성의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="23c76-111">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="23c76-111">Optional.</span></span> <span data-ttu-id="23c76-112">시작 특성의 이름 부분을 나타냅니다 때 `attribute` 에서 유효한 식별자가 아닌 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 `attribute`  
 <span data-ttu-id="23c76-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="23c76-113">Required.</span></span> <span data-ttu-id="23c76-114">폼의 액세스 하는 특성의 이름을 [`prefix`:]`name`합니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="23c76-115">파트</span><span class="sxs-lookup"><span data-stu-id="23c76-115">Part</span></span>|<span data-ttu-id="23c76-116">설명</span><span class="sxs-lookup"><span data-stu-id="23c76-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="23c76-117">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="23c76-117">Optional.</span></span> <span data-ttu-id="23c76-118">특성에 대 한 XML 네임 스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="23c76-119">`Imports` 문으로 정의되는 전역 XML 네임스페이스여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="23c76-120">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="23c76-120">Required.</span></span> <span data-ttu-id="23c76-121">로컬 특성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-121">Local attribute name.</span></span> <span data-ttu-id="23c76-122">참조 [선언 된 XML 요소 및 특성의 이름을](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="23c76-123">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="23c76-123">Optional.</span></span> <span data-ttu-id="23c76-124">특성의 이름의 끝을 나타냅니다 때 `attribute` 에서 유효한 식별자가 아닌 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23c76-125">반환 값</span><span class="sxs-lookup"><span data-stu-id="23c76-125">Return Value</span></span>  
 <span data-ttu-id="23c76-126">값을 포함 하는 문자열 `attribute`합니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="23c76-127">특성 이름이 없으면 `Nothing` 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23c76-128">주의</span><span class="sxs-lookup"><span data-stu-id="23c76-128">Remarks</span></span>  
 <span data-ttu-id="23c76-129">XML 특성 축 속성을 사용 하 여 이름을 사용 하 여 특성의 값에 액세스할 수는 <xref:System.Xml.Linq.XElement>개체 또는 컬렉션의 첫 번째 요소에서 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="23c76-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="23c76-130">이름으로 특성 값을 검색 하거나 앞에 새 이름을 지정 하 여 요소에 새 특성을 추가할 수는 @ 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="23c76-131">사용 하 여 XML 특성을 참조 하는 경우는 @ 식별자, 특성 값을 문자열로 반환 되 고 명시적으로 지정할 필요가 없습니다는 <xref:System.Xml.Linq.XAttribute.Value%2A>속성.</xref:System.Xml.Linq.XAttribute.Value%2A></span><span class="sxs-lookup"><span data-stu-id="23c76-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="23c76-132">XML 특성에 대 한 명명 규칙에 대 한 명명 규칙에서 다른 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-132">The naming rules for XML attributes differ from the naming rules for [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] identifiers.</span></span> <span data-ttu-id="23c76-133">유효한 Visual Basic 식별자 되지 않는 이름을 가진 XML 특성에 액세스 하려면 이름을 꺾쇠 괄호로 묶습니다 (\< 및 >).</span><span class="sxs-lookup"><span data-stu-id="23c76-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="23c76-134">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="23c76-134">XML Namespaces</span></span>  
 <span data-ttu-id="23c76-135">특성 축 속성의 이름을 사용 하 여 전역적으로 선언 된 XML 네임 스페이스 접두사만 사용할 수는 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="23c76-136">XML 요소 리터럴 내에서 로컬로 선언된 XML 네임스페이스 접두사를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="23c76-137">자세한 내용은 참조 [Imports 문 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="23c76-138">예제</span><span class="sxs-lookup"><span data-stu-id="23c76-138">Example</span></span>  
 <span data-ttu-id="23c76-139">다음 예제에서는 라는 XML 특성의 값을 가져오는 `type` 라고 하는 XML 요소의 컬렉션에서 `phone`합니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 <span data-ttu-id="23c76-140">[!code-vb[VbXMLSamples #&12;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="23c76-140">[!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]</span></span>  
  
 <span data-ttu-id="23c76-141">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-141">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="23c76-142">예제</span><span class="sxs-lookup"><span data-stu-id="23c76-142">Example</span></span>  
 <span data-ttu-id="23c76-143">다음 예제에는 모두 XML 요소에 대 한 특성을 일부로 XML, 그리고 동적으로 특성의 인스턴스를 추가 하 여 선언적으로 만드는 방법을 보여 줍니다는 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="23c76-143">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="23c76-144">`type` 특성을 선언적으로 만든 및 `owne`r 특성을 동적으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-144">The `type` attribute is created declaratively and the `owne`r attribute is created dynamically.</span></span>  
  
 <span data-ttu-id="23c76-145">[!code-vb[VbXMLSamples #&44;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="23c76-145">[!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]</span></span>  
  
 <span data-ttu-id="23c76-146">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-146">This code displays the following text:</span></span>  
  
```  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="23c76-147">예제</span><span class="sxs-lookup"><span data-stu-id="23c76-147">Example</span></span>  
 <span data-ttu-id="23c76-148">다음 예제는 꺾쇠 괄호를 찾아 구문을 사용 하 여 이라는 XML 특성의 값을 가져올 `number-type`에 유효한 식별자가 없는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-148">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 <span data-ttu-id="23c76-149">[!code-vb[VbXMLSamples #&13;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="23c76-149">[!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]</span></span>  
  
 <span data-ttu-id="23c76-150">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-150">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="23c76-151">예제</span><span class="sxs-lookup"><span data-stu-id="23c76-151">Example</span></span>  
 <span data-ttu-id="23c76-152">다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="23c76-152">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="23c76-153">다음 네임 스페이스의 접두사는 XML 리터럴을 만들고 노드의 정규화 된 이름 가진 첫 번째 자식 노드를 사용 하 여 "`ns:name`"입니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-153">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 <span data-ttu-id="23c76-154">[!code-vb[VbXMLSamples #&14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="23c76-154">[!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]</span></span>  
  
 <span data-ttu-id="23c76-155">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23c76-155">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="23c76-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23c76-156">See Also</span></span>  
 <span data-ttu-id="23c76-157"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="23c76-157"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="23c76-158"> [XML 축 속성](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="23c76-158"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="23c76-159"> [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="23c76-159"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="23c76-160"> [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="23c76-160"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="23c76-161"> [선언된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="23c76-161"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span></span>
