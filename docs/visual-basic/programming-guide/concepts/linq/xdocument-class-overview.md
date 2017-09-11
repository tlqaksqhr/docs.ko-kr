---
title: "XDocument 클래스 개요 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 45cb7e71-196a-47da-bfe9-7a5589db1eed
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3f51808a64d51fb354159df1a7323ad2fc26eedc
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="xdocument-class-overview-visual-basic"></a><span data-ttu-id="07b5d-102">XDocument 클래스 개요 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07b5d-102">XDocument Class Overview (Visual Basic)</span></span>
<span data-ttu-id="07b5d-103">이 항목에서는 <xref:System.Xml.Linq.XDocument>클래스</xref:System.Xml.Linq.XDocument> 소개</span><span class="sxs-lookup"><span data-stu-id="07b5d-103">This topic introduces the <xref:System.Xml.Linq.XDocument> class.</span></span>  
  
## <a name="overview-of-the-xdocument-class"></a><span data-ttu-id="07b5d-104">XDocument 클래스 개요</span><span class="sxs-lookup"><span data-stu-id="07b5d-104">Overview of the XDocument class</span></span>  
 <span data-ttu-id="07b5d-105"><xref:System.Xml.Linq.XDocument>클래스는 유효한 XML 문서에 필요한 정보를 포함 합니다.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="07b5d-105">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document.</span></span> <span data-ttu-id="07b5d-106">여기에는 XML 선언, 처리 명령 및 주석이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07b5d-106">This includes an XML declaration, processing instructions, and comments.</span></span>  
  
 <span data-ttu-id="07b5d-107">Note 있다고 <xref:System.Xml.Linq.XDocument> <xref:System.Xml.Linq.XDocument>클래스</xref:System.Xml.Linq.XDocument> 에서 제공 하는 특정 기능이 필요한 경우 개체를</xref:System.Xml.Linq.XDocument> 만들려면</span><span class="sxs-lookup"><span data-stu-id="07b5d-107">Note that you only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="07b5d-108">대부분의 경우 <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 로 직접 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07b5d-108">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="07b5d-109">직접 작업할 <xref:System.Xml.Linq.XElement>더 간단한 프로그래밍 모델.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="07b5d-109">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>  
  
 <span data-ttu-id="07b5d-110"><xref:System.Xml.Linq.XDocument><xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer> 에서 파생</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="07b5d-110"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="07b5d-111">자식 노드를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07b5d-111">Therefore, it can contain child nodes.</span></span> <span data-ttu-id="07b5d-112">그러나 <xref:System.Xml.Linq.XDocument>개체에 자식 노드가 한 개만 가질 수 있습니다 <xref:System.Xml.Linq.XElement>노드.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="07b5d-112">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="07b5d-113">이는 XML 문서에 루트 요소가 하나만 있어야 하는 XML 표준을 반영하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="07b5d-113">This reflects the XML standard that there can be only one root element in an XML document.</span></span>  
  
## <a name="components-of-xdocument"></a><span data-ttu-id="07b5d-114">XDocument의 구성 요소</span><span class="sxs-lookup"><span data-stu-id="07b5d-114">Components of XDocument</span></span>  
 <span data-ttu-id="07b5d-115"><xref:System.Xml.Linq.XDocument>는 다음과 같은 요소가 포함 될 수 있습니다:</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="07b5d-115">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>  
  
-   <span data-ttu-id="07b5d-116">하나의 <xref:System.Xml.Linq.XDeclaration>개체.</xref:System.Xml.Linq.XDeclaration></span><span class="sxs-lookup"><span data-stu-id="07b5d-116">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="07b5d-117"><xref:System.Xml.Linq.XDeclaration>XML 선언의 관련 부분인 지정할 수 있습니다: XML 버전, 문서의 인코딩 및 XML 문서가 독립 실행형인지 여부.</xref:System.Xml.Linq.XDeclaration></span><span class="sxs-lookup"><span data-stu-id="07b5d-117"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.</span></span>  
  
-   <span data-ttu-id="07b5d-118">하나의 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="07b5d-118">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="07b5d-119">이 개체는 XML 문서의 루트 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="07b5d-119">This is the root node of the XML document.</span></span>  
  
