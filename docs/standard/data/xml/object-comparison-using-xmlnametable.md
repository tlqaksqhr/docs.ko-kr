---
title: XmlNameTable을 사용한 개체 비교
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 8d94e041-d340-4ddf-9a2c-d7319e3f4f86
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09f717cb4c09c1e35b9472b7b549f1d3edf0dd15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="object-comparison-using-xmlnametable"></a><span data-ttu-id="58838-102">XmlNameTable을 사용한 개체 비교</span><span class="sxs-lookup"><span data-stu-id="58838-102">Object Comparison Using XmlNameTable</span></span>
<span data-ttu-id="58838-103">**XmlDocuments**가 생성되면 해당 문서와 관련된 이름 테이블도 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="58838-103">**XmlDocuments**, when created, have a name table created specifically for that document.</span></span> <span data-ttu-id="58838-104">XML이 문서에 로드되거나 새 요소 또는 특성이 생성되면 해당 특성 및 요소 이름이 **XmlNameTable**에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58838-104">When XML is loaded into the document, or new elements or attributes are created, the attribute and element names are put into the **XmlNameTable**.</span></span> <span data-ttu-id="58838-105">또한 다른 문서의 기존 **NameTable**을 사용하여 **XmlDocument**를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58838-105">You can also create an **XmlDocument** using an existing **NameTable** from another document.</span></span> <span data-ttu-id="58838-106">**XmlNameTable** 매개 변수를 사용하는 생성자로 **XmlDocuments**를 만들면 문서에서 **XmlNameTable**에 저장된 노드 이름, 네임스페이스 및 접두사에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58838-106">When **XmlDocuments** are created with the constructor that takes an **XmlNameTable** parameter, the document has access to the node names, namespaces, and prefixes already stored in the **XmlNameTable**.</span></span> <span data-ttu-id="58838-107">이름 테이블에 이름이 로드되는 방법에 관계없이 테이블에 이름을 저장한 후에는 문자열 비교 대신 개체 비교를 통해 이름을 신속하게 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58838-107">Regardless of how the name table is loaded with names, once the names are stored in the table, names can be compared quickly using object comparison instead of string comparison.</span></span> <span data-ttu-id="58838-108">또한 <xref:System.Xml.NameTable.Add%2A>를 사용하여 이름 테이블에 문자열을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58838-108">Strings can also be added to the name table using the <xref:System.Xml.NameTable.Add%2A>.</span></span> <span data-ttu-id="58838-109">다음 코드 샘플에서는 이름 테이블을 만들고 테이블에 **MyString** 문자열을 추가하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="58838-109">The following code sample shows a name table being created and the string **MyString** being added to the table.</span></span> <span data-ttu-id="58838-110">그런 다음, 해당 테이블을 사용하여 **XmlDocument**를 만들고, 기존 이름 테이블에 **Myfile.xml**의 요소 및 특성 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58838-110">After that, an **XmlDocument** is created using that table, and the element and attribute names in **Myfile.xml** are added to the existing name table.</span></span>  
  
```vb  
Dim nt As New NameTable()  
nt.Add("MyString")  
Dim doc As New XmlDocument(nt)  
doc.Load("Myfile.xml")  
```  
  
```csharp  
NameTable nt = new NameTable();  
nt.Add("MyString");  
XmlDocument doc = new XmlDocument(nt);  
doc.Load("Myfile.xml");  
```  
  
 <span data-ttu-id="58838-111">다음 코드 예제에서는 문서를 만들고, 해당 문서에 새 요소 두 개를 추가하여 문서 이름 테이블에 추가하고, 이름에 대한 개체 비교를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58838-111">The following code example shows the creation of a document, two new elements being added to the document, which also adds them to the document name table, and the object comparison on the names.</span></span>  
  
```vb  
Dim doc1 As XmlDocument = imp.CreateDocument()  
Dim node1 As XmlElement = doc.CreateElement("node1")  
Dim doc2 As XmlDocument = imp.CreateDocument()  
Dim node2 As XmlElement = doc.CreateElement("node2")  
if (CType(node1.Name, object) = CType(node2.Name, object))  
```  
  
```csharp  
XmlDocument doc1 = imp.CreateDocument();  
node1 = doc1.CreateElement ("node1");  
XmlDocument doc2 = imp.CreateDocument();  
node2 = doc2.CreateElement ("node1");  
if (((object)node1.Name) == ((object)node2.Name))  
{ ...  
```  
  
 <span data-ttu-id="58838-112">두 문서 사이에서 이름 테이블이 전달되는 위의 시나리오는 주로 XSD(XML 스키마 정의 언어) 스키마나 DTD(문서 종류 정의)를 따르고 동일한 문자열이 반복되는 전자 상거래 사이트의 주문서와 같이 동일한 종류의 문서를 반복적으로 처리하는 경우에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="58838-112">The above scenario of a name table passed between two documents is typical when the same type of document is being processed repeatedly, such as order documents at an ecommerce site, which conform to an XML Schema definition language (XSD) schema or document type definition (DTD) and the same strings are repeated.</span></span> <span data-ttu-id="58838-113">이 경우 동일한 이름 테이블을 사용하면 여러 문서에서 동일한 요소 이름이 나타나기 때문에 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="58838-113">Using the same name table gives a performance improvement, as the same element name occurs in multiple documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58838-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58838-114">See Also</span></span>  
 [<span data-ttu-id="58838-115">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="58838-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
