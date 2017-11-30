---
title: "엔터티 참조 유지"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 770c714e8f5942ea733c417ae9b06f69e4acf1a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="entity-references-are-preserved"></a><span data-ttu-id="54082-102">엔터티 참조 유지</span><span class="sxs-lookup"><span data-stu-id="54082-102">Entity References are Preserved</span></span>
<span data-ttu-id="54082-103">엔터티 참조가 확장 되지 않고, 유지 때 XML 문서 개체 모델 (DOM)에서는 **XmlEntityReference** 노드 엔터티 참조를 발견 한 경우.</span><span class="sxs-lookup"><span data-stu-id="54082-103">When the entity reference is not expanded, but preserved, the XML Document Object Model (DOM) builds an **XmlEntityReference** node when it encounters an entity reference.</span></span>  
  
 <span data-ttu-id="54082-104">다음 XML을 사용한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="54082-104">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="54082-105">DOM 빌드는 **XmlEntityReference** 에 도달할 때 노드는 `&publisher;` 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="54082-105">the DOM builds an **XmlEntityReference** node when it encounters the `&publisher;` reference.</span></span> <span data-ttu-id="54082-106">**XmlEntityReference** 엔터티 선언의 내용에서 복사 된 자식 노드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="54082-106">The **XmlEntityReference** contains child nodes copied from the content in the entity declaration.</span></span> <span data-ttu-id="54082-107">이전 코드 예제에서는 엔터티 선언에 텍스트를 되므로 포함 한 **XmlText** entityreference 노드의 자식 노드로 노드가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="54082-107">The preceding code example contains text in the entity declaration, so an **XmlText** node is created as the child node of the entity reference node.</span></span>  
  
 <span data-ttu-id="54082-108">![트리 구조 유지 된 엔터티 참조에 대 한](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span><span class="sxs-lookup"><span data-stu-id="54082-108">![Tree structure for preserved entity references](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span></span>  
<span data-ttu-id="54082-109">유지되는 엔터티 참조의 트리 구조</span><span class="sxs-lookup"><span data-stu-id="54082-109">Tree structure for entity references that are preserved</span></span>  
  
 <span data-ttu-id="54082-110">자식 노드는 **XmlEntityReference** 은 모든 자식의 복사본에서 만든 노드는 **XmlEntity** 엔터티 선언이 발생 했을 때 노드.</span><span class="sxs-lookup"><span data-stu-id="54082-110">The child nodes of the **XmlEntityReference** are copies of all the child nodes created from the **XmlEntity** node when the entity declaration was encountered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54082-111">복사한 노드는 **XmlEntity** 없는 경우가 entityreference 노드 아래의 정확히 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="54082-111">The nodes copied from the **XmlEntity** are not always exact copies once placed under the entity reference node.</span></span> <span data-ttu-id="54082-112">entityreference 노드 범위에 속한 네임스페이스가 있을 수 있으며 자식 노드의 최종 구성에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54082-112">There can be namespaces that are in scope at the entity reference node, and that affects the final configuration of the child nodes.</span></span>  
  
 <span data-ttu-id="54082-113">같은 일반 엔터티 기본적으로 `&abc;` 유지 및 **XmlEntityReference** 노드 항상 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54082-113">By default, general entities like `&abc;` are preserved and **XmlEntityReference** nodes always created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54082-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54082-114">See Also</span></span>  
 [<span data-ttu-id="54082-115">XML 문서 개체 모델 (DOM)</span><span class="sxs-lookup"><span data-stu-id="54082-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
