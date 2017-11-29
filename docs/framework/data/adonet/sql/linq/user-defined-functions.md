---
title: "사용자 정의 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ff13a123bcb2c61d786f2156e600a16cdd6bb31e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="user-defined-functions"></a><span data-ttu-id="ec52c-102">사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="ec52c-102">User-Defined Functions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="ec52c-103">에서는 개체 모델에 메서드를 사용하여 사용자 정의 함수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52c-103"> uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="ec52c-104">필요한 위치에 <xref:System.Data.Linq.Mapping.FunctionAttribute> 특성과 <xref:System.Data.Linq.Mapping.ParameterAttribute> 특성을 적용하여 메서드를 함수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52c-104">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="ec52c-105">자세한 내용은 참조 [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52c-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="ec52c-106"><xref:System.InvalidOperationException>을 방지하려면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 사용자 정의 함수는 다음 폼 중 하나에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52c-106">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
-   <span data-ttu-id="ec52c-107">올바른 매핑 특성이 있는 메서드 호출로 래핑된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="ec52c-107">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="ec52c-108">자세한 내용은 참조 [특성 기반 매핑](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52c-108">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
-   <span data-ttu-id="ec52c-109">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 관련된 정적 SQL 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="ec52c-109">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
-   <span data-ttu-id="ec52c-110">[!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 메서드에서 지원되는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="ec52c-110">A function supported by a [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] method.</span></span>  
  
 <span data-ttu-id="ec52c-111">이 단원의 항목에서는 코드를 사용자가 직접 작성하는 경우 응용 프로그램에서 이러한 메서드를 만들어 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec52c-111">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="ec52c-112">[!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 개발자는 일반적으로 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]를 사용하여 사용자 정의 함수를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52c-112">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] would typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ec52c-113">단원 내용</span><span class="sxs-lookup"><span data-stu-id="ec52c-113">In This Section</span></span>  
 [<span data-ttu-id="ec52c-114">방법: 스칼라 반환 사용자 정의 함수를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="ec52c-114">How to: Use Scalar-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="ec52c-115">스칼라 값을 반환하는 함수를 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52c-115">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="ec52c-116">방법: 테이블 반환 사용자 정의 함수를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="ec52c-116">How to: Use Table-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="ec52c-117">표 값을 반환하는 함수를 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52c-117">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="ec52c-118">방법: 사용자 정의 함수 인라인 호출</span><span class="sxs-lookup"><span data-stu-id="ec52c-118">How to: Call User-Defined Functions Inline</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="ec52c-119">함수를 인라인 호출하는 방법과 인라인 호출을 통한 실행의 차이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52c-119">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
