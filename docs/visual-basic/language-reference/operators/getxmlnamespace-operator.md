---
title: "GetXmlNamespace 연산자 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
dev_langs:
- VB
helpviewer_keywords:
- GetXmlNamespace operator
- GetXmlNamespace keyword
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: 14
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
ms.openlocfilehash: d6f977ab8c0b7dfb2dee936436ef4ec8530ba8f6
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="fb632-102">GetXmlNamespace 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb632-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="fb632-103">가져옵니다는 <xref:System.Xml.Linq.XNamespace>지정된 된 XML 네임 스페이스 접두사에 해당 하는 개체입니다.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="fb632-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb632-104">구문</span><span class="sxs-lookup"><span data-stu-id="fb632-104">Syntax</span></span>  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="fb632-105">요소</span><span class="sxs-lookup"><span data-stu-id="fb632-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="fb632-106">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="fb632-106">Optional.</span></span> <span data-ttu-id="fb632-107">XML 네임 스페이스 접두사를 식별 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fb632-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="fb632-108">값을 제공 하는 경우이 문자열은 유효한 XML 식별자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb632-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="fb632-109">자세한 내용은 참조 [이름의 선언 된 XML 요소 및 특성](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb632-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="fb632-110">지정 된 접두사가 기본 네임 스페이스가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb632-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="fb632-111">기본 네임 스페이스를 지정 하는 경우에 빈 네임 스페이스가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb632-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb632-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="fb632-112">Return Value</span></span>  
 <span data-ttu-id="fb632-113"><xref:System.Xml.Linq.XNamespace>XML 네임 스페이스 접두사에 해당 하는 개체입니다.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="fb632-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb632-114">주의</span><span class="sxs-lookup"><span data-stu-id="fb632-114">Remarks</span></span>  
 <span data-ttu-id="fb632-115">`GetXmlNamespace` 연산자 가져옵니다는 <xref:System.Xml.Linq.XNamespace>XML 네임 스페이스 접두사에 해당 하는 개체 `xmlNamespacePrefix`.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="fb632-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="fb632-116">XML 리터럴 및 XML 축 속성에서 직접 XML 네임 스페이스 접두사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb632-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="fb632-117">하지만 사용 해야는 `GetXmlNamespace` 네임 스페이스 접두사를 변환 하는 연산자는 <xref:System.Xml.Linq.XNamespace>전에 코드에서 사용할 수 있습니다.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="fb632-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="fb632-118">정규화 되지 않은 요소 이름을 추가할 수는 <xref:System.Xml.Linq.XNamespace>개체를 가져올 정규화 된 <xref:System.Xml.Linq.XName>개체, 많은 [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 메서드에 필요.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="fb632-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb632-119">예제</span><span class="sxs-lookup"><span data-stu-id="fb632-119">Example</span></span>  
 <span data-ttu-id="fb632-120">다음 예제에서는 `ns` XML 네임 스페이스 접두사로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb632-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="fb632-121">다음 네임 스페이스의 접두사는 XML 리터럴을 만들고 노드의 정규화 된 이름을 가진 첫 번째 자식 노드를 사용 하 여 `ns:phone`합니다.</span><span class="sxs-lookup"><span data-stu-id="fb632-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="fb632-122">그런 다음 해당 자식 노드를 전달는 `ShowName` 정규화 된 이름을 사용 하 여 생성 하는 서브루틴의 `GetXmlNamespace` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="fb632-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="fb632-123">`ShowName` 서브루틴은 다음에 정규화 된 이름을 전달는 <xref:System.Xml.Linq.XNode.Ancestors%2A>메서드를 부모 `ns:contact` 노드.</xref:System.Xml.Linq.XNode.Ancestors%2A></span><span class="sxs-lookup"><span data-stu-id="fb632-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 <span data-ttu-id="fb632-124">[!code-vb[VbXMLSamples #&38;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="fb632-124">[!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]</span></span>  
  
 <span data-ttu-id="fb632-125">호출 하는 경우 `TestGetXmlNamespace.RunSample()`, 다음 텍스트가 포함 된 메시지 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb632-125">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="fb632-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb632-126">See Also</span></span>  
 <span data-ttu-id="fb632-127">[Imports 문 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="fb632-127">[Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="fb632-128"> [Visual Basic의 XML에 액세스](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)</span><span class="sxs-lookup"><span data-stu-id="fb632-128"> [Accessing XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)</span></span>
