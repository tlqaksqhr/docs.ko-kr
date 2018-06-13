---
title: DOM의 요소 노드에서 특성 제거
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 7ede6f9e-a3ac-49a4-8488-ab8360a44aa4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 758ce84390c9ba47e3eb56e1feb293a4cf0408a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570569"
---
# <a name="removing-attributes-from-an-element-node-in-the-dom"></a><span data-ttu-id="bbc42-102">DOM의 요소 노드에서 특성 제거</span><span class="sxs-lookup"><span data-stu-id="bbc42-102">Removing Attributes from an Element Node in the DOM</span></span>
<span data-ttu-id="bbc42-103">여러 가지 방법으로 특성을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-103">There are many ways to remove attributes.</span></span> <span data-ttu-id="bbc42-104">그 중 한 가지 방법은 특성 컬렉션에서 특성을 제거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-104">One technique is to remove them from the attribute collection.</span></span> <span data-ttu-id="bbc42-105">이 방법을 사용하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-105">To do this, the following steps are performed:</span></span>  
  
1.  <span data-ttu-id="bbc42-106">`XmlAttributeCollection attrs = elem.Attributes;`를 사용하여 요소에서 특성 컬렉션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-106">Get the attribute collection from the element using `XmlAttributeCollection attrs = elem.Attributes;`.</span></span>  
  
2.  <span data-ttu-id="bbc42-107">다음 세 가지 메서드 중 하나를 사용하여 특성 컬렉션에서 특성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-107">Remove the attribute from the attribute collection using one of three methods:</span></span>  
  
    -   <span data-ttu-id="bbc42-108">특정 특성을 제거하려면 <xref:System.Xml.XmlAttributeCollection.Remove%2A>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-108">Use <xref:System.Xml.XmlAttributeCollection.Remove%2A> to remove a specific attribute.</span></span>  
  
    -   <span data-ttu-id="bbc42-109">컬렉션에서 모든 특성을 제거하고 특성이 없는 요소는 남겨 두려면 <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-109">Use <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> to remove all attributes from the collection and leave the element with no attributes.</span></span>  
  
    -   <span data-ttu-id="bbc42-110">인덱스 번호를 사용하여 특성 컬렉션에서 특성을 제거하려면 <xref:System.Xml.XmlAttributeCollection.RemoveAt%2A>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-110">Use <xref:System.Xml.XmlAttributeCollection.RemoveAt%2A> to remove an attribute from the attribute collection by using its index number.</span></span>  
  
 <span data-ttu-id="bbc42-111">다음 메서드는 요소 노드에서 특성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-111">The following methods remove attributes from the element node.</span></span>  
  
-   <span data-ttu-id="bbc42-112">특성 컬렉션을 제거하려면 <xref:System.Xml.XmlElement.RemoveAllAttributes%2A>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-112">Use <xref:System.Xml.XmlElement.RemoveAllAttributes%2A> to remove the attribute collection.</span></span>  
  
-   <span data-ttu-id="bbc42-113">컬렉션에서 이름으로 특성 하나를 제거하려면 <xref:System.Xml.XmlElement.RemoveAttribute%2A>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-113">Use <xref:System.Xml.XmlElement.RemoveAttribute%2A> to remove a single attribute by name from the collection.</span></span>  
  
-   <span data-ttu-id="bbc42-114">컬렉션에서 인덱스 번호로 특성 하나를 제거하려면 <xref:System.Xml.XmlElement.RemoveAttributeAt%2A>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-114">Use <xref:System.Xml.XmlElement.RemoveAttributeAt%2A> to remove a single attribute by index number from the collection.</span></span>  
  
 <span data-ttu-id="bbc42-115">또 다른 방법은 요소를 가져오고 특성 컬렉션에서 특성을 가져온 다음 특성 노드를 직접 제거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-115">One more alternative is to get the element, get the attribute from the attribute collection, and remove the attribute node directly.</span></span> <span data-ttu-id="bbc42-116">특성 컬렉션에서 특성을 가져오려면 이름, `XmlAttribute attr = attrs["attr_name"];`, 인덱스 `XmlAttribute attr = attrs[0];`를 사용하거나 네임스페이스 `XmlAttribute attr = attrs["attr_localName", "attr_namespace"]`로 이름을 정규화합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-116">To get the attribute from the attribute collection, you can use a name, `XmlAttribute attr = attrs["attr_name"];`, an index `XmlAttribute attr = attrs[0];`, or by fully qualifying the name with the namespace `XmlAttribute attr = attrs["attr_localName", "attr_namespace"]`.</span></span>  
  
 <span data-ttu-id="bbc42-117">특성을 제거하는 데 사용한 메서드와 상관없이 DTD(문서 종류 정의)에 기본 특성으로 정의된 특성을 제거할 때는 특별한 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-117">Regardless of the method used to remove attributes, there are special limitations on removing attributes that are defined as default attributes in the document type definition (DTD).</span></span> <span data-ttu-id="bbc42-118">기본 특성이 속해 있는 요소를 제거해야 기본 특성을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-118">Default attributes cannot be removed unless the element they belong to is removed.</span></span> <span data-ttu-id="bbc42-119">기본 특성은 기본 특성을 선언한 요소에 대해 항상 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-119">Default attributes are always present for elements that have default attributes declared.</span></span> <span data-ttu-id="bbc42-120"><xref:System.Xml.XmlAttributeCollection> 또는 <xref:System.Xml.XmlElement>에서 기본 특성을 제거하면 대체 특성이 요소의 <xref:System.Xml.XmlAttributeCollection>에 삽입되고 선언된 기본값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-120">Removing a default attribute from an <xref:System.Xml.XmlAttributeCollection> or from the <xref:System.Xml.XmlElement> results in a replacement attribute inserted into the <xref:System.Xml.XmlAttributeCollection> of the element, initialized to the default value that was declared.</span></span> <span data-ttu-id="bbc42-121">`<book att1="1" att2="2" att3="3"></book>`으로 정의된 요소가 있을 경우 기본 특성 3개가 선언된 `book` 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-121">If you have an element defined as `<book att1="1" att2="2" att3="3"></book>`, then you have a `book` element with three default attributes declared.</span></span> <span data-ttu-id="bbc42-122">XML DOM(문서 개체 모델)을 구현하면 이 `book` 요소가 있는 한, 기본 특성 `att1`, `att2` 및 `att3`이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-122">The XML Document Object Model (DOM) implementation guarantees that as long as this `book` element exists, it has these three default attributes of `att1`, `att2`, and `att3`.</span></span>  
  
 <span data-ttu-id="bbc42-123"><xref:System.Xml.XmlAttribute>를 사용하여 <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> 메서드를 호출하면 값이 없는 특성이 있을 수 없으므로 특성 값이 String.Empty로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc42-123">When called with an <xref:System.Xml.XmlAttribute>, the <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> method sets the value of the attribute to String.Empty, as an attribute cannot exist without a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbc42-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bbc42-124">See Also</span></span>  
 [<span data-ttu-id="bbc42-125">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="bbc42-125">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
