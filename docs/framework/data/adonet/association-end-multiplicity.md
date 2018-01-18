---
title: "연결 End 복합성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 36f6d22a8fd3a3c0f1fd997d5101b9fdf8e91a8c
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="3a3b4-102">연결 End 복합성</span><span class="sxs-lookup"><span data-stu-id="3a3b4-102">association end multiplicity</span></span>
<span data-ttu-id="3a3b4-103">*연결 end 복합성* 수를 정의 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 의 한쪽 end에 있을 수 있는 인스턴스는 [연결](../../../../docs/framework/data/adonet/association-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a3b4-103">*Association end multiplicity* defines the number of [entity type](../../../../docs/framework/data/adonet/entity-type.md) instances that can be at one end of an [association](../../../../docs/framework/data/adonet/association-type.md).</span></span>  
  
 <span data-ttu-id="3a3b4-104">연결 End 복합성은 다음 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a3b4-104">An association end multiplicity can have one of the following values:</span></span>  
  
-   <span data-ttu-id="3a3b4-105">한 개(1): 연결 End에 엔터티 형식 인스턴스가 정확히 한 개 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3a3b4-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
-   <span data-ttu-id="3a3b4-106">0개 또는 한 개(0..1): 연결 End에 엔터티 형식 인스턴스가 0개 또는 한 개 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3a3b4-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
-   <span data-ttu-id="3a3b4-107">다수(\*): 연결 End에 엔터티 형식 인스턴스가 0개 또는 한 개 이상 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3a3b4-107">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="3a3b4-108">연결은 대체로 연결 End 복합성 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a3b4-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="3a3b4-109">예를 들어, 연결의 End 복합성이 한 개(1) 및 다수(\*)이면 해당 연결을 일대다 연결이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a3b4-109">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="3a3b4-110">다음 예에서 `PublishedBy` 연결은 일대다 연결입니다. 즉, 한 명의 발행자가 많은 책을 출판하고 책 하나는 한 명의 발행자에 의해 출판됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a3b4-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="3a3b4-111">`WrittenBy` 연결은 다대다 연결입니다. 한 권의 책에 저자가 여러 명일 수 있고 한 명의 저자가 여러 책을 쓸 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a3b4-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a3b4-112">예제</span><span class="sxs-lookup"><span data-stu-id="3a3b4-112">Example</span></span>  
 <span data-ttu-id="3a3b4-113">다음 다이어그램에서는 두 연결 `PublishedBy` 및 `WrittenBy`의 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a3b4-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="3a3b4-114">`PublishedBy` 연결의 연결 End는 `Book` 및 `Publisher` 엔터티 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3a3b4-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="3a3b4-115">`Publisher` 끝의 복합성은 한 개(1)이고 `Book` 끝의 복합성은 다수(\*)입니다.</span><span class="sxs-lookup"><span data-stu-id="3a3b4-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 <span data-ttu-id="3a3b4-116">![예제 모델](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="3a3b4-116">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="3a3b4-117">ADO.NET Entity Framework 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a3b4-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="3a3b4-118">다음 CSDL에서는 위의 다이어그램에 표시된 `PublishedBy` 연결을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3a3b4-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="3a3b4-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a3b4-119">See Also</span></span>  
 [<span data-ttu-id="3a3b4-120">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="3a3b4-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="3a3b4-121">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="3a3b4-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
