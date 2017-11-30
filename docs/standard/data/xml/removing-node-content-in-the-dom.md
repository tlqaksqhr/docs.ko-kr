---
title: "DOM에서 노드 내용 제거"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 76be90829a414b091d3b311b96bf9bab9a2b56ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="removing-node-content-in-the-dom"></a><span data-ttu-id="6842a-102">DOM에서 노드 내용 제거</span><span class="sxs-lookup"><span data-stu-id="6842a-102">Removing Node Content in the DOM</span></span>
<span data-ttu-id="6842a-103"><xref:System.Xml.XmlCharacterData>에서 상속되는 <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, <xref:System.Xml.XmlSignificantWhitespace> 등의 노드 형식의 경우 노드에서 문자 범위를 제거하는 <xref:System.Xml.XmlCharacterData.DeleteData%2A> 메서드를 사용하여 문자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6842a-103">For node types that inherit from <xref:System.Xml.XmlCharacterData>, which are the <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, and <xref:System.Xml.XmlSignificantWhitespace> node types, you can remove characters using the <xref:System.Xml.XmlCharacterData.DeleteData%2A> method, which removes a range of characters from the node.</span></span> <span data-ttu-id="6842a-104">내용을 완전히 제거하려면 내용이 있는 노드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6842a-104">If you want to remove content completely, you remove the node that contains the content.</span></span> <span data-ttu-id="6842a-105">내용은 잘못되었지만 노드를 유지하려면 내용을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6842a-105">If you want to keep the node, but the content is incorrect, then modify the content.</span></span> <span data-ttu-id="6842a-106">노드의 콘텐츠를 수정 하는 방법에 대 한 정보를 참조 하십시오. [노드 수정, 내용 및 XML 문서에서 값](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6842a-106">For information on modifying the content of a node, see [Modifying Nodes, Content, and Values in an XML Document](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6842a-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6842a-107">See Also</span></span>  
 [<span data-ttu-id="6842a-108">XML 문서 개체 모델 (DOM)</span><span class="sxs-lookup"><span data-stu-id="6842a-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
