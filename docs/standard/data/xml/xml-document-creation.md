---
title: "XML 문서 만들기"
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
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a0806e34cfbf7c8e0b5ba995ca4876b8d10405e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-creation"></a><span data-ttu-id="e1b68-102">XML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="e1b68-102">XML Document Creation</span></span>
<span data-ttu-id="e1b68-103">XML 문서를 만드는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-103">There are two ways to create an XML document.</span></span> <span data-ttu-id="e1b68-104">만드는 한 가지 방법은 것는 **XmlDocument** 매개 변수가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-104">One way is to create an **XmlDocument** with no parameters.</span></span> <span data-ttu-id="e1b68-105">다른 방법으로 만드는 것는 **XmlDocument** XmlNameTable에 매개 변수로 전달 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-105">The other way is to create an **XmlDocument** and pass it an XmlNameTable as a parameter.</span></span> <span data-ttu-id="e1b68-106">다음 예제에는 새로운 빈을 만드는 방법을 보여 줍니다 **XmlDocument** 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-106">The following example shows how to create a new, empty **XmlDocument** using no parameters.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 <span data-ttu-id="e1b68-107">문서를 만든 후 문자열의 데이터와 함께 로드할 수 있습니다 스트림, URL, 텍스트 판독기 또는 **XmlReader** 클래스를 사용 하 여 파생 된 **로드** 메서드.</span><span class="sxs-lookup"><span data-stu-id="e1b68-107">Once a document is created, you can load it with data from a string, stream, URL, text reader, or an **XmlReader** derived class using the **Load** method.</span></span> <span data-ttu-id="e1b68-108">다른 로드 메서드도 이기도 **LoadXML** 메서드는 문자열에서 XML을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-108">There is also another load method, the **LoadXML** method, which reads XML from a string.</span></span> <span data-ttu-id="e1b68-109">다양 한 대 한 자세한 내용은 **부하** 메서드 참조 [DOM에 XML 문서 읽어오기](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-109">For more information on the various **Load** methods, see [Reading an XML Document into the DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).</span></span>  
  
 <span data-ttu-id="e1b68-110">라는 클래스가 **XmlNameTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-110">There is a class called the **XmlNameTable**.</span></span> <span data-ttu-id="e1b68-111">이 클래스는 원자화된 문자열 개체를 포함하는 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-111">This class is a table of atomized string objects.</span></span> <span data-ttu-id="e1b68-112">이 테이블을 사용하면 XML 파서에서 쉽게 XML 문서의 반복되는 모든 요소 및 특성 이름에 같은 문자열 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-112">This table provides an efficient means for the XML parser to use the same string object for all repeated element and attribute names in an XML document.</span></span> <span data-ttu-id="e1b68-113">**XmlNameTable** 문서 위에 표시 된 상태로 만들어지는 하 고 문서를 로드 하는 경우 특성 및 요소 이름으로 로드 될 때 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-113">An **XmlNameTable** is automatically created when a document is created as shown above and is loaded with attribute and element names when the document is loaded.</span></span> <span data-ttu-id="e1b68-114">사용 하 여 새 문서를 만들 수 이름 테이블을 사용 하 여 문서에 이미 있는 경우 해당 이름은 다른 문서에도 유용 하다는 **부하** 를 받는 메서드에 **XmlNameTable** 매개 변수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-114">If you already have a document with a name table, and those names would be useful in another document, you can create a new document using the **Load** method that takes an **XmlNameTable** as a parameter.</span></span> <span data-ttu-id="e1b68-115">이 메서드로 문서를 만들면 사용 하 여 기존 **XmlNameTable** 모든 특성 및 요소를 다른 문서에서 이미 로드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-115">When the document is created with this method, it uses the existing **XmlNameTable** with all the attributes and elements already loaded into it from the other document.</span></span> <span data-ttu-id="e1b68-116">이를 사용하여 요소 및 특성 이름을 효율적으로 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-116">It can be used for efficiently comparing element and attribute names.</span></span> <span data-ttu-id="e1b68-117">대 한 자세한 내용은 **XmlNameTable**, 참조 [개체 XmlNameTable을 사용한 비교](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-117">For more information on the **XmlNameTable**, see [Object Comparison Using XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).</span></span> <span data-ttu-id="e1b68-118">참조를 참조 하십시오. <xref:System.Xml.XmlNameTable>합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-118">For reference, see <xref:System.Xml.XmlNameTable>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1b68-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1b68-119">See Also</span></span>  
 [<span data-ttu-id="e1b68-120">XML 문서 개체 모델 (DOM)</span><span class="sxs-lookup"><span data-stu-id="e1b68-120">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