-   <span data-ttu-id="07b5d-120">개수에 관계 없이 <xref:System.Xml.Linq.XProcessingInstruction>개체.</xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="07b5d-120">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="07b5d-121">처리 명령은 XML을 처리하는 정보를 응용 프로그램에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="07b5d-121">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
-   <span data-ttu-id="07b5d-122">개수에 관계 없이 <xref:System.Xml.Linq.XComment>개체.</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="07b5d-122">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="07b5d-123">주석은 루트 요소의 형제입니다.</span><span class="sxs-lookup"><span data-stu-id="07b5d-123">The comments will be siblings to the root element.</span></span> <span data-ttu-id="07b5d-124"><xref:System.Xml.Linq.XComment>유효 하지 않은 주석으로 시작 하는 XML 문서에 대 한 개체 목록에서 첫 번째 인수 일 수 없습니다.</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="07b5d-124">The <xref:System.Xml.Linq.XComment> object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.</span></span>  
  
-   <span data-ttu-id="07b5d-125">하나의 <xref:System.Xml.Linq.XDocumentType>DTD에 대 한.</xref:System.Xml.Linq.XDocumentType></span><span class="sxs-lookup"><span data-stu-id="07b5d-125">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>  
  
 <span data-ttu-id="07b5d-126">Serialize 할 때는 <xref:System.Xml.Linq.XDocument>, 경우에 `XDocument.Declaration` 는 `null`, 작성기 있으면 출력에 XML 선언이 포함 됩니다 `Writer.Settings.OmitXmlDeclaration` 로 설정 `false` (기본값).</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="07b5d-126">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>  
  
 <span data-ttu-id="07b5d-127">기본적으로 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]에서는 버전을 "1.0"으로 설정하고 인코딩을 "utf-8"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="07b5d-127">By default, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] sets the version to "1.0", and sets the encoding to "utf-8".</span></span>  
  
## <a name="using-xelement-without-xdocument"></a><span data-ttu-id="07b5d-128">XDocument 없이 XElement 사용</span><span class="sxs-lookup"><span data-stu-id="07b5d-128">Using XElement without XDocument</span></span>  
 <span data-ttu-id="07b5d-129">에서 설명한 대로 <xref:System.Xml.Linq.XElement>클래스의 기본 클래스는는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 프로그래밍 인터페이스입니다.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="07b5d-129">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] programming interface.</span></span> <span data-ttu-id="07b5d-130">응용 프로그램에서는 대부분의 경우 문서를 만들도록 요구하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07b5d-130">In many cases, your application will not require that you create a document.</span></span> <span data-ttu-id="07b5d-131">사용 하 여는 <xref:System.Xml.Linq.XElement>클래스를 XML 트리를 만들고, 다른 XML 트리를 추가, XML 트리를 수정 및 저장 합니다. 수 있습니다</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="07b5d-131">By using the <xref:System.Xml.Linq.XElement> class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.</span></span>  
  
## <a name="using-xdocument"></a><span data-ttu-id="07b5d-132">XDocument 사용</span><span class="sxs-lookup"><span data-stu-id="07b5d-132">Using XDocument</span></span>  
 <span data-ttu-id="07b5d-133">생성 하는 <xref:System.Xml.Linq.XDocument>를 생성 하려면와 마찬가지로 함수 생성을 사용 하 여 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="07b5d-133">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="07b5d-134">다음 코드는 <xref:System.Xml.Linq.XDocument>개체와 연결 된 포함.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="07b5d-134">The following code creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>  
  
```vb  
Dim doc As XDocument = <?xml version="1.0" encoding="utf-8"?>  
                       <!--This is a comment.-->  
                       <?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
                       <Pubs>  
                           <Book>  
                               <Title>Artifacts of Roman Civilization</Title>  
                               <Author>Moreno, Jordao</Author>  
                           </Book>  
                           <Book>  
                               <Title>Midieval Tools and Implements</Title>  
                               <Author>Gazit, Inbar</Author>  
                           </Book>  
                       </Pubs>  
                       <!--This is another comment.-->  
doc.Save("test.xml")  
```  
  
 <span data-ttu-id="07b5d-135">test.xml 파일을 검사할 때 다음과 같은 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="07b5d-135">When you examine the file test.xml, you get the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!--This is a comment.-->  
<?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
<Pubs>  
  <Book>  
    <Title>Artifacts of Roman Civilization</Title>  
    <Author>Moreno, Jordao</Author>  
  </Book>  
  <Book>  
    <Title>Midieval Tools and Implements</Title>  
    <Author>Gazit, Inbar</Author>  
  </Book>  
</Pubs>  
<!--This is another comment.-->  
```  
  
## <a name="see-also"></a><span data-ttu-id="07b5d-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07b5d-136">See Also</span></span>  
 [<span data-ttu-id="07b5d-137">LINQ to XML 프로그래밍 개요 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07b5d-137">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
