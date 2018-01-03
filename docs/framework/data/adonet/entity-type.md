---
title: "엔터티 형식(entity type)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: dd1a669b81b9dbbb54b83d13dbb7c0ba7ce3f5cd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="entity-type"></a><span data-ttu-id="0ae9b-102">엔터티 형식(entity type)</span><span class="sxs-lookup"><span data-stu-id="0ae9b-102">entity type</span></span>
<span data-ttu-id="0ae9b-103">*엔터티 형식* 는 엔터티 데이터 모델 (EDM)와 데이터의 구조를 설명 하기 위한 기본적인 빌딩 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="0ae9b-103">The *entity type* is the fundamental building block for describing the structure of data with the Entity Data Model (EDM).</span></span> <span data-ttu-id="0ae9b-104">개념적 모델에서 엔터티 형식은 고객이나 주문과 같은 최상위 개념의 구조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0ae9b-104">In a conceptual model, an entity type represents the structure of top-level concepts, such as customers or orders.</span></span> <span data-ttu-id="0ae9b-105">엔터티 형식은 엔터티 형식 인스턴스의 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="0ae9b-105">An entity type is a template for entity type instances.</span></span> <span data-ttu-id="0ae9b-106">각 템플릿에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae9b-106">Each template contains the following information:</span></span>  
  
-   <span data-ttu-id="0ae9b-107">고유한 이름</span><span class="sxs-lookup"><span data-stu-id="0ae9b-107">A unique name.</span></span> <span data-ttu-id="0ae9b-108">(필수)</span><span class="sxs-lookup"><span data-stu-id="0ae9b-108">(Required.)</span></span>  
  
-   <span data-ttu-id="0ae9b-109">[엔터티 키](../../../../docs/framework/data/adonet/entity-key.md) 하나 이상의 속성에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae9b-109">An [entity key](../../../../docs/framework/data/adonet/entity-key.md) defined by one or more properties.</span></span> <span data-ttu-id="0ae9b-110">(필수)</span><span class="sxs-lookup"><span data-stu-id="0ae9b-110">(Required.)</span></span>  
  
-   <span data-ttu-id="0ae9b-111">데이터 형식으로 [속성](../../../../docs/framework/data/adonet/property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae9b-111">Data in the form of [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="0ae9b-112">(선택적 요소)</span><span class="sxs-lookup"><span data-stu-id="0ae9b-112">(Optional.)</span></span>  
  
-   <span data-ttu-id="0ae9b-113">[탐색 속성](../../../../docs/framework/data/adonet/navigation-property.md) 하나 탐색할 수 있도록 하는 [끝](../../../../docs/framework/data/adonet/association-end.md) 의 [연결](../../../../docs/framework/data/adonet/association-type.md) 다른 쪽 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="0ae9b-113">[Navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) that allow for navigation from one [end](../../../../docs/framework/data/adonet/association-end.md) of an [association](../../../../docs/framework/data/adonet/association-type.md) to the other end.</span></span> <span data-ttu-id="0ae9b-114">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0ae9b-114">(Optional)</span></span>  
  
 <span data-ttu-id="0ae9b-115">응용 프로그램에서 엔터티 형식의 인스턴스는 특정 고객 또는 주문과 같은 특정 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0ae9b-115">In an application, an instance of an entity type represents a specific object (such as a specific customer or order).</span></span> <span data-ttu-id="0ae9b-116">각 엔터티 형식의 인스턴스는 고유 해야 합니다. [엔터티 키](../../../../docs/framework/data/adonet/entity-key.md) 내는 [엔터티 집합](../../../../docs/framework/data/adonet/entity-set.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae9b-116">Each instance of an entity type must have a unique [entity key](../../../../docs/framework/data/adonet/entity-key.md) within an [entity set](../../../../docs/framework/data/adonet/entity-set.md).</span></span>  
  
 <span data-ttu-id="0ae9b-117">두 엔터티 형식 인스턴스는 형식이 동일하고 해당 엔터티 키 값이 동일한 경우에만 동일한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae9b-117">Two entity type instances are considered equal only if they are of the same type and the values of their entity keys are the same.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ae9b-118">예제</span><span class="sxs-lookup"><span data-stu-id="0ae9b-118">Example</span></span>  
 <span data-ttu-id="0ae9b-119">다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ae9b-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`:</span></span>  
  
 <span data-ttu-id="0ae9b-120">![예제 모델](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="0ae9b-120">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="0ae9b-121">엔터티 키를 구성하는 각 엔터티 형식의 속성은 "(키)"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae9b-121">Note that the properties of each entity type that make up its entity key are denoted with "(Key)".</span></span>  
  
 <span data-ttu-id="0ae9b-122">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae9b-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="0ae9b-123">다음 CSDL에서는 위의 다이어그램에 표시된 `Book` 엔터티 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae9b-123">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="0ae9b-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ae9b-124">See Also</span></span>  
 [<span data-ttu-id="0ae9b-125">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="0ae9b-125">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="0ae9b-126">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="0ae9b-126">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [<span data-ttu-id="0ae9b-127">facet</span><span class="sxs-lookup"><span data-stu-id="0ae9b-127">facet</span></span>](../../../../docs/framework/data/adonet/facet.md)
