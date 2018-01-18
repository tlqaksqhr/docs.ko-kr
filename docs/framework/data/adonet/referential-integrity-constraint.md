---
title: "참조 무결성 제약 조건"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c343a0eba2478e041186f7bef18a85400c54bb5c
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="referential-integrity-constraint"></a><span data-ttu-id="ea8b4-102">참조 무결성 제약 조건</span><span class="sxs-lookup"><span data-stu-id="ea8b4-102">referential integrity constraint</span></span>
<span data-ttu-id="ea8b4-103">A *참조 무결성 제약 조건을* 엔터티 데이터 모델 (EDM)에 관계형 데이터베이스의 참조 무결성 제약 조건을 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8b4-103">A *referential integrity constraint* in the Entity Data Model (EDM) is similar to a referential integrity constraint in a relational database.</span></span> <span data-ttu-id="ea8b4-104">데이터베이스 테이블에서 열 (또는 열) 다른 테이블의 기본 키를 참조할 수 있도록 동일한 방법으로 [속성](../../../../docs/framework/data/adonet/property.md) (또는 속성)의 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 참조할 수는 [엔터티 키 ](../../../../docs/framework/data/adonet/entity-key.md) 다른 엔터티 형식의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8b4-104">In the same way that a column (or columns) from a database table can reference the primary key of another table, a [property](../../../../docs/framework/data/adonet/property.md) (or properties) of an [entity type](../../../../docs/framework/data/adonet/entity-type.md) can reference the [entity key](../../../../docs/framework/data/adonet/entity-key.md) of another entity type.</span></span> <span data-ttu-id="ea8b4-105">참조 되는 엔터티 형식 라고는 *주 끝* 제약 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8b4-105">The entity type that is referenced is called the *principal end* of the constraint.</span></span> <span data-ttu-id="ea8b4-106">주 끝을 참조 하는 엔터티 형식은 라고는 *종속 끝* 제약 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8b4-106">The entity type that references the principal end is called the *dependent end* of the constraint.</span></span>  
  
 <span data-ttu-id="ea8b4-107">참조 무결성 제약 조건을의 일부로 정의 되는 [연결](../../../../docs/framework/data/adonet/association-type.md) 두 엔터티 형식 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8b4-107">A referential integrity constraint is defined as part of an [association](../../../../docs/framework/data/adonet/association-type.md) between two entity types.</span></span> <span data-ttu-id="ea8b4-108">참조 무결성 제약 조건 정의에서는 다음 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8b4-108">The definition for a referential integrity constraint specifies the following information:</span></span>  
  
-   <span data-ttu-id="ea8b4-109">제약 조건의 주 끝</span><span class="sxs-lookup"><span data-stu-id="ea8b4-109">The principal end of the constraint.</span></span> <span data-ttu-id="ea8b4-110">(엔터티 키가 종속 끝에서 참조되는 엔터티 형식)</span><span class="sxs-lookup"><span data-stu-id="ea8b4-110">(An entity type whose entity key is referenced by the dependent end.)</span></span>  
  
-   <span data-ttu-id="ea8b4-111">주 끝의 엔터티 키</span><span class="sxs-lookup"><span data-stu-id="ea8b4-111">The entity key of the principal end.</span></span>  
  
-   <span data-ttu-id="ea8b4-112">제약 조건의 종속 끝</span><span class="sxs-lookup"><span data-stu-id="ea8b4-112">The dependent end of the constraint.</span></span> <span data-ttu-id="ea8b4-113">(주 끝의 엔터티 키를 참조하는 속성이 있는 엔터티 형식)</span><span class="sxs-lookup"><span data-stu-id="ea8b4-113">(An entity type that has a property or properties that reference the entity key of the principal end.)</span></span>  
  
-   <span data-ttu-id="ea8b4-114">종속 끝의 참조 속성</span><span class="sxs-lookup"><span data-stu-id="ea8b4-114">The referencing property or properties of the dependent end.</span></span>  
  
 <span data-ttu-id="ea8b4-115">EDM의 참조 무결성 제약 조건은 항상 올바른 연결이 존재하도록 보장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea8b4-115">The purpose of referential integrity constraints in the EDM is to ensure that valid associations always exist.</span></span> <span data-ttu-id="ea8b4-116">자세한 내용은 참조 [외래 키 속성](../../../../docs/framework/data/adonet/foreign-key-property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8b4-116">For more information, see [foreign key property](../../../../docs/framework/data/adonet/foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea8b4-117">예</span><span class="sxs-lookup"><span data-stu-id="ea8b4-117">Example</span></span>  
 <span data-ttu-id="ea8b4-118">다음 다이어그램에서는 두 연결 `WrittenBy` 및 `PublishedBy`의 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ea8b4-118">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span> <span data-ttu-id="ea8b4-119">`Book` 엔터티 형식에는 `PublisherId` 연결에 참조 무결성 제약 조건을 정의할 때 `Publisher` 엔터티 형식의 엔터티 키를 참조하는 `PublishedBy` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea8b4-119">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="ea8b4-120">![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")</span><span class="sxs-lookup"><span data-stu-id="ea8b4-120">![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")</span></span>  
  
 <span data-ttu-id="ea8b4-121">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8b4-121">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="ea8b4-122">다음 CSDL에서는 위의 개념적 모델에 표시된 `PublishedBy` 연결에 참조 무결성 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8b4-122">The following CSDL defines a referential integrity constraint on the `PublishedBy` association shown in the conceptual model above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="ea8b4-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea8b4-123">See Also</span></span>  
 [<span data-ttu-id="ea8b4-124">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="ea8b4-124">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="ea8b4-125">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="ea8b4-125">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
