---
title: 연결 집합 End
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 440cfdee4581496d9d131fbaf3d1796f38931532
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756204"
---
# <a name="association-set-end"></a><span data-ttu-id="78070-102">연결 집합 End</span><span class="sxs-lookup"><span data-stu-id="78070-102">association set end</span></span>
<span data-ttu-id="78070-103">*연결 집합 end* 식별 된 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 및 [엔터티 집합](../../../../docs/framework/data/adonet/entity-set.md) 의 끝에는 [연결 집합](../../../../docs/framework/data/adonet/association-set.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="78070-103">An *association set end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) and the [entity set](../../../../docs/framework/data/adonet/entity-set.md) at the end of an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span> <span data-ttu-id="78070-104">연결 집합 End는 연결 집합의 일부로 정의되고 연결 집합에는 정확히 두 개의 연결 집합 End가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78070-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="78070-105">연결 집합 End 정의에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78070-105">An association set end definition contains the following information:</span></span>  
  
-   <span data-ttu-id="78070-106">연결 집합과 관련된 엔터티 형식 중 하나</span><span class="sxs-lookup"><span data-stu-id="78070-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="78070-107">(필수)</span><span class="sxs-lookup"><span data-stu-id="78070-107">(Required)</span></span>  
  
-   <span data-ttu-id="78070-108">연결 집합과 관련된 엔터티 형식에 대한 엔터티 집합</span><span class="sxs-lookup"><span data-stu-id="78070-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="78070-109">(필수)</span><span class="sxs-lookup"><span data-stu-id="78070-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="78070-110">예제</span><span class="sxs-lookup"><span data-stu-id="78070-110">Example</span></span>  
 <span data-ttu-id="78070-111">다음 다이어그램에서는 두 연결 `WrittenBy` 및 `PublishedBy`의 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78070-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 <span data-ttu-id="78070-112">![예제 모델](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="78070-112">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="78070-113">다음 다이어그램에서는 위에 나온 개념적 모델을 기반으로 하여 하나의 연결 집합(`PublishedBy`) 및 두 개의 엔터티 집합(`Books` 및 `Publishers`)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78070-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="78070-114">연결 집합 End는 `Books` 및 `Publishers` 엔터티 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="78070-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="78070-115">bi는 `Books` 엔터티 집합의 인스턴스를 나타내며는 `Book` 런타임 시 엔터티 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="78070-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="78070-116">마찬가지로, Pj 나타냅니다는 `Publisher` 인스턴스는 `Publishers` 엔터티 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="78070-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="78070-117">BiPj의 인스턴스를 나타내며는 `PublishedBy` 에서 연결의 `PublishedBy` 연결 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="78070-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 <span data-ttu-id="78070-118">![예제 설정](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span><span class="sxs-lookup"><span data-stu-id="78070-118">![Sets Example](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span></span>  
  
 <span data-ttu-id="78070-119">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어 이라고 하는 DSL을 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="78070-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="78070-120">다음 CSDL에서는 위의 다이어그램에 있는 각 연결에 대한 하나의 연결 집합을 사용하여 엔터티 컨테이너를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="78070-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="78070-121">연결 집합 End는 각 연결 집합 정의의 일부로 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78070-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="78070-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78070-122">See Also</span></span>  
 [<span data-ttu-id="78070-123">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="78070-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="78070-124">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="78070-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
