---
title: 요소 및 특성이 있는 새 노드의 엔터티 참조 확장에 대한 네임스페이스의 영향
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 64359aee-aab0-4042-9a32-d19789af6ca7
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e2ba9964f17380e868ea5fe906a40f8b491018a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568903"
---
# <a name="namespace-affect-on-entity-reference-expansion-for-new-nodes-containing-elements-and-attributes"></a><span data-ttu-id="42893-102">요소 및 특성이 있는 새 노드의 엔터티 참조 확장에 대한 네임스페이스의 영향</span><span class="sxs-lookup"><span data-stu-id="42893-102">Namespace Affect on Entity Reference Expansion for New Nodes Containing Elements and Attributes</span></span>
<span data-ttu-id="42893-103">엔터티 선언 내용은 거의 모든 항목을 포함할 수 있기 때문에 이 내용에 `<!ENTITY aname "<elem>test</elem>">`와 같은 요소가 포함될 가능성도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42893-103">Because the content of an entity declaration can contain almost anything, there is a possibility that the content could contain an element like `<!ENTITY aname "<elem>test</elem>">`.</span></span>  
  
 <span data-ttu-id="42893-104">XML이 구문 분석될 때 `&aname;`은 구문 분석할 때의 대체 내용으로 확장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42893-104">When the XML is parsed, `&aname;` is not expanded with its replacement content at parse time.</span></span> <span data-ttu-id="42893-105">노드가 문서에 배치되지 않으면 요소에 대한 네임스페이스 확인 작업이 발생하지 않으므로 XML 확장이 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42893-105">The expansion of the XML is not done because resolution of the namespace for the element cannot occur until the node is placed in the document.</span></span> <span data-ttu-id="42893-106">따라서 그전에는 범위에 있는 네임스페이스를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42893-106">Until that time, there is no knowledge of what namespace is in scope.</span></span> <span data-ttu-id="42893-107">노드가 문서에 배치되면 네임스페이스 확인 작업이 발생하고 그에 따른 엔터티 내용이 해당 노드로 구문 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="42893-107">When the node is put into the document, then the namespace resolution occurs, and the resulting entity content is parsed into its appropriate nodes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42893-108">새로 만들어진 entityreference 노드는 한 번 확장된 후에는 다시 확장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42893-108">Once the expansion occurs on a newly created entity reference node, it never reoccurs.</span></span> <span data-ttu-id="42893-109">따라서 부모 노드가 설정될 때 요소의 대체 텍스트에서 사용된 네임스페이스가 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="42893-109">Therefore, the namespaces used in the replacement text for the element are bound at the time that the parent node is set.</span></span> <span data-ttu-id="42893-110">하지만 기존 엔터티 참조 노드를 제거하고 다른 위치에 삽입할 경우 또는 **CloneNode** 메서드로 복제된 엔터티 참조 노드의 경우 해당 노드의 네임스페이스가 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42893-110">However, the namespace can be changed for existing entity reference nodes when you remove and insert them somewhere else, or on entity reference nodes that are cloned with the **CloneNode** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42893-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42893-111">See Also</span></span>  
 [<span data-ttu-id="42893-112">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="42893-112">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
