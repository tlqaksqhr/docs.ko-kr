---
title: "엔터티 데이터 모델: 네임스페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: dfa18b0f71e30c4e901dc3b55726306a4d46b220
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="entity-data-model-namespaces"></a><span data-ttu-id="c0722-102">엔터티 데이터 모델: 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="c0722-102">Entity Data Model: Namespaces</span></span>
<span data-ttu-id="c0722-103">엔터티 데이터 모델 (EDM)의 네임 스페이스에 대 한 추상 컨테이너는 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md), [복합 형식을](../../../../docs/framework/data/adonet/complex-type.md), 및 [연결](../../../../docs/framework/data/adonet/association-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0722-103">A namespace in the Entity Data Model (EDM) is an abstract container for [entity types](../../../../docs/framework/data/adonet/entity-type.md), [complex types](../../../../docs/framework/data/adonet/complex-type.md), and [associations](../../../../docs/framework/data/adonet/association-type.md).</span></span> <span data-ttu-id="c0722-104">EDM의 네임스페이스는 프로그래밍 언어의 네임스페이스와 유사하며, 포함하는 개체에 대한 컨텍스트를 제공하고 이름은 같지만 다른 네임스페이스에 포함된 개체를 구분하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0722-104">Namespaces in the EDM are similar to namespaces in a programming language: they provide context for the objects that they contain and they provide a way to disambiguate objects that have the same name (but are contained in different namespaces).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0722-105">예</span><span class="sxs-lookup"><span data-stu-id="c0722-105">Example</span></span>  
 <span data-ttu-id="c0722-106">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0722-106">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="c0722-107">다음 CSDL 코드에서는 네임스페이스를 사용하여 다른 개념적 모델에서 정의된 형식을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c0722-107">The following CSDL code uses a namespace to identify a type that is defined in a different conceptual model.</span></span> <span data-ttu-id="c0722-108">다음 예제에서는 `Publisher` 네임스페이스에서 가져온 복합 형식 속성(`Address`)이 있는 엔터티 형식(`ExtendedBooksModel`)을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c0722-108">The example defines an entity type (`Publisher`) that has a complex type property (`Address`) that is imported from the `ExtendedBooksModel` namespace.</span></span> <span data-ttu-id="c0722-109">`Using` 요소는 네임스페이스를 가져왔음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0722-109">Note that the `Using` element indicates that a namespace has been imported.</span></span> <span data-ttu-id="c0722-110">`Address` 속성의 형식은 정규화된 이름(`ExtendedBooksModel.Address`)을 사용하여 정의되며, 이 형식이 `ExtendedBooksModel` 네임스페이스에 정의되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0722-110">Also note that the type of the `Address` property is defined by using its fully qualified name (`ExtendedBooksModel.Address`), indicating that this type is defined in the `ExtendedBooksModel` namespace.</span></span>  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a><span data-ttu-id="c0722-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0722-111">See Also</span></span>  
 [<span data-ttu-id="c0722-112">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="c0722-112">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="c0722-113">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="c0722-113">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
