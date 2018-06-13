---
title: NodeList 및 NamedNodeMap에 대한 동적 업데이트
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1de133d0208f1b86ad3240cdc00d8016af0a160c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568968"
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a><span data-ttu-id="82795-102">NodeList 및 NamedNodeMap에 대한 동적 업데이트</span><span class="sxs-lookup"><span data-stu-id="82795-102">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>
<span data-ttu-id="82795-103">**XmlNodeList** 및 **XmlNamedNodeMap**에는 노드 집합이 포함되므로, XML 문서를 메모리에 로드하고 수정하려는 경우 W3C(World Wide Web 컨소시엄)에서는 노드 집합을 포함하는 이러한 개체가 동적이어야 한다고 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="82795-103">Because the **XmlNodeList** and the **XmlNamedNodeMap** contain a set of nodes, yet the XML document is loaded into memory and is being modified, the World Wide Web Consortium (W3C) states that these objects that contain sets of nodes need to be dynamic.</span></span> <span data-ttu-id="82795-104">즉, 원본으로 사용하는 문서가 변경되면 이러한 두 개체의 데이터도 변경되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82795-104">That is, if the underlying document changes, then the data in these two objects should change also.</span></span> <span data-ttu-id="82795-105">따라서 특정 요소의 자식 요소를 모두 포함하는 **XmlNodeList**인 X 요소가 있다면 X 요소 아래의 문서에 Q 요소를 추가하는 경우 **XmlNodeList**에도 해당 컬렉션에 새 Q 요소가 추가되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82795-105">Therefore, if you have an **XmlNodeList** that contains all the child elements of a particular element (for example, element X), then you add an additional element, element Q, to the document under element X. The **XmlNodeList** should also have that new element Q added to its collection.</span></span> <span data-ttu-id="82795-106">그 반대의 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="82795-106">The same is true in reverse.</span></span> <span data-ttu-id="82795-107">**XmlNodeList**에 노드가 추가되면 원본으로 사용하는 문서 역시 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="82795-107">If a node is added to the **XmlNodeList**, the underlying document is updated as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82795-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82795-108">See Also</span></span>  
 [<span data-ttu-id="82795-109">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="82795-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
