---
title: "새 노드를 만들 때 XML 요소 및 특성 이름 확인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c041d5d2830222f3fae09a39f1ea10eb08772388
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a><span data-ttu-id="44c15-102">새 노드를 만들 때 XML 요소 및 특성 이름 확인</span><span class="sxs-lookup"><span data-stu-id="44c15-102">XML Element and Attribute Name Verification when Creating New Nodes</span></span>
<span data-ttu-id="44c15-103">XML DOM(문서 개체 모델)에서는 새 요소 노드나 특성 노드를 만들 때 해당 이름의 유효성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="44c15-103">The XML Document Object Model (DOM) checks the validity of the names when creating new element nodes or attribute nodes.</span></span> <span data-ttu-id="44c15-104">이름에 잘못된 문자가 있으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="44c15-104">If the names contain illegal characters, an exception is thrown.</span></span> <span data-ttu-id="44c15-105">이름이 유효 하 고 인코딩된 올바르게 위해이를 사용 해야는 **XmlConvert** 클래스를 이름을 인코딩 및 응용 프로그램 수준에서 다시 디코딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44c15-105">To ensure that names are valid and encoded correctly, you need to use the **XmlConvert** class to encode the name and decode it back at an application level.</span></span> <span data-ttu-id="44c15-106">**XmlWriter** 에 올바른 형식의 XML이 생성 되도록 추가 작업을 수행 하는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c15-106">The **XmlWriter** has methods that do additional work to ensure well-formed XML is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c15-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44c15-107">See Also</span></span>  
 [<span data-ttu-id="44c15-108">XML 문서 개체 모델 (DOM)</span><span class="sxs-lookup"><span data-stu-id="44c15-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
