---
title: "모델 정의 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 754a13d62a8a3eb238799b46ae2304b84077140e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="model-defined-function"></a><span data-ttu-id="aaada-102">모델 정의 함수</span><span class="sxs-lookup"><span data-stu-id="aaada-102">model-defined function</span></span>
<span data-ttu-id="aaada-103">A *모델 정의 함수* 는 개념적 모델에 정의 된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="aaada-103">A *model-defined function* is a function that is defined in a conceptual model.</span></span> <span data-ttu-id="aaada-104">모델 정의 함수의 본문을 단위로 [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), 규칙을 허용 하는 함수를 독립적으로 표현할 수에 대 한 또는 데이터 원본에서 지원 되는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="aaada-104">The body of a model-defined function is expressed in [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), which allows for the function to be expressed independently of rules or languages supported in the data source.</span></span>  
  
 <span data-ttu-id="aaada-105">모델 정의 함수 정의에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaada-105">A definition for a model-defined function contains the following information:</span></span>  
  
-   <span data-ttu-id="aaada-106">함수 이름</span><span class="sxs-lookup"><span data-stu-id="aaada-106">A function name.</span></span> <span data-ttu-id="aaada-107">(필수)</span><span class="sxs-lookup"><span data-stu-id="aaada-107">(Required)</span></span>  
  
-   <span data-ttu-id="aaada-108">반환 값의 형식</span><span class="sxs-lookup"><span data-stu-id="aaada-108">The type of the return value.</span></span> <span data-ttu-id="aaada-109">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aaada-109">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aaada-110">반환 형식을 지정하지 않으면 반환 값은 void입니다.</span><span class="sxs-lookup"><span data-stu-id="aaada-110">If no return type is specified, the return value is void.</span></span>  
  
-   <span data-ttu-id="aaada-111">매개 변수 정보</span><span class="sxs-lookup"><span data-stu-id="aaada-111">Parameter information.</span></span> <span data-ttu-id="aaada-112">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aaada-112">(Optional)</span></span>  
  
-   <span data-ttu-id="aaada-113">[Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) 함수 본문을 정의 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="aaada-113">An [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) expression that defines the body of the function.</span></span>  
  
 <span data-ttu-id="aaada-114">모델 정의 함수는 출력 매개 변수를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aaada-114">Note that model-defined functions do not support output parameters.</span></span> <span data-ttu-id="aaada-115">모델 정의 함수를 작성할 수 있도록 이러한 제한이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaada-115">This restriction is in place so that model-defined functions can be composed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaada-116">예제</span><span class="sxs-lookup"><span data-stu-id="aaada-116">Example</span></span>  
 <span data-ttu-id="aaada-117">다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aaada-117">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 <span data-ttu-id="aaada-118">![게시 된 날짜가 있는 모델](../../../../docs/framework/data/adonet/media/modelwithpublisheddate.gif "ModelWithPublishedDate")</span><span class="sxs-lookup"><span data-stu-id="aaada-118">![Model With Published Date](../../../../docs/framework/data/adonet/media/modelwithpublisheddate.gif "ModelWithPublishedDate")</span></span>  
  
 <span data-ttu-id="aaada-119">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaada-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="aaada-120">다음 CSDL에서는 위 다이어그램의 `Book` 인스턴스가 출판된 이후의 년 수를 반환하는 함수를 개념적 모델에 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="aaada-120">The following CSDL defines a function in the conceptual model that returns the numbers of years since an instance of a `Book` (in the diagram above) was published.</span></span>  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a><span data-ttu-id="aaada-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aaada-121">See Also</span></span>  
 [<span data-ttu-id="aaada-122">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="aaada-122">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="aaada-123">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="aaada-123">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [<span data-ttu-id="aaada-124">엔터티 데이터 모델: 기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="aaada-124">Entity Data Model: Primitive Data Types</span></span>](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
