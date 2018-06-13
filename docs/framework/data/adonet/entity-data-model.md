---
title: 엔터티 데이터 모델
ms.date: 03/30/2017
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
ms.openlocfilehash: bb3c529a19ca96ea5695061fb1b612f9179899be
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765245"
---
# <a name="entity-data-model"></a><span data-ttu-id="4e476-102">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="4e476-102">Entity Data Model</span></span>
<span data-ttu-id="4e476-103">EDM(엔터티 데이터 모델)은 저장된 폼에 관계없이 데이터 구조를 설명하는 개념 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-103">The Entity Data Model (EDM) is a set of concepts that describe the structure of data, regardless of its stored form.</span></span> <span data-ttu-id="4e476-104">EDM은 Peter Chen이 1976년에 설명한 엔터티-관계 모델에서 차용하지만 엔터티-관계 모델을 기반으로 하여 기존의 사용을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-104">The EDM borrows from the Entity-Relationship Model described by Peter Chen in 1976, but it also builds on the Entity-Relationship Model and extends its traditional uses.</span></span>  
  
 <span data-ttu-id="4e476-105">EDM은 데이터가 여러 폼에 저장되어 있을 경우 발생하는 문제를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-105">The EDM addresses the challenges that arise from having data stored in many forms.</span></span> <span data-ttu-id="4e476-106">예를 들어, 관계형 데이터베이스, 텍스트 파일, XML 파일, 스프레드시트 및 보고서에 데이터를 저장하는 비즈니스를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="4e476-106">For example, consider a business that stores data in relational databases, text files, XML files, spreadsheets, and reports.</span></span> <span data-ttu-id="4e476-107">이 경우 데이터 모델링, 응용 프로그램 디자인 및 데이터 액세스가 상당히 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-107">This presents significant challenges in data modeling, application design, and data access.</span></span> <span data-ttu-id="4e476-108">데이터 지향 응용 프로그램을 디자인하는 경우 효율적인 데이터 액세스, 저장 및 확장성의 손실 없이 효율적이고 유지 관리 가능한 코드를 작성하는 것이 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-108">When designing a data-oriented application, the challenge is to write efficient and maintainable code without sacrificing efficient data access, storage, and scalability.</span></span> <span data-ttu-id="4e476-109">데이터가 관계형 구조이면 데이터 액세스, 저장 및 확장성이 매우 효율적이지만 효율적이고 유지 관리 가능한 코드를 작성하기가 더 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-109">When data has a relational structure, data access, storage, and scalability are very efficient, but writing efficient and maintainable code becomes more difficult.</span></span> <span data-ttu-id="4e476-110">데이터가 개체 구조이면 이러한 상쇄는 반대가 됩니다. 효율적인 데이터 액세스, 저장 및 확장성이 저하되면 효율적이고 유지 관리 가능한 코드를 작성하기가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-110">When data has an object structure, the trade-offs are reversed: Writing efficient and maintainable code comes at the cost of efficient data access, storage, and scalability.</span></span> <span data-ttu-id="4e476-111">이러한 상쇄 간에 적절한 균형을 찾을 수 있다고 해도 한 폼에서 다른 폼으로 데이터를 이동하는 경우 새로운 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-111">Even if the right balance between these trade-offs can be found, new challenges arise when data is moved from one form to another.</span></span> <span data-ttu-id="4e476-112">엔터티 데이터 모델은 저장소 스키마에 독립적인 엔터티 및 관계를 기준으로 데이터 구조를 설명하여 이러한 문제를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-112">The Entity Data Model addresses these challenges by describing the structure of data in terms of entities and relationships that are independent of any storage schema.</span></span> <span data-ttu-id="4e476-113">이렇게 하면 저장된 데이터 폼이 응용 프로그램 디자인 및 개발과 관련이 없어집니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-113">This makes the stored form of data irrelevant to application design and development.</span></span> <span data-ttu-id="4e476-114">그리고 저장된 폼이 아니라 엔터티와 관계가 응용 프로그램에서 사용되는 데이터 구조를 설명하기 때문에 응용 프로그램 개발에 따라 엔터티와 관계도 개발될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-114">And, because entities and relationships describe the structure of data as it is used in an application (not its stored form), they can evolve as an application evolves.</span></span>  
  
 <span data-ttu-id="4e476-115">`conceptual model`은 엔터티 및 관계로서의 특정 데이터 구조 표현이며, 일반적으로 EDM의 개념을 구현하는 DSL(Domain-Specific Language)에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-115">A `conceptual model` is a specific representation of the structure of data as entities and relationships, and is generally defined in a domain-specific language (DSL) that implements the concepts of the EDM.</span></span> <span data-ttu-id="4e476-116">[개념 스키마 정의 언어 (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) 은 이러한 도메인 특정 언어의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-116">[Conceptual schema definition language (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) is an example of such a domain-specific language.</span></span> <span data-ttu-id="4e476-117">개념적 모델에서 설명되는 엔터티와 관계를 응용 프로그램의 개체 및 연결 추상화로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-117">Entities and relationships described in a conceptual model can be thought of as abstractions of objects and associations in an application.</span></span> <span data-ttu-id="4e476-118">이렇게 하면 개발자가 저장소 스키마에 대해 염려하지 않고 개념적 모델에 집중할 수 있으며 효율성과 유지 관리 기능을 고려하여 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-118">This allows developers to focus on the conceptual model without concern for the storage schema, and allows them to write code with efficiency and maintainability in mind.</span></span> <span data-ttu-id="4e476-119">한편, 저장소 스키마 디자이너는 효율적인 데이터 액세스, 저장 및 확장성에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-119">Meanwhile storage schema designers can focus on the efficiency of data access, storage, and scalability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4e476-120">단원 내용</span><span class="sxs-lookup"><span data-stu-id="4e476-120">In This Section</span></span>  
 <span data-ttu-id="4e476-121">이 단원의 항목에서는 엔터티 데이터 모델의 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-121">Topics in this section describe the concepts of the Entity Data Model.</span></span> <span data-ttu-id="4e476-122">EDM을 구현하는 모든 DSL에는 여기에 설명된 개념이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-122">Any DSL that implements the EDM should include the concepts described here.</span></span> <span data-ttu-id="4e476-123">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) CSDL을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-123">Note that the [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses CSDL to define conceptual models.</span></span> <span data-ttu-id="4e476-124">자세한 내용은 참조 [CSDL 사양](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e476-124">For more information, see [CSDL Specification](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span></span>  
  
 [<span data-ttu-id="4e476-125">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="4e476-125">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
  
 [<span data-ttu-id="4e476-126">엔터티 데이터 모델: 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="4e476-126">Entity Data Model: Namespaces</span></span>](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)  
  
 [<span data-ttu-id="4e476-127">엔터티 데이터 모델: 기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e476-127">Entity Data Model: Primitive Data Types</span></span>](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)  
  
 [<span data-ttu-id="4e476-128">엔터티 데이터 모델: 상속</span><span class="sxs-lookup"><span data-stu-id="4e476-128">Entity Data Model: Inheritance</span></span>](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)  
  
 [<span data-ttu-id="4e476-129">연결 끝</span><span class="sxs-lookup"><span data-stu-id="4e476-129">association end</span></span>](../../../../docs/framework/data/adonet/association-end.md)  
  
 [<span data-ttu-id="4e476-130">연결 끝 다중성</span><span class="sxs-lookup"><span data-stu-id="4e476-130">association end multiplicity</span></span>](../../../../docs/framework/data/adonet/association-end-multiplicity.md)  
  
 [<span data-ttu-id="4e476-131">연결 집합</span><span class="sxs-lookup"><span data-stu-id="4e476-131">association set</span></span>](../../../../docs/framework/data/adonet/association-set.md)  
  
 [<span data-ttu-id="4e476-132">연결 집합 끝</span><span class="sxs-lookup"><span data-stu-id="4e476-132">association set end</span></span>](../../../../docs/framework/data/adonet/association-set-end.md)  
  
 [<span data-ttu-id="4e476-133">연결 형식</span><span class="sxs-lookup"><span data-stu-id="4e476-133">association type</span></span>](../../../../docs/framework/data/adonet/association-type.md)  
  
 [<span data-ttu-id="4e476-134">복합 형식</span><span class="sxs-lookup"><span data-stu-id="4e476-134">complex type</span></span>](../../../../docs/framework/data/adonet/complex-type.md)  
  
 [<span data-ttu-id="4e476-135">엔터티 컨테이너</span><span class="sxs-lookup"><span data-stu-id="4e476-135">entity container</span></span>](../../../../docs/framework/data/adonet/entity-container.md)  
  
 [<span data-ttu-id="4e476-136">엔터티 키</span><span class="sxs-lookup"><span data-stu-id="4e476-136">entity key</span></span>](../../../../docs/framework/data/adonet/entity-key.md)  
  
 [<span data-ttu-id="4e476-137">엔터티 집합</span><span class="sxs-lookup"><span data-stu-id="4e476-137">entity set</span></span>](../../../../docs/framework/data/adonet/entity-set.md)  
  
 [<span data-ttu-id="4e476-138">엔터티 형식</span><span class="sxs-lookup"><span data-stu-id="4e476-138">entity type</span></span>](../../../../docs/framework/data/adonet/entity-type.md)  
  
 [<span data-ttu-id="4e476-139">facet</span><span class="sxs-lookup"><span data-stu-id="4e476-139">facet</span></span>](../../../../docs/framework/data/adonet/facet.md)  
  
 [<span data-ttu-id="4e476-140">외래 키 속성</span><span class="sxs-lookup"><span data-stu-id="4e476-140">foreign key property</span></span>](../../../../docs/framework/data/adonet/foreign-key-property.md)  
  
 [<span data-ttu-id="4e476-141">모델 선언 함수</span><span class="sxs-lookup"><span data-stu-id="4e476-141">model-declared function</span></span>](../../../../docs/framework/data/adonet/model-declared-function.md)  
  
 [<span data-ttu-id="4e476-142">모델 정의 함수</span><span class="sxs-lookup"><span data-stu-id="4e476-142">model-defined function</span></span>](../../../../docs/framework/data/adonet/model-defined-function.md)  
  
 [<span data-ttu-id="4e476-143">탐색 속성</span><span class="sxs-lookup"><span data-stu-id="4e476-143">navigation property</span></span>](../../../../docs/framework/data/adonet/navigation-property.md)  
  
 [<span data-ttu-id="4e476-144">속성</span><span class="sxs-lookup"><span data-stu-id="4e476-144">property</span></span>](../../../../docs/framework/data/adonet/property.md)  
  
 [<span data-ttu-id="4e476-145">참조 무결성 제약 조건</span><span class="sxs-lookup"><span data-stu-id="4e476-145">referential integrity constraint</span></span>](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)  
  
## <a name="see-also"></a><span data-ttu-id="4e476-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e476-146">See Also</span></span>  
 [<span data-ttu-id="4e476-147">ADO.NET 엔터티 데이터 모델 도구</span><span class="sxs-lookup"><span data-stu-id="4e476-147">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="4e476-148">.edmx 파일 개요</span><span class="sxs-lookup"><span data-stu-id="4e476-148">.edmx File Overview</span></span>](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="4e476-149">CSDL 사양</span><span class="sxs-lookup"><span data-stu-id="4e476-149">CSDL Specification</span></span>](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)
