---
title: "복합 형식"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6a7fbdace6403d2f1037beff8fe28d7c934d3174
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="complex-type"></a><span data-ttu-id="8ea14-102">복합 형식</span><span class="sxs-lookup"><span data-stu-id="8ea14-102">complex type</span></span>
<span data-ttu-id="8ea14-103">A *복합 형식* 는 다양 한 구조적된 속성을 정의 하기 위한 서식 파일 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 또는 다른 복합 형식의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea14-103">A *complex type* is a template for defining rich, structured properties on [entity types](../../../../docs/framework/data/adonet/entity-type.md) or on other complex types.</span></span> <span data-ttu-id="8ea14-104">각 템플릿에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea14-104">Each template contains the following:</span></span>  
  
-   <span data-ttu-id="8ea14-105">고유한 이름</span><span class="sxs-lookup"><span data-stu-id="8ea14-105">A unique name.</span></span> <span data-ttu-id="8ea14-106">(필수)</span><span class="sxs-lookup"><span data-stu-id="8ea14-106">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8ea14-107">복합 형식의 이름은 동일한 네임스페이스 내의 엔터티 형식 이름과 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea14-107">The name of a complex type cannot be the same as an entity type name within the same namespace.</span></span>  
  
-   <span data-ttu-id="8ea14-108">하나 이상의 형식으로 데이터를에서 [속성](../../../../docs/framework/data/adonet/property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea14-108">Data in the form of one or more [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="8ea14-109">(선택적 요소)</span><span class="sxs-lookup"><span data-stu-id="8ea14-109">(Optional.)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8ea14-110">복합 형식의 속성은 다른 복합 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea14-110">A property of a complex type can be another complex type.</span></span>  
  
 <span data-ttu-id="8ea14-111">복합 형식은 기본 형식 속성이나 다른 복합 형식의 형태로 데이터 페이로드를 전달할 수 있다는 점에서 엔터티 형식과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea14-111">A complex type is similar to an entity type in that a complex type can carry a data payload in the form of primitive type properties or other complex types.</span></span> <span data-ttu-id="8ea14-112">그러나 복합 형식과 엔터티 형식 사이에는 약간의 중요한 차이점이 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea14-112">However, there are some key differences between complex types and entity types:</span></span>  
  
-   <span data-ttu-id="8ea14-113">복합 형식은 식별자를 포함하지 않으므로 독립적으로 존재할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea14-113">Complex types do not have identities and therefore cannot exist independently.</span></span> <span data-ttu-id="8ea14-114">복합 형식은 엔터티 형식 또는 다른 복합 형식의 속성으로만 존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea14-114">Complex types can only exist as properties on entity types or other complex types.</span></span>  
  
-   <span data-ttu-id="8ea14-115">복합 형식에 참여할 수 없는 [연결](../../../../docs/framework/data/adonet/association-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea14-115">Complex types cannot participate in [associations](../../../../docs/framework/data/adonet/association-type.md).</span></span> <span data-ttu-id="8ea14-116">연결의 어느 end도 복합 형식을 수 있으므로 [탐색 속성](../../../../docs/framework/data/adonet/navigation-property.md) 복합 형식에 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea14-116">Neither end of an association can be a complex type, and therefore [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) cannot be defined on complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ea14-117">예</span><span class="sxs-lookup"><span data-stu-id="8ea14-117">Example</span></span>  
 <span data-ttu-id="8ea14-118">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea14-118">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="8ea14-119">다음 CSDL에서는 기본 형식 속성 `StreetAddress`, `City`, `StateOrProvince`, `Country` 및 `PostalCode`가 있는 복합 형식 Address를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea14-119">The following CSDL defines a complex type, Address, with the primitive type properties `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 <span data-ttu-id="8ea14-120">위의 `Address` 복합 형식을 엔터티 형식의 속성으로 정의하려면 엔터티 형식 정의에서 속성 형식을 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea14-120">To define the complex type `Address` (above) as a property on an entity type, you must declare the property type in the entity type definition.</span></span> <span data-ttu-id="8ea14-121">다음 CSDL에서는 `Address` 속성을 엔터티 형식(Publisher)의 복합 형식으로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea14-121">The following CSDL declares the `Address` property as a complex type on an entity type (Publisher):</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a><span data-ttu-id="8ea14-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ea14-122">See Also</span></span>  
 [<span data-ttu-id="8ea14-123">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="8ea14-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="8ea14-124">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="8ea14-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
