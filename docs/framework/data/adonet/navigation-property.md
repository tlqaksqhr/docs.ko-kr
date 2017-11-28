---
title: "탐색 속성(navigation property)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1677ab1be071eeabd72b29c7ce61d01aaf6164a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="navigation-property"></a><span data-ttu-id="9438e-102">탐색 속성(navigation property)</span><span class="sxs-lookup"><span data-stu-id="9438e-102">navigation property</span></span>
<span data-ttu-id="9438e-103">A *탐색 속성* 은 선택적 속성에는 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 하나씩 탐색할 수 있게 해 주는 [끝](../../../../docs/framework/data/adonet/association-end.md) 의 [연결](../../../../docs/framework/data/adonet/association-type.md) 를 다른 쪽 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="9438e-103">A *navigation property* is an optional property on an [entity type](../../../../docs/framework/data/adonet/entity-type.md) that allows for navigation from one [end](../../../../docs/framework/data/adonet/association-end.md) of an [association](../../../../docs/framework/data/adonet/association-type.md) to the other end.</span></span> <span data-ttu-id="9438e-104">다른 달리 [속성](../../../../docs/framework/data/adonet/property.md), 탐색 속성은 데이터를 전달 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9438e-104">Unlike other [properties](../../../../docs/framework/data/adonet/property.md), navigation properties do not carry data.</span></span>  
  
 <span data-ttu-id="9438e-105">탐색 속성 정의에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9438e-105">A navigation property definition includes the following:</span></span>  
  
-   <span data-ttu-id="9438e-106">이름</span><span class="sxs-lookup"><span data-stu-id="9438e-106">A name.</span></span> <span data-ttu-id="9438e-107">(필수)</span><span class="sxs-lookup"><span data-stu-id="9438e-107">(Required)</span></span>  
  
-   <span data-ttu-id="9438e-108">탐색하는 연결</span><span class="sxs-lookup"><span data-stu-id="9438e-108">The association that it navigates.</span></span> <span data-ttu-id="9438e-109">(필수)</span><span class="sxs-lookup"><span data-stu-id="9438e-109">(Required)</span></span>  
  
-   <span data-ttu-id="9438e-110">탐색하는 연결의 End</span><span class="sxs-lookup"><span data-stu-id="9438e-110">The ends of the association that it navigates.</span></span> <span data-ttu-id="9438e-111">(필수)</span><span class="sxs-lookup"><span data-stu-id="9438e-111">(Required)</span></span>  
  
 <span data-ttu-id="9438e-112">탐색 속성은 연결의 양쪽 End에 있는 엔터티 형식 모두에 대해 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9438e-112">Note that navigation properties are optional on both entity types at the ends of an association.</span></span> <span data-ttu-id="9438e-113">연결의 End에 있는 한 엔터티 형식에 대해 탐색 속성을 정의하는 경우 연결의 다른 End에 있는 엔터티 형식에 대해서는 탐색 속성을 정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9438e-113">If you define a navigation property on one entity type at the end of an association, you do not have to define a navigation property on the entity type at the other end of the association.</span></span>  
  
 <span data-ttu-id="9438e-114">탐색 속성의 데이터 형식을 따라 사용자가 [복합성](../../../../docs/framework/data/adonet/association-end-multiplicity.md) 해당 원격 [연결 end](../../../../docs/framework/data/adonet/association-end.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9438e-114">The data type of a navigation property is determined by the [multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) of its remote [association end](../../../../docs/framework/data/adonet/association-end.md).</span></span> <span data-ttu-id="9438e-115">예를 들어, `OrdersNavProp` 탐색 속성이 `Customer` 엔터티 형식에 존재하며 `Customer`와 `Order` 간의 일대다 연결을 탐색한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="9438e-115">For example, suppose a navigation property, `OrdersNavProp`, exists on a `Customer` entity type and navigates a one-to-many association between `Customer` and `Order`.</span></span> <span data-ttu-id="9438e-116">탐색 속성에 대한 원격 연결 End의 복합성이 다수(*)이므로 해당 데이터 형식은 `Order`의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="9438e-116">Because the remote association end for the navigation property has multiplicity of many (*), its data type is a collection (of `Order`).</span></span> <span data-ttu-id="9438e-117">마찬가지로 `CustomerNavProp` 탐색 속성이 `Order` 엔터티 형식에 존재하는 경우 원격 End의 복합성이 한 개(1)이므로 해당 데이터 형식은 `Customer`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9438e-117">Similarly, if a navigation property, `CustomerNavProp`, exists on the `Order` entity type, its data type would be `Customer`, because the multiplicity of the remote end is one (1).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9438e-118">예제</span><span class="sxs-lookup"><span data-stu-id="9438e-118">Example</span></span>  
 <span data-ttu-id="9438e-119">다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9438e-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="9438e-120">탐색 속성 `Publisher` 및 `Authors`는 Book 엔터티 형식에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9438e-120">Navigation properties, `Publisher` and `Authors`, are defined on the Book entity type.</span></span> <span data-ttu-id="9438e-121">탐색 속성 `Books`는 Publisher 엔터티 형식과 `Author` 엔터티 형식에 모두 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9438e-121">Navigation property `Books` is defined on both the Publisher entity type and the `Author` entity type.</span></span>  
  
 <span data-ttu-id="9438e-122">![탐색 속성이 있는 모델](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")</span><span class="sxs-lookup"><span data-stu-id="9438e-122">![Model with Navigation Properties](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")</span></span>  
  
 <span data-ttu-id="9438e-123">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9438e-123">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="9438e-124">다음 CSDL에서는 위의 다이어그램에 표시된 `Book` 엔터티 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9438e-124">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="9438e-125">XML 특성을 사용하여 탐색 속성을 정의하는 데 필요한 정보를 전달합니다. `Name` 특성에는 속성 이름이 포함되고, `Relationship` 특성에는 탐색하는 연결 이름이 포함되고, `FromRole` 및 `ToRole` 특성에는 연결 End가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9438e-125">Note that XML attributes are used to communicate the information necessary to define a navigation property: The attribute `Name` contains the name of the property, `Relationship` contains the name of the association it navigates, and `FromRole` and `ToRole` contain the ends of the association.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9438e-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9438e-126">See Also</span></span>  
 [<span data-ttu-id="9438e-127">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="9438e-127">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="9438e-128">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="9438e-128">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
