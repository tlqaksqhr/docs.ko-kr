---
title: 문서 작성 및 저장
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 097b0cb1-5743-4c3a-86ef-caf5cbe6750d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 389ae0d95f3d612ca9c81ce69b74f8b58534d679
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573596"
---
# <a name="saving-and-writing-a-document"></a><span data-ttu-id="344fd-102">문서 작성 및 저장</span><span class="sxs-lookup"><span data-stu-id="344fd-102">Saving and Writing a Document</span></span>
<span data-ttu-id="344fd-103"><xref:System.Xml.XmlDocument>를 로드하고 저장할 경우 저장된 문서는 다음과 같이 원래 문서와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-103">When you load and save an <xref:System.Xml.XmlDocument>, the saved document may differ from the original in the following ways:</span></span>  
  
-   <span data-ttu-id="344fd-104"><xref:System.Xml.XmlDocument.PreserveWhitespace%2A> 메서드를 호출하기 전에 `true` 속성을 <xref:System.Xml.XmlDocument.Save%2A>로 설정한 경우 문서 내의 공백이 출력에서 유지되며 `false`로 설정한 경우 <xref:System.Xml.XmlDocument>는 출력을 자동으로 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-104">If the <xref:System.Xml.XmlDocument.PreserveWhitespace%2A> property is set to `true` before the <xref:System.Xml.XmlDocument.Save%2A> method is called, white space in the document is preserved in the output; if this property is `false`, <xref:System.Xml.XmlDocument> auto-indents the output.</span></span>  
  
-   <span data-ttu-id="344fd-105">특성 사이에 있는 모든 공백은 단일 공백 문자로 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-105">All the white space between attributes is reduced to a single space character.</span></span>  
  
-   <span data-ttu-id="344fd-106">요소 사이에 있는 공백이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-106">The white space between elements is changed.</span></span> <span data-ttu-id="344fd-107">유효 공백은 유지되고 무효 공백은 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-107">Significant white space is preserved and insignificant white space is not.</span></span> <span data-ttu-id="344fd-108">그러나 문서를 저장할 때 기본적으로 <xref:System.Xml.XmlTextWriter> **Indenting** 모드를 사용하여 출력이 읽기 쉽도록 정리됩니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-108">But when the document is saved, it will use the <xref:System.Xml.XmlTextWriter> **Indenting** mode by default to neatly print the output to make it more readable.</span></span>  
  
-   <span data-ttu-id="344fd-109">특성 값 주위에 사용된 작은따옴표는 기본적으로 큰따옴표로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-109">The quote character used around attribute values is changed to double quote by default.</span></span> <span data-ttu-id="344fd-110"><xref:System.Xml.XmlTextReader.QuoteChar%2A>의 <xref:System.Xml.XmlTextWriter> 속성을 사용하여 인용 문자를 작은따옴표나 큰따옴표로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-110">You can use the <xref:System.Xml.XmlTextReader.QuoteChar%2A> property on <xref:System.Xml.XmlTextWriter> to set the quote character to either double quote or single quote.</span></span>  
  
-   <span data-ttu-id="344fd-111">기본적으로 `{`과 같은 숫자 엔터티는 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-111">By default, numeric character entities like `{` are expanded.</span></span>  
  
-   <span data-ttu-id="344fd-112">입력 문서에 있는 바이트 순서 표시는 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-112">The byte-order mark found in the input document is not preserved.</span></span> <span data-ttu-id="344fd-113">명시적으로 다른 인코딩을 지정하는 XML 선언을 하지 않으면 UCS-2는 UTF-8로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-113">UCS-2 is saved as UTF-8 unless you explicitly create an XML declaration that specifies a different encoding.</span></span>  
  
-   <span data-ttu-id="344fd-114">파일이나 스트림에 <xref:System.Xml.XmlDocument>를 쓸 경우 출력된 내용은 문서의 내용과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-114">If you want to write out the <xref:System.Xml.XmlDocument> into a file or stream, the output written out is the same as the content of the document.</span></span> <span data-ttu-id="344fd-115">즉, <xref:System.Xml.XmlDeclaration>은 문서에 포함되어 있고 문서를 쓸 때 사용되는 인코딩이 선언 노드에 지정된 인코딩과 같은 경우에만 쓰여집니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-115">That is, the <xref:System.Xml.XmlDeclaration> is written out only if there is one contained in the document, and the encoding used when writing out the document is the same encoding given in the declaration node.</span></span>  
  
