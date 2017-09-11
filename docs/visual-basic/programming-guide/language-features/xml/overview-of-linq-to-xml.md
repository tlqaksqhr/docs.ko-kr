---
title: "Visual Basic의 LINQ to XML 개요 | Microsoft 문서"
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
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: cab0c219fe62064c62af4bd93e445107d73974db
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a><span data-ttu-id="eb27d-102">Visual Basic의 LINQ to XML 개요</span><span class="sxs-lookup"><span data-stu-id="eb27d-102">Overview of LINQ to XML in Visual Basic</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="eb27d-103">에 대 한 지원을 제공 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] XML 리터럴과 XML 축 속성을 통해.</span><span class="sxs-lookup"><span data-stu-id="eb27d-103"> provides support for [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] through XML literals and XML axis properties.</span></span> <span data-ttu-id="eb27d-104">이렇게 하면에서 XML 사용에 대 한 친숙 하 고 편리한 구문을 사용 하 여 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-104">This enables you to use a familiar, convenient syntax for working with XML in your [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span> <span data-ttu-id="eb27d-105">*XML 리터럴* 코드에서 직접 XML을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-105">*XML literals* enable you to include XML directly in your code.</span></span> <span data-ttu-id="eb27d-106">*XML 축 속성* 액세스 자식 노드, 하위 노드 및 XML 리터럴의 특성을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-106">*XML axis properties* enable you to access child nodes, descendant nodes, and attributes of an XML literal.</span></span> <span data-ttu-id="eb27d-107">자세한 내용은 참조 [XML 리터럴 개요](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) 및 [Visual Basic의 XML에 액세스](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-107">For more information, see [XML Literals Overview](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) and [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="eb27d-108">메모리 내 XML 프로그래밍 API를 활용 하도록 특별히 설계 된 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-108"> is an in-memory XML programming API designed specifically to take advantage of [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)].</span></span> <span data-ttu-id="eb27d-109">호출할 수 있지만 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Api를 직접만 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] XML 리터럴 선언 및 XML 축 속성에 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-109">Although you can call the [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] APIs directly, only [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enables you to declare XML literals and directly access XML axis properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb27d-110">XML 리터럴 및 XML 축 속성은 ASP.NET 페이지에 선언적 코드에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-110">XML literals and XML axis properties are not supported in declarative code in an ASP.NET page.</span></span> <span data-ttu-id="eb27d-111">Visual Basic XML 기능을 사용 하려면 ASP.NET 응용 프로그램에서 코드 숨김 페이지에 코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-111">To use Visual Basic XML features, put your code in a code-behind page in your ASP.NET application.</span></span>  
  
 <span data-ttu-id="eb27d-112">![비디오에 링크](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") 관련된 비디오 데모를 참조 하십시오. [하는 LINQ to XML 시작 하는 방법?](http://go.microsoft.com/fwlink/?LinkId=143034) 및 [방법 LINQ to XML 사용 하 여 Excel 스프레드시트 만들기?](http://go.microsoft.com/fwlink/?LinkId=143536)합니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-112">![link to video](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") For related video demonstrations, see [How Do I Get Started with LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143034) and [How Do I Create Excel Spreadsheets using LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143536).</span></span>  
  
## <a name="creating-xml"></a><span data-ttu-id="eb27d-113">XML 만들기</span><span class="sxs-lookup"><span data-stu-id="eb27d-113">Creating XML</span></span>  
 <span data-ttu-id="eb27d-114">XML 트리를 만드는 두 가지 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-114">There are two ways to create XML trees in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="eb27d-115">코드에서 직접 리터럴 XML를 선언할 수 또는 사용할 수는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Api 트리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-115">You can declare an XML literal directly in code, or you can use the [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] APIs to create the tree.</span></span> <span data-ttu-id="eb27d-116">XML 트리의 최종 구조를 반영 하도록 코드를 사용 하는 두 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-116">Both processes enable the code to reflect the final structure of the XML tree.</span></span> <span data-ttu-id="eb27d-117">예를 들어 다음 코드 예제에서는 XML 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-117">For example, the following code example creates an XML element:</span></span>  
  
 <span data-ttu-id="eb27d-118">[!code-vb[VbXmlSamples #&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb27d-118">[!code-vb[VbXmlSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]</span></span>  
  
 <span data-ttu-id="eb27d-119">자세한 내용은 참조 [Visual Basic의 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-119">For more information, see [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).</span></span>  
  
## <a name="accessing-and-navigating-xml"></a><span data-ttu-id="eb27d-120">액세스 하 고 XML을 탐색</span><span class="sxs-lookup"><span data-stu-id="eb27d-120">Accessing and Navigating XML</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="eb27d-121">에 액세스 하 고 XML 구조를 탐색 하기 위한 XML 축 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-121"> provides XML axis properties for accessing and navigating XML structures.</span></span> <span data-ttu-id="eb27d-122">이러한 속성을 사용 하 여 XML 자식 요소 이름을 지정 하 여 XML 요소 및 특성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-122">These properties enable you to access XML elements and attributes by specifying the XML child element names.</span></span> <span data-ttu-id="eb27d-123">명시적으로 호출 수 또는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 탐색 하 고 요소와 특성을 찾는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-123">Alternatively, you can explicitly call the [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] methods for navigating and locating elements and attributes.</span></span> <span data-ttu-id="eb27d-124">예를 들어 다음 코드 예제에서는 XML 축 속성을 사용 하 여 XML 요소의 자식 요소 및 특성을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-124">For example, the following code example uses XML axis properties to refer to the attributes and child elements of an XML element.</span></span> <span data-ttu-id="eb27d-125">사용 하 여 코드 예제는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 를 자식 요소를 검색 하 여 변환을 수행 하 고 XML 요소로 출력 하 여 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-125">The code example uses a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query to retrieve child elements and output them as XML elements, effectively performing a transform.</span></span>  
  
 <span data-ttu-id="eb27d-126">[!code-vb[VbXmlSamples #&8;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb27d-126">[!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]</span></span>  
  
 <span data-ttu-id="eb27d-127">자세한 내용은 참조 [Visual Basic의 XML에 액세스](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-127">For more information, see [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="eb27d-128">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="eb27d-128">XML Namespaces</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="eb27d-129">사용 하 여 전역 XML 네임 스페이스에 대 한 별칭을 지정할 수 있도록는 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-129"> enables you to specify an alias to a global XML namespace by using the `Imports` statement.</span></span> <span data-ttu-id="eb27d-130">다음 예제를 사용 하는 방법을 보여 줍니다는 `Imports` 을 XML 네임 스페이스를 가져오기 위한 문:</span><span class="sxs-lookup"><span data-stu-id="eb27d-130">The following example shows how to use the `Imports` statement to import an XML namespace:</span></span>  
  
 <span data-ttu-id="eb27d-131">[!code-vb[VbXMLSamples #&1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb27d-131">[!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]</span></span>  
  
 <span data-ttu-id="eb27d-132">XML 축 속성에 액세스 하 고 XML 문서 및 요소에 대 한 XML 리터럴을 선언할 때 XML 네임 스페이스 별칭을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-132">You can use an XML namespace alias when you access XML axis properties and declare XML literals for XML documents and elements.</span></span>  
  
 <span data-ttu-id="eb27d-133">검색할 수는 <xref:System.Xml.Linq.XNamespace>를 사용 하 여 특정 네임 스페이스 접두사에 대 한 개체는 [GetXmlNamespace 연산자](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="eb27d-133">You can retrieve an <xref:System.Xml.Linq.XNamespace> object for a particular namespace prefix by using the [GetXmlNamespace Operator](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).</span></span>  
  
 <span data-ttu-id="eb27d-134">자세한 내용은 참조 [Imports 문 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-134">For more information, see [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
### <a name="using-xml-namespaces-in-xml-literals"></a><span data-ttu-id="eb27d-135">XML 리터럴과에서 XML 네임 스페이스를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="eb27d-135">Using XML Namespaces in XML Literals</span></span>  
 <span data-ttu-id="eb27d-136">다음 예제에서는 만드는 방법을 보여 줍니다.는 <xref:System.Xml.Linq.XElement>전역 네임 스페이스를 사용 하는 개체 `ns`:</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="eb27d-136">The following example shows how to create an <xref:System.Xml.Linq.XElement> object that uses the global namespace `ns`:</span></span>  
  
 <span data-ttu-id="eb27d-137">[!code-vb[VbXMLSamples #&2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb27d-137">[!code-vb[VbXMLSamples#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]</span></span>  
  
 <span data-ttu-id="eb27d-138">[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러는 XML 표기법을 사용 하 여 XML 네임 스페이스를 사용 하는 코드로 XML 네임 스페이스 별칭을 포함 하는 XML 리터럴을 변환의 `xmlns` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-138">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler translates XML literals that contain XML namespace aliases into equivalent code that uses the XML notation for using XML namespaces, with the `xmlns` attribute.</span></span> <span data-ttu-id="eb27d-139">를 컴파일할 때 이전 섹션의 예제 코드에서는 다음 예제와 같이 동일한 실행 코드 기본적으로 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-139">When compiled, the code in the previous section's example produces essentially the same executable code as the following example:</span></span>  
  
 <span data-ttu-id="eb27d-140">[!code-vb[VbXMLSamples #&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb27d-140">[!code-vb[VbXMLSamples#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]</span></span>  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a><span data-ttu-id="eb27d-141">XML 축 속성에 XML 네임 스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="eb27d-141">Using XML Namespaces in XML Axis Properties</span></span>  
 <span data-ttu-id="eb27d-142">XML 리터럴에서 선언 된 XML 네임 스페이스 XML 축 속성에서 사용 하기 위해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-142">XML namespaces declared in XML literals are not available for use in XML axis properties.</span></span> <span data-ttu-id="eb27d-143">그러나 XML 축 속성이 설정 된 전역 네임 스페이스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-143">However, global namespaces can be used with the XML axis properties.</span></span> <span data-ttu-id="eb27d-144">로컬 요소 이름에서 XML 네임 스페이스 접두사를 구분 하려면 콜론을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-144">Use a colon to separate the XML namespace prefix from the local element name.</span></span> <span data-ttu-id="eb27d-145">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eb27d-145">Following is an example:</span></span>  
  
 <span data-ttu-id="eb27d-146">[!code-vb[VbXMLSamples #&4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb27d-146">[!code-vb[VbXMLSamples#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb27d-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb27d-147">See Also</span></span>  
 <span data-ttu-id="eb27d-148">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="eb27d-148">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="eb27d-149"> [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="eb27d-149"> [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="eb27d-150"> [Visual Basic의 XML에 액세스](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md) </span><span class="sxs-lookup"><span data-stu-id="eb27d-150"> [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md) </span></span>  
<span data-ttu-id="eb27d-151"> [Visual Basic에서 XML 조작](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)</span><span class="sxs-lookup"><span data-stu-id="eb27d-151"> [Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)</span></span>
