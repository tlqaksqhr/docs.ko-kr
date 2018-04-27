---
title: XML 특성 축 속성(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyAttributeAxis
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
ms.openlocfilehash: 9968e5de0f8cb45fb896ba43c80d9c9a3ab8ef08
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="ce5f1-102">XML 특성 축 속성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce5f1-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="ce5f1-103">에 대 한 특성의 값에 액세스할 수는 <xref:System.Xml.Linq.XElement> 개체 또는 컬렉션의 첫 번째 요소로 <xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce5f1-104">구문</span><span class="sxs-lookup"><span data-stu-id="ce5f1-104">Syntax</span></span>  
  
```  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="ce5f1-105">요소</span><span class="sxs-lookup"><span data-stu-id="ce5f1-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="ce5f1-106">필수.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-106">Required.</span></span> <span data-ttu-id="ce5f1-107"><xref:System.Xml.Linq.XElement> 개체 또는 컬렉션 <xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="ce5f1-108">.@</span><span class="sxs-lookup"><span data-stu-id="ce5f1-108">.@</span></span>  
 <span data-ttu-id="ce5f1-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-109">Required.</span></span> <span data-ttu-id="ce5f1-110">특성 축 속성의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="ce5f1-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-111">Optional.</span></span> <span data-ttu-id="ce5f1-112">특성의 이름의 시작 부분을 나타내는 경우 `attribute` Visual Basic에서 유효한 식별자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
 `attribute`  
 <span data-ttu-id="ce5f1-113">필수.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-113">Required.</span></span> <span data-ttu-id="ce5f1-114">폼의에 액세스 하려면 특성의 이름을 [`prefix`:]`name`합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="ce5f1-115">파트</span><span class="sxs-lookup"><span data-stu-id="ce5f1-115">Part</span></span>|<span data-ttu-id="ce5f1-116">설명</span><span class="sxs-lookup"><span data-stu-id="ce5f1-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="ce5f1-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-117">Optional.</span></span> <span data-ttu-id="ce5f1-118">특성에 대 한 XML 네임 스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="ce5f1-119">`Imports` 문으로 정의되는 전역 XML 네임스페이스여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="ce5f1-120">필수.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-120">Required.</span></span> <span data-ttu-id="ce5f1-121">로컬 특성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-121">Local attribute name.</span></span> <span data-ttu-id="ce5f1-122">참조 [선언 된 XML 요소 및 특성의 이름을](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="ce5f1-123">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-123">Optional.</span></span> <span data-ttu-id="ce5f1-124">특성의 이름의 끝을 나타냅니다 때 `attribute` Visual Basic에서 유효한 식별자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce5f1-125">반환 값</span><span class="sxs-lookup"><span data-stu-id="ce5f1-125">Return Value</span></span>  
 <span data-ttu-id="ce5f1-126">값을 포함 하는 문자열 `attribute`합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="ce5f1-127">특성 이름이 없으면 `Nothing` 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce5f1-128">설명</span><span class="sxs-lookup"><span data-stu-id="ce5f1-128">Remarks</span></span>  
 <span data-ttu-id="ce5f1-129">이름을 기준으로 특성의 값에 액세스 하는 XML 특성 축 속성을 사용할 수 있습니다는 <xref:System.Xml.Linq.XElement> 개체 또는 컬렉션의 첫 번째 요소에서 <xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="ce5f1-130">이름으로 특성 값을 검색 하거나 앞에 새 이름을 지정 하 여 요소에 새 특성을 추가할 수 있습니다는 @ 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="ce5f1-131">사용 하 여 XML 특성을 참조 하는 경우는 @ 식별자, 특성 값을 문자열로 반환 되 고 명시적으로 지정할 필요가 없습니다는 <xref:System.Xml.Linq.XAttribute.Value%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="ce5f1-132">Visual Basic 식별자에 대 한 명명 규칙에서 XML 특성에 대 한 명명 규칙은 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-132">The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers.</span></span> <span data-ttu-id="ce5f1-133">이름이 유효한 Visual Basic 식별자가 아닌 XML 특성에 액세스 하려면 이름을 꺾쇠 괄호로 묶습니다 (\< 및 >).</span><span class="sxs-lookup"><span data-stu-id="ce5f1-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="ce5f1-134">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="ce5f1-134">XML Namespaces</span></span>  
 <span data-ttu-id="ce5f1-135">특성 축 속성의 이름을 사용 하 여 전역적으로 선언 된 XML 네임 스페이스 접두사만 사용할 수는 `Imports` 문.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="ce5f1-136">XML 요소 리터럴 내에서 로컬로 선언된 XML 네임스페이스 접두사를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="ce5f1-137">자세한 내용은 참조 [Imports 문 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce5f1-138">예제</span><span class="sxs-lookup"><span data-stu-id="ce5f1-138">Example</span></span>  
 <span data-ttu-id="ce5f1-139">라는 XML 특성의 값을 가져오는 방법을 보여 주는 다음 예제 `type` 라고 하는 XML 요소의 컬렉션에서 `phone`합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]  
  
 <span data-ttu-id="ce5f1-140">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-140">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="ce5f1-141">예제</span><span class="sxs-lookup"><span data-stu-id="ce5f1-141">Example</span></span>  
 <span data-ttu-id="ce5f1-142">다음 예제에서는 두 XML 요소에 대 한 특성을 선언적으로 XML의 그 특성의 인스턴스를 추가 하 여 동적으로 만드는 방법을 보여 줍니다는 <xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="ce5f1-143">`type` 특성을 선언적으로 만든 및 `owner` 특성이 동적으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]  
  
 <span data-ttu-id="ce5f1-144">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-144">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="ce5f1-145">예제</span><span class="sxs-lookup"><span data-stu-id="ce5f1-145">Example</span></span>  
 <span data-ttu-id="ce5f1-146">다음 예제에서는 꺾쇠 괄호 구문 라는 XML 특성의 값을 사용 하 여 `number-type`는 Visual Basic에서 유효한 식별자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.</span></span>  
  
 [!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]  
  
 <span data-ttu-id="ce5f1-147">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-147">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="ce5f1-148">예제</span><span class="sxs-lookup"><span data-stu-id="ce5f1-148">Example</span></span>  
 <span data-ttu-id="ce5f1-149">다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="ce5f1-149">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="ce5f1-150">다음 네임 스페이스의 접두사는 XML 리터럴을 만들고 정규화 된 이름 가진 첫 번째 자식 노드에 액세스를 사용 하 여 "`ns:name`"입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]  
  
 <span data-ttu-id="ce5f1-151">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5f1-151">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="ce5f1-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce5f1-152">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="ce5f1-153">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="ce5f1-153">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="ce5f1-154">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="ce5f1-154">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="ce5f1-155">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="ce5f1-155">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="ce5f1-156">선언된 XML 요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="ce5f1-156">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
