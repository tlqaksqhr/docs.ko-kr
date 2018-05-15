---
title: COLLECTION(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 2b13d373e6c54221249b17de4fa91347cbc0f9e6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="collection-entity-sql"></a><span data-ttu-id="0a057-102">COLLECTION(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0a057-102">COLLECTION (Entity SQL)</span></span>
<span data-ttu-id="0a057-103">COLLECTION 키워드는 인라인 함수의 정의에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a057-103">The COLLECTION keyword is only used in the definition of an inline function.</span></span> <span data-ttu-id="0a057-104">컬렉션 함수는 값 컬렉션에 대해 작업을 수행하고 스칼라 출력을 생성하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="0a057-104">Collection functions are functions that operate on a collection of values and produce a scalar output.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a057-105">구문</span><span class="sxs-lookup"><span data-stu-id="0a057-105">Syntax</span></span>  
  
```  
COLLECTION(type_definition)   
```  
  
## <a name="arguments"></a><span data-ttu-id="0a057-106">인수</span><span class="sxs-lookup"><span data-stu-id="0a057-106">Arguments</span></span>  
 `type_definition`  
 <span data-ttu-id="0a057-107">지원되는 형식, 행 또는 참조 컬렉션을 반환하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0a057-107">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a057-108">설명</span><span class="sxs-lookup"><span data-stu-id="0a057-108">Remarks</span></span>  
 <span data-ttu-id="0a057-109">COLLECTION 키워드에 대한 자세한 내용은 [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a057-109">For more information about the COLLECTION keyword, see [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a057-110">예제</span><span class="sxs-lookup"><span data-stu-id="0a057-110">Example</span></span>  
 <span data-ttu-id="0a057-111">다음 샘플에서는 COLLECTION 키워드를 사용하여 10진수 컬렉션을 인라인 쿼리 함수의 인수로 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a057-111">The following sample shows how to use the COLLECTION keyword to declare a collection of decimals as an argument for an inline query function.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a><span data-ttu-id="0a057-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a057-112">See Also</span></span>  
 [<span data-ttu-id="0a057-113">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="0a057-113">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
