---
title: "DOM의 네임스페이스 지원"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0548ead-0fed-41ee-b33e-117ba900d3bc
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3145df6517df9db580bfcc5d67edd9d1a61f290b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="namespace-support-in-the-dom"></a><span data-ttu-id="9b0a6-102">DOM의 네임스페이스 지원</span><span class="sxs-lookup"><span data-stu-id="9b0a6-102">Namespace Support in the DOM</span></span>
<span data-ttu-id="9b0a6-103">XML DOM(문서 개체 모델)은 네임스페이스를 완전하게 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0a6-103">The XML Document Object Model (DOM) is completely namespace-aware.</span></span> <span data-ttu-id="9b0a6-104">또한 네임스페이스를 인식하는 XML 문서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0a6-104">Only namespace-aware XML documents are supported.</span></span> <span data-ttu-id="9b0a6-105">W3C(World Wide Web 컨소시엄)는 Level 1을 구현한 DOM 응용 프로그램은 네임스페이스를 인식하지 못할 수 있으며 DOM Level 2 기능은 네임스페이스를 인식한다고 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0a6-105">The World Wide Web Consortium (W3C) specifies that DOM applications that implement Level 1 can be non-namespace-aware, and DOM Level 2 features are namespace-aware.</span></span> <span data-ttu-id="9b0a6-106">하지만 메서드가 Level 1 또는 Level 2 DOM 권장 사항을 따르는지 여부에 관계없이 XML DOM의 모든 기능은 네임스페이스를 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0a6-106">However, all features in the XML DOM are namespace-aware, regardless if the method is from the Level 1 or Level 2 DOM Recommendation.</span></span>  
  
 <span data-ttu-id="9b0a6-107">예를 들어, 네임스페이스를 인식하지 않는 설정에서는 DOM Level 1 권장 사항에 지정된 것처럼 `setAttribute("A:b", "123")`를 호출해도 접두사 `A`와 로컬 이름 `b`를 갖는 특성에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0a6-107">For example, in a non-namespace-aware setting, calling `setAttribute("A:b", "123")`, as specified in the DOM Level 1 Recommendation, does not result in an attribute with a prefix of `A` and a local name of `b`.</span></span> <span data-ttu-id="9b0a6-108">대신 `A:b` 값을 갖는 특성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0a6-108">It would result in an attribute with the value `A:b`.</span></span>  
  
 <span data-ttu-id="9b0a6-109">네임스페이스를 인식하는 환경에서 DOM Level 2 `setAttribute("A:b", "123")`를 호출하면 접두사 `A`와 로컬 이름 `b`를 갖는 특성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0a6-109">In a namespace-aware environment, the call to the DOM Level 2 `setAttribute("A:b", "123")` results in an attribute with a prefix of `A` and a local name of `b`.</span></span> <span data-ttu-id="9b0a6-110">Microsoft.NET Framework DOM의 작동 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="9b0a6-110">This is how the Microsoft .NET Framework DOM works.</span></span>  
  
 <span data-ttu-id="9b0a6-111">따라서 이름 매개 변수가 사용되는 모든 메서드에서 이름을 정규화하는 접두사도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0a6-111">Therefore, for all methods that take a name parameter, these methods also take a prefix to qualify the name.</span></span> <span data-ttu-id="9b0a6-112">Name 매개 변수 같은 `A:b` 에 **setAttribute** DOM Level 1 메서드의 다음과 같은 구문 분석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0a6-112">The name parameter, such as the `A:b` in the **setAttribute** DOM Level 1 method, is parsed as follows:</span></span>  
  
-   <span data-ttu-id="9b0a6-113">콜론(:)이 없으면 로컬 이름이 `name` 매개 변수로 설정되고 접두사와 NamespaceURI는 빈 문자열로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0a6-113">If there are no colon (:) characters, then the local name is set to the `name` parameter, and the prefix and NamespaceURI are empty strings.</span></span>  
  
-   <span data-ttu-id="9b0a6-114">콜론이 있으면 첫 번째 콜론의 위치에 따라 이름이 두 부분으로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0a6-114">If a colon is found, then the name is split into two parts based on the position of the first colon character.</span></span> <span data-ttu-id="9b0a6-115">콜론 앞에 있는 문자열이 접두사로 설정되고 콜론 뒤에 있는 문자열이 로컬 이름으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0a6-115">The prefix is set to the string found before the colon, and local name is set to the string found after the colon.</span></span> <span data-ttu-id="9b0a6-116">NamespaceURI 값을 사용하지 않는 메서드의 경우 NamespaceURI가 확인되지 않으며 빈 문자열로 설정된 상태를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0a6-116">For methods that do not take a NamespaceURI value, the NamespaceURI is not resolved and remains set to empty string.</span></span> <span data-ttu-id="9b0a6-117">그렇지 않으면 NamespaceURI가 메서드에 전달된 문자열로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0a6-117">Otherwise, the NamespaceURI is set to the string passed to the method.</span></span> <span data-ttu-id="9b0a6-118">정의 되지 않은 경우 하면 **저장** 메서드 및 **InnerXml** 및 **OuterXml** 속성에서 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0a6-118">If the prefix is undefined, then the **Save** method and **InnerXml** and **OuterXml** properties fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b0a6-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b0a6-119">See Also</span></span>  
 [<span data-ttu-id="9b0a6-120">XML 문서 개체 모델 (DOM)</span><span class="sxs-lookup"><span data-stu-id="9b0a6-120">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
