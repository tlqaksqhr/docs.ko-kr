---
title: XPathDocument 및 XmlDocument를 사용하여 XML 데이터 읽기
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 5711b225-6aa2-4e4f-9898-19f2d518ad1a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc8e1b85543fca0281b6433dd5c87c28b37818db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575468"
---
# <a name="reading-xml-data-using-xpathdocument-and-xmldocument"></a><span data-ttu-id="4c3b7-102">XPathDocument 및 XmlDocument를 사용하여 XML 데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="4c3b7-102">Reading XML Data using XPathDocument and XmlDocument</span></span>
<span data-ttu-id="4c3b7-103">두 가지 방법으로 <xref:System.Xml.XPath?displayProperty=nameWithType> 네임스페이스에서 XML 문서를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-103">There are two ways to read an XML document in the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="4c3b7-104">하나는 읽기 전용 <xref:System.Xml.XPath.XPathDocument> 클래스를 사용하여 XML 문서를 읽는 것이고 다른 하나는 <xref:System.Xml.XmlDocument> 네임스페이스에서 편집 가능한 <xref:System.Xml?displayProperty=nameWithType> 클래스를 사용하여 XML 문서를 읽는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-104">One is to read an XML document using the read-only <xref:System.Xml.XPath.XPathDocument> class and the other is to read an XML document using the editable <xref:System.Xml.XmlDocument> class in the <xref:System.Xml?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="reading-xml-documents-using-the-xpathdocument-class"></a><span data-ttu-id="4c3b7-105">XPathDocument 클래스를 사용하여 XML 문서 읽기</span><span class="sxs-lookup"><span data-stu-id="4c3b7-105">Reading XML Documents using the XPathDocument Class</span></span>  
 <span data-ttu-id="4c3b7-106"><xref:System.Xml.XPath.XPathDocument> 클래스는 XPath 데이터 모델을 사용하여 빠른 속도의 읽기 전용 메모리 내 XML 문서 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-106">The <xref:System.Xml.XPath.XPathDocument> class provides a fast, read-only, in-memory representation of an XML document using the XPath data model.</span></span> <span data-ttu-id="4c3b7-107">6개 생성자 중 하나를 사용하여 <xref:System.Xml.XPath.XPathDocument> 클래스의 인스턴스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-107">Instances of the <xref:System.Xml.XPath.XPathDocument> class are created using one of its six constructors.</span></span> <span data-ttu-id="4c3b7-108">이러한 생성자를 사용하면 XML 파일에 대한 <xref:System.IO.Stream> 경로뿐 아니라 <xref:System.IO.TextReader>, <xref:System.Xml.XmlReader> 또는 `string` 개체를 사용하여 XML 문서를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-108">These constructors allow you to read an XML document using a <xref:System.IO.Stream>, <xref:System.IO.TextReader>, or <xref:System.Xml.XmlReader> object, as well as the `string` path to an XML file.</span></span>  
  
 <span data-ttu-id="4c3b7-109">다음 예제에서는 <xref:System.Xml.XPath.XPathDocument> 클래스의 `string` 생성자를 사용하여 XML 문서를 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-109">The following example illustrates using the <xref:System.Xml.XPath.XPathDocument> class's `string` constructor to read an XML document.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
```  
  
## <a name="reading-xml-documents-using-the-xmldocument-class"></a><span data-ttu-id="4c3b7-110">XmlDocument 클래스를 사용하여 XML 문서 읽기</span><span class="sxs-lookup"><span data-stu-id="4c3b7-110">Reading XML Documents using the XmlDocument Class</span></span>  
 <span data-ttu-id="4c3b7-111"><xref:System.Xml.XmlDocument> 클래스는 W3C DOM(문서 개체 모델) Level 1 Core 및 DOM Level 2 Core를 구현하는 XML 문서의 편집 가능한 메모리 내 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-111">The <xref:System.Xml.XmlDocument> class is an editable in-memory representation of an XML document implementing W3C Document Object Model (DOM) Level 1 Core and Core DOM Level 2.</span></span> <span data-ttu-id="4c3b7-112">세 가지 생성자 중 하나를 사용하여 <xref:System.Xml.XmlDocument> 클래스의 인스턴스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-112">Instances of the <xref:System.Xml.XmlDocument> class are created using one of its three constructors.</span></span> <span data-ttu-id="4c3b7-113">매개 변수 없이 <xref:System.Xml.XmlDocument> 클래스 생성자를 호출하여 비어 있는 새 <xref:System.Xml.XmlDocument> 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-113">You can create a new, empty <xref:System.Xml.XmlDocument> object by calling the <xref:System.Xml.XmlDocument> class constructor with no parameters.</span></span> <span data-ttu-id="4c3b7-114">생성자를 호출한 후 <xref:System.Xml.XmlDocument.Load%2A> 메서드를 사용하여 XML 파일의 <xref:System.Xml.XmlDocument> 경로뿐 아니라 <xref:System.IO.Stream>, <xref:System.IO.TextReader> 또는 <xref:System.Xml.XmlReader> 개체에서 새 `string` 개체로 XML 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-114">After calling the constructor, use the <xref:System.Xml.XmlDocument.Load%2A> method to load XML data into the new <xref:System.Xml.XmlDocument> object from a <xref:System.IO.Stream>, <xref:System.IO.TextReader>, or <xref:System.Xml.XmlReader> object, as well as the `string` path to an XML file.</span></span>  
  
 <span data-ttu-id="4c3b7-115">다음 예제에서는 매개 변수 없이 <xref:System.Xml.XmlDocument> 클래스 생성자 및 <xref:System.Xml.XmlDocument.Load%2A> 메서드를 사용하여 XML 문서를 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-115">The following example illustrates using the <xref:System.Xml.XmlDocument> class constructor with no parameters and the <xref:System.Xml.XmlDocument.Load%2A> method to read an XML document.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
```  
  
