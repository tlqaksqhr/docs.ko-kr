---
title: "패싯"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91c4e6aa-3e54-4b6c-a38a-abf27808cc85
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3dde7c08fcbdd6c69ecfd987244cb71465ce807f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="facet"></a><span data-ttu-id="74352-102">패싯</span><span class="sxs-lookup"><span data-stu-id="74352-102">facet</span></span>
<span data-ttu-id="74352-103">A *패싯* 세부 정보는 기본 형식 속성 정의를 추가 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74352-103">A *facet* is used to add detail to a primitive type property definition.</span></span> <span data-ttu-id="74352-104">A [속성](../../../../docs/framework/data/adonet/property.md) 정의 속성 형식에 대 한 정보를 포함 하지만 자주 자세히는 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="74352-104">A [property](../../../../docs/framework/data/adonet/property.md) definition contains information about the property type, but often more detail is necessary.</span></span> <span data-ttu-id="74352-105">예를 들어, 개념적 모델의 엔터티 형식에는 값을 null로 설정할 수 없는 `String` 형식의 속성이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74352-105">For example, an entity type in a conceptual model might have a property of type `String` whose value cannot be set to null.</span></span> <span data-ttu-id="74352-106">패싯을 사용하면 이 수준의 세부 정보를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74352-106">Facets allow you to specify this level of detail.</span></span>  
  
 <span data-ttu-id="74352-107">다음 표에서는 EDM에서 지원되는 패싯에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="74352-107">The table below describes the facets that are supported in the EDM.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74352-108">패싯의 정확한 값과 동작은 EDM 구현을 사용하는 런타임 환경에서 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="74352-108">The exact values and behaviors of facets are determined by the run-time environment that uses an EDM implementation.</span></span>  
  
|<span data-ttu-id="74352-109">패싯</span><span class="sxs-lookup"><span data-stu-id="74352-109">Facet</span></span>|<span data-ttu-id="74352-110">설명</span><span class="sxs-lookup"><span data-stu-id="74352-110">Description</span></span>|<span data-ttu-id="74352-111">적용 대상</span><span class="sxs-lookup"><span data-stu-id="74352-111">Applies to</span></span>|  
|-----------|-----------------|----------------|  
|`Collation`|<span data-ttu-id="74352-112">속성 값에 대한 비교 및 순서 지정 작업을 수행할 때 사용할 데이터 정렬 순서 또는 정렬 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74352-112">Specifies the collating sequence (or sorting sequence) to be used when performing comparison and ordering operations on values of the property.</span></span>|`String`|  
|`ConcurrencyMode`|<span data-ttu-id="74352-113">속성 값을 낙관적 동시성 검사에 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74352-113">Indicates that the value of the property should be used for optimistic concurrency checks.</span></span>|<span data-ttu-id="74352-114">모든 기본 형식 속성</span><span class="sxs-lookup"><span data-stu-id="74352-114">All primitive type properties</span></span>|  
|`Default`|<span data-ttu-id="74352-115">인스턴스화 시 값이 제공되지 않는 경우 속성의 기본값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74352-115">Specifies the default value of the property if no value is supplied upon instantiation.</span></span>|<span data-ttu-id="74352-116">모든 기본 형식 속성</span><span class="sxs-lookup"><span data-stu-id="74352-116">All primitive type properties</span></span>|  
|`FixedLength`|<span data-ttu-id="74352-117">속성 값 길이가 다양할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74352-117">Specifies whether the length of the property value can vary.</span></span>|<span data-ttu-id="74352-118">`Binary`, `String`</span><span class="sxs-lookup"><span data-stu-id="74352-118">`Binary`, `String`</span></span>|  
|`MaxLength`|<span data-ttu-id="74352-119">속성 값의 최대 길이를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74352-119">Specifies the maximum length of the property value.</span></span>|<span data-ttu-id="74352-120">`Binary`, `String`</span><span class="sxs-lookup"><span data-stu-id="74352-120">`Binary`, `String`</span></span>|  
|`Nullable`|<span data-ttu-id="74352-121">속성 값이 null일 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74352-121">Specifies whether the property can have a null value.</span></span>|<span data-ttu-id="74352-122">모든 기본 형식 속성</span><span class="sxs-lookup"><span data-stu-id="74352-122">All primitive type properties</span></span>|  
|`Precision`|<span data-ttu-id="74352-123">형식이 `Decimal`인 속성의 경우 속성 값에 포함할 수 있는 자릿수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74352-123">For properties of type `Decimal`, specifies the number of digits a property value can have.</span></span> <span data-ttu-id="74352-124">형식이 `Time`, `DateTime` 및 `DateTimeOffset`인 속성의 경우 속성 값에 대한 초의 소수 부분 자릿수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74352-124">For properties of type `Time`, `DateTime`, and `DateTimeOffset`, specifies the number of digits for the fractional part of seconds of the property value.</span></span>|<span data-ttu-id="74352-125">`DateTime`, `DateTimeOffset`, `Decimal`, `Time`,</span><span class="sxs-lookup"><span data-stu-id="74352-125">`DateTime`, `DateTimeOffset`, `Decimal`, `Time`,</span></span>|  
|`Scale`|<span data-ttu-id="74352-126">속성 값에 대한 소수점 오른쪽의 자릿수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74352-126">Specifies the number of digits to the right of the decimal point for the property value.</span></span>|<span data-ttu-id="74352-127">Decimal</span><span class="sxs-lookup"><span data-stu-id="74352-127">Decimal</span></span>|  
|`Unicode`|<span data-ttu-id="74352-128">속성 값을 유니코드로 저장할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="74352-128">Indicates whether the property value is stored as Unicode.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="74352-129">예</span><span class="sxs-lookup"><span data-stu-id="74352-129">Example</span></span>  
 <span data-ttu-id="74352-130">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="74352-130">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="74352-131">다음 CSDL에서는 `Book` 엔터티 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="74352-131">The following CSDL defines a `Book` entity type.</span></span> <span data-ttu-id="74352-132">패싯은 XML 특성으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="74352-132">Note that facets are implemented as XML attributes.</span></span> <span data-ttu-id="74352-133">패싯 값은 속성을 null로 설정할 수 없으며 `Scale` 속성의 `Precision` 및 `Revision`이 각각 29로 설정됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="74352-133">The facet values indicate that no property can be set to null, and that the `Scale` and `Precision` of the `Revision` property are each set to 29.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="74352-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74352-134">See Also</span></span>  
 [<span data-ttu-id="74352-135">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="74352-135">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="74352-136">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="74352-136">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
