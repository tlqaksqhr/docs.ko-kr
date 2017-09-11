---
title: "Imports 문 (XML Namespace) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ImportsXmlns
dev_langs:
- VB
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
caps.latest.revision: 18
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
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 66ac2bd947328dab9df812709525b43fb27145ac
ms.contentlocale: ko-kr
ms.lasthandoff: 06/01/2017

---
# <a name="imports-statement-xml-namespace"></a><span data-ttu-id="dcc7c-102">Imports 문(XML 네임스페이스)</span><span class="sxs-lookup"><span data-stu-id="dcc7c-102">Imports Statement (XML Namespace)</span></span>
<span data-ttu-id="dcc7c-103">XML 리터럴 및 XML 축 속성에 사용할 XML 네임 스페이스 접두사를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-103">Imports XML namespace prefixes for use in XML literals and XML axis properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcc7c-104">구문</span><span class="sxs-lookup"><span data-stu-id="dcc7c-104">Syntax</span></span>  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a><span data-ttu-id="dcc7c-105">요소</span><span class="sxs-lookup"><span data-stu-id="dcc7c-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="dcc7c-106">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-106">Optional.</span></span> <span data-ttu-id="dcc7c-107">XML 특성과 해당 요소를 참조할 수는 문자열 `xmlNamespaceName`합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-107">The string by which XML elements and attributes can refer to `xmlNamespaceName`.</span></span> <span data-ttu-id="dcc7c-108">없으면 `xmlNamespacePrefix` 는 가져온된 XML 네임 스페이스는 기본 XML 네임 스페이스는 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-108">If no `xmlNamespacePrefix` is supplied, the imported XML namespace is the default XML namespace.</span></span> <span data-ttu-id="dcc7c-109">유효한 XML 식별자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-109">Must be a valid XML identifier.</span></span> <span data-ttu-id="dcc7c-110">자세한 내용은 참조 [이름의 선언 된 XML 요소 및 특성](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-110">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>  
  
 `xmlNamespaceName`  
 <span data-ttu-id="dcc7c-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-111">Required.</span></span> <span data-ttu-id="dcc7c-112">가져올 XML 네임 스페이스를 식별 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-112">The string identifying the XML namespace being imported.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcc7c-113">주의</span><span class="sxs-lookup"><span data-stu-id="dcc7c-113">Remarks</span></span>  
 <span data-ttu-id="dcc7c-114">사용할 수는 `Imports` XML 리터럴과 XML 축 속성 또는에 전달 된 매개 변수로 사용할 수 있는 전역 XML 네임 스페이스를 정의 하는 문에 `GetXmlNamespace` 연산자.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-114">You can use the `Imports` statement to define global XML namespaces that you can use with XML literals and XML axis properties, or as parameters passed to the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="dcc7c-115">(사용 하는 방법에 대 한 내용은 `Imports` 을 코드에 형식 이름을 사용 되는 위치에 사용할 수 있는 별칭을 가져오기 위한 문 참조 [Imports 문 (.NET Namespace 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) 사용 하 여 XML 네임 스페이스를 선언 하기 위한 구문에서 `Imports` 문에 XML에 사용 되는 구문은 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-115">(For information about using the `Imports` statement to import an alias that can be used where type names are used in your code, see [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) The syntax for declaring an XML namespace by using the `Imports` statement is identical to the syntax used in XML.</span></span> <span data-ttu-id="dcc7c-116">따라서 네임 스페이스 선언은 XML 파일에서 복사한에서 사용 하 여 한 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-116">Therefore, you can copy a namespace declaration from an XML file and use it in an `Imports` statement.</span></span>  
  
 <span data-ttu-id="dcc7c-117">XML 네임 스페이스 접두사는 동일한 네임 스페이스에서 생성 되는 XML 요소를 반복적으로 만들려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-117">XML namespace prefixes are useful when you want to repeatedly create XML elements that are from the same namespace.</span></span> <span data-ttu-id="dcc7c-118">으로 선언 된 XML 네임 스페이스 접두사는 `Imports` 문은 모든 코드 파일에서 사용할 수 있다는 점에서 전역적입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-118">The XML namespace prefix declared with the `Imports` statement is global in the sense that it is available to all code in the file.</span></span> <span data-ttu-id="dcc7c-119">XML 요소 리터럴 및 XML 축 속성에 액세스할 때 만들 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-119">You can use it when you create XML element literals and when you access XML axis properties.</span></span> <span data-ttu-id="dcc7c-120">자세한 내용은 참조 [XML 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) 및 [XML 축 속성](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-120">For more information, see [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).</span></span>  
  
 <span data-ttu-id="dcc7c-121">네임 스페이스 접두사 없이 전역 XML 네임 스페이스를 정의 하는 경우 (예를 들어 `Imports <xmlns="http://SomeNameSpace>"`), 해당 네임 스페이스에는 기본 XML 네임 스페이스 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-121">If you define a global XML namespace without a namespace prefix (for example, `Imports <xmlns="http://SomeNameSpace>"`), that namespace is considered the default XML namespace.</span></span> <span data-ttu-id="dcc7c-122">기본 XML 네임 스페이스는 모든 XML 요소 리터럴 또는 네임 스페이스를 명시적으로 지정 하지 않은 XML 특성 축 속성에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-122">The default XML namespace is used for any XML element literals or XML attribute axis properties that do not explicitly specify a namespace.</span></span> <span data-ttu-id="dcc7c-123">기본 네임 스페이스는 지정된 된 네임 스페이스는 빈 네임 스페이스 하는 경우에 사용 됩니다 (즉, `xmlns=""`).</span><span class="sxs-lookup"><span data-stu-id="dcc7c-123">The default namespace is also used if the specified namespace is the empty namespace (that is, `xmlns=""`).</span></span> <span data-ttu-id="dcc7c-124">기본 XML 네임 스페이스는 네임 스페이스가 없는 XML 특성 축 속성 또는 XML 리터럴과에서 XML 특성에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-124">The default XML namespace does not apply to XML attributes in XML literals or to XML attribute axis properties that do not have a namespace.</span></span>  
  
 <span data-ttu-id="dcc7c-125">XML 네임 스페이스는 리터럴, XML에 정의 된 이라고 하는 *XML 네임 스페이스를 로컬*, XML 네임 스페이스에 정의 된 우선는 `Imports` 문은 전역으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-125">XML namespaces that are defined in an XML literal, which are called *local XML namespaces*, take precedence over XML namespaces that are defined by the `Imports` statement as global.</span></span> <span data-ttu-id="dcc7c-126">에 정의 된 XML 네임 스페이스는 `Imports` 문은 Visual Basic 프로젝트에 대 한 가져온 XML 네임 스페이스 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-126">XML namespaces that are defined by the `Imports` statement take precedence over XML namespaces imported for a Visual Basic project.</span></span> <span data-ttu-id="dcc7c-127">XML 리터럴과 XML 네임 스페이스를 정의 하는 경우 해당 로컬 네임 스페이스는 포함된 식에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-127">If an XML literal defines an XML namespace, that local namespace does not apply to embedded expressions.</span></span>  
  
 <span data-ttu-id="dcc7c-128">전역 XML 네임 스페이스는.NET Framework 네임 스페이스와 동일한 범위 지정 및 정의 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-128">Global XML namespaces follow the same scoping and definition rules as .NET Framework namespaces.</span></span> <span data-ttu-id="dcc7c-129">결과적으로 포함할 수는 `Imports` 전역 XML 네임 스페이스를 정의 하는 문을 어디서 나.NET Framework 네임 스페이스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-129">As a result, you can include an `Imports` statement to define a global XML namespace anywhere you can import a .NET Framework namespace.</span></span> <span data-ttu-id="dcc7c-130">코드 파일 및 프로젝트 수준의 가져온된 네임 스페이스를 모두 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-130">This includes both code files and project-level imported namespaces.</span></span> <span data-ttu-id="dcc7c-131">프로젝트 수준 가져온된 네임 스페이스에 대 한 정보를 참조 하십시오. [프로젝트 디자이너 (Visual Basic), 참조 페이지](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-131">For information about project-level imported namespaces, see [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="dcc7c-132">각 소스 파일에는 개수에 제한 없이 포함 될 수 있습니다 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-132">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="dcc7c-133">이러한 옵션 선언 같은 따라야는 `Option Strict` 않으며 문 앞에 야 프로그래밍 요소 선언와 같은 `Module` 또는 `Class` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-133">These must follow option declarations, such as the `Option Strict` statement, and they must precede programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcc7c-134">예제</span><span class="sxs-lookup"><span data-stu-id="dcc7c-134">Example</span></span>  
 <span data-ttu-id="dcc7c-135">다음 예제에서는 기본 XML 네임 스페이스와 XML 네임 스페이스 접두사로 식별 `ns`합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-135">The following example imports a default XML namespace and an XML namespace identified with the prefix `ns`.</span></span> <span data-ttu-id="dcc7c-136">그런 다음 두 가지 네임 스페이스를 사용 하는 XML 리터럴을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-136">It then creates XML literals that use both namespaces.</span></span>  
  
 <span data-ttu-id="dcc7c-137">[!code-vb[VbXMLSamples #&45;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="dcc7c-137">[!code-vb[VbXMLSamples#45](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]</span></span>  
  
 <span data-ttu-id="dcc7c-138">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-138">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## <a name="example"></a><span data-ttu-id="dcc7c-139">예제</span><span class="sxs-lookup"><span data-stu-id="dcc7c-139">Example</span></span>  
 <span data-ttu-id="dcc7c-140">다음 예제에서는 XML 네임 스페이스 접두사를 가져옵니다 `ns`합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-140">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="dcc7c-141">그런 다음 네임 스페이스 접두사를 사용 하 고 요소의 최종 폼을 표시 하는 XML 리터럴을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-141">It then creates an XML literal that uses the namespace prefix and displays the element's final form.</span></span>  
  
 <span data-ttu-id="dcc7c-142">[!code-vb[VbXMLSamples #&22;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="dcc7c-142">[!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]</span></span>  
  
 <span data-ttu-id="dcc7c-143">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-143">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="dcc7c-144">에 컴파일러가 변환 XML 네임 스페이스 접두사를 전역 접두사에서 로컬 접두사 정의 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-144">Notice that the compiler converted the XML namespace prefix from a global prefix to a local prefix definition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcc7c-145">예제</span><span class="sxs-lookup"><span data-stu-id="dcc7c-145">Example</span></span>  
 <span data-ttu-id="dcc7c-146">다음 예제에서는 XML 네임 스페이스 접두사를 가져옵니다 `ns`합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-146">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="dcc7c-147">네임스페이스의 접두사를 사용하여 XML 리터럴을 만들고 정규화된 이름 `ns:name`을 가진 첫 번째 자식 노드에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-147">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 <span data-ttu-id="dcc7c-148">[!code-vb[VbXMLSamples #&19;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="dcc7c-148">[!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]</span></span>  
  
 <span data-ttu-id="dcc7c-149">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7c-149">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="dcc7c-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dcc7c-150">See Also</span></span>  
 <span data-ttu-id="dcc7c-151">[XML 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="dcc7c-151">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="dcc7c-152"> [XML 축 속성](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="dcc7c-152"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="dcc7c-153"> [선언 된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="dcc7c-153"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md) </span></span>  
<span data-ttu-id="dcc7c-154"> [GetXmlNamespace 연산자](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)</span><span class="sxs-lookup"><span data-stu-id="dcc7c-154"> [GetXmlNamespace Operator](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)</span></span>
