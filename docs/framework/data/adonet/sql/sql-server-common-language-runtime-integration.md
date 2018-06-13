---
title: SQL Server 공용 언어 런타임 통합
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: 7451ed06e8a7c9797c66fd81734eb8b6b3b81f12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355739"
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="e3c9a-102">SQL Server 공용 언어 런타임 통합</span><span class="sxs-lookup"><span data-stu-id="e3c9a-102">SQL Server Common Language Runtime Integration</span></span>
<span data-ttu-id="e3c9a-103">SQL Server 2005에는 .NET Framework for Microsoft Windows의 CLR(공용 언어 런타임) 구성 요소가 통합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-103">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="e3c9a-104">따라서 Microsoft Visual Basic .NET 및 Microsoft Visual C#을 비롯하여 모든 .NET Framework 언어를 사용하여 저장 프로시저, 트리거, 사용자 정의 형식, 사용자 정의 함수, 사용자 정의 집계 및 스트리밍 테이블 반환 함수를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-104">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="e3c9a-105"><xref:Microsoft.SqlServer.Server> 네임스페이스에는 관리 코드에서 Microsoft SQL Server 환경과 상호 작용할 수 있도록 하는 새로운 API(응용 프로그래밍 인터페이스) 집합이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-105">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="e3c9a-106">이 단원에서는 SQL Server CLR(공용 언어 런타임) 통합 및 ADO.NET에 대한 SQL Server in-process 고유의 확장과 관련된 기능 및 동작에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-106">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="e3c9a-107">이 단원은 SQL Server CLR 통합으로 프로그래밍을 시작하는 데 필요한 정보만 제공하며 모든 정보를 포괄적으로 다루지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-107">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="e3c9a-108">자세한 내용을 보려면 현재 사용하고 있는 SQL Server 버전에 해당하는 SQL Server 온라인 설명서 버전을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-108">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="e3c9a-109">**SQL Server 온라인 설명서**</span><span class="sxs-lookup"><span data-stu-id="e3c9a-109">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="e3c9a-110">공용 언어 런타임 (CLR) 통합 프로그래밍 개요</span><span class="sxs-lookup"><span data-stu-id="e3c9a-110">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](http://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a><span data-ttu-id="e3c9a-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e3c9a-111">In This Section</span></span>  
 [<span data-ttu-id="e3c9a-112">SQL Server CLR 통합 소개</span><span class="sxs-lookup"><span data-stu-id="e3c9a-112">Introduction to SQL Server CLR Integration</span></span>](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="e3c9a-113">SQL Server CLR 통합에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-113">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="e3c9a-114">또한 추가 항목에 대한 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-114">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="e3c9a-115">CLR 사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="e3c9a-115">CLR User-Defined Functions</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 <span data-ttu-id="e3c9a-116">테이블 반환 함수, 스칼라 함수 및 사용자 정의 집계 함수 같은 다양한 종류의 CLR 함수를 구현 및 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-116">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="e3c9a-117">CLR 사용자 정의 형식</span><span class="sxs-lookup"><span data-stu-id="e3c9a-117">CLR User-Defined Types</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 <span data-ttu-id="e3c9a-118">CLR 사용자 정의 형식을 구현 및 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-118">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="e3c9a-119">또한 추가 항목에 대한 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-119">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="e3c9a-120">CLR 저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="e3c9a-120">CLR Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 <span data-ttu-id="e3c9a-121">CLR 저장 프로시저를 구현 및 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-121">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="e3c9a-122">또한 추가 항목에 대한 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-122">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="e3c9a-123">CLR 트리거</span><span class="sxs-lookup"><span data-stu-id="e3c9a-123">CLR Triggers</span></span>](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 <span data-ttu-id="e3c9a-124">CLR 트리거를 구현 및 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-124">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="e3c9a-125">또한 추가 항목에 대한 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-125">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="e3c9a-126">컨텍스트 연결</span><span class="sxs-lookup"><span data-stu-id="e3c9a-126">The Context Connection</span></span>](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 <span data-ttu-id="e3c9a-127">컨텍스트 연결에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-127">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="e3c9a-128">ADO.NET의 SQL Server In-Process별 동작</span><span class="sxs-lookup"><span data-stu-id="e3c9a-128">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="e3c9a-129">ADO.NET에 대한 SQL Server in-process 고유의 확장명 및 컨텍스트 연결에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-129">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="e3c9a-130">또한 추가 항목에 대한 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c9a-130">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3c9a-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3c9a-131">See Also</span></span>  
 [<span data-ttu-id="e3c9a-132">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e3c9a-132">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="e3c9a-133">관리 코드에서 SQL Server 2005 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="e3c9a-133">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="e3c9a-134">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="e3c9a-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
