---
title: DOM의 네임스페이스 및 DTD
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1e9b55c4-76ad-4f54-8d96-7ce4b4cf1e05
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92d7a50d2db25f5e4d32734d550ce2d55a02e3c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="namespaces-and-dtds-in-the-dom"></a><span data-ttu-id="1c961-102">DOM의 네임스페이스 및 DTD</span><span class="sxs-lookup"><span data-stu-id="1c961-102">Namespaces and DTDs in the DOM</span></span>
<span data-ttu-id="1c961-103">DTD(문서 종류 정의)는 네임스페이스 지원을 어렵게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c961-103">Document type definitions (DTDs) complicate namespace support.</span></span> <span data-ttu-id="1c961-104">예를 들어, 다음 XML에는 이름에 콜론이 포함되는 기본 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c961-104">For example, the following XML contains default attributes containing colons in their names.</span></span>  
  
```xml  
<!ATTLIST item x:id CDATA #IMPLIED>  
```  
  
 <span data-ttu-id="1c961-105">다음은 이 구문이 허용되는 경우의 해결책입니다.</span><span class="sxs-lookup"><span data-stu-id="1c961-105">The following are possible resolutions if this construct is allowed:</span></span>  
  
-   <span data-ttu-id="1c961-106">`x:`를 네임스페이스 접두사로 처리하지만 이 접두사는 `xmlns:x` 네임스페이스 선언을 사용하여 확인할 수 있도록 DTD에도 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c961-106">The `x:` is treated as a namespace prefix, but this prefix must be resolvable using an `xmlns:x` namespace declaration, which must also exist somewhere in the DTD.</span></span> <span data-ttu-id="1c961-107">이 접두사를 인스턴스 문서의 다른 항목에 매핑하는 것은 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="1c961-107">It is an error to map this prefix to something different in the instance document.</span></span>  
  
-   <span data-ttu-id="1c961-108">`x:`는 네임스페이스 접두사로 처리하지만 이 접두사는 항상 인스턴스 요소의 컨텍스트에서 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c961-108">The `x:` is treated as a namespace prefix, but this prefix is always resolved in the context of the instance elements.</span></span> <span data-ttu-id="1c961-109">즉, 실제로 `item` 요소가 나타난 네임스페이스 범위에 따라 다양한 네임스페이스 URI(Uniform Resource Identifier)에 접두사가 매핑될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c961-109">This means the prefix could actually map to different namespace Uniform Resource Identifiers (URIs), depending on the namespace scope in which the `item` element appears.</span></span> <span data-ttu-id="1c961-110">이 동작은 이전 목록에서 제시된 해결책보다는 예측 가능성이 크지만 기본 특성을 구체화해야 하기 때문에 다른 복잡한 문제를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c961-110">This behavior is more predictable than the resolution given in the earlier bullet, but it has other complicated ramifications because it requires the default attributes be materialized.</span></span>  
  
-   <span data-ttu-id="1c961-111">콜론은 DTD에 있기 때문에 무시되고 특성 이름은 접두사와 네임스페이스 URI가 없는 `x:y`입니다.</span><span class="sxs-lookup"><span data-stu-id="1c961-111">The colon is ignored because it is in a DTD, and the name of the attribute is `x:y`, no prefix and no namespace URI.</span></span>  
  
-   <span data-ttu-id="1c961-112">기본 특성의 콜론은 DTD 내부에서 이름에 콜론을 사용할 수 없음을 알리는 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c961-112">The colon in the default attribute throws an exception, saying that colons in names inside a DTD are not supported.</span></span> <span data-ttu-id="1c961-113">이것은 예측 가능한 동작이지만 W3C(World Wide Web 컨소시엄)에서 배포한 많은 DTD를 로드할 수 없다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="1c961-113">This results in a predictable behavior, but means you cannot load many of the World Wide Web Consortium (W3C) published DTDs.</span></span>  
  
-   <span data-ttu-id="1c961-114">사용자가 DTD 유효성 검사를 요청하면 전체 문서에 대한 네임스페이스 지원이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c961-114">When the user requests DTD validation, namespace support for the entire document is turned off.</span></span> <span data-ttu-id="1c961-115">이렇게 하면 W3C DTD를 로드하고 동작을 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c961-115">This makes it possible to load W3C DTDs and results in a predictable behavior.</span></span>  
  
 <span data-ttu-id="1c961-116">Microsoft .NET Framework의 XML은 W3C 호환성을 극대화하기 위해 두 번째 옵션을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="1c961-116">The XML in the Microsoft .NET Framework implements the second option for maximum W3C compatibility.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c961-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c961-117">See Also</span></span>  
 [<span data-ttu-id="1c961-118">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="1c961-118">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
