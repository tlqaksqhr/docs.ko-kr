---
title: "직렬화할 때 공백 유지3"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: df0ee9bedd4123ac47c06d1c64f305fcf0b0825a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="preserving-white-space-while-serializing"></a><span data-ttu-id="760fb-102">serialize할 때 공백 유지</span><span class="sxs-lookup"><span data-stu-id="760fb-102">Preserving White Space While Serializing</span></span>
<span data-ttu-id="760fb-103">이 항목에서는 XML 트리를 serialize할 때 공백을 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="760fb-103">This topic describes how to control white space when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="760fb-104">일반적인 시나리오는 들여쓴 XML을 읽고 공백 텍스트 노드 없이 메모리 내 XML 트리를 만든 다음(공백을 유지하지 않음) XML에 대한 작업을 수행하고 들여쓰기를 사용하여 XML을 저장하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="760fb-104">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="760fb-105">서식이 있는 XML을 serialize하는 경우 XML 트리의 유효 공백만 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="760fb-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="760fb-106">이것이 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]의 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="760fb-106">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="760fb-107">다른 일반적인 시나리오는 이미 의도적으로 들여쓴 XML을 읽고 수정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="760fb-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="760fb-108">이 들여쓰기를 변경하려고 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760fb-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="760fb-109">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서는 XML을 로드하거나 구문 분석할 때 공백을 유지하고 XML을 serialize할 때 서식을 해제하는 경우 이렇게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760fb-109">To do this in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a><span data-ttu-id="760fb-110">XML 트리를 serialize하는 메서드의 공백 동작</span><span class="sxs-lookup"><span data-stu-id="760fb-110">White Space Behavior of Methods that Serialize XML Trees</span></span>  
 <span data-ttu-id="760fb-111"><xref:System.Xml.Linq.XElement> 및 <xref:System.Xml.Linq.XDocument> 클래스의 다음 메서드는 XML 트리를 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="760fb-111">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes serialize an XML tree.</span></span> <span data-ttu-id="760fb-112">XML 트리를 파일, <xref:System.IO.TextReader> 또는 <xref:System.Xml.XmlReader>로 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760fb-112">You can serialize an XML tree to a file, a <xref:System.IO.TextReader>, or an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="760fb-113">`ToString` 메서드는 문자열로 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="760fb-113">The `ToString` method serializes to a string.</span></span>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="760fb-114">이 메서드는 <xref:System.Xml.Linq.SaveOptions>를 인수로 사용하지 않는 경우 serialize된 XML의 서식을 지정합니다(들여씁니다).</span><span class="sxs-lookup"><span data-stu-id="760fb-114">If the method does not take <xref:System.Xml.Linq.SaveOptions> as an argument, then the method will format (indent) the serialized XML.</span></span> <span data-ttu-id="760fb-115">이 경우 XML 트리의 모든 무효 공백이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="760fb-115">In this case, all insignificant white space in the XML tree is discarded.</span></span>  
  
 <span data-ttu-id="760fb-116">이 메서드가 <xref:System.Xml.Linq.SaveOptions>를 인수로 사용하는 경우에는 serialize된 XML의 서식을 지정하지(들여쓰지) 않도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760fb-116">If the method does take <xref:System.Xml.Linq.SaveOptions> as an argument, then you can specify that the method not format (indent) the serialized XML.</span></span> <span data-ttu-id="760fb-117">이 경우 XML 트리의 모든 공백이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="760fb-117">In this case, all white space in the XML tree is preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="760fb-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="760fb-118">See Also</span></span>  
 [<span data-ttu-id="760fb-119">XML 트리 serialize(C#)</span><span class="sxs-lookup"><span data-stu-id="760fb-119">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
