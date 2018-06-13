---
title: XML 문서 만들기
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ab7632966cd2a0087a8bdc1d452d02543edbec4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572790"
---
# <a name="xml-document-creation"></a><span data-ttu-id="64470-102">XML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="64470-102">XML Document Creation</span></span>
<span data-ttu-id="64470-103">XML 문서를 만드는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64470-103">There are two ways to create an XML document.</span></span> <span data-ttu-id="64470-104">하나는 매개 변수 없이 **XmlDocument**를 만드는 방법이고</span><span class="sxs-lookup"><span data-stu-id="64470-104">One way is to create an **XmlDocument** with no parameters.</span></span> <span data-ttu-id="64470-105">다른 방법은 **XmlDocument**를 만들어 XmlNameTable를 매개 변수로 전달하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="64470-105">The other way is to create an **XmlDocument** and pass it an XmlNameTable as a parameter.</span></span> <span data-ttu-id="64470-106">다음 예제에서는 매개 변수를 사용하지 않고 비어 있는 새 **XmlDocument**를 만드는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="64470-106">The following example shows how to create a new, empty **XmlDocument** using no parameters.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 <span data-ttu-id="64470-107">문서를 만든 후에는 **Load** 메서드를 사용하여 문자열, 스트림, URL, 텍스트 판독기 또는 **XmlReader** 파생 클래스의 데이터와 함께 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64470-107">Once a document is created, you can load it with data from a string, stream, URL, text reader, or an **XmlReader** derived class using the **Load** method.</span></span> <span data-ttu-id="64470-108">또한 문자열에서 XML을 읽는 **LoadXML** 메서드라는 다른 로드 메서드도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64470-108">There is also another load method, the **LoadXML** method, which reads XML from a string.</span></span> <span data-ttu-id="64470-109">다양한 **Load** 메서드에 대한 자세한 내용은 [DOM에 XML 문서 읽어오기](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="64470-109">For more information on the various **Load** methods, see [Reading an XML Document into the DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).</span></span>  
  
 <span data-ttu-id="64470-110">**XmlNameTable**이라는 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64470-110">There is a class called the **XmlNameTable**.</span></span> <span data-ttu-id="64470-111">이 클래스는 원자화된 문자열 개체를 포함하는 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="64470-111">This class is a table of atomized string objects.</span></span> <span data-ttu-id="64470-112">이 테이블을 사용하면 XML 파서에서 쉽게 XML 문서의 반복되는 모든 요소 및 특성 이름에 같은 문자열 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64470-112">This table provides an efficient means for the XML parser to use the same string object for all repeated element and attribute names in an XML document.</span></span> <span data-ttu-id="64470-113">**XmlNameTable**은 문서가 생성될 때 위와 같이 자동으로 생성되며 문서가 로드되면 특성 및 요소 이름과 함께 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="64470-113">An **XmlNameTable** is automatically created when a document is created as shown above and is loaded with attribute and element names when the document is loaded.</span></span> <span data-ttu-id="64470-114">이름 테이블이 포함된 문서가 이미 있고 해당 이름이 다른 문서에도 유용하다면 **XmlNameTable**이 매개 변수인 **Load** 메서드를 사용하여 새 문서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64470-114">If you already have a document with a name table, and those names would be useful in another document, you can create a new document using the **Load** method that takes an **XmlNameTable** as a parameter.</span></span> <span data-ttu-id="64470-115">이 메서드로 문서를 만들면 해당 문서는 다른 문서의 모든 특성 및 요소를 이미 로드한 기존의 **XmlNameTable**을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="64470-115">When the document is created with this method, it uses the existing **XmlNameTable** with all the attributes and elements already loaded into it from the other document.</span></span> <span data-ttu-id="64470-116">이를 사용하여 요소 및 특성 이름을 효율적으로 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64470-116">It can be used for efficiently comparing element and attribute names.</span></span> <span data-ttu-id="64470-117">**XmlNameTable**에 대한 자세한 내용은 [XmlNameTable을 사용한 개체 비교](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="64470-117">For more information on the **XmlNameTable**, see [Object Comparison Using XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).</span></span> <span data-ttu-id="64470-118">참조에 대한 내용은 <xref:System.Xml.XmlNameTable>을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="64470-118">For reference, see <xref:System.Xml.XmlNameTable>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64470-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64470-119">See Also</span></span>  
 [<span data-ttu-id="64470-120">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="64470-120">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
