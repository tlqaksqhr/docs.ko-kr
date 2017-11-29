---
title: "연결 형식"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 476a92979ff0dc6292e64ce5514cc600a9dee50a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="association-type"></a><span data-ttu-id="53272-102">연결 형식</span><span class="sxs-lookup"><span data-stu-id="53272-102">association type</span></span>
<span data-ttu-id="53272-103">*연결 형식* (연결이 라고도 함)는 엔터티 데이터 모델 (EDM)의 관계를 설명 하기 위한 기본적인 빌딩 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="53272-103">An *association type* (also called an association) is the fundamental building block for describing relationships in the Entity Data Model (EDM).</span></span> <span data-ttu-id="53272-104">개념적 모델에서 연결 두 개 사이의 관계를 나타내는 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) (같은 `Customer` 및 `Order`).</span><span class="sxs-lookup"><span data-stu-id="53272-104">In a conceptual model, an association represents a relationship between two [entity types](../../../../docs/framework/data/adonet/entity-type.md) (such as `Customer` and `Order`).</span></span> <span data-ttu-id="53272-105">응용 프로그램에서 연결 인스턴스는 특정 연결(예: `Customer` 인스턴스와 `Order` 인스턴스 간의 연결)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="53272-105">In an application, an instance of an association represents a specific association (such as an association between an instance of `Customer` and an instance of `Order`).</span></span> <span data-ttu-id="53272-106">연결 인스턴스는 논리적으로 그룹화는 [연결 집합](../../../../docs/framework/data/adonet/association-set.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="53272-106">Association instances are logically grouped in an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span>  
  
 <span data-ttu-id="53272-107">연결 정의에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53272-107">An association definition contains the following information:</span></span>  
  
-   <span data-ttu-id="53272-108">고유한 이름</span><span class="sxs-lookup"><span data-stu-id="53272-108">A unique name.</span></span> <span data-ttu-id="53272-109">(필수)</span><span class="sxs-lookup"><span data-stu-id="53272-109">(Required)</span></span>  
  
-   <span data-ttu-id="53272-110">두 개의 [연결 end](../../../../docs/framework/data/adonet/association-end.md), 관계의 각 엔터티 형식에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="53272-110">Two [association ends](../../../../docs/framework/data/adonet/association-end.md), one for each entity type in the relationship.</span></span> <span data-ttu-id="53272-111">(필수)</span><span class="sxs-lookup"><span data-stu-id="53272-111">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="53272-112">연결은 셋 이상 엔터티 형식 간의 관계를 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53272-112">An association cannot represent a relationship among more than two entity types.</span></span> <span data-ttu-id="53272-113">그러나 연결은 각 연결 End에 같은 엔터티 형식을 지정하여 자체 관계를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53272-113">An association can, however, define a self-relationship by specifying the same entity type for each of its association ends.</span></span>  
  
-   <span data-ttu-id="53272-114">A [참조 무결성 제약 조건을](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="53272-114">A [referential integrity constraint](../../../../docs/framework/data/adonet/referential-integrity-constraint.md).</span></span> <span data-ttu-id="53272-115">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="53272-115">(Optional)</span></span>  
  
 <span data-ttu-id="53272-116">각 연결 end 지정 해야 합니다는 [연결 end 복합성](../../../../docs/framework/data/adonet/association-end-multiplicity.md) 는 association의 한 end에 있을 수 있는 엔터티 형식 인스턴스 수를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="53272-116">Each association end must specify an [association end multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="53272-117">연결 End의 복합성 값은 한 개(1), 0개 또는 한 개(0..1) 또는 다수(*)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53272-117">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (*).</span></span> <span data-ttu-id="53272-118">연결의 한쪽 end에 엔터티 형식 인스턴스를 통해 액세스할 수 [탐색 속성](../../../../docs/framework/data/adonet/navigation-property.md) 또는 엔터티 형식에서 노출 된 경우 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="53272-118">Entity type instances at one end of an association can be accessed through [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) or foreign keys if they are exposed on an entity type.</span></span> <span data-ttu-id="53272-119">자세한 내용은 참조 [엔터티 데이터 모델: 외래 키](../../../../docs/framework/data/adonet/foreign-key-property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="53272-119">For more information, see [Entity Data Model: Foreign Keys](../../../../docs/framework/data/adonet/foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53272-120">예제</span><span class="sxs-lookup"><span data-stu-id="53272-120">Example</span></span>  
 <span data-ttu-id="53272-121">다음 다이어그램에서는 두 연결 `PublishedBy` 및 `WrittenBy`의 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="53272-121">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="53272-122">`PublishedBy` 연결의 연결 End는 `Book` 및 `Publisher` 엔터티 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="53272-122">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="53272-123">`Publisher` 끝의 복합성은 한 개(1)이고 `Book` 끝의 복합성은 다수(*)이므로 한 명의 발행자가 많은 책을 출판하고 책 하나는 한 명의 발행자에 의해 출판됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="53272-123">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 <span data-ttu-id="53272-124">![예제 모델](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="53272-124">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="53272-125">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="53272-125">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="53272-126">다음 CSDL에서는 위의 다이어그램에 표시된 `PublishedBy` 연결을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="53272-126">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="53272-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53272-127">See Also</span></span>  
 [<span data-ttu-id="53272-128">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="53272-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="53272-129">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="53272-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