## <a name="writing-an-xmldeclaration"></a><span data-ttu-id="344fd-116">XmlDeclaration 쓰기</span><span class="sxs-lookup"><span data-stu-id="344fd-116">Writing an XmlDeclaration</span></span>  
 <span data-ttu-id="344fd-117"><xref:System.Xml.XmlDocument> 및 <xref:System.Xml.XmlDeclaration>의 <xref:System.Xml.XmlNode.OuterXml%2A> 메서드 외에도 <xref:System.Xml.XmlNode.InnerXml%2A>, <xref:System.Xml.XmlNode.WriteTo%2A> 및 <xref:System.Xml.XmlDocument>의 <xref:System.Xml.XmlDocument.Save%2A> 및 <xref:System.Xml.XmlDocument.WriteContentTo%2A> 멤버는 XML 선언을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-117">The <xref:System.Xml.XmlDocument> and <xref:System.Xml.XmlDeclaration> members of <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlNode.InnerXml%2A>, and <xref:System.Xml.XmlNode.WriteTo%2A>, in addition to the <xref:System.Xml.XmlDocument> methods of <xref:System.Xml.XmlDocument.Save%2A> and <xref:System.Xml.XmlDocument.WriteContentTo%2A>, create an XML declaration.</span></span>  
  
 <span data-ttu-id="344fd-118"><xref:System.Xml.XmlDocument>, <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlDocument.InnerXml%2A>, <xref:System.Xml.XmlDocument.Save%2A> 및 <xref:System.Xml.XmlDocument.WriteTo%2A> 메서드의 <xref:System.Xml.XmlDocument.WriteContentTo%2A> 속성의 경우 XML 선언에 쓰여질 인코딩을 <xref:System.Xml.XmlDeclaration> 노드에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-118">For the <xref:System.Xml.XmlDocument> properties of <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlDocument.InnerXml%2A>, and the <xref:System.Xml.XmlDocument.Save%2A>, <xref:System.Xml.XmlDocument.WriteTo%2A>, and <xref:System.Xml.XmlDocument.WriteContentTo%2A> methods, the encoding written out in the XML declaration is taken from the <xref:System.Xml.XmlDeclaration> node.</span></span> <span data-ttu-id="344fd-119"><xref:System.Xml.XmlDeclaration> 노드가 없으면 <xref:System.Xml.XmlDeclaration>이 쓰여지지 않습니다. <xref:System.Xml.XmlDeclaration> 노드에 인코딩이 없으면 XML 선언에 인코딩이 쓰여지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-119">If there is no <xref:System.Xml.XmlDeclaration> node, <xref:System.Xml.XmlDeclaration> is not written out. If there is no encoding in the <xref:System.Xml.XmlDeclaration> node, encoding is not written out in the XML declaration.</span></span>  
  
 <span data-ttu-id="344fd-120"><xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType> 및 <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType> 메서드는 항상 <xref:System.Xml.XmlDeclaration>을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-120">The <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType> and <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType> methods always write out an <xref:System.Xml.XmlDeclaration>.</span></span> <span data-ttu-id="344fd-121">이러한 메서드는 쓰려는 작성기에서 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-121">These methods take the encoding from the writer that it is writing to.</span></span> <span data-ttu-id="344fd-122">즉, 작성기의 인코딩 값이 문서와 <xref:System.Xml.XmlDeclaration> 개체의 인코딩을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-122">That is, the encoding value on the writer overrides the encoding on the document and in the <xref:System.Xml.XmlDeclaration>.</span></span> <span data-ttu-id="344fd-123">예를 들어, 다음 코드에서는 `out.xml` 출력 파일에서 찾은 XML 선언에 인코딩을 쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-123">For example, the following code does not write an encoding in the XML declaration found in the output file `out.xml`.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
