---
title: "DOM에 XML 문서 읽어오기"
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
ms.assetid: a4fb291f-5630-49ba-a49a-5b66c3b71e49
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b8844705b492574443ff4f37de33ccaf1f5fedd7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="reading-an-xml-document-into-the-dom"></a><span data-ttu-id="86191-102">DOM에 XML 문서 읽어오기</span><span class="sxs-lookup"><span data-stu-id="86191-102">Reading an XML Document into the DOM</span></span>
<span data-ttu-id="86191-103">다양한 형식으로 XML 정보를 메모리에 읽어옵니다.</span><span class="sxs-lookup"><span data-stu-id="86191-103">XML information is read into memory from different formats.</span></span> <span data-ttu-id="86191-104">문자열, 스트림, URL, 텍스트 판독기 또는 <xref:System.Xml.XmlReader>에서 파생된 클래스에서 XML 정보를 읽어올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86191-104">It can be read from a string, stream, URL, text reader, or a class derived from the <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="86191-105"><xref:System.Xml.XmlDocument.Load%2A> 메서드는 문서를 메모리로 가져오며 이 메서드에는 각각의 다양한 형식에서 데이터를 가져오는 데 사용할 수 있는 오버로드된 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86191-105">The <xref:System.Xml.XmlDocument.Load%2A> method brings the document into memory and has overloaded methods available to take data from each of the different formats.</span></span> <span data-ttu-id="86191-106">또한 문자열에서 XML을 읽는 <xref:System.Xml.XmlDocument.LoadXml%2A> 메서드도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86191-106">There is also a <xref:System.Xml.XmlDocument.LoadXml%2A> method that reads XML from a string.</span></span>  
  
 <span data-ttu-id="86191-107">XML DOM(문서 개체 모델)이 로드될 때 만들어지는 노드는 각 <xref:System.Xml.XmlDocument.Load%2A> 메서드에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="86191-107">Different <xref:System.Xml.XmlDocument.Load%2A> methods affect which nodes are created when the XML Document Object Model (DOM) is loaded.</span></span> <span data-ttu-id="86191-108">다음 표에서는 일부 <xref:System.Xml.XmlDocument.Load%2A> 메서드 간의 차이점 및 이러한 차이점을 다루는 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="86191-108">The following table lists the differences between some of the <xref:System.Xml.XmlDocument.Load%2A> methods and topics that address them.</span></span>  
  
|<span data-ttu-id="86191-109">Subject</span><span class="sxs-lookup"><span data-stu-id="86191-109">Subject</span></span>|<span data-ttu-id="86191-110">항목</span><span class="sxs-lookup"><span data-stu-id="86191-110">Topic</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="86191-111">공백 노드 만들기</span><span class="sxs-lookup"><span data-stu-id="86191-111">Creation of white space nodes</span></span>|<span data-ttu-id="86191-112">DOM을 로드하는 데 사용된 개체는 DOM에 생성된 공백 및 유효 공백 노드에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="86191-112">The object used to load the DOM has an affect on the white space and significant white space nodes generated in the DOM.</span></span> <span data-ttu-id="86191-113">자세한 내용은 참조 [공백 및 DOM을 로드할 때 중요 한 공백 처리](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="86191-113">For more information, see [White Space and Significant White Space Handling when Loading the DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span></span>|  
|<span data-ttu-id="86191-114">특정 노드부터 XML 로드 또는 전체 XML 문서 로드</span><span class="sxs-lookup"><span data-stu-id="86191-114">Loading XML starting from a specific node or loading the entire XML document</span></span>|<span data-ttu-id="86191-115">사용 하 여 <xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType> DOM에 있으며 특정 노드에서 메서드 데이터를 로드할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="86191-115">Using the <xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType> method data can be loaded from a specific node into the DOM.</span></span> <span data-ttu-id="86191-116">자세한 내용은 참조 [판독기에서 데이터 로드](../../../../docs/standard/data/xml/load-data-from-a-reader.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="86191-116">For more information, see [Load Data from a Reader](../../../../docs/standard/data/xml/load-data-from-a-reader.md).</span></span>|  
|<span data-ttu-id="86191-117">XML을 로드할 때 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="86191-117">Validating the XML as it is loaded</span></span>|<span data-ttu-id="86191-118">DOM으로 XML 데이터를 로드할 때 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86191-118">The XML data loaded into the DOM can be validated as it is loaded.</span></span> <span data-ttu-id="86191-119"><xref:System.Xml.XmlReader> 유효성 검사를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86191-119">This is accomplished using a validating <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="86191-120">로드 되 면 XML의 유효성을 검사 하는 방법에 대 한 자세한 내용은 참조 [DOM에서 XML 문서 유효성 검사](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="86191-120">For more information about validating XML as it is loaded, see [Validating an XML Document in the DOM](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md).</span></span>|  
  
 <span data-ttu-id="86191-121">다음 예제에서는 <xref:System.Xml.XmlDocument.LoadXml%2A> 메서드를 사용하여 XML을 로드하고 `data.xml`이라는 텍스트 파일에 데이터를 저장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="86191-121">The following example shows XML being loaded with the <xref:System.Xml.XmlDocument.LoadXml%2A> method and the data subsequently saved to a text file called `data.xml`.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
        ' Create the XmlDocument.  
        Dim doc As New XmlDocument()  
        doc.LoadXml(("<book genre='novel' ISBN='1-861001-57-5'>" & _  
                    "<title>Pride And Prejudice</title>" & _  
                    "</book>"))  
        ' Save the document to a file.  
        doc.Save("data.xml")  
    End Sub 'Main  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    public static void Main()  
    {  
        // Create the XmlDocument.  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5'>" +  
                    "<title>Pride And Prejudice</title>" +  
                    "</book>");  
  
        // Save the document to a file.  
        doc.Save("data.xml");  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="86191-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86191-122">See Also</span></span>  
 [<span data-ttu-id="86191-123">XML 문서 개체 모델 (DOM)</span><span class="sxs-lookup"><span data-stu-id="86191-123">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