## <a name="determining-the-encoding-of-an-xml-document"></a><span data-ttu-id="4c3b7-116">XML 문서의 인코딩 결정</span><span class="sxs-lookup"><span data-stu-id="4c3b7-116">Determining the Encoding of an XML Document</span></span>  
 <span data-ttu-id="4c3b7-117">이전 단원에 표시된 것과 같이 <xref:System.Xml.XmlReader> 개체를 사용하여 XML 문서를 읽고 <xref:System.Xml.XPath.XPathDocument> 및 <xref:System.Xml.XmlDocument> 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-117">An <xref:System.Xml.XmlReader> object can be used to read an XML document and to create <xref:System.Xml.XPath.XPathDocument> and <xref:System.Xml.XmlDocument> objects as shown in the previous sections.</span></span> <span data-ttu-id="4c3b7-118">그러나 <xref:System.Xml.XmlReader> 개체는 인코딩되지 않은 데이터를 읽을 수 있으며 이러한 경우 인코딩 정보를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-118">However, an <xref:System.Xml.XmlReader> object may read data that is not encoded and as a result does not provide any encoding information.</span></span>  
  
 <span data-ttu-id="4c3b7-119"><xref:System.Xml.XmlTextReader> 클래스는 <xref:System.Xml.XmlReader> 클래스에서 상속되며 <xref:System.Xml.XmlTextReader.Encoding%2A> 속성을 사용하여 인코딩 정보를 제공합니다. 또한 <xref:System.Xml.XPath.XPathDocument> 개체 또는 <xref:System.Xml.XmlDocument> 개체를 만드는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-119">The <xref:System.Xml.XmlTextReader> class inherits from the <xref:System.Xml.XmlReader> class, provides encoding information using its <xref:System.Xml.XmlTextReader.Encoding%2A> property, and can be used to create an <xref:System.Xml.XPath.XPathDocument> object or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 <span data-ttu-id="4c3b7-120"><xref:System.Xml.XmlTextReader> 클래스에서 제공하는 인코딩 정보에 대한 자세한 내용은 <xref:System.Xml.XmlTextReader.Encoding%2A> 클래스 참조 문서의 <xref:System.Xml.XmlTextReader> 속성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-120">For more information about the encoding information provided by the <xref:System.Xml.XmlTextReader> class, see the <xref:System.Xml.XmlTextReader.Encoding%2A> property in the <xref:System.Xml.XmlTextReader> class reference documentation.</span></span>  
  
## <a name="creating-xpathnavigator-objects"></a><span data-ttu-id="4c3b7-121">XPathNavigator 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="4c3b7-121">Creating XPathNavigator Objects</span></span>  
 <span data-ttu-id="4c3b7-122"><xref:System.Xml.XPath.XPathDocument> 또는 <xref:System.Xml.XmlDocument> 개체로 XML 문서를 읽어온 후 <xref:System.Xml.XPath.XPathNavigator> 개체를 만들어 기본 XML 데이터를 선택, 평가 및 탐색할 수 있으며 일부 경우에 편집할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-122">After you have read an XML document into either an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object, you can create an <xref:System.Xml.XPath.XPathNavigator> object to select, evaluate, navigate, and in some cases, edit the underlying XML data.</span></span>  
  
 <span data-ttu-id="4c3b7-123"><xref:System.Xml.XPath.XPathDocument> 클래스와 더불어 <xref:System.Xml.XmlDocument> 및 <xref:System.Xml.XmlNode> 클래스는 <xref:System.Xml.XPath.IXPathNavigable> 네임스페이스의 <xref:System.Xml.XPath?displayProperty=nameWithType> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-123">Both the <xref:System.Xml.XPath.XPathDocument> and <xref:System.Xml.XmlDocument> classes, in addition to the <xref:System.Xml.XmlNode> class, implement the <xref:System.Xml.XPath.IXPathNavigable> interface of the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="4c3b7-124">결과적으로 세 클래스는 모두 <xref:System.Xml.XPath.IXPathNavigable.CreateNavigator%2A> 개체를 반환하는 <xref:System.Xml.XPath.XPathNavigator> 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-124">As a result, all three classes provide a <xref:System.Xml.XPath.IXPathNavigable.CreateNavigator%2A> method that returns an <xref:System.Xml.XPath.XPathNavigator> object.</span></span>  
  
