---
title: "방법: 파일, 문자열 또는 스트림에서 XML 로드(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 572e34b1cd4813fad35e6afaf2ec3d0d9dac470a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="017aa-102">방법: 파일, 문자열 또는 스트림에서 XML 로드(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="017aa-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>
<span data-ttu-id="017aa-103">만들 수 있습니다 [XML 리터럴을](../../../../visual-basic/language-reference/xml-literals/index.md) 여러 가지 방법을 사용 하 여 파일, 문자열 또는 스트림에 같은 외부 소스에서 내용으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="017aa-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="017aa-104">이러한 메서드는 다음 예제에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="017aa-104">These methods are shown in the following examples.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a><span data-ttu-id="017aa-105">파일에서 XML을 로드 하지</span><span class="sxs-lookup"><span data-stu-id="017aa-105">To load XML from a file</span></span>  
  
-   <span data-ttu-id="017aa-106">XML과 같은 리터럴 채우려면는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 을 사용 하 여 파일에서 개체는 `Load` 메서드.</span><span class="sxs-lookup"><span data-stu-id="017aa-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="017aa-107">이 메서드는 입력으로는 파일 경로, 텍스트 스트림에 또는 XML 스트림을 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="017aa-107">This method can take a file path, text stream, or XML stream as input.</span></span>  
  
     <span data-ttu-id="017aa-108">다음 코드 예제에서는 사용을 보여 줍니다.는 <xref:System.Xml.Linq.XDocument.Load%28System.String%29> 를 채우는 메서드는 <xref:System.Xml.Linq.XDocument> 텍스트 파일에서 XML로 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="017aa-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>  
  
     [!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### <a name="to-load-xml-from-a-string"></a><span data-ttu-id="017aa-109">문자열에서 XML을 로드 하지</span><span class="sxs-lookup"><span data-stu-id="017aa-109">To load XML from a string</span></span>  
  
-   <span data-ttu-id="017aa-110">XML과 같은 리터럴 채우려면는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체는 문자열에서 사용할 수 있습니다는 `Parse` 메서드.</span><span class="sxs-lookup"><span data-stu-id="017aa-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>  
  
     <span data-ttu-id="017aa-111">다음 코드 예제에서는 사용을 보여 줍니다.는 <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> 를 채우는 메서드는 <xref:System.Xml.Linq.XDocument> 문자열에서 XML로 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="017aa-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>  
  
     [!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="017aa-112">스트림에서 XML을 로드 하지</span><span class="sxs-lookup"><span data-stu-id="017aa-112">To load XML from a stream</span></span>  
  
-   <span data-ttu-id="017aa-113">XML과 같은 리터럴 채우려면는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체 스트림, 사용할 수 있습니다는 `Load` 메서드 또는 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="017aa-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="017aa-114">다음 코드 예제에서는 사용을 보여 줍니다.는 <xref:System.Xml.Linq.XNode.ReadFrom%2A> 를 채우는 메서드는 <xref:System.Xml.Linq.XDocument> XML 스트림에서 xml 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="017aa-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>  
  
 [!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="017aa-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="017aa-115">See Also</span></span>  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="017aa-116">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="017aa-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="017aa-117">XML</span><span class="sxs-lookup"><span data-stu-id="017aa-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="017aa-118">Visual Basic에서 XML 조작</span><span class="sxs-lookup"><span data-stu-id="017aa-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
