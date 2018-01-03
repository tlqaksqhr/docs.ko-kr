---
title: "방법: 동시성 충돌에 테스트할 멤버 지정"
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
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 06a34c5d68e12793b5638bcb292dc44f7abae777
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-which-members-are-tested-for-concurrency-conflicts"></a><span data-ttu-id="917f3-102">방법: 동시성 충돌에 테스트할 멤버 지정</span><span class="sxs-lookup"><span data-stu-id="917f3-102">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>
<span data-ttu-id="917f3-103">에 세 가지 열거형 중 하나를 적용는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성에는 <xref:System.Data.Linq.Mapping.ColumnAttribute> 낙관적 동시성 충돌 감지에 대 한 업데이트에 포함 될 멤버를 지정 하는 특성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="917f3-103">Apply one of three enums to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify which members are to be included in update checks for the detection of optimistic concurrency conflicts.</span></span>  
  
 <span data-ttu-id="917f3-104">디자인 타임에 매핑된 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 런타임 동시성 기능과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="917f3-104">The <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property (mapped at design time) is used together with run-time concurrency features in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="917f3-105">자세한 내용은 참조 [낙관적 동시성: 개요](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="917f3-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="917f3-106">`IsVersion=true`로 디자인된 멤버가 없으면 원래 멤버 값이 현재 데이터베이스 상태와 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="917f3-106">Original member values are compared with the current database state as long as no member is designated as `IsVersion=true`.</span></span> <span data-ttu-id="917f3-107">자세한 내용은 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="917f3-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 <span data-ttu-id="917f3-108">코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="917f3-108">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
### <a name="to-always-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="917f3-109">충돌 확인에 항상 이 멤버를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="917f3-109">To always use this member for detecting conflicts</span></span>  
  
1.  <span data-ttu-id="917f3-110"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="917f3-110">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="917f3-111"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성 값을 `Always`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="917f3-111">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Always`.</span></span>  
  
### <a name="to-never-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="917f3-112">충돌 확인에 이 멤버를 사용하지 않으려면</span><span class="sxs-lookup"><span data-stu-id="917f3-112">To never use this member for detecting conflicts</span></span>  
  
1.  <span data-ttu-id="917f3-113"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="917f3-113">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="917f3-114"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성 값을 `Never`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="917f3-114">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Never`.</span></span>  
  
### <a name="to-use-this-member-for-detecting-conflicts-only-when-the-application-has-changed-the-value-of-the-member"></a><span data-ttu-id="917f3-115">응용 프로그램이 멤버의 값을 변경하는 경우에만 충돌 확인에 이 멤버를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="917f3-115">To use this member for detecting conflicts only when the application has changed the value of the member</span></span>  
  
1.  <span data-ttu-id="917f3-116"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="917f3-116">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="917f3-117"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성 값을 `WhenChanged`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="917f3-117">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `WhenChanged`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="917f3-118">예</span><span class="sxs-lookup"><span data-stu-id="917f3-118">Example</span></span>  
 <span data-ttu-id="917f3-119">다음 예제에서는 업데이트를 확인하는 동안 `HomePage` 개체를 테스트하지 말아야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="917f3-119">The following example specifies that `HomePage` objects should never be tested during update checks.</span></span> <span data-ttu-id="917f3-120">자세한 내용은 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="917f3-120">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="917f3-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="917f3-121">See Also</span></span>  
 [<span data-ttu-id="917f3-122">방법: 변경 내용 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="917f3-122">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="917f3-123">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="917f3-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
