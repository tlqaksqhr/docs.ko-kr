---
title: NamedNodeMap 및 NodeList의 노드 컬렉션
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 025954b8-7aa8-47c5-a1c1-f81064fb4d65
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b1ffe5eb791decfd7d36f7e8ecd29fa80e8e983
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="node-collections-in-namednodemaps-and-nodelists"></a><span data-ttu-id="71a1a-102">NamedNodeMap 및 NodeList의 노드 컬렉션</span><span class="sxs-lookup"><span data-stu-id="71a1a-102">Node Collections in NamedNodeMaps and NodeLists</span></span>
<span data-ttu-id="71a1a-103">노드 집합을 검색하여 정렬되거나 정렬되지 않은 컬렉션에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71a1a-103">You can retrieve a set of nodes and put it in an ordered or unordered collection.</span></span> <span data-ttu-id="71a1a-104">노드 집합을 정렬되지 않은 컬렉션에 배치할 경우 해당 집합을 W3C(World Wide Web 컨소시엄)에 따라 NamedNodeMap이라고 합니다. 이 컬렉션 형식에서는 이름이나 인덱스를 사용하여 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71a1a-104">When putting a set of nodes into an unordered collection, the set is called a NamedNodeMap by the World Wide Web Consortium (W3C); you can retrieve the data by name or index in this type of collection.</span></span> <span data-ttu-id="71a1a-105">노드 집합을 W3C에 따라 NodeList라고 하는 정렬된 컬렉션에 배치하면 인덱스(0부터 시작)를 사용하여 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71a1a-105">Putting a set of nodes in an ordered collection is called a NodeList by the W3C, and the data can be retrieved by a zero-based index.</span></span> <span data-ttu-id="71a1a-106">NamedNodeMap과 NodeList는 W3C에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="71a1a-106">NamedNodeMaps and NodeLists are described by the W3C.</span></span> <span data-ttu-id="71a1a-107">NamedNodeMap에 대한 Microsoft .NET Framework 구현은 **XmlNamedNodeMap**이며 NodeList에 대한 구현은 **XmlNodeList**입니다.</span><span class="sxs-lookup"><span data-stu-id="71a1a-107">The implementations in the Microsoft .NET Framework for the NamedNodeMap is the **XmlNamedNodeMap**, and the NodeList is implemented by the **XmlNodeList**.</span></span>  
  
 <span data-ttu-id="71a1a-108">정렬되지 않은 컬렉션에 대한 자세한 내용은 [이름 또는 인덱스별로 정렬되지 않은 노드 검색](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71a1a-108">For information on the unordered collection, see [Unordered Node Retrieval by Name or Index](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span></span> <span data-ttu-id="71a1a-109">정렬된 컬렉션에 대한 자세한 내용은 [인덱스를 사용한 정렬된 노드 검색](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71a1a-109">For information on the ordered collection, see [Ordered Node Retrieval by Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a1a-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71a1a-110">See Also</span></span>  
 [<span data-ttu-id="71a1a-111">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="71a1a-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
