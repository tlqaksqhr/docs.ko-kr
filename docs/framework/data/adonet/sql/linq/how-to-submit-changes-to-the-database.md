---
title: "방법: 데이터베이스에 변경 내용 전송"
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
ms.assetid: c7cba174-9d40-491d-b32c-f2d73b7e9eab
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bf1f9c7982cf9f328fe060266762658ab9693c2e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-submit-changes-to-the-database"></a><span data-ttu-id="71b1c-102">방법: 데이터베이스에 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="71b1c-102">How to: Submit Changes to the Database</span></span>
<span data-ttu-id="71b1c-103">개체의 변경 내용 수에 관계없이 메모리 내의 복제본에만 변경 내용이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-103">Regardless of how many changes you make to your objects, changes are made only to in-memory replicas.</span></span> <span data-ttu-id="71b1c-104">데이터베이스의 실제 데이터는 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-104">You have made no changes to the actual data in the database.</span></span> <span data-ttu-id="71b1c-105"><xref:System.Data.Linq.DataContext.SubmitChanges%2A>의 <xref:System.Data.Linq.DataContext>를 명시적으로 호출한 후에 변경 내용이 서버에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-105">Your changes are not transmitted to the server until you explicitly call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="71b1c-106">이러한 호출을 수행할 때 <xref:System.Data.Linq.DataContext>는 변경 내용을 해당 SQL 명령으로 변환하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-106">When you make this call, the <xref:System.Data.Linq.DataContext> tries to translate your changes into equivalent SQL commands.</span></span> <span data-ttu-id="71b1c-107">이러한 동작을 재정의 하려면 사용자 지정 논리를 사용할 수 있지만 전송 순서의 서비스에 의해 오케스트레이션 됩니다는 <xref:System.Data.Linq.DataContext> 라고는 *변경 프로세서*합니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-107">You can use your own custom logic to override these actions, but the order of submission is orchestrated by a service of the <xref:System.Data.Linq.DataContext> known as the *change processor*.</span></span> <span data-ttu-id="71b1c-108">작업이 진행되는 순서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-108">The sequence of events is as follows:</span></span>  
  
1.  <span data-ttu-id="71b1c-109"><xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출하는 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 알려진 개체 집합을 사용하여 새 인스턴스와의 연결 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-109">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] examines the set of known objects to determine whether new instances have been attached to them.</span></span> <span data-ttu-id="71b1c-110">새 인스턴스와 연결되어 있는 경우 새 인스턴스는 추적된 개체 집합에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-110">If they have, these new instances are added to the set of tracked objects.</span></span>  
  
2.  <span data-ttu-id="71b1c-111">보류 중인 변경 내용이 있는 모든 개체는 이들 간의 종속성을 기반으로 개체 시퀀스로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-111">All objects that have pending changes are ordered into a sequence of objects based on the dependencies between them.</span></span> <span data-ttu-id="71b1c-112">다른 개체에 종속된 변경 내용을 가진 개체는 해당 종속 개체 뒤에 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-112">Objects whose changes depend on other objects are sequenced after their dependencies.</span></span>  
  
3.  <span data-ttu-id="71b1c-113">실제 변경 내용이 전송되기 직전 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 트랜잭션을 시작하여 일련의 개별 명령을 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-113">Immediately before any actual changes are transmitted, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] starts a transaction to encapsulate the series of individual commands.</span></span>  
  
4.  <span data-ttu-id="71b1c-114">개체에 대한 변경 내용은 하나씩 SQL 명령으로 변환되어 서버로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-114">The changes to the objects are translated one by one to SQL commands and sent to the server.</span></span>  
  
 <span data-ttu-id="71b1c-115">이때 데이터베이스에서 오류가 발견되면 전송 프로세스가 중지되고 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-115">At this point, any errors detected by the database cause the submission process to stop, and an exception is raised.</span></span> <span data-ttu-id="71b1c-116">데이터베이스의 모든 변경 내용이 어떠한 전송도 발생하지 않은 것처럼 롤백됩니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-116">All changes to the database are rolled back as if no submissions ever occurred.</span></span> <span data-ttu-id="71b1c-117"><xref:System.Data.Linq.DataContext>에는 여전히 모든 변경 내용에 대한 전체 기록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-117">The <xref:System.Data.Linq.DataContext> still has a full recording of all changes.</span></span> <span data-ttu-id="71b1c-118">따라서 문제를 해결하고 다음 코드 예제에서처럼 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 다시 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-118">You can therefore try to correct the problem and call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> again, as in the code example that follows.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71b1c-119">예</span><span class="sxs-lookup"><span data-stu-id="71b1c-119">Example</span></span>  
 <span data-ttu-id="71b1c-120">전송 주위의 트랜잭션이 성공적으로 완료되는 경우 <xref:System.Data.Linq.DataContext>는 변경 추적 정보를 무시하여 개체의 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="71b1c-120">When the transaction around the submission is completed successfully, the <xref:System.Data.Linq.DataContext> accepts the changes to the objects by ignoring the change-tracking information.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#1)]
 [!code-vb[DLinqSubmittingChanges#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="71b1c-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71b1c-121">See Also</span></span>  
 [<span data-ttu-id="71b1c-122">방법: 전송 충돌 검색 및 해결</span><span class="sxs-lookup"><span data-stu-id="71b1c-122">How to: Detect and Resolve Conflicting Submissions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)  
 [<span data-ttu-id="71b1c-123">방법: 변경 내용 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="71b1c-123">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="71b1c-124">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="71b1c-124">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="71b1c-125">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="71b1c-125">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
