---
title: GetXmlNamespace 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: e21cf160d10f308990894d1a85c4f5d05b90f68d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603485"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="911b7-102">GetXmlNamespace 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="911b7-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="911b7-103">가져옵니다는 <xref:System.Xml.Linq.XNamespace> 지정된 된 XML 네임 스페이스 접두사에 해당 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="911b7-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="911b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="911b7-104">Syntax</span></span>  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="911b7-105">요소</span><span class="sxs-lookup"><span data-stu-id="911b7-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="911b7-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="911b7-106">Optional.</span></span> <span data-ttu-id="911b7-107">XML 네임 스페이스 접두사를 식별 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="911b7-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="911b7-108">제공 된 경우이 문자열에 유효한 XML 식별자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="911b7-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="911b7-109">자세한 내용은 참조 [이름을의 선언 된 XML 요소 및 특성](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="911b7-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="911b7-110">지정 된 접두사가 기본 네임 스페이스가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="911b7-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="911b7-111">기본 네임 스페이스를 지정 하는 경우 빈 네임 스페이스가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="911b7-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="911b7-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="911b7-112">Return Value</span></span>  
 <span data-ttu-id="911b7-113"><xref:System.Xml.Linq.XNamespace> XML 네임 스페이스 접두사에 해당 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="911b7-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="911b7-114">설명</span><span class="sxs-lookup"><span data-stu-id="911b7-114">Remarks</span></span>  
 <span data-ttu-id="911b7-115">`GetXmlNamespace` 연산자 가져옵니다는 <xref:System.Xml.Linq.XNamespace> XML 네임 스페이스 접두사에 해당 하는 개체 `xmlNamespacePrefix`합니다.</span><span class="sxs-lookup"><span data-stu-id="911b7-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="911b7-116">XML 리터럴 및 XML 축 속성에 직접 XML 네임 스페이스 접두사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="911b7-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="911b7-117">그러나 사용 해야 합니다는 `GetXmlNamespace` 네임 스페이스 접두사를 변환 하는 연산자는 <xref:System.Xml.Linq.XNamespace> 개체 코드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="911b7-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="911b7-118">정규화 되지 않은 요소 이름을 추가할 수 있습니다는 <xref:System.Xml.Linq.XNamespace> 가져올 정규화 된 개체 <xref:System.Xml.Linq.XName> 개체, 많은 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 메서드에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="911b7-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="911b7-119">예제</span><span class="sxs-lookup"><span data-stu-id="911b7-119">Example</span></span>  
 <span data-ttu-id="911b7-120">다음 예제에서는 `ns` XML 네임 스페이스 접두사로 합니다.</span><span class="sxs-lookup"><span data-stu-id="911b7-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="911b7-121">다음 네임 스페이스의 접두사는 XML 리터럴을 만들고 정규화 된 이름을 가진 첫 번째 자식 노드에 액세스를 사용 하 여 `ns:phone`합니다.</span><span class="sxs-lookup"><span data-stu-id="911b7-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="911b7-122">그런 다음 해당 자식 노드 전달는 `ShowName` 정규화 된 이름을 사용 하 여 생성 하는 서브루틴은 `GetXmlNamespace` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="911b7-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="911b7-123">`ShowName` 서브루틴은 다음에 정규화 된 이름을 전달는 <xref:System.Xml.Linq.XNode.Ancestors%2A> 부모를 가져올 메서드 `ns:contact` 노드.</span><span class="sxs-lookup"><span data-stu-id="911b7-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 <span data-ttu-id="911b7-124">호출 하는 경우 `TestGetXmlNamespace.RunSample()`, 다음 텍스트를 포함 하는 메시지 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="911b7-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="911b7-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="911b7-125">See Also</span></span>  
 [<span data-ttu-id="911b7-126">Imports 문(XML 네임스페이스)</span><span class="sxs-lookup"><span data-stu-id="911b7-126">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [<span data-ttu-id="911b7-127">Visual Basic에서 XML에 액세스</span><span class="sxs-lookup"><span data-stu-id="911b7-127">Accessing XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
