---
title: "모델 선언 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e47c89524bf149d862ae872c0c5956b7debd818
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="model-declared-function"></a><span data-ttu-id="dc371-102">모델 선언 함수</span><span class="sxs-lookup"><span data-stu-id="dc371-102">model-declared function</span></span>
<span data-ttu-id="dc371-103">A *모델 선언 함수* 개념적 모델에서 선언 되었지만 해당 개념적 모델에 정의 되지 않은 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="dc371-103">A *model-declared function* is a function that is declared in a conceptual model, but is not defined in that conceptual model.</span></span> <span data-ttu-id="dc371-104">호스팅 또는 저장소 환경에서 함수를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc371-104">The function might be defined in the hosting or storage environment.</span></span> <span data-ttu-id="dc371-105">예를 들어, 모델 선언 함수를 데이터베이스에 정의된 함수에 매핑하여 개념적 모델에 서버 쪽 기능을 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc371-105">For example, a model-declared function might be mapped to a function that is defined in a database, thus exposing server-side functionality in the conceptual model.</span></span>  
  
 <span data-ttu-id="dc371-106">모델 선언 함수의 선언에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc371-106">The declaration of a model-declared function contains the following information:</span></span>  
  
-   <span data-ttu-id="dc371-107">함수의 이름.</span><span class="sxs-lookup"><span data-stu-id="dc371-107">The name of the function.</span></span> <span data-ttu-id="dc371-108">(필수)</span><span class="sxs-lookup"><span data-stu-id="dc371-108">(Required)</span></span>  
  
-   <span data-ttu-id="dc371-109">반환 값의 형식</span><span class="sxs-lookup"><span data-stu-id="dc371-109">The type of the return value.</span></span> <span data-ttu-id="dc371-110">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dc371-110">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dc371-111">반환 값을 지정하지 않으면 반환 형식은 void입니다.</span><span class="sxs-lookup"><span data-stu-id="dc371-111">If no return value is specified, the return type is void.</span></span>  
  
-   <span data-ttu-id="dc371-112">매개 변수 이름과 형식을 포함하는 매개 변수 정보</span><span class="sxs-lookup"><span data-stu-id="dc371-112">Parameter information, including parameter name and type.</span></span> <span data-ttu-id="dc371-113">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dc371-113">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc371-114">예제</span><span class="sxs-lookup"><span data-stu-id="dc371-114">Example</span></span>  
 <span data-ttu-id="dc371-115">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc371-115">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="dc371-116">CSDL에서 모델 선언 함수의 구현 하는 하나는 한 [함수 가져오기](http://msdn.microsoft.com/en-us/125704ae-56c7-4233-80b7-389a10f3a65d)합니다.</span><span class="sxs-lookup"><span data-stu-id="dc371-116">In CSDL, one implementation of a model-declared function is a [function import](http://msdn.microsoft.com/en-us/125704ae-56c7-4233-80b7-389a10f3a65d).</span></span> <span data-ttu-id="dc371-117">다음 CSDL에서는 함수 가져오기 정의를 사용하여 엔터티 컨테이너를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dc371-117">The following CSDL defines an entity container with a function import definition.</span></span> <span data-ttu-id="dc371-118">반환 형식을 지정하지 않았으므로 함수의 반환 형식은 void입니다.</span><span class="sxs-lookup"><span data-stu-id="dc371-118">Note that the return type for the function is void since no return type is specified.</span></span>  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a><span data-ttu-id="dc371-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc371-119">See Also</span></span>  
 [<span data-ttu-id="dc371-120">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="dc371-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="dc371-121">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="dc371-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
