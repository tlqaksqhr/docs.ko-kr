---
title: 엔터티 참조 유지
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 652a044bf1b5293bc9c36477a46a78d9851f1810
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568487"
---
# <a name="entity-references-are-preserved"></a><span data-ttu-id="0d687-102">엔터티 참조 유지</span><span class="sxs-lookup"><span data-stu-id="0d687-102">Entity References are Preserved</span></span>
<span data-ttu-id="0d687-103">엔터티 참조가 확장되지 않고 유지되면 XML DOM(문서 개체 모델)에서는 엔터티 참조가 발생하는 경우 **XmlEntityReference** 노드를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0d687-103">When the entity reference is not expanded, but preserved, the XML Document Object Model (DOM) builds an **XmlEntityReference** node when it encounters an entity reference.</span></span>  
  
 <span data-ttu-id="0d687-104">다음 XML을 사용한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d687-104">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="0d687-105">DOM에서 `&publisher;` 참조가 발생하는 경우 **XmlEntityReference** 노드를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0d687-105">the DOM builds an **XmlEntityReference** node when it encounters the `&publisher;` reference.</span></span> <span data-ttu-id="0d687-106">**XmlEntityReference**는 엔터티 선언의 내용에서 복사된 자식 노드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0d687-106">The **XmlEntityReference** contains child nodes copied from the content in the entity declaration.</span></span> <span data-ttu-id="0d687-107">앞의 코드 예제에서는 엔터티 선언에 텍스트를 포함하고 있으므로 **XmlText** 노드가 엔터티 참조 노드의 자식 노드로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d687-107">The preceding code example contains text in the entity declaration, so an **XmlText** node is created as the child node of the entity reference node.</span></span>  
  
 <span data-ttu-id="0d687-108">![유지된 엔터티 참조에 대한 트리 구조](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span><span class="sxs-lookup"><span data-stu-id="0d687-108">![Tree structure for preserved entity references](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span></span>  
<span data-ttu-id="0d687-109">유지되는 엔터티 참조의 트리 구조</span><span class="sxs-lookup"><span data-stu-id="0d687-109">Tree structure for entity references that are preserved</span></span>  
  
 <span data-ttu-id="0d687-110">**XmlEntityReference**의 자식 노드는 엔터티 선언이 발생했을 경우 **XmlEntity** 노드에서 만들어진 모든 자식 노드의 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="0d687-110">The child nodes of the **XmlEntityReference** are copies of all the child nodes created from the **XmlEntity** node when the entity declaration was encountered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d687-111">**XmlEntity**에서 복사한 노드는 경우에 따라 해당 엔터티 참조 노드 아래의 복사본과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d687-111">The nodes copied from the **XmlEntity** are not always exact copies once placed under the entity reference node.</span></span> <span data-ttu-id="0d687-112">entityreference 노드 범위에 속한 네임스페이스가 있을 수 있으며 자식 노드의 최종 구성에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d687-112">There can be namespaces that are in scope at the entity reference node, and that affects the final configuration of the child nodes.</span></span>  
  
 <span data-ttu-id="0d687-113">기본적으로 `&abc;`와 같은 일반 엔터티는 유지되며 항상 **XmlEntityReference** 노드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d687-113">By default, general entities like `&abc;` are preserved and **XmlEntityReference** nodes always created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d687-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d687-114">See Also</span></span>  
 [<span data-ttu-id="0d687-115">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="0d687-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
