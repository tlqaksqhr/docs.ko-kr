---
title: 프로젝션 작성
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: d8215a016face76b8a258d694a36657be327b5e0
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="formulate-projections"></a><span data-ttu-id="f8db3-102">프로젝션 작성</span><span class="sxs-lookup"><span data-stu-id="f8db3-102">Formulate Projections</span></span>
<span data-ttu-id="f8db3-103">다음 예제에 나온 방법을 `select` C# 문 및 `Select` 문이 Visual Basic에서는 쿼리 프로젝션 구성 하는 다른 기능도와 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8db3-103">The following examples show how the `select` statement in C# and `Select` statement in Visual Basic can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8db3-104">예제</span><span class="sxs-lookup"><span data-stu-id="f8db3-104">Example</span></span>  
 <span data-ttu-id="f8db3-105">다음 예제에서는 `Select` Visual Basic의 절 (`select` 절에 C#)에 대 한 연락처 이름의 시퀀스를 반환 `Customers`합니다.</span><span class="sxs-lookup"><span data-stu-id="f8db3-105">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="f8db3-106">예제</span><span class="sxs-lookup"><span data-stu-id="f8db3-106">Example</span></span>  
 <span data-ttu-id="f8db3-107">사용 하 여 다음 예제는 `Select` Visual Basic의 절 (`select` 절에 C#) 및 *익명 형식* 및 전화 번호에 대 한 연락처 이름의 시퀀스를 반환 하려면 `Customers`합니다.</span><span class="sxs-lookup"><span data-stu-id="f8db3-107">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="f8db3-108">예제</span><span class="sxs-lookup"><span data-stu-id="f8db3-108">Example</span></span>  
 <span data-ttu-id="f8db3-109">다음 예제에서는 `Select` Visual Basic의 절 (`select` 절에 C#) 및 *익명 형식* 이름의 시퀀스를 반환 하 고 직원에 대 한 전화 번호를 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8db3-109">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="f8db3-110">결과 시퀀스에서 `FirstName`과 `LastName` 필드는 단일 필드(`Name`)로 결합되고 `HomePhone` 필드는 `Phone`으로 이름이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8db3-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="f8db3-111">예제</span><span class="sxs-lookup"><span data-stu-id="f8db3-111">Example</span></span>  
 <span data-ttu-id="f8db3-112">다음 예제에서는 `Select` Visual Basic의 절 (`select` 절에 C#) 및 *익명 형식* 모든 시퀀스를 반환 `ProductID`s 및 라는 계산 된 값을 `HalfPrice`합니다.</span><span class="sxs-lookup"><span data-stu-id="f8db3-112">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="f8db3-113">이 값은 2로 나누어진 `UnitPrice`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8db3-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="f8db3-114">예제</span><span class="sxs-lookup"><span data-stu-id="f8db3-114">Example</span></span>  
 <span data-ttu-id="f8db3-115">다음 예제에서는 `Select` Visual Basic의 절 (`select` 절에 C#)와 *조건문* 제품 이름과 제품 사용 가능성의 시퀀스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8db3-115">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="f8db3-116">예제</span><span class="sxs-lookup"><span data-stu-id="f8db3-116">Example</span></span>  
 <span data-ttu-id="f8db3-117">다음 예제에서는 Visual Basic을 사용 하 여 `Select` 절 (`select` 절에 C#)와 *알려진 형식의* (이름)의 직원 이름의 시퀀스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8db3-117">The following example uses a Visual Basic `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="f8db3-118">예제</span><span class="sxs-lookup"><span data-stu-id="f8db3-118">Example</span></span>  
 <span data-ttu-id="f8db3-119">다음 예제에서는 `Select` 및 `Where` Visual basic에서 (`select` 및 `where` C#) 반환 하는 *필터링 된 시퀀스* 런던에 살고 있는 고객에 대 한 연락처 이름의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8db3-119">The following example uses `Select` and `Where` in Visual Basic (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="f8db3-120">예제</span><span class="sxs-lookup"><span data-stu-id="f8db3-120">Example</span></span>  
 <span data-ttu-id="f8db3-121">사용 하 여 다음 예제는 `Select` Visual Basic의 절 (`select` 절에 C#) 및 *익명 형식* 반환 하는 *생성 된 하위 집합* 고객에 대 한 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="f8db3-121">The following example uses a `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="f8db3-122">예제</span><span class="sxs-lookup"><span data-stu-id="f8db3-122">Example</span></span>  
 <span data-ttu-id="f8db3-123">다음 예제에서는 중첩된 쿼리를 사용하여 다음 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f8db3-123">The following example uses nested queries to return the following results:</span></span>  
  
-   <span data-ttu-id="f8db3-124">모든 주문의 시퀀스와 해당 `OrderID`입니다.</span><span class="sxs-lookup"><span data-stu-id="f8db3-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
-   <span data-ttu-id="f8db3-125">할인이 있는 주문 항목에 대한 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="f8db3-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
-   <span data-ttu-id="f8db3-126">운송 비용이 포함되지 않은 총 금액입니다.</span><span class="sxs-lookup"><span data-stu-id="f8db3-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="f8db3-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8db3-127">See Also</span></span>  
 [<span data-ttu-id="f8db3-128">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="f8db3-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
