---
title: "네임 스페이스 개요 (LINQ to XML) | Microsoft 문서"
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
ms.assetid: b8eb31fa-4b26-4acf-8050-6e705687f458
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
ms.openlocfilehash: 7e9536615871b83099a11e46125ed85b44d9335d
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="namespaces-overview-linq-to-xml"></a><span data-ttu-id="1fa29-102">네임스페이스 개요(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="1fa29-102">Namespaces Overview (LINQ to XML)</span></span>
<span data-ttu-id="1fa29-103">이 항목에서는 네임 스페이스의 <xref:System.Xml.Linq.XName>클래스 및 <xref:System.Xml.Linq.XNamespace>클래스</xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName> 소개</span><span class="sxs-lookup"><span data-stu-id="1fa29-103">This topic introduces namespaces, the <xref:System.Xml.Linq.XName> class, and the <xref:System.Xml.Linq.XNamespace> class.</span></span>  
  
## <a name="xml-names"></a><span data-ttu-id="1fa29-104">XML 이름</span><span class="sxs-lookup"><span data-stu-id="1fa29-104">XML Names</span></span>  
 <span data-ttu-id="1fa29-105">XML 이름으로 인해 XML 프로그래밍이 복잡해지는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="1fa29-105">XML names are often a source of complexity in XML programming.</span></span> <span data-ttu-id="1fa29-106">XML 이름은 XML 네임스페이스(또는 XML 네임스페이스 URI라고 함)와 로컬 이름으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fa29-106">An XML name consists of an XML namespace (also called an XML namespace URI) and a local name.</span></span> <span data-ttu-id="1fa29-107">XML 네임스페이스는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 기반 프로그램의 네임스페이스와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="1fa29-107">An XML namespace is similar to a namespace in a [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]-based program.</span></span> <span data-ttu-id="1fa29-108">XML 네임스페이스를 통해 요소와 특성의 이름을 고유하게 정규화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fa29-108">It enables you to uniquely qualify the names of elements and attributes.</span></span> <span data-ttu-id="1fa29-109">이에 따라 XML 문서의 다양한 부분 간에 이름 충돌이 방지됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fa29-109">This helps avoid name conflicts between various parts of an XML document.</span></span> <span data-ttu-id="1fa29-110">XML 네임스페이스를 선언한 경우 해당 네임스페이스에서만 고유해야 하는 로컬 이름을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fa29-110">When you have declared an XML namespace, you can select a local name that only has to be unique within that namespace.</span></span>  
  
 <span data-ttu-id="1fa29-111">XML 이름의 또 다른 측면은 XML *네임 스페이스 접두사*합니다.</span><span class="sxs-lookup"><span data-stu-id="1fa29-111">Another aspect of XML names is XML *namespace prefixes*.</span></span> <span data-ttu-id="1fa29-112">XML 접두사는 XML 이름이 복잡해지는 주된 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="1fa29-112">XML prefixes cause most of the complexity of XML names.</span></span> <span data-ttu-id="1fa29-113">이러한 접두사를 통해 XML 네임스페이스의 바로 가기를 만들 수 있으며 이에 따라 XML 문서가 간결하고 이해하기 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="1fa29-113">These prefixes enable you to create a shortcut for an XML namespace, which makes the XML document more concise and understandable.</span></span> <span data-ttu-id="1fa29-114">그러나 XML 접두사는 의미를 갖기 위해 컨텍스트에 의존하므로 복잡성이 가중됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fa29-114">However, XML prefixes depend on their context to have meaning, which adds complexity.</span></span> <span data-ttu-id="1fa29-115">예를 들어, XML 접두사 `aw`를 XML 트리의 한 부분에 있는 한 XML 네임스페이스와 연결하고 XML 트리의 다른 부분에 있는 다른 XML 네임스페이스와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fa29-115">For example, the XML prefix `aw` could be associated with one XML namespace in one part of an XML tree, and with a different XML namespace in a different part of the XML tree.</span></span>  
  
 <span data-ttu-id="1fa29-116">Visual Basic 및 XML 리터럴과 함께 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]을 사용하는 경우 네임스페이스의 문서로 작업할 때 네임스페이스 접두사를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fa29-116">When using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] with Visual Basic and XML literals, you must use namespace prefixes when working with documents in namespaces.</span></span>  
  
 <span data-ttu-id="1fa29-117">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], XML 이름을 나타내는 클래스는 <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="1fa29-117">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], the class that represents XML names is <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="1fa29-118">XML 이름 전반에서 자주 나타나며는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] API를 찾을 수 있습니다 XML 이름이 필요할 때마다는 <xref:System.Xml.Linq.XName>매개 변수.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="1fa29-118">XML names appear frequently throughout the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] API, and wherever an XML name is required, you will find an <xref:System.Xml.Linq.XName> parameter.</span></span> <span data-ttu-id="1fa29-119">그러나 거의 직접 작업할 수 <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="1fa29-119">However, you rarely work directly with an <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="1fa29-120"><xref:System.Xml.Linq.XName>문자열에서의 암시적 변환이 포함 되어 있습니다.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="1fa29-120"><xref:System.Xml.Linq.XName> contains an implicit conversion from string.</span></span>  
  
 <span data-ttu-id="1fa29-121">자세한 내용은 <xref:System.Xml.Linq.XNamespace>및 <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1fa29-121">For more information, see <xref:System.Xml.Linq.XNamespace> and <xref:System.Xml.Linq.XName>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fa29-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1fa29-122">See Also</span></span>  
 [<span data-ttu-id="1fa29-123">XML 네임 스페이스 (Visual Basic) 작업</span><span class="sxs-lookup"><span data-stu-id="1fa29-123">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
