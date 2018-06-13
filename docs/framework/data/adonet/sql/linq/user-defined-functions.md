---
title: 사용자 정의 함수
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: f1222d9332d365c9c3c6ca2aa28cbb48e92c04e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33363602"
---
# <a name="user-defined-functions"></a><span data-ttu-id="eea11-102">사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="eea11-102">User-Defined Functions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="eea11-103">에서는 개체 모델에 메서드를 사용하여 사용자 정의 함수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eea11-103"> uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="eea11-104">필요한 위치에 <xref:System.Data.Linq.Mapping.FunctionAttribute> 특성과 <xref:System.Data.Linq.Mapping.ParameterAttribute> 특성을 적용하여 메서드를 함수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea11-104">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="eea11-105">자세한 내용은 참조 [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eea11-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="eea11-106"><xref:System.InvalidOperationException>을 방지하려면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 사용자 정의 함수는 다음 폼 중 하나에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eea11-106">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
-   <span data-ttu-id="eea11-107">올바른 매핑 특성이 있는 메서드 호출로 래핑된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="eea11-107">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="eea11-108">자세한 내용은 참조 [특성 기반 매핑](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eea11-108">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
-   <span data-ttu-id="eea11-109">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 관련된 정적 SQL 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="eea11-109">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
-   <span data-ttu-id="eea11-110">[!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 메서드에서 지원되는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="eea11-110">A function supported by a [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] method.</span></span>  
  
 <span data-ttu-id="eea11-111">이 단원의 항목에서는 코드를 사용자가 직접 작성하는 경우 응용 프로그램에서 이러한 메서드를 만들어 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eea11-111">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="eea11-112">Visual Studio를 사용 하 여 개발자가 일반적으로 사용 된 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 사용자 정의 함수에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="eea11-112">Developers using Visual Studio would typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eea11-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="eea11-113">In This Section</span></span>  
 [<span data-ttu-id="eea11-114">방법: 스칼라 반환 사용자 정의 함수 사용</span><span class="sxs-lookup"><span data-stu-id="eea11-114">How to: Use Scalar-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="eea11-115">스칼라 값을 반환하는 함수를 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eea11-115">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="eea11-116">방법: 테이블 반환 사용자 정의 함수 사용</span><span class="sxs-lookup"><span data-stu-id="eea11-116">How to: Use Table-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="eea11-117">표 값을 반환하는 함수를 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eea11-117">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="eea11-118">방법: 사용자 정의 함수 인라인 호출</span><span class="sxs-lookup"><span data-stu-id="eea11-118">How to: Call User-Defined Functions Inline</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="eea11-119">함수를 인라인 호출하는 방법과 인라인 호출을 통한 실행의 차이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eea11-119">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
