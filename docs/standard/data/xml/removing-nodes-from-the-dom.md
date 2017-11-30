---
title: "DOM에서 노드 제거"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a98e0ca-0555-45c1-ab69-0d8d20ca1abd
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0885d53e737153448fabfd394d49bfdc793e0599
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="removing-nodes-from-the-dom"></a><span data-ttu-id="b422d-102">DOM에서 노드 제거</span><span class="sxs-lookup"><span data-stu-id="b422d-102">Removing Nodes from the DOM</span></span>
<span data-ttu-id="b422d-103">XML DOM(문서 개체 모델)에서 노드를 제거하려면 <xref:System.Xml.XmlNode.RemoveChild%2A> 메서드를 사용하여 특정 노드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b422d-103">To remove a node from the XML Document Object Model (DOM), use the <xref:System.Xml.XmlNode.RemoveChild%2A> method to remove a specific node.</span></span> <span data-ttu-id="b422d-104">이때 삭제하는 노드가 리프 노드가 아닌 경우 이 노드에 속한 하위 트리도 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="b422d-104">When you remove a node, the method removes the subtree belonging to the node being removed; that is, if it is not a leaf node.</span></span>  
  
 <span data-ttu-id="b422d-105">DOM에서 여러 노드를 제거하려면 <xref:System.Xml.XmlNode.RemoveAll%2A> 메서드를 사용하여 현재 노드의 모든 자식 및 특성을(해당 사항이 있을 경우) 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b422d-105">To remove multiple nodes from the DOM, use the <xref:System.Xml.XmlNode.RemoveAll%2A> method to remove all the children and attributes, if applicable, of the current node.</span></span>  
  
 <span data-ttu-id="b422d-106"><xref:System.Xml.XmlNamedNodeMap>으로 작업하는 경우 <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A> 메서드를 사용하여 노드를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b422d-106">If you are working with an <xref:System.Xml.XmlNamedNodeMap>, you can remove a node using the <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A> method.</span></span>  
  
 <span data-ttu-id="b422d-107">특성을 제거 하려면 참조 [DOM의 요소 노드에서 특성 제거](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b422d-107">To remove attributes, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b422d-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b422d-108">See Also</span></span>  
 [<span data-ttu-id="b422d-109">XML 문서 개체 모델 (DOM)</span><span class="sxs-lookup"><span data-stu-id="b422d-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
