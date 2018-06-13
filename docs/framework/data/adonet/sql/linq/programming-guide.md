---
title: 프로그래밍 가이드
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: 081b5b9fb0765a69e1f45dd0dc25234b8d217ab4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361386"
---
# <a name="programming-guide"></a><span data-ttu-id="c0d92-102">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c0d92-102">Programming Guide</span></span>
<span data-ttu-id="c0d92-103">이 단원에는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개체 모델을 생성하고 사용하는 방법에 대한 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d92-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="c0d92-104">Visual Studio를 사용 하는 경우 사용할 수도 있습니다는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 많은 이와 같은 태스크를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d92-104">If you are using Visual Studio, you can also use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="c0d92-105">특정 문제에 대 한 Microsoft Docs를 검색할 수도 및에 참여할 수 있습니다는 [LINQ 포럼](http://go.microsoft.com/fwlink/?LinkId=76488)전문가 함께 보다 복잡 한 주제를 자세히 논의할 수 있는, 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d92-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](http://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="c0d92-106">마지막으로 [LINQ to SQL: 관계형 데이터에 대 한 쿼리.NET Language-Integrated](http://go.microsoft.com/fwlink/?LinkId=93205) 백서 세부 정보 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기술, Visual Basic 및 C# 코드 예제와 함께 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d92-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](http://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0d92-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c0d92-107">In This Section</span></span>  
 [<span data-ttu-id="c0d92-108">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="c0d92-108">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 <span data-ttu-id="c0d92-109">개체 모델을 생성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d92-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="c0d92-110">데이터베이스와 통신</span><span class="sxs-lookup"><span data-stu-id="c0d92-110">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)  
 <span data-ttu-id="c0d92-111"><xref:System.Data.Linq.DataContext> 개체를 데이터베이스에 대한 통로로 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d92-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="c0d92-112">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="c0d92-112">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 <span data-ttu-id="c0d92-113">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 쿼리를 실행하는 방법에 대해 설명하고 여러 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d92-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="c0d92-114">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="c0d92-114">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 <span data-ttu-id="c0d92-115">데이터베이스에서 데이터를 변경하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d92-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="c0d92-116">디버깅 지원</span><span class="sxs-lookup"><span data-stu-id="c0d92-116">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)  
 <span data-ttu-id="c0d92-117">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프로젝트 디버깅에서 사용 가능한 지원에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d92-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="c0d92-118">배경 정보</span><span class="sxs-lookup"><span data-stu-id="c0d92-118">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 <span data-ttu-id="c0d92-119">고급 사용자를 위한 동시성 충돌 해결 방법, 새로운 데이터베이스 생성 등과 같은 추가 항목도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d92-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c0d92-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="c0d92-120">Related Sections</span></span>  
 [<span data-ttu-id="c0d92-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c0d92-121">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="c0d92-122">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기술에 대해 설명하고 기능을 보여 주는 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d92-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="c0d92-123">저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="c0d92-123">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 <span data-ttu-id="c0d92-124">저장 프로시저를 사용하는 방법을 보여 주는 항목에 대한 링크를 포함합니다. </span><span class="sxs-lookup"><span data-stu-id="c0d92-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="c0d92-125">LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="c0d92-125">Introduction to LINQ</span></span>](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e)  
 <span data-ttu-id="c0d92-126">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]를 배우는데 도움이 되는 리소스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d92-126">Provides resources to help you begin to learn about [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