Dim tw As XmlTextWriter = New XmlTextWriter("out.xml", Nothing)  
doc.Load("text.xml")  
doc.Save(tw)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlTextWriter tw = new XmlTextWriter("out.xml", null);  
doc.Load("text.xml");  
doc.Save(tw);  
```  
  
 <span data-ttu-id="344fd-124"><xref:System.Xml.XmlDocument.Save%2A> 메서드의 경우 <xref:System.Xml.XmlWriter.WriteStartDocument%2A> 클래스의 <xref:System.Xml.XmlWriter> 메서드를 사용하여 XML 선언을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-124">For the <xref:System.Xml.XmlDocument.Save%2A> method, the XML declaration is written out using the <xref:System.Xml.XmlWriter.WriteStartDocument%2A> method in the <xref:System.Xml.XmlWriter> class.</span></span> <span data-ttu-id="344fd-125">따라서 <xref:System.Xml.XmlWriter.WriteStartDocument%2A> 메서드를 덮어쓰면 문서의 시작 부분을 쓰는 방법이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-125">Therefore, overwriting the <xref:System.Xml.XmlWriter.WriteStartDocument%2A> method changes how the start of the document is written.</span></span>  
  
 <span data-ttu-id="344fd-126"><xref:System.Xml.XmlDeclaration>, <xref:System.Xml.XmlNode.OuterXml%2A> 및 <xref:System.Xml.XmlDeclaration.WriteTo%2A>의 <xref:System.Xml.XmlNode.InnerXml%2A> 멤버의 경우 <xref:System.Xml.XmlDeclaration.Encoding%2A> 속성을 설정하지 않으면 인코딩이 쓰여지지 않습니다. 그렇지 않은 경우 XML 선언에 쓰여지는 인코딩은 <xref:System.Xml.XmlDeclaration.Encoding%2A> 속성에서 찾은 인코딩과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-126">For the <xref:System.Xml.XmlDeclaration> members of <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlDeclaration.WriteTo%2A>, and <xref:System.Xml.XmlNode.InnerXml%2A>, if the <xref:System.Xml.XmlDeclaration.Encoding%2A> property is not set, no encoding is written out. Otherwise, the encoding written out in the XML declaration is the same as the encoding found in the <xref:System.Xml.XmlDeclaration.Encoding%2A> property.</span></span>  
  
## <a name="writing-document-content-using-the-outerxml-property"></a><span data-ttu-id="344fd-127">OuterXml 속성을 사용하여 문서 내용 작성</span><span class="sxs-lookup"><span data-stu-id="344fd-127">Writing Document Content Using the OuterXml Property</span></span>  
 <span data-ttu-id="344fd-128"><xref:System.Xml.XmlNode.OuterXml%2A> 속성은 Microsoft에서 W3C(World Wide Web 컨소시엄) XML DOM(문서 개체 모델) 표준을 확장한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-128">The <xref:System.Xml.XmlNode.OuterXml%2A> property is a Microsoft extension to the World Wide Web Consortium (W3C) XML Document Object Model (DOM) standards.</span></span> <span data-ttu-id="344fd-129"><xref:System.Xml.XmlNode.OuterXml%2A> 속성을 사용하여 전체 XML 문서의 태그를 가져오거나 단일 노드 및 해당 자식 노드의 태그만 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-129">The <xref:System.Xml.XmlNode.OuterXml%2A> property is used to get the markup of the whole XML document, or just the markup of a single node and its child nodes.</span></span> <span data-ttu-id="344fd-130"><xref:System.Xml.XmlNode.OuterXml%2A>은 지정된 노드 및 모든 자식 노드를 나타내는 태그를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-130"><xref:System.Xml.XmlNode.OuterXml%2A> returns the markup representing the given node and all its child nodes.</span></span>  
  
 <span data-ttu-id="344fd-131">다음 코드 예제에서는 문서 전체를 문자열로 저장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-131">The following code sample shows how to save a document in its entirety as a string.</span></span>  
  
```vb  
Dim mydoc As New XmlDocument()  
' Perform application needs here, like mydoc.Load("myfile");  
' Now save the entire document to a string variable called "xml".  
Dim xml As String = mydoc.OuterXml  
```  
  
```csharp  
XmlDocument mydoc = new XmlDocument();  
// Perform application needs here, like mydoc.Load("myfile");  
// Now save the entire document to a string variable called "xml".  
string xml = mydoc.OuterXml;  
```  
  
 <span data-ttu-id="344fd-132">다음 코드 예제에서는 문서 요소만 저장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-132">The following code sample shows how to save only the document element.</span></span>  
  
```vb  
' For the content of the Document Element only.  
Dim xml As String = mydoc.DocumentElement.OuterXml  
```  
  
```csharp  
// For the content of the Document Element only.  
string xml = mydoc.DocumentElement.OuterXml;  
```  
  
 <span data-ttu-id="344fd-133">이와는 반대로 자식 노드의 내용이 필요한 경우 <xref:System.Xml.XmlNode.InnerText%2A> 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fd-133">In contrast, you can use the <xref:System.Xml.XmlNode.InnerText%2A> property if you want the content of child nodes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="344fd-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="344fd-134">See Also</span></span>  
 [<span data-ttu-id="344fd-135">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="344fd-135">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
