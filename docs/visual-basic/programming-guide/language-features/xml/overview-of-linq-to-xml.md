---
title: Visual Basic의 LINQ to XML 개요
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be9038fb194c0e4890593b4b80751a477def20a7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a><span data-ttu-id="c26a4-102">Visual Basic의 LINQ to XML 개요</span><span class="sxs-lookup"><span data-stu-id="c26a4-102">Overview of LINQ to XML in Visual Basic</span></span>
<span data-ttu-id="c26a4-103">Visual Basic에 대 한 지원을 제공 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] XML 리터럴과 XML 축 속성을 통해.</span><span class="sxs-lookup"><span data-stu-id="c26a4-103">Visual Basic provides support for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] through XML literals and XML axis properties.</span></span> <span data-ttu-id="c26a4-104">그러면 Visual Basic 코드에서 XML을 사용 하는 것에 대 한 친숙 하 고 편리한 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-104">This enables you to use a familiar, convenient syntax for working with XML in your Visual Basic code.</span></span> <span data-ttu-id="c26a4-105">*XML 리터럴* 코드에서 직접 XML을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-105">*XML literals* enable you to include XML directly in your code.</span></span> <span data-ttu-id="c26a4-106">*XML 축 속성* XML 리터럴의 특성, 하위 노드 및 자식 노드의 액세스를 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-106">*XML axis properties* enable you to access child nodes, descendant nodes, and attributes of an XML literal.</span></span> <span data-ttu-id="c26a4-107">자세한 내용은 참조 [XML 리터럴 개요](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) 및 [Visual Basic의 XML에 액세스](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-107">For more information, see [XML Literals Overview](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) and [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="c26a4-108"> 메모리 내 XML 프로그래밍 API를 활용 하도록 특별히 설계 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-108"> is an in-memory XML programming API designed specifically to take advantage of [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].</span></span> <span data-ttu-id="c26a4-109">호출할 수 있지만 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 직접 Api, 유일한 Visual Basic XML 리터럴 선언 및 XML 축 속성에 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-109">Although you can call the [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] APIs directly, only Visual Basic enables you to declare XML literals and directly access XML axis properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c26a4-110">ASP.NET 페이지의 선언적 코드에서 XML 리터럴과 XML 축 속성이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-110">XML literals and XML axis properties are not supported in declarative code in an ASP.NET page.</span></span> <span data-ttu-id="c26a4-111">Visual Basic XML 기능을 사용 하려면 ASP.NET 응용 프로그램에서 코드 숨김 페이지에 코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-111">To use Visual Basic XML features, put your code in a code-behind page in your ASP.NET application.</span></span>  
  
 <span data-ttu-id="c26a4-112">![비디오에 링크](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") 관련된 비디오 데모를 참조 하십시오. [하는 LINQ to XML 시작 하는 방법?](http://go.microsoft.com/fwlink/?LinkId=143034) 및 [어떻게 할까요? LINQ to XML 사용 하 여 Excel 스프레드시트 만들?](http://go.microsoft.com/fwlink/?LinkId=143536)합니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-112">![link to video](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") For related video demonstrations, see [How Do I Get Started with LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143034) and [How Do I Create Excel Spreadsheets using LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143536).</span></span>  
  
## <a name="creating-xml"></a><span data-ttu-id="c26a4-113">XML 만들기</span><span class="sxs-lookup"><span data-stu-id="c26a4-113">Creating XML</span></span>  
 <span data-ttu-id="c26a4-114">Visual Basic에서 XML 트리를 만드는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-114">There are two ways to create XML trees in Visual Basic.</span></span> <span data-ttu-id="c26a4-115">XML를 코드에 직접 리터럴 선언할 수 있습니다 또는 사용할 수는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Api 트리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-115">You can declare an XML literal directly in code, or you can use the [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] APIs to create the tree.</span></span> <span data-ttu-id="c26a4-116">XML 트리의 최종 구조를 반영 하도록 코드를 사용 하는 두 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-116">Both processes enable the code to reflect the final structure of the XML tree.</span></span> <span data-ttu-id="c26a4-117">예를 들어 다음 코드 예제에서는 XML 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-117">For example, the following code example creates an XML element:</span></span>  
  
 [!code-vb[VbXmlSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]  
  
 <span data-ttu-id="c26a4-118">자세한 내용은 참조 [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-118">For more information, see [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).</span></span>  
  
## <a name="accessing-and-navigating-xml"></a><span data-ttu-id="c26a4-119">액세스 하 고 XML 탐색</span><span class="sxs-lookup"><span data-stu-id="c26a4-119">Accessing and Navigating XML</span></span>  
 <span data-ttu-id="c26a4-120">Visual Basic에서 XML 축 속성에 액세스 하 고 XML 구조를 탐색 하기 위한 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-120">Visual Basic provides XML axis properties for accessing and navigating XML structures.</span></span> <span data-ttu-id="c26a4-121">이러한 속성을 사용 하는 XML 자식 요소 이름을 지정 하 여 XML 요소 및 특성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-121">These properties enable you to access XML elements and attributes by specifying the XML child element names.</span></span> <span data-ttu-id="c26a4-122">명시적으로 호출할 수 또는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 탐색 하 고 특성과 해당 요소를 찾는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-122">Alternatively, you can explicitly call the [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] methods for navigating and locating elements and attributes.</span></span> <span data-ttu-id="c26a4-123">예를 들어 다음 코드 예제를 사용 하 여 XML 축 속성 특성 및 XML 요소의 자식 요소를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c26a4-123">For example, the following code example uses XML axis properties to refer to the attributes and child elements of an XML element.</span></span> <span data-ttu-id="c26a4-124">사용 하 여 코드 예제는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 자식 요소를 검색 하 고 변환을 수행 하 고 XML 요소로 출력 하 여를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-124">The code example uses a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query to retrieve child elements and output them as XML elements, effectively performing a transform.</span></span>  
  
 [!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]  
  
 <span data-ttu-id="c26a4-125">자세한 내용은 참조 [Visual Basic의 XML에 액세스](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-125">For more information, see [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="c26a4-126">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="c26a4-126">XML Namespaces</span></span>  
 <span data-ttu-id="c26a4-127">Visual Basic을 사용 하면 사용 하 여 전역 XML 네임 스페이스에 대 한 별칭을 지정할 수 있습니다는 `Imports` 문.</span><span class="sxs-lookup"><span data-stu-id="c26a4-127">Visual Basic enables you to specify an alias to a global XML namespace by using the `Imports` statement.</span></span> <span data-ttu-id="c26a4-128">사용 하는 방법을 보여 주는 다음 예제는 `Imports` XML 네임 스페이스를 가져올 계정:</span><span class="sxs-lookup"><span data-stu-id="c26a4-128">The following example shows how to use the `Imports` statement to import an XML namespace:</span></span>  
  
 [!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]  
  
 <span data-ttu-id="c26a4-129">XML 축 속성에 액세스 하 고 XML 문서 및 요소에 대 한 XML 리터럴을 선언할 XML 네임 스페이스 별칭을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-129">You can use an XML namespace alias when you access XML axis properties and declare XML literals for XML documents and elements.</span></span>  
  
 <span data-ttu-id="c26a4-130">검색할 수 있습니다는 <xref:System.Xml.Linq.XNamespace> 를 사용 하 여 특정 네임 스페이스 접두사에 대 한 개체는 [GetXmlNamespace 연산자](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-130">You can retrieve an <xref:System.Xml.Linq.XNamespace> object for a particular namespace prefix by using the [GetXmlNamespace Operator](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).</span></span>  
  
 <span data-ttu-id="c26a4-131">자세한 내용은 참조 [Imports 문 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-131">For more information, see [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
### <a name="using-xml-namespaces-in-xml-literals"></a><span data-ttu-id="c26a4-132">XML 리터럴의 XML 네임 스페이스를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="c26a4-132">Using XML Namespaces in XML Literals</span></span>  
 <span data-ttu-id="c26a4-133">만드는 방법을 보여 주는 다음 예제는 <xref:System.Xml.Linq.XElement> 전역 네임 스페이스를 사용 하는 개체 `ns`:</span><span class="sxs-lookup"><span data-stu-id="c26a4-133">The following example shows how to create an <xref:System.Xml.Linq.XElement> object that uses the global namespace `ns`:</span></span>  
  
 [!code-vb[VbXMLSamples#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]  
  
 <span data-ttu-id="c26a4-134">XML 네임 스페이스에 사용 하기 위해 XML 표기법을 사용 하 여 해당 하는 코드에 XML 네임 스페이스 별칭을 포함 하는 XML 리터럴을 변환 하는 Visual Basic 컴파일러는 `xmlns` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-134">The Visual Basic compiler translates XML literals that contain XML namespace aliases into equivalent code that uses the XML notation for using XML namespaces, with the `xmlns` attribute.</span></span> <span data-ttu-id="c26a4-135">를 컴파일할 때 이전 섹션의 예제 코드에서는 다음 예제와 같이 동일한 실행 코드 기본적으로 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-135">When compiled, the code in the previous section's example produces essentially the same executable code as the following example:</span></span>  
  
 [!code-vb[VbXMLSamples#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a><span data-ttu-id="c26a4-136">XML 축 속성에 XML 네임 스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="c26a4-136">Using XML Namespaces in XML Axis Properties</span></span>  
 <span data-ttu-id="c26a4-137">XML 리터럴 선언 된 XML 네임 스페이스 XML 축 속성에서 사용 하기 위해 사용할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="c26a4-137">XML namespaces declared in XML literals are not available for use in XML axis properties.</span></span> <span data-ttu-id="c26a4-138">그러나 XML 축 속성을 가진 전역 네임 스페이스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-138">However, global namespaces can be used with the XML axis properties.</span></span> <span data-ttu-id="c26a4-139">로컬 요소 이름에서 XML 네임 스페이스 접두사를 구분 하려면 콜론을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-139">Use a colon to separate the XML namespace prefix from the local element name.</span></span> <span data-ttu-id="c26a4-140">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c26a4-140">Following is an example:</span></span>  
  
 [!code-vb[VbXMLSamples#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c26a4-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c26a4-141">See Also</span></span>  
 [<span data-ttu-id="c26a4-142">XML</span><span class="sxs-lookup"><span data-stu-id="c26a4-142">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="c26a4-143">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="c26a4-143">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="c26a4-144">Visual Basic에서 XML에 액세스</span><span class="sxs-lookup"><span data-stu-id="c26a4-144">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [<span data-ttu-id="c26a4-145">Visual Basic에서 XML 조작</span><span class="sxs-lookup"><span data-stu-id="c26a4-145">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
