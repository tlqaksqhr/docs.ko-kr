---
title: "XPathNavigator를 사용하여 XML 데이터 삽입"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 2ed8c28b-b88d-4be7-9c87-92df01f0821f
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 34151590a14c48c0a84677f2d7cae662291edf40
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="insert-xml-data-using-xpathnavigator"></a><span data-ttu-id="73a39-102">XPathNavigator를 사용하여 XML 데이터 삽입</span><span class="sxs-lookup"><span data-stu-id="73a39-102">Insert XML Data using XPathNavigator</span></span>
<span data-ttu-id="73a39-103"><xref:System.Xml.XPath.XPathNavigator> 클래스는 XML 문서에 형제, 자식 및 특성 노드를 삽입하는 메서드 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to insert sibling, child, and attribute nodes in an XML document.</span></span> <span data-ttu-id="73a39-104">이러한 메서드를 사용하려면 <xref:System.Xml.XPath.XPathNavigator> 개체가 편집 가능한 상태여야 합니다. 즉, <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> 속성이 `true`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-104">In order to use these methods, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be `true`.</span></span>  
  
 <span data-ttu-id="73a39-105"><xref:System.Xml.XPath.XPathNavigator> 클래스의 <xref:System.Xml.XmlDocument.CreateNavigator%2A> 메서드에서는 XML 문서를 편집할 수 있는 <xref:System.Xml.XmlDocument> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-105"><xref:System.Xml.XPath.XPathNavigator> objects that can edit an XML document are created by the <xref:System.Xml.XmlDocument.CreateNavigator%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="73a39-106"><xref:System.Xml.XPath.XPathNavigator> 클래스에서 만든 <xref:System.Xml.XPath.XPathDocument> 개체는 읽기 전용이며, <xref:System.Xml.XPath.XPathNavigator> 개체에서 만든 <xref:System.Xml.XPath.XPathDocument> 개체의 편집 메서드를 사용하려고 하면 <xref:System.NotSupportedException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-106"><xref:System.Xml.XPath.XPathNavigator> objects created by the <xref:System.Xml.XPath.XPathDocument> class are read-only and any attempt to use the editing methods of an <xref:System.Xml.XPath.XPathNavigator> object created by an <xref:System.Xml.XPath.XPathDocument> object results in a <xref:System.NotSupportedException>.</span></span>  
  
 <span data-ttu-id="73a39-107">편집 가능한 만들기에 대 한 자세한 내용은 <xref:System.Xml.XPath.XPathNavigator> 개체 참조 [XPathDocument 및 XmlDocument를 사용 하 여 XML 데이터를 읽는](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-107">For more information about creating editable <xref:System.Xml.XPath.XPathNavigator> objects, see [Reading XML Data using XPathDocument and XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).</span></span>  
  
## <a name="inserting-nodes"></a><span data-ttu-id="73a39-108">노드 삽입</span><span class="sxs-lookup"><span data-stu-id="73a39-108">Inserting Nodes</span></span>  
 <span data-ttu-id="73a39-109"><xref:System.Xml.XPath.XPathNavigator> 클래스는 XML 문서에 형제, 자식 및 특성 노드를 삽입하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-109">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to insert sibling, child, and attribute nodes in an XML document.</span></span> <span data-ttu-id="73a39-110">이러한 메서드를 사용하여 <xref:System.Xml.XPath.XPathNavigator> 개체의 현재 위치와 관련된 여러 위치에 노드와 특성을 삽입할 수 있습니다. 이 메서드에 대한 자세한 내용은 다음 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73a39-110">These methods allow you to insert nodes and attributes in different locations in relation to the current position of an <xref:System.Xml.XPath.XPathNavigator> object and are described in the following sections.</span></span>  
  
### <a name="inserting-sibling-nodes"></a><span data-ttu-id="73a39-111">형제 노드 삽입</span><span class="sxs-lookup"><span data-stu-id="73a39-111">Inserting Sibling Nodes</span></span>  
 <span data-ttu-id="73a39-112"><xref:System.Xml.XPath.XPathNavigator> 클래스는 다음과 같은 메서드를 통해 형제 노드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-112">The <xref:System.Xml.XPath.XPathNavigator> class provides the following methods to insert sibling nodes.</span></span>  
  
-   <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A>  
  
 <span data-ttu-id="73a39-113">이러한 메서드는 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 배치되어 있는 노드의 앞뒤에 형제 노드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-113">These methods insert sibling nodes before and after the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="73a39-114"><xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> 및 <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> 메서드가 오버로드되며 `string`, <xref:System.Xml.XmlReader> 개체 또는 추가할 형제 노드가 포함된 <xref:System.Xml.XPath.XPathNavigator> 개체를 매개 변수로 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-114">The <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> methods are overloaded and accept a `string`, <xref:System.Xml.XmlReader> object, or <xref:System.Xml.XPath.XPathNavigator> object containing the sibling node to add as parameters.</span></span> <span data-ttu-id="73a39-115">또한 두 메서드는 형제 노드를 삽입하는 데 사용하는 <xref:System.Xml.XmlWriter> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-115">Both methods also return an <xref:System.Xml.XmlWriter> object used to insert sibling nodes.</span></span>  
  
 <span data-ttu-id="73a39-116"><xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> 및 <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> 메서드는 네임스페이스 접두사, 로컬 이름, 네임스페이스 URI 및 매개 변수로 지정된 값을 사용하여 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 배치되어 있는 노드 앞뒤에 단일 형제 노드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-116">The <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> methods insert a single sibling node before and after the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on using the namespace prefix, local name, namespace URI, and value specified as parameters.</span></span>  
  
 <span data-ttu-id="73a39-117">다음 예제에서는 `pages` 파일에서 첫 번째 `price` 요소의 `book` 자식 요소 앞에 새 `contosoBooks.xml` 요소를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-117">In the following example a new `pages` element is inserted before the `price` child element of the first `book` element in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#19](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#19)]
 [!code-csharp[XPathNavigatorMethods#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#19)]
 [!code-vb[XPathNavigatorMethods#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#19)]  
  
 <span data-ttu-id="73a39-118">이 예제에서는 `contosoBooks.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-118">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="73a39-119"><xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> 및 <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> 메서드에 대한 자세한 내용은 <xref:System.Xml.XPath.XPathNavigator> 클래스 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73a39-119">For more information about the <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> methods, see the <xref:System.Xml.XPath.XPathNavigator> class reference documentation.</span></span>  
  
### <a name="inserting-child-nodes"></a><span data-ttu-id="73a39-120">자식 노드 삽입</span><span class="sxs-lookup"><span data-stu-id="73a39-120">Inserting Child Nodes</span></span>  
 <span data-ttu-id="73a39-121"><xref:System.Xml.XPath.XPathNavigator> 클래스는 다음과 같은 메서드를 통해 자식 노드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-121">The <xref:System.Xml.XPath.XPathNavigator> class provides the following methods to insert child nodes.</span></span>  
  
-   <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A>  
  
 <span data-ttu-id="73a39-122">이러한 메서드는 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 배치되어 있는 노드의 자식 노드 목록 시작과 끝 부분에 자식 노드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-122">These methods append and prepend child nodes to the end of and the beginning of the list of child nodes of the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="73a39-123">"형제 노드 삽입" 단원의 메서드와 마찬가지로 <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> 및 <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> 메서드는 `string`, <xref:System.Xml.XmlReader> 개체 또는 추가할 자식 노드가 포함된 <xref:System.Xml.XPath.XPathNavigator> 개체를 매개 변수로 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-123">Like the methods in the "Inserting Sibling Nodes" section, the <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> methods accept a `string`, <xref:System.Xml.XmlReader> object, or <xref:System.Xml.XPath.XPathNavigator> object containing the child node to add as parameters.</span></span> <span data-ttu-id="73a39-124">또한 두 메서드는 자식 노드를 삽입하는 데 사용하는 <xref:System.Xml.XmlWriter> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-124">Both methods also return an <xref:System.Xml.XmlWriter> object used to insert child nodes.</span></span>  
  
 <span data-ttu-id="73a39-125">또한 "형제 노드 삽입" 단원의 메서드와 같이 <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> 및 <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> 메서드는 네임스페이스 접두사, 로컬 이름, 네임스페이스 URI 및 매개 변수로 지정된 값을 사용하여 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 배치되어 있는 노드의 자식 노드 목록 시작과 끝 부분에 단일 자식 노드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-125">Also like the methods in the "Inserting Sibling Nodes" section, the <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> methods insert a single child node to the end of and the beginning of the list of child nodes of the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on using the namespace prefix, local name, namespace URI, and value specified as parameters.</span></span>  
  
 <span data-ttu-id="73a39-126">다음 예제에서는 `pages` 파일에서 첫 번째 `book` 요소의 자식 요소 목록에 새 `contosoBooks.xml` 자식 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-126">In the following example, a new `pages` child element is appended to the list of child elements of the first `book` element in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#2](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#2)]
 [!code-csharp[XPathNavigatorMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#2)]
 [!code-vb[XPathNavigatorMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#2)]  
  
 <span data-ttu-id="73a39-127">이 예제에서는 `contosoBooks.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-127">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="73a39-128"><xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> 및 <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> 메서드에 대한 자세한 내용은 <xref:System.Xml.XPath.XPathNavigator> 클래스 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73a39-128">For more information about the <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> methods, see the <xref:System.Xml.XPath.XPathNavigator> class reference documentation.</span></span>  
  
### <a name="inserting-attribute-nodes"></a><span data-ttu-id="73a39-129">특성 노드 삽입</span><span class="sxs-lookup"><span data-stu-id="73a39-129">Inserting Attribute Nodes</span></span>  
 <span data-ttu-id="73a39-130"><xref:System.Xml.XPath.XPathNavigator> 클래스는 다음과 같은 메서드를 통해 특성 노드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-130">The <xref:System.Xml.XPath.XPathNavigator> class provides the following methods to insert attribute nodes.</span></span>  
  
-   <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>  
  
 <span data-ttu-id="73a39-131">이러한 메서드는 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 배치되어 있는 요소 노드에 특성 노드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-131">These methods insert attribute nodes on the element node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="73a39-132"><xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> 메서드는 네임스페이스 접두사, 로컬 이름, 네임스페이스 URI 및 매개 변수로 지정된 값을 사용하여 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 배치되어 있는 요소 노드에 특성 노드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-132">The <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> method creates an attribute node on the element node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on using the namespace prefix, local name, namespace URI, and value specified as parameters.</span></span> <span data-ttu-id="73a39-133"><xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> 메서드는 특성 노드를 삽입하는 데 사용하는 <xref:System.Xml.XmlWriter> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-133">The <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> method returns an <xref:System.Xml.XmlWriter> object used to insert attribute nodes.</span></span>  
  
 <span data-ttu-id="73a39-134">다음 예제에서는 `discount` 메서드에서 반환된 `currency` 개체를 사용하여 `price` 파일에서 첫 번째 `book` 요소의 `contosoBooks.xml` 자식 요소에 새 <xref:System.Xml.XmlWriter> 및 <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> 특성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-134">In the following example, new `discount` and `currency` attributes are created on the `price` child element of the first `book` element in the `contosoBooks.xml` file using the <xref:System.Xml.XmlWriter> object returned from the <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> method.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#8](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#8)]
 [!code-csharp[XPathNavigatorMethods#8](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#8)]
 [!code-vb[XPathNavigatorMethods#8](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#8)]  
  
 <span data-ttu-id="73a39-135">이 예제에서는 `contosoBooks.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-135">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="73a39-136"><xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> 및 <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> 메서드에 대한 자세한 내용은 <xref:System.Xml.XPath.XPathNavigator> 클래스 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73a39-136">For more information about the <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> and <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> methods, see the <xref:System.Xml.XPath.XPathNavigator> class reference documentation.</span></span>  
  
## <a name="copying-nodes"></a><span data-ttu-id="73a39-137">노드 복사</span><span class="sxs-lookup"><span data-stu-id="73a39-137">Copying Nodes</span></span>  
 <span data-ttu-id="73a39-138">다른 XML 문서의 내용으로 XML 문서를 채워야 할 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-138">In certain cases you may want to populate an XML document with the contents from another XML document.</span></span> <span data-ttu-id="73a39-139"><xref:System.Xml.XPath.XPathNavigator> 클래스와 <xref:System.Xml.XmlWriter> 클래스는 기존 <xref:System.Xml.XmlDocument> 개체 또는 <xref:System.Xml.XmlReader> 개체에서 <xref:System.Xml.XPath.XPathNavigator> 개체에 노드를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-139">Both the <xref:System.Xml.XPath.XPathNavigator> class and the <xref:System.Xml.XmlWriter> class can copy nodes to an <xref:System.Xml.XmlDocument> object from an existing <xref:System.Xml.XmlReader> object or <xref:System.Xml.XPath.XPathNavigator> object.</span></span>  
  
 <span data-ttu-id="73a39-140"><xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> 및 <xref:System.Xml.XPath.XPathNavigator> 메서드는 모두 오버로드되며 <xref:System.Xml.XPath.XPathNavigator> 개체나 <xref:System.Xml.XmlReader> 개체를 매개 변수로 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-140">The <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class all have overloads that can accept an <xref:System.Xml.XPath.XPathNavigator> object or an <xref:System.Xml.XmlReader> object as a parameter.</span></span>  
  
 <span data-ttu-id="73a39-141"><xref:System.Xml.XmlWriter.WriteNode%2A> 클래스의 <xref:System.Xml.XmlWriter> 메서드는 오버로드되며 <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlReader> 또는 <xref:System.Xml.XPath.XPathNavigator> 개체를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-141">The <xref:System.Xml.XmlWriter.WriteNode%2A> method of the <xref:System.Xml.XmlWriter> class has overloads that can accept an <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlReader>, or <xref:System.Xml.XPath.XPathNavigator> object.</span></span>  
  
 <span data-ttu-id="73a39-142">다음 예제에서는 문서의 모든 `book` 요소를 다른 문서로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-142">The following example copies all the `book` elements from one document to another.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", String.Empty)  
  
Dim newBooks As XPathDocument = New XPathDocument("newBooks.xml")  
Dim newBooksNavigator As XPathNavigator = newBooks.CreateNavigator()  
  
Dim nav As XPathNavigator  
For Each nav in newBooksNavigator.SelectDescendants("book", "", false)  
    navigator.AppendChild(nav)  
Next  
  
document.Save("newBooks.xml");  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", String.Empty);  
  
XPathDocument newBooks = new XPathDocument("newBooks.xml");  
XPathNavigator newBooksNavigator = newBooks.CreateNavigator();  
  
foreach (XPathNavigator nav in newBooksNavigator.SelectDescendants("book", "", false))  
{  
    navigator.AppendChild(nav);  
}  
  
document.Save("newBooks.xml");  
```  
  
## <a name="inserting-values"></a><span data-ttu-id="73a39-143">값 삽입</span><span class="sxs-lookup"><span data-stu-id="73a39-143">Inserting Values</span></span>  
 <span data-ttu-id="73a39-144"><xref:System.Xml.XPath.XPathNavigator> 클래스는 노드 값을 <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> 개체에 삽입하는 <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> 및 <xref:System.Xml.XmlDocument> 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-144">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods to insert values for a node into an <xref:System.Xml.XmlDocument> object.</span></span>  
  
### <a name="inserting-untyped-values"></a><span data-ttu-id="73a39-145">형식화되지 않은 값 삽입</span><span class="sxs-lookup"><span data-stu-id="73a39-145">Inserting Untyped Values</span></span>  
 <span data-ttu-id="73a39-146"><xref:System.Xml.XPath.XPathNavigator.SetValue%2A> 메서드는 형식화되지 않은 `string` 값을 간단히 삽입합니다. 이 값은 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 위치하는 노드의 값인 매개 변수로서 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-146">The <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method simply inserts the untyped `string` value passed as a parameter as the value of the node the <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="73a39-147">이 값은 스키마 정보를 사용할 수 있을 경우 노드 형식에 따라 새 값이 유효한지 여부를 확인하지 않거나 특정한 형식 없이 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-147">The value is inserted without any type or without verifying that the new value is valid according to the type of the node if schema information is available.</span></span>  
  
 <span data-ttu-id="73a39-148">다음 예제에서는 <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> 메서드를 사용하여 `price` 파일의 모든 `contosoBooks.xml` 요소를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-148">In the following example, the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method is used to update all `price` elements in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#47](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#47)]
 [!code-csharp[XPathNavigatorMethods#47](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#47)]
 [!code-vb[XPathNavigatorMethods#47](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#47)]  
  
 <span data-ttu-id="73a39-149">이 예제에서는 `contosoBooks.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-149">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="inserting-typed-values"></a><span data-ttu-id="73a39-150">형식화된 값 삽입</span><span class="sxs-lookup"><span data-stu-id="73a39-150">Inserting Typed Values</span></span>  
 <span data-ttu-id="73a39-151">노드의 형식이 W3C XML 스키마 단순 형식이면 <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> 메서드에서 삽입한 새 값은 설정되기 전에 단순 형식의 패싯에 대해 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-151">When the type of a node is a W3C XML Schema simple type, the new value inserted by the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method is checked against the facets of the simple type before the value is set.</span></span> <span data-ttu-id="73a39-152">노드의 형식에 따라 새 값이 유효하지 않은 경우, 예를 들면 `-1` 형식의 요소에 `xs:positiveInteger`의 값을 설정하는 경우에는 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-152">If the new value is not valid according to the type of the node (for example, setting a value of `-1` on an element whose type is `xs:positiveInteger`), it results in an exception.</span></span>  
  
 <span data-ttu-id="73a39-153">다음 예제에서는 `price` 파일에 있는 첫 번째 `book` 요소의 `contosoBooks.xml` 요소 값을 <xref:System.DateTime> 값으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-153">The following example attempts to change the value of the `price` element of the first `book` element in the `contosoBooks.xml` file to a <xref:System.DateTime> value.</span></span> <span data-ttu-id="73a39-154">`price` 요소의 XML 스키마 형식은 `xs:decimal` 파일의 `contosoBooks.xsd`로 정의되므로 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-154">Because the XML Schema type of the `price` element is defined as `xs:decimal` in the `contosoBooks.xsd` files, this results in an exception.</span></span>  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetTypedValue(DateTime.Now)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.SetTypedValue(DateTime.Now);  
```  
  
 <span data-ttu-id="73a39-155">이 예제에서는 `contosoBooks.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-155">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="73a39-156">이 예제에서는 또한 `contosoBooks.xsd`를 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-156">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
## <a name="the-innerxml-and-outerxml-properties"></a><span data-ttu-id="73a39-157">InnerXml 및 OuterXml 속성</span><span class="sxs-lookup"><span data-stu-id="73a39-157">The InnerXml and OuterXml Properties</span></span>  
 <span data-ttu-id="73a39-158"><xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> 및 <xref:System.Xml.XPath.XPathNavigator> 속성은 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 위치하는 노드의 XML 태그를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-158">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties of the <xref:System.Xml.XPath.XPathNavigator> class change the XML markup of the nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="73a39-159"><xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> 속성은 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 위치하는 자식 노드의 XML 태그를 주어진 XML `string`의 구문 분석된 내용과 함께 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-159">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on with the parsed contents of the given XML `string`.</span></span> <span data-ttu-id="73a39-160">마찬가지로, <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> 속성은 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 위치하는 자식 노드의 XML 태그뿐만 아니라 현재 노드 자체도 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-160">Similarly, the <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on as well as the current node itself.</span></span>  
  
 <span data-ttu-id="73a39-161">이 항목에 설명된 메서드 외에도 <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> 및 <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> 속성을 사용하여 XML 문서에 노드와 값을 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-161">In addition to the methods described in this topic, the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties can be used to insert nodes and values in an XML document.</span></span> <span data-ttu-id="73a39-162">사용 하는 방법에 대 한 자세한 내용은 <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> 및 <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> 노드와 값을 삽입 하는 속성 참조는 [XPathNavigator를 사용 하 여 XML 데이터 수정](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-162">For more information about using the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties to insert nodes and values, see the [Modify XML Data using XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md) topic.</span></span>  
  
## <a name="namespace-and-xmllang-conflicts"></a><span data-ttu-id="73a39-163">네임스페이스와 xml:lang 충돌</span><span class="sxs-lookup"><span data-stu-id="73a39-163">Namespace and xml:lang Conflicts</span></span>  
 <span data-ttu-id="73a39-164">`xml:lang` 개체를 매개 변수로 사용하는 <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> 및 <xref:System.Xml.XPath.XPathNavigator> 메서드를 통해 XML 데이터를 삽입하면 네임스페이스 및 <xref:System.Xml.XmlReader> 선언의 범위와 관련된 충돌이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-164">Certain conflicts related to the scope of namespace and `xml:lang` declarations can occur when inserting XML data using the <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class that take <xref:System.Xml.XmlReader> objects as parameters.</span></span>  
  
 <span data-ttu-id="73a39-165">다음은 발생할 수 있는 네임스페이스 충돌입니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-165">The following are the possible namespace conflicts.</span></span>  
  
-   <span data-ttu-id="73a39-166"><xref:System.Xml.XmlReader> 개체의 컨텍스트에 네임스페이스 URI 접두사 매핑이 없을 경우 <xref:System.Xml.XPath.XPathNavigator> 개체의 컨텍스트 범위 내에 네임스페이스가 있으면 새로 삽입된 노드에 새 네임스페이스 선언이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-166">If there is a namespace in-scope within the <xref:System.Xml.XmlReader> object's context, where the prefix to namespace URI mapping is not in the <xref:System.Xml.XPath.XPathNavigator> object's context, a new namespace declaration is added to the newly inserted node.</span></span>  
  
-   <span data-ttu-id="73a39-167"><xref:System.Xml.XmlReader> 개체의 컨텍스트와 <xref:System.Xml.XPath.XPathNavigator> 개체의 컨텍스트 내에서 같은 네임스페이스 URI가 범위 내에 있지만 두 컨텍스트에서 다른 접두사가 매핑된 경우 새로 삽입된 노드에 새 네임스페이스 선언이 추가되고 <xref:System.Xml.XmlReader> 개체의 접두사와 네임스페이스 URI가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-167">If the same namespace URI is in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but has a different prefix mapped to it in both contexts, a new namespace declaration is added to the newly inserted node, with the prefix and namespace URI taken from the <xref:System.Xml.XmlReader> object.</span></span>  
  
-   <span data-ttu-id="73a39-168"><xref:System.Xml.XmlReader> 개체의 컨텍스트와 <xref:System.Xml.XPath.XPathNavigator> 개체의 컨텍스트 내에서 같은 네임스페이스 접두사가 범위 내에 있지만 두 컨텍스트에 다른 네임스페이스 URI가 매핑된 경우 새로 삽입된 노드에 새 네임스페이스 선언이 추가되며 접두사가 다시 선언되고 <xref:System.Xml.XmlReader> 개체의 네임스페이스 URI가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-168">If the same namespace prefix is in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but has a different namespace URI mapped to it in both contexts, a new namespace declaration is added to the newly inserted node which re-declares that prefix with the namespace URI taken from <xref:System.Xml.XmlReader> object.</span></span>  
  
-   <span data-ttu-id="73a39-169"><xref:System.Xml.XmlReader> 개체의 컨텍스트와 <xref:System.Xml.XPath.XPathNavigator> 개체의 컨텍스트에서 네임스페이스 URI와 접두사가 같을 경우 새로 삽입된 노드에 새 네임스페이스 선언이 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-169">If the prefix as well as the namespace URI in both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context is the same, no new namespace declaration is added to the newly inserted node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73a39-170">위 설명은 기본 네임스페이스 선언과 같이 접두사로 빈 `string`이 있는 네임스페이스 선언에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-170">The description above also applies to namespace declarations with the empty `string` as a prefix (for example, the default namespace declaration).</span></span>  
  
 <span data-ttu-id="73a39-171">다음은 발생할 수 있는 `xml:lang` 충돌입니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-171">The following are the possible `xml:lang` conflicts.</span></span>  
  
-   <span data-ttu-id="73a39-172">`xml:lang` 개체의 컨텍스트 내 범위에 <xref:System.Xml.XmlReader> 특성이 있지만 <xref:System.Xml.XPath.XPathNavigator> 개체의 컨텍스트에는 없을 경우 `xml:lang` 개체에서 값을 가져오는 <xref:System.Xml.XmlReader> 특성이 새로 삽입된 노드에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-172">If there is an `xml:lang` attribute in-scope within the <xref:System.Xml.XmlReader> object's context but not in the <xref:System.Xml.XPath.XPathNavigator> object's context, an `xml:lang` attribute whose value is taken from the <xref:System.Xml.XmlReader> object is added to the newly inserted node.</span></span>  
  
-   <span data-ttu-id="73a39-173">`xml:lang` 개체의 컨텍스트와 <xref:System.Xml.XmlReader> 개체의 컨텍스트 내 범위에 <xref:System.Xml.XPath.XPathNavigator> 특성이 있지만 각각 값이 다를 경우 `xml:lang` 개체에서 값을 가져오는 <xref:System.Xml.XmlReader> 특성이 새로 삽입된 노드에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-173">If there is an `xml:lang` attribute in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but each has a different value, an `xml:lang` attribute whose value is taken from the <xref:System.Xml.XmlReader> object is added to the newly inserted node.</span></span>  
  
-   <span data-ttu-id="73a39-174">`xml:lang` 개체의 컨텍스트와 <xref:System.Xml.XmlReader> 개체의 컨텍스트 내 범위에 <xref:System.Xml.XPath.XPathNavigator> 특성이 있고 값이 같을 경우 새로 삽입된 노드에 새 `xml:lang` 특성이 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-174">If there is an `xml:lang` attribute in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but each with the same value, no new `xml:lang` attribute is added on the newly inserted node.</span></span>  
  
-   <span data-ttu-id="73a39-175">`xml:lang` 개체의 컨텍스트 내 범위에 <xref:System.Xml.XPath.XPathNavigator> 특성이 있지만 <xref:System.Xml.XmlReader> 개체의 컨텍스트에는 없을 경우 새로 삽입된 노드에 `xml:lang` 특성이 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-175">If there is an `xml:lang` attribute in-scope within the <xref:System.Xml.XPath.XPathNavigator> object's context, but none existing in the <xref:System.Xml.XmlReader> object's context, no `xml:lang` attribute is added to the newly inserted node.</span></span>  
  
## <a name="inserting-nodes-with-xmlwriter"></a><span data-ttu-id="73a39-176">XmlWriter를 사용하여 노드 삽입</span><span class="sxs-lookup"><span data-stu-id="73a39-176">Inserting Nodes with XmlWriter</span></span>  
 <span data-ttu-id="73a39-177">"노드 및 값 삽입" 단원에 설명된 형제, 자식 및 특성 노드를 삽입하는 데 사용하는 메서드는 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-177">The methods used to insert sibling, child and attribute nodes described in the "Inserting Nodes and Values" section are overloaded.</span></span> <span data-ttu-id="73a39-178"><xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> 및 <xref:System.Xml.XPath.XPathNavigator> 메서드는 노드를 삽입하는 데 사용하는 <xref:System.Xml.XmlWriter> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-178">The <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> and <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class return an <xref:System.Xml.XmlWriter> object used to insert nodes.</span></span>  
  
### <a name="unsupported-xmlwriter-methods"></a><span data-ttu-id="73a39-179">지원되지 않는 XmlWriter 메서드</span><span class="sxs-lookup"><span data-stu-id="73a39-179">Unsupported XmlWriter Methods</span></span>  
 <span data-ttu-id="73a39-180"><xref:System.Xml.XmlWriter> 클래스를 통해 XML 문서에 정보를 작성하는 데 사용되는 메서드 중 일부는 XPath 데이터 모델과 DOM(문서 개체 모델)의 차이로 인해 <xref:System.Xml.XPath.XPathNavigator> 클래스에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-180">Not all of the methods used for writing information to an XML document using the <xref:System.Xml.XmlWriter> class are supported by the <xref:System.Xml.XPath.XPathNavigator> class due to difference between the XPath data model and the Document Object Model (DOM).</span></span>  
  
 <span data-ttu-id="73a39-181">다음 표에서는 <xref:System.Xml.XmlWriter> 클래스에서 지원하지 않는 <xref:System.Xml.XPath.XPathNavigator> 클래스 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-181">The following table describes the <xref:System.Xml.XmlWriter> class methods not supported by the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
|<span data-ttu-id="73a39-182">메서드</span><span class="sxs-lookup"><span data-stu-id="73a39-182">Method</span></span>|<span data-ttu-id="73a39-183">설명</span><span class="sxs-lookup"><span data-stu-id="73a39-183">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.XmlWriter.WriteEntityRef%2A>|<span data-ttu-id="73a39-184"><xref:System.NotSupportedException> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-184">Throws a <xref:System.NotSupportedException> exception.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteDocType%2A>|<span data-ttu-id="73a39-185">루트 수준에서 무시되며 XML 문서의 다른 수준에서 호출할 경우 <xref:System.NotSupportedException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-185">Ignored at the root level and throws a <xref:System.NotSupportedException> exception if called at any other level in the XML document.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteCData%2A>|<span data-ttu-id="73a39-186">해당 문자의 <xref:System.Xml.XmlWriter.WriteString%2A> 메서드에 대한 호출로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-186">Treated as a call to the <xref:System.Xml.XmlWriter.WriteString%2A> method for the equivalent character or characters.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteCharEntity%2A>|<span data-ttu-id="73a39-187">해당 문자의 <xref:System.Xml.XmlWriter.WriteString%2A> 메서드에 대한 호출로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-187">Treated as a call to the <xref:System.Xml.XmlWriter.WriteString%2A> method for the equivalent character or characters.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteSurrogateCharEntity%2A>|<span data-ttu-id="73a39-188">해당 문자의 <xref:System.Xml.XmlWriter.WriteString%2A> 메서드에 대한 호출로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-188">Treated as a call to the <xref:System.Xml.XmlWriter.WriteString%2A> method for the equivalent character or characters.</span></span>|  
  
 <span data-ttu-id="73a39-189"><xref:System.Xml.XmlWriter> 클래스에 대한 자세한 내용은 <xref:System.Xml.XmlWriter> 클래스 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73a39-189">For more information about the <xref:System.Xml.XmlWriter> class, see the <xref:System.Xml.XmlWriter> class reference documentation.</span></span>  
  
### <a name="multiple-xmlwriter-objects"></a><span data-ttu-id="73a39-190">여러 XmlWriter 개체</span><span class="sxs-lookup"><span data-stu-id="73a39-190">Multiple XmlWriter Objects</span></span>  
 <span data-ttu-id="73a39-191">하나 이상의 <xref:System.Xml.XPath.XPathNavigator> 개체를 열어 놓은 상태에서 여러 <xref:System.Xml.XmlWriter> 개체가 각각 XML 문서의 다른 부분을 가리키도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-191">It is possible to have multiple <xref:System.Xml.XPath.XPathNavigator> objects pointing to different parts of an XML document with one or more open <xref:System.Xml.XmlWriter> objects.</span></span> <span data-ttu-id="73a39-192">단일 스레드 시나리오에서 여러 <xref:System.Xml.XmlWriter> 개체가 허용 및 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-192">Multiple <xref:System.Xml.XmlWriter> objects are allowed and supported in single-threaded scenarios.</span></span>  
  
 <span data-ttu-id="73a39-193">다음은 여러 <xref:System.Xml.XmlWriter> 개체를 사용할 때 고려해야 할 중요 참고 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-193">The following are important notes to consider when using multiple <xref:System.Xml.XmlWriter> objects.</span></span>  
  
-   <span data-ttu-id="73a39-194">각 <xref:System.Xml.XmlWriter> 개체의 <xref:System.Xml.XmlWriter.Close%2A> 메서드를 호출하면 <xref:System.Xml.XmlWriter> 개체를 사용하여 작성한 XML 조각이 XML 문서에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-194">XML fragments written by <xref:System.Xml.XmlWriter> objects are added to the XML document when the <xref:System.Xml.XmlWriter.Close%2A> method of each <xref:System.Xml.XmlWriter> object is called.</span></span> <span data-ttu-id="73a39-195">그때까지 <xref:System.Xml.XmlWriter> 개체는 연결되지 않은 조각을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-195">Until that point, the <xref:System.Xml.XmlWriter> object is writing a disconnected fragment.</span></span> <span data-ttu-id="73a39-196">XML 문서에서 작업을 수행해도 <xref:System.Xml.XmlWriter>를 호출하기 전에 <xref:System.Xml.XmlWriter.Close%2A> 개체를 사용하여 작성 중인 조각에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-196">If an operation is performed on the XML document, any fragments being written by an <xref:System.Xml.XmlWriter> object, before the <xref:System.Xml.XmlWriter.Close%2A> has been called, are not affected.</span></span>  
  
-   <span data-ttu-id="73a39-197">특정 XML 하위 트리에 <xref:System.Xml.XmlWriter> 개체가 열려 있을 경우 이 하위 트리를 삭제해도 <xref:System.Xml.XmlWriter> 개체가 이 하위 트리에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-197">If there is an open <xref:System.Xml.XmlWriter> object on a particular XML subtree and that subtree is deleted, the <xref:System.Xml.XmlWriter> object may still add to the sub-tree.</span></span> <span data-ttu-id="73a39-198">하위 트리는 단순히 삭제된 조각이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-198">The subtree simply becomes a deleted fragment.</span></span>  
  
-   <span data-ttu-id="73a39-199">XML 문서의 동일한 지점에 여러 <xref:System.Xml.XmlWriter> 개체가 동시에 열려 있을 경우 <xref:System.Xml.XmlWriter> 개체를 연 순서가 아니라 닫은 순서대로 XML 문서에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-199">If multiple <xref:System.Xml.XmlWriter> objects are opened at the same point in the XML document, they are added to the XML document in the order in which the <xref:System.Xml.XmlWriter> objects are closed, not in the order in which they were opened.</span></span>  
  
 <span data-ttu-id="73a39-200">다음 예제에서는 <xref:System.Xml.XmlDocument> 개체를 만들고 <xref:System.Xml.XPath.XPathNavigator> 개체를 만든 다음 <xref:System.Xml.XmlWriter> 메서드에서 반환된 <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> 개체를 사용하여 `books.xml` 파일에 첫 번째 책의 구조를 만들고</span><span class="sxs-lookup"><span data-stu-id="73a39-200">The following example creates an <xref:System.Xml.XmlDocument> object, creates an <xref:System.Xml.XPath.XPathNavigator> object, and then uses the <xref:System.Xml.XmlWriter> object returned by the <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> method to create the structure of the first book in the `books.xml` file.</span></span> <span data-ttu-id="73a39-201">`book.xml` 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-201">The example then saves it as the `book.xml` file.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
Using writer As XmlWriter = navigator.PrependChild()  
  
    writer.WriteStartElement("bookstore")  
    writer.WriteStartElement("book")  
    writer.WriteAttributeString("genre", "autobiography")  
    writer.WriteAttributeString("publicationdate", "1981-03-22")  
    writer.WriteAttributeString("ISBN", "1-861003-11-0")  
    writer.WriteElementString("title", "The Autobiography of Benjamin Franklin")  
    writer.WriteStartElement("author")  
    writer.WriteElementString("first-name", "Benjamin")  
    writer.WriteElementString("last-name", "Franklin")  
    writer.WriteElementString("price", "8.99")  
    writer.WriteEndElement()  
    writer.WriteEndElement()  
    writer.WriteEndElement()  
  
End Using  
  
document.Save("book.xml")  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
XPathNavigator navigator = document.CreateNavigator();  
  
using (XmlWriter writer = navigator.PrependChild())  
{  
    writer.WriteStartElement("bookstore");  
    writer.WriteStartElement("book");  
    writer.WriteAttributeString("genre", "autobiography");  
    writer.WriteAttributeString("publicationdate", "1981-03-22");  
    writer.WriteAttributeString("ISBN", "1-861003-11-0");  
    writer.WriteElementString("title", "The Autobiography of Benjamin Franklin");  
    writer.WriteStartElement("author");  
    writer.WriteElementString("first-name", "Benjamin");  
    writer.WriteElementString("last-name", "Franklin");  
    writer.WriteElementString("price", "8.99");  
    writer.WriteEndElement();  
    writer.WriteEndElement();  
    writer.WriteEndElement();  
}  
document.Save("book.xml");  
```  
  
## <a name="saving-an-xml-document"></a><span data-ttu-id="73a39-202">XML 문서 저장</span><span class="sxs-lookup"><span data-stu-id="73a39-202">Saving an XML Document</span></span>  
 <span data-ttu-id="73a39-203"><xref:System.Xml.XmlDocument> 클래스의 메서드를 사용하면 <xref:System.Xml.XmlDocument> 개체에서 변경된 내용을 이 항목에서 설명하는 메서드의 결과로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-203">Saving changes made to an <xref:System.Xml.XmlDocument> object as the result of the methods described in this topic is performed using the methods of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="73a39-204">변경 내용을 저장 하는 방법에 대 한 자세한 내용은 <xref:System.Xml.XmlDocument> 개체, 참조 [문서 작성 및 저장](../../../../docs/standard/data/xml/saving-and-writing-a-document.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-204">For more information about saving changes made to an <xref:System.Xml.XmlDocument> object, see [Saving and Writing a Document](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a39-205">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73a39-205">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="73a39-206">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="73a39-206">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="73a39-207">XPathNavigator를 사용 하 여 XML 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="73a39-207">Modify XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="73a39-208">XPathNavigator를 사용 하 여 XML 데이터를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="73a39-208">Remove XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md)
