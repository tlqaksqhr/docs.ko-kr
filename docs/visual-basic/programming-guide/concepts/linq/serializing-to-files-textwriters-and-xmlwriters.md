---
title: "파일, TextWriters 및 XmlWriters3에 대 한 직렬화"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f4c5578bc20f91eb35f78355dff0fc4c44e878e2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a><span data-ttu-id="535f0-102">Files, TextWriters 및 XmlWriters로 serialization</span><span class="sxs-lookup"><span data-stu-id="535f0-102">Serializing to Files, TextWriters, and XmlWriters</span></span>
<span data-ttu-id="535f0-103">XML 트리를 <xref:System.IO.File>, <xref:System.IO.TextWriter> 또는 <xref:System.Xml.XmlWriter>로 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535f0-103">You can serialize XML trees to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="535f0-104"><xref:System.Xml.Linq.XDocument> 메서드를 사용하여 <xref:System.Xml.Linq.XElement> 및 `ToString`와 같은 XML 구성 요소를 문자열로 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535f0-104">You can serialize any XML component, including <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement>, to a string by using the `ToString` method.</span></span>  
  
 <span data-ttu-id="535f0-105">문자열로 serialize할 때 서식 지정을 방지하려면 <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType> 메서드를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="535f0-105">If you want to suppress formatting when serializing to a string, you can use the <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="535f0-106">파일로 serialize할 때의 기본 동작은 생성되는 XML 문서의 서식을 지정하는(들여쓰는) 것입니다.</span><span class="sxs-lookup"><span data-stu-id="535f0-106">Thedefault behavior when serializing to a file is to format (indent) the resulting XML document.</span></span> <span data-ttu-id="535f0-107">들여쓰는 경우 XML 트리의 무효 공백은 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="535f0-107">When you indent, the insignificant white space in the XML tree is not preserved.</span></span> <span data-ttu-id="535f0-108">서식을 사용하여 serialize하려면 <xref:System.Xml.Linq.SaveOptions>를 인수로 사용하지 않는 다음 메서드의 오버로드 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="535f0-108">To serialize with formatting, use one of the overloads of the following methods that do not take <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="535f0-109">들여쓰지 않고 XML 트리에서 무효 공백을 유지하려면 <xref:System.Xml.Linq.SaveOptions>를 인수로 사용하는 다음 메서드의 오버로드 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="535f0-109">If you want the option not to indent and to preserve the insignificant white space in the XML tree, use one of the overloads of the following methods that takes <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="535f0-110">예제를 보려면 적절한 참조 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="535f0-110">For examples, see the appropriate reference topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="535f0-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="535f0-111">See Also</span></span>  
 [<span data-ttu-id="535f0-112">XML 트리 (Visual Basic)를 직렬화 하는 작업</span><span class="sxs-lookup"><span data-stu-id="535f0-112">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
