---
title: "개체 ID"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c788f2f9-65cc-4455-9907-e8388a268e00
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 97c07ce351de5b7939bdcaf441bc46dac50a8c23
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="object-identity"></a><span data-ttu-id="dc9c7-102">개체 ID</span><span class="sxs-lookup"><span data-stu-id="dc9c7-102">Object Identity</span></span>
<span data-ttu-id="dc9c7-103">런타임의 개체는 고유한 ID를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-103">Objects in the runtime have unique identities.</span></span> <span data-ttu-id="dc9c7-104">동일한 개체를 참조하는 두 개의 변수는 실제로 해당 개체의 동일한 인스턴스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-104">Two variables that refer to the same object actually refer to the same instance of the object.</span></span> <span data-ttu-id="dc9c7-105">따라서 하나의 변수를 통해 수행한 변경 내용을 다른 변수를 통해 즉시 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-105">Because of this fact, changes that you make by way of a path through one variable are immediately visible through the other.</span></span>  
  
 <span data-ttu-id="dc9c7-106">관계형 데이터베이스 테이블의 행에는 고유한 ID가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-106">Rows in a relational database table do not have unique identities.</span></span> <span data-ttu-id="dc9c7-107">각 행에 고유한 기본 키가 있으므로 두 개 행이 동일한 키 값을 공유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-107">Because each row has a unique primary key, no two rows share the same key value.</span></span> <span data-ttu-id="dc9c7-108">그러나 데이터베이스 테이블의 콘텐츠에만 이 제한이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-108">However, this fact constrains only the contents of the database table.</span></span>  
  
 <span data-ttu-id="dc9c7-109">실제로는 응용 프로그램이 데이터를 사용하는 다른 계층으로 데이터베이스의 데이터를 가져오는 경우가 가장 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-109">In reality, data is most often brought out of the database and into a different tier, where an application works with it.</span></span> <span data-ttu-id="dc9c7-110">이는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 지원하는 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-110">This is the model that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports.</span></span> <span data-ttu-id="dc9c7-111">데이터를 데이터베이스에서 행으로 가져올 때 동일한 데이터를 나타내는 두 개의 행이 실제로 동일한 행 인스턴스에 해당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-111">When data is brought out of the database as rows, you have no expectation that two rows that represent the same data actually correspond to the same row instances.</span></span> <span data-ttu-id="dc9c7-112">특정 고객을 두 번 쿼리할 경우 두 개의 데이터 행을 얻게 되며</span><span class="sxs-lookup"><span data-stu-id="dc9c7-112">If you query for a specific customer two times, you get two rows of data.</span></span> <span data-ttu-id="dc9c7-113">각 행은 동일한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-113">Each row contains the same information.</span></span>  
  
 <span data-ttu-id="dc9c7-114">개체의 경우 전혀 다른 결과가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-114">With objects you expect something very different.</span></span> <span data-ttu-id="dc9c7-115"><xref:System.Data.Linq.DataContext>에 동일한 정보를 반복해서 요청할 경우 실제로 동일한 개체 인스턴스가 제공될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-115">You expect that if you ask the <xref:System.Data.Linq.DataContext> for the same information repeatedly, it will in fact give you the same object instance.</span></span> <span data-ttu-id="dc9c7-116">개체가 응용 프로그램에 대해 특별한 의미를 가지며 동일한 개체로 작동할 것으로 예상되므로 이 동작이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-116">You expect this behavior because objects have special meaning for your application and you expect them to behave like objects.</span></span> <span data-ttu-id="dc9c7-117">개체를 계층 구조나 그래프로 디자인하고</span><span class="sxs-lookup"><span data-stu-id="dc9c7-117">You designed them as hierarchies or graphs.</span></span> <span data-ttu-id="dc9c7-118">동일한 항목을 여러 번 요청했으면 개체는 이와 같이 검색되고 중복된 많은 인스턴스가 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-118">You expect to retrieve them as such and not to receive multitudes of replicated instances just because you asked for the same thing more than one time.</span></span>  
  
 <span data-ttu-id="dc9c7-119">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 <xref:System.Data.Linq.DataContext>는 개체 ID를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-119">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Data.Linq.DataContext> manages object identity.</span></span> <span data-ttu-id="dc9c7-120">데이터베이스에서 새 행을 검색할 때마다 해당 기본 키별로 ID 테이블에 행이 기록되고 새 개체가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-120">Whenever you retrieve a new row from the database, the row is logged in an identity table by its primary key, and a new object is created.</span></span> <span data-ttu-id="dc9c7-121">동일한 해당 행을 검색할 때마다 원래 개체 인스턴스가 응용 프로그램에 다시 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-121">Whenever you retrieve that same row, the original object instance is handed back to the application.</span></span> <span data-ttu-id="dc9c7-122">이와 같은 방식으로 <xref:System.Data.Linq.DataContext>는 데이터베이스에 인식하는 ID의 개념(즉, 기본 키)을 언어에서 인식하는 ID의 개념(즉, 인스턴스)으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-122">In this manner the <xref:System.Data.Linq.DataContext> translates the concept of identity as seen by the database (that is, primary keys) into the concept of identity seen by the language (that is, instances).</span></span> <span data-ttu-id="dc9c7-123">응용 프로그램은 처음 검색된 상태로만 개체를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-123">The application only sees the object in the state that it was first retrieved.</span></span> <span data-ttu-id="dc9c7-124">새 데이터는 다를 경우 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-124">The new data, if different, is discarded.</span></span> <span data-ttu-id="dc9c7-125">자세한 내용은 참조 [Id 캐시에서 개체 검색](../../../../../../docs/framework/data/adonet/sql/linq/retrieving-objects-from-the-identity-cache.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-125">For more information, see [Retrieving Objects from the Identity Cache](../../../../../../docs/framework/data/adonet/sql/linq/retrieving-objects-from-the-identity-cache.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="dc9c7-126">은 낙관적 업데이트를 지원하기 위해 이 방법을 사용하여 로컬 개체의 무결성을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-126"> uses this approach to manage the integrity of local objects in order to support optimistic updates.</span></span> <span data-ttu-id="dc9c7-127">개체가 처음 만들어진 후에 발생한 변경만 응용 프로그램에 의해 수행된 변경이므로 응용 프로그램에서 의도하는 바를 분명히 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-127">Because the only changes that occur after the object is at first created are those made by the application, the intent of the application is clear.</span></span> <span data-ttu-id="dc9c7-128">도중에 외부로부터 변경이 발생한 경우에는 `SubmitChanges()`가 호출될 때 해당 변경 내용이 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-128">If changes by an outside party have occurred in the interim, they are identified at the time `SubmitChanges()` is called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc9c7-129">쿼리에 의해 요청된 개체를 이미 검색된 개체로 쉽게 식별할 수 있는 경우 쿼리가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-129">If the object requested by the query is easily identifiable as one already retrieved, no query is executed.</span></span> <span data-ttu-id="dc9c7-130">ID 테이블은 이전에 검색된 모든 개체의 캐시로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-130">The identity table acts as a cache of all previously retrieved objects.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="dc9c7-131">예제</span><span class="sxs-lookup"><span data-stu-id="dc9c7-131">Examples</span></span>  
  
### <a name="object-caching-example-1"></a><span data-ttu-id="dc9c7-132">개체 캐싱 예제 1</span><span class="sxs-lookup"><span data-stu-id="dc9c7-132">Object Caching Example 1</span></span>  
 <span data-ttu-id="dc9c7-133">이 예제에서는 동일한 쿼리를 두 번 실행할 경우 항상 메모리의 동일한 개체에 대한 참조가 수신됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-133">In this example, if you execute the same query two times, you receive a reference to the same object in memory every time.</span></span>  
  
 [!code-csharp[DLinqObjectIdentity#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectIdentity/cs/Program.cs#1)]
 [!code-vb[DLinqObjectIdentity#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectIdentity/vb/Module1.vb#1)]  
  
### <a name="object-caching-example-2"></a><span data-ttu-id="dc9c7-134">개체 캐싱 예제 2</span><span class="sxs-lookup"><span data-stu-id="dc9c7-134">Object Caching Example 2</span></span>  
 <span data-ttu-id="dc9c7-135">이 예제에서는 데이터베이스에서 동일한 행을 반환하는 다른 쿼리를 실행할 경우 항상 메모리의 동일한 개체에 대한 참조가 수신됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc9c7-135">In this example, if you execute different queries that return the same row from the database, you receive a reference to the same object in memory every time.</span></span>  
  
 [!code-csharp[DLinqObjectIdentity#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectIdentity/cs/Program.cs#2)]
 [!code-vb[DLinqObjectIdentity#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectIdentity/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="dc9c7-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc9c7-136">See Also</span></span>  
 [<span data-ttu-id="dc9c7-137">배경 정보</span><span class="sxs-lookup"><span data-stu-id="dc9c7-137">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
