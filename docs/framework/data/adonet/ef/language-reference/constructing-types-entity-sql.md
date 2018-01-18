---
title: "형식 생성(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41fa7bde-8d20-4a3f-a3d2-fb791e128010
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8a6ae2334c879733e964014716c2b67e77f271d5
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="constructing-types-entity-sql"></a><span data-ttu-id="81e72-102">형식 생성(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="81e72-102">Constructing Types (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="81e72-103">세 가지 종류의 생성자를 제공: 행 생성자, 명명 된 형식 생성자 및 컬렉션 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-103"> provides three kinds of constructors: row constructors, named type constructors, and collection constructors.</span></span>  
  
## <a name="row-constructors"></a><span data-ttu-id="81e72-104">행 생성자</span><span class="sxs-lookup"><span data-stu-id="81e72-104">Row Constructors</span></span>  
 <span data-ttu-id="81e72-105">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]의 행 생성자를 사용하여 값 하나 이상을 기반으로 구조적으로 형식화된 익명 레코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-105">You use row constructors in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to construct anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="81e72-106">행 생성자의 결과 형식은 필드 형식이 행 생성에 사용된 값의 형식과 동일한 행 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-106">The result type of a row constructor is a row type whose field types correspond to the types of the values used to construct the row.</span></span> <span data-ttu-id="81e72-107">예를 들어 다음 식은 `Record(a int, b string, c int)` 형식의 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-107">For example, the following expression constructs a value of type `Record(a int, b string, c int)`:</span></span>  
  
 `ROW(1 AS a, "abc" AS b, a + 34 AS c)`  
  
 <span data-ttu-id="81e72-108">행 생성자에서 식의 별칭을 제공하지 않으면 Entity Framework에서 별칭을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-108">If you do not provide an alias for an expression in a row constructor, the Entity Framework will try to generate one.</span></span> <span data-ttu-id="81e72-109">자세한 내용은의 "별칭 지정 규칙" 섹션을 참조 하십시오. [식별자](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-109">For more information, see the "Aliasing Rules" section in [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="81e72-110">행 생성자에서 식에 별칭을 지정하는 데 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-110">The following rules apply to expression aliasing in a row constructor:</span></span>  
  
-   <span data-ttu-id="81e72-111">행 생성자의 식은 동일한 생성자 내의 다른 별칭을 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-111">Expressions in a row constructor cannot refer to other aliases in the same constructor.</span></span>  
  
-   <span data-ttu-id="81e72-112">동일한 행 생성자 내의 서로 다른 두 식은 별칭이 같을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-112">Two expressions in the same row constructor cannot have the same alias.</span></span>  
  
 <span data-ttu-id="81e72-113">행 생성자에 대 한 자세한 내용은 참조 [행](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-113">For more information about row constructors, see [ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).</span></span>  
  
## <a name="collection-constructors"></a><span data-ttu-id="81e72-114">컬렉션 생성자</span><span class="sxs-lookup"><span data-stu-id="81e72-114">Collection Constructors</span></span>  
 <span data-ttu-id="81e72-115">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]의 컬렉션 생성자를 사용하여 값 목록에서 multiset 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-115">You use collection constructors in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to create an instance of a multiset from a list of values.</span></span> <span data-ttu-id="81e72-116">생성자의 모든 값은 상호 호환되는 `T` 형식이어야 하며, 생성자는 `Multiset<T>` 형식의 컬렉션을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-116">All the values in the constructor must be of mutually compatible type `T`, and the constructor produces a collection of type `Multiset<T>`.</span></span> <span data-ttu-id="81e72-117">예를 들어, 다음 식은 정수 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-117">For example, the following expression creates a collection of integers:</span></span>  
  
 `Multiset(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
 <span data-ttu-id="81e72-118">빈 multiset 생성자는 요소 형식을 확인할 수 없으므로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-118">Empty multiset constructors are not allowed because the type of the elements cannot be determined.</span></span> <span data-ttu-id="81e72-119">다음은 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-119">The following is not valid:</span></span>  
  
 `multiset() {}`  
  
 <span data-ttu-id="81e72-120">자세한 내용은 참조 [MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-120">For more information, see [MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md).</span></span>  
  
## <a name="named-type-constructors-namedtype-initializers"></a><span data-ttu-id="81e72-121">명명된 형식 생성자(NamedType 이니셜라이저)</span><span class="sxs-lookup"><span data-stu-id="81e72-121">Named Type Constructors (NamedType Initializers)</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="81e72-122">에서 형식 생성자(이니셜라이저)는 명명된 복합 형식과 엔터티 형식 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-122"> allows type constructors (initializers) to create instances of named complex types and entity types.</span></span> <span data-ttu-id="81e72-123">예를 들어, 다음 식은 `Person` 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-123">For example, the following expression creates an instance of a `Person` type.</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="81e72-124">다음 식은 복합 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-124">The following expression creates an instance of a complex type.</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="81e72-125">다음 식은 중첩된 복합 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-125">The following expression creates an instance of a nested complex type.</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="81e72-126">다음 식은 중첩된 복합 형식을 가진 엔터티의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-126">The following expression creates an instance of an entity with a nested complex type.</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="81e72-127">다음 예제에서는 복합 형식의 속성을 null로 초기화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-127">The following example shows how to initialize a property of a complex type to null.</span></span> `MyModel.ZipCode(‘98118’, null)`  
  
 <span data-ttu-id="81e72-128">생성자의 인수는 형식의 특성 선언과 동일한 순서인 것으로 가정됩니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-128">The arguments to the constructor are assumed to be in the same order as the declaration of the attributes of the type.</span></span>  
  
 <span data-ttu-id="81e72-129">자세한 내용은 참조 [명명 된 형식 생성자](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="81e72-129">For more information, see [Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e72-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81e72-130">See Also</span></span>  
 [<span data-ttu-id="81e72-131">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="81e72-131">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="81e72-132">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="81e72-132">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="81e72-133">형식 시스템</span><span class="sxs-lookup"><span data-stu-id="81e72-133">Type System</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)
