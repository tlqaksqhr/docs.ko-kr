---
title: "엔터티 키"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d447a6d-fa7a-4db0-8e7a-fd45e385fca0
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d0d7df7ff1a0e8e732688e10befb4bffa86599d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="entity-key"></a><span data-ttu-id="5a3a6-102">엔터티 키</span><span class="sxs-lookup"><span data-stu-id="5a3a6-102">entity key</span></span>
<span data-ttu-id="5a3a6-103">*엔터티 키* 는 [속성](../../../../docs/framework/data/adonet/property.md) 또는의 속성 집합은 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 신분을 확인 하는 데 사용 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-103">An *entity key* is a [property](../../../../docs/framework/data/adonet/property.md) or a set of properties of an [entity type](../../../../docs/framework/data/adonet/entity-type.md) that are used to determine identity.</span></span> <span data-ttu-id="5a3a6-104">엔터티 키를 구성하는 속성은 디자인 타임에 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-104">The properties that make up an entity key are chosen at design time.</span></span> <span data-ttu-id="5a3a6-105">엔터티 키 속성의 값 내에서 엔터티 형식 인스턴스를 고유 하 게 식별 해야 합니다는 [엔터티 집합](../../../../docs/framework/data/adonet/entity-set.md) 런타임 시.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-105">The values of entity key properties must uniquely identify an entity type instance within an [entity set](../../../../docs/framework/data/adonet/entity-set.md) at run time.</span></span> <span data-ttu-id="5a3a6-106">엔터티 키를 구성하는 속성을 선택하여 엔터티 집합에서 인스턴스의 고유성을 보장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-106">The properties that make up an entity key should be chosen to guarantee uniqueness of instances in an entity set.</span></span>  
  
 <span data-ttu-id="5a3a6-107">다음은 속성 집합이 엔터티 키가 되기 위한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-107">The following are the requirements for a set of properties to be an entity key:</span></span>  
  
-   <span data-ttu-id="5a3a6-108">엔터티 집합 내의 두 엔터티 키는 같지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-108">No two entity keys within an entity set can be identical.</span></span> <span data-ttu-id="5a3a6-109">즉, 엔터티 집합 내의 두 엔터티에서 키를 구성하는 모든 속성 값은 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-109">That is, for any two entities within an entity set, the values for all of the properties that constitute a key cannot be the same.</span></span> <span data-ttu-id="5a3a6-110">그러나 엔터티 키를 구성하는 일부 값은 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-110">However, some (but not all) of the values that make up an entity key can be the same.</span></span>  
  
-   <span data-ttu-id="5a3a6-111">Nullable이 아닌, 변경할 수 없는 집합이 엔터티 키로 구성 되도록 [기본 형식 속성](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-111">An entity key must consist of a set of non-nullable, immutable, [primitive type properties](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).</span></span>  
  
-   <span data-ttu-id="5a3a6-112">지정된 엔터티 형식의 엔터티 키를 구성하는 속성은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-112">The properties that make up an entity key for a given entity type cannot change.</span></span> <span data-ttu-id="5a3a6-113">지정된 엔터티 형식에 사용 가능한 엔터티 키를 여러 개 허용할 수는 없습니다. 서로게이트 키는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-113">You cannot allow more than one possible entity key for a given entity type; surrogate keys are not supported.</span></span>  
  
-   <span data-ttu-id="5a3a6-114">엔터티가 상속 계층 구조에 포함되어 있는 경우 루트 엔터티는 엔터티 키를 구성하는 모든 속성을 포함해야 하며, 루트 엔터티 형식에 엔터티 키를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-114">When an entity is involved in an inheritance hierarchy, the root entity must contain all the properties that make up the entity key, and the entity key must be defined on the root entity type.</span></span> <span data-ttu-id="5a3a6-115">자세한 내용은 참조 [엔터티 데이터 모델: 상속](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-115">For more information, see [Entity Data Model: Inheritance](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a3a6-116">예제</span><span class="sxs-lookup"><span data-stu-id="5a3a6-116">Example</span></span>  
 <span data-ttu-id="5a3a6-117">다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-117">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="5a3a6-118">엔터티 키를 구성하는 각 엔터티 형식의 속성은 "(키)"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-118">The properties of each entity type that make up its entity key are denoted with "(Key)".</span></span> <span data-ttu-id="5a3a6-119">`Author` 엔터티 형식에는 두 가지 속성 `Name` 및 `Address`로 구성된 엔터티 키가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-119">Note that the `Author` entity type has an entity key that consists of two properties, `Name` and `Address`.</span></span>  
  
 <span data-ttu-id="5a3a6-120">![예제 모델](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="5a3a6-120">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="5a3a6-121">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-121">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="5a3a6-122">다음 CSDL에서는 위의 다이어그램에 표시된 `Book` 엔터티 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-122">The CSDL below defines the `Book` entity type shown in the diagram above.</span></span> <span data-ttu-id="5a3a6-123">엔터티 키는 엔터티 형식의 `ISBN` 속성을 참조하여 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-123">Note that the entity key is defined by referencing the `ISBN` property of the entity type.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="5a3a6-124">ISBN(International Standard Book Number)은 책을 고유하게 식별하므로 엔터티 키에 대해 `ISBN` 속성을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-124">The `ISBN` property is a good choice for the entity key because an International Standard Book Number (ISBN) uniquely identifies a book.</span></span>  
  
 <span data-ttu-id="5a3a6-125">다음 CSDL에서는 위의 다이어그램에 표시된 `Author` 엔터티 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-125">The CSDL below defines the `Author` entity type shown in the diagram above.</span></span> <span data-ttu-id="5a3a6-126">엔터티 키는 두 가지 속성 `Name` 및 `Address`로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-126">Note that the entity key consists of two properties, `Name` and `Address`.</span></span>  
  
 [!code-xml[EDM_Example_Model#CompositeKeyExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#compositekeyexample)]  
  
 <span data-ttu-id="5a3a6-127">이름이 같은 두 저자가 같은 주소지에서 거주할 가능성은 없으므로 엔터티 키에 대해 `Name` 및 `Address`를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-127">Using `Name` and `Address` for the entity key is a reasonable choice, because two authors of the same name are unlikely to live at the same address.</span></span> <span data-ttu-id="5a3a6-128">그러나 이러한 엔터티 키 선택이 엔터티 집합에서의 고유한 엔터티 키를 절대적으로 보장하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-128">However, this choice for an entity key does not absolutely guarantee unique entity keys in an entity set.</span></span> <span data-ttu-id="5a3a6-129">이 경우에는 저자를 고유하게 식별하는 데 사용할 수 있는 `AuthorId`와 같은 속성을 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3a6-129">Adding a property, such as `AuthorId`, that could be used to uniquely identify an author would be recommended in this case.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a3a6-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a3a6-130">See Also</span></span>  
 [<span data-ttu-id="5a3a6-131">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="5a3a6-131">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="5a3a6-132">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="5a3a6-132">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
