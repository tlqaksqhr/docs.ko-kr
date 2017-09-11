---
title: "Files, TextWriters 및 XmlWriters3로 | Microsoft 문서"
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
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
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
ms.openlocfilehash: f8f8672004b0704b00ff60e5b58256f664bcbd82
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a><span data-ttu-id="b6851-102">Files, TextWriters 및 XmlWriters로 serialization</span><span class="sxs-lookup"><span data-stu-id="b6851-102">Serializing to Files, TextWriters, and XmlWriters</span></span>
<span data-ttu-id="b6851-103">XML 트리를 serialize 할 수는 <xref:System.IO.File>, <xref:System.IO.TextWriter>, 또는 <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="b6851-103">You can serialize XML trees to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="b6851-104">XML 구성 요소를 serialize 할 수 있습니다 포함 하 여 <xref:System.Xml.Linq.XDocument>및 <xref:System.Xml.Linq.XElement>를 사용 하 여 문자열에는 `ToString` 메서드.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="b6851-104">You can serialize any XML component, including <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement>, to a string by using the `ToString` method.</span></span>  
  
 <span data-ttu-id="b6851-105">문자열로 직렬화 할 때 서식 지정을 방지 하려는 경우 사용할 수 있습니다는 <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName>메서드.</xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b6851-105">If you want to suppress formatting when serializing to a string, you can use the <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName> method.</span></span>  
  
 <span data-ttu-id="b6851-106">(들여쓰기)는 결과 XML 문서 서식을 지정 하는 파일에 직렬화 할 때 모드용 기본 동작이입니다.</span><span class="sxs-lookup"><span data-stu-id="b6851-106">Thedefault behavior when serializing to a file is to format (indent) the resulting XML document.</span></span> <span data-ttu-id="b6851-107">들여쓰는 경우 XML 트리의 무효 공백은 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6851-107">When you indent, the insignificant white space in the XML tree is not preserved.</span></span> <span data-ttu-id="b6851-108">서식을 사용 하 여 serialize 할 사용 하지 않는 다음 메서드의 오버 로드 중 하나를 사용 <xref:System.Xml.Linq.SaveOptions>인수로:</xref:System.Xml.Linq.SaveOptions></span><span class="sxs-lookup"><span data-stu-id="b6851-108">To serialize with formatting, use one of the overloads of the following methods that do not take <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <span data-ttu-id="b6851-109"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b6851-109"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="b6851-110"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b6851-110"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="b6851-111">XML 트리에서 무효 공백을 유지 하려면 옵션을 들여쓸를 하려는 경우 사용 하는 다음 메서드의 오버 로드 중 하나를 사용 <xref:System.Xml.Linq.SaveOptions>인수로:</xref:System.Xml.Linq.SaveOptions></span><span class="sxs-lookup"><span data-stu-id="b6851-111">If you want the option not to indent and to preserve the insignificant white space in the XML tree, use one of the overloads of the following methods that takes <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <span data-ttu-id="b6851-112"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b6851-112"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="b6851-113"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b6851-113"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="b6851-114">예제를 보려면 적절한 참조 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6851-114">For examples, see the appropriate reference topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6851-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6851-115">See Also</span></span>  
 [<span data-ttu-id="b6851-116">XML 트리 (Visual Basic)를 직렬화 하는 작업</span><span class="sxs-lookup"><span data-stu-id="b6851-116">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
