---
title: 엔터티 컨테이너(entity container)
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: ed2123629c61b179e07e86effa0c39d9a3222b62
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764043"
---
# <a name="entity-container"></a><span data-ttu-id="31bd4-102">엔터티 컨테이너(entity container)</span><span class="sxs-lookup"><span data-stu-id="31bd4-102">entity container</span></span>
<span data-ttu-id="31bd4-103">*엔터티 컨테이너* 의 논리적 그룹 [엔터티 집합](../../../../docs/framework/data/adonet/entity-set.md), [연결 집합](../../../../docs/framework/data/adonet/association-set.md), 및 [imports 함수](../../../../docs/framework/data/adonet/model-declared-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="31bd4-103">An *entity container* is a logical grouping of [entity sets](../../../../docs/framework/data/adonet/entity-set.md), [association sets](../../../../docs/framework/data/adonet/association-set.md), and [function imports](../../../../docs/framework/data/adonet/model-declared-function.md).</span></span>  
  
 <span data-ttu-id="31bd4-104">개념적 모델에 정의된 엔터티 컨테이너에 대해 다음 조건이 충족되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31bd4-104">The following must be true of an entity container defined in a conceptual model:</span></span>  
  
-   <span data-ttu-id="31bd4-105">각 개념적 모델에 엔터티 컨테이너가 하나 이상 정의되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31bd4-105">At least one entity container must be defined in each conceptual model.</span></span>  
  
-   <span data-ttu-id="31bd4-106">각 개념적 모델 내에서 엔터티 컨테이너의 이름이 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31bd4-106">The entity container must have a unique name within each conceptual model.</span></span>  
  
 <span data-ttu-id="31bd4-107">엔터티 컨테이너는 하나 이상의 네임스페이스에 정의된 엔터티 형식이나 연결을 사용하는 엔터티 집합 또는 연결 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31bd4-107">An entity container can define entity sets or association sets that use entity types or associations defined in one or more namespaces.</span></span> <span data-ttu-id="31bd4-108">자세한 내용은 참조 [엔터티 데이터 모델: 네임 스페이스](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="31bd4-108">For more information, see [Entity Data Model: Namespaces](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="31bd4-109">예제</span><span class="sxs-lookup"><span data-stu-id="31bd4-109">Example</span></span>  
 <span data-ttu-id="31bd4-110">다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31bd4-110">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  <span data-ttu-id="31bd4-111">자세한 내용은 다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31bd4-111">See the next example for more information.</span></span>  
  
 <span data-ttu-id="31bd4-112">![예제 모델](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="31bd4-112">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="31bd4-113">다이어그램에는 엔터티 컨테이너 정보가 표시되지 않지만 개념적 모델에서 엔터티 컨테이너를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31bd4-113">Although the diagram does not convey entity container information, the conceptual model must define an entity container.</span></span> <span data-ttu-id="31bd4-114">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어 이라고 하는 DSL을 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="31bd4-114">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="31bd4-115">다음 CSDL에서는 위의 다이어그램에 표시된 개념적 모델의 엔터티 컨테이너를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="31bd4-115">The following CSDL defines an entity container for the conceptual model shown in the diagram above.</span></span> <span data-ttu-id="31bd4-116">엔터티 컨테이너 이름은 XML 특성에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31bd4-116">Note that the entity container name is defined in an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="31bd4-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31bd4-117">See Also</span></span>  
 [<span data-ttu-id="31bd4-118">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="31bd4-118">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="31bd4-119">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="31bd4-119">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