### <a name="editing-xml-documents-using-the-xpathnavigator-class"></a><span data-ttu-id="4c3b7-125">XPathNavigator 클래스를 사용하여 XML 문서 편집</span><span class="sxs-lookup"><span data-stu-id="4c3b7-125">Editing XML Documents using the XPathNavigator Class</span></span>  
 <span data-ttu-id="4c3b7-126"><xref:System.Xml.XPath.XPathNavigator> 클래스를 사용하여 XML 데이터를 선택, 평가 및 탐색할 수 있을 뿐 아니라 XML 문서가 생성된 개체를 기반으로 XML 문서를 편집할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-126">In addition to selecting, evaluating, and navigating XML data, the <xref:System.Xml.XPath.XPathNavigator> class can be used to edit an XML document in some cases, based on the object that created it.</span></span>  
  
 <span data-ttu-id="4c3b7-127"><xref:System.Xml.XPath.XPathDocument> 클래스는 읽기 전용인 반면, <xref:System.Xml.XmlDocument> 클래스는 편집 가능하므로 <xref:System.Xml.XPath.XPathNavigator> 개체에서 만든 <xref:System.Xml.XPath.XPathDocument> 개체는 XML 문서를 편집하는 데 사용할 수 없는 반면, <xref:System.Xml.XmlDocument> 개체에서 만든 개체는 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-127">The <xref:System.Xml.XPath.XPathDocument> class is read-only while the <xref:System.Xml.XmlDocument> class is editable and as a result, <xref:System.Xml.XPath.XPathNavigator> objects created from an <xref:System.Xml.XPath.XPathDocument> object cannot be used to edit an XML document while those created from an <xref:System.Xml.XmlDocument> object can.</span></span> <span data-ttu-id="4c3b7-128">XML 문서를 읽기만 하려면 <xref:System.Xml.XPath.XPathDocument> 클래스를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-128">The <xref:System.Xml.XPath.XPathDocument> class should be used to read an XML document only.</span></span> <span data-ttu-id="4c3b7-129">XML 문서를 편집해야 하거나 <xref:System.Xml.XmlDocument> 클래스에서 제공하는 이벤트 처리 등의 추가 기능에 액세스해야 할 경우 <xref:System.Xml.XmlDocument> 클래스를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-129">In cases where you need to edit an XML document, or require access to the additional functionality provided by the <xref:System.Xml.XmlDocument> class, like event handling, the <xref:System.Xml.XmlDocument> class should be used.</span></span>  
  
 <span data-ttu-id="4c3b7-130"><xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator> 속성은 <xref:System.Xml.XPath.XPathNavigator> 개체가 XML 데이터를 편집할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-130">The <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class specifies if an <xref:System.Xml.XPath.XPathNavigator> object may edit XML data.</span></span>  
  
 <span data-ttu-id="4c3b7-131">다음 표에서는 각 클래스에 대한 <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> 속성 값에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3b7-131">The following table describes the value of the <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property for each class.</span></span>  
  
|<span data-ttu-id="4c3b7-132"><xref:System.Xml.XPath.IXPathNavigable> 구현</span><span class="sxs-lookup"><span data-stu-id="4c3b7-132"><xref:System.Xml.XPath.IXPathNavigable> Implementation</span></span>|<span data-ttu-id="4c3b7-133"><xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> 값</span><span class="sxs-lookup"><span data-stu-id="4c3b7-133"><xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> Value</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Xml.XPath.XPathDocument>|`false`|  
|<xref:System.Xml.XmlDocument>|`true`|  
  
## <a name="see-also"></a><span data-ttu-id="4c3b7-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c3b7-134">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="4c3b7-135">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="4c3b7-135">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="4c3b7-136">XPathNavigator를 사용하여 XML 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="4c3b7-136">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="4c3b7-137">XPathNavigator를 사용하여 XML 데이터 편집</span><span class="sxs-lookup"><span data-stu-id="4c3b7-137">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="4c3b7-138">XPathNavigator를 사용하여 스키마 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="4c3b7-138">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
