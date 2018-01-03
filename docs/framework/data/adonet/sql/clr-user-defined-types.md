---
title: "CLR 사용자 정의 형식"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 7b083dd7284789b1d0271bc688c08bbae591e160
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="3463d-102">CLR 사용자 정의 형식</span><span class="sxs-lookup"><span data-stu-id="3463d-102">CLR User-Defined Types</span></span>
<span data-ttu-id="3463d-103">Microsoft SQL Server에서는 Microsoft .NET Framework CLR(공용 언어 런타임)로 구현된 UDT(사용자 정의 형식)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3463d-103">Microsoft SQL Server provides support for user-defined types (UDTs) implemented with the Microsoft .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="3463d-104">CLR은 SQL Server에 통합되어 있으며 이 메커니즘을 통해 데이터베이스의 형식 시스템을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3463d-104">The CLR is integrated into SQL Server, and this mechanism enables you to extend the type system of the database.</span></span> <span data-ttu-id="3463d-105">UDT는 SQL Server 데이터 형식 시스템에 대한 사용자 확장성 및 구조적 복합 형식을 정의할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3463d-105">UDTs provide user extensibility of the SQL Server data type system, and also the ability to define complex structured types.</span></span>  
  
 <span data-ttu-id="3463d-106">UDT는 응용 프로그램 아키텍처 측면에서 다음과 같은 두 가지 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3463d-106">UDTs can provide two key benefits from an application architecture perspective:</span></span>  
  
-   <span data-ttu-id="3463d-107">클라이언트와 서버에서 내부 상태 및 외부 동작 간의 강력한 캡슐화</span><span class="sxs-lookup"><span data-stu-id="3463d-107">Strong encapsulation (both in the client and the server) between the internal state and the external behaviors.</span></span>  
  
-   <span data-ttu-id="3463d-108">다른 관련 서버 기능과의 밀접한 통합.</span><span class="sxs-lookup"><span data-stu-id="3463d-108">Deep integration with other related server features.</span></span> <span data-ttu-id="3463d-109">고유한 UDT를 정의하고 나면 열 정의를 포함한 SQL Server에 시스템 형식을 사용할 수 있는 경우 모든 컨텍스트에 사용할 수 있으며 변수, 매개 변수, 함수 결과, 커서, 트리거 및 복제로도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3463d-109">Once you define your own UDT, you can use it in all contexts where you can use a system type in SQL Server, including column definitions, and as variables, parameters, function results, cursors, triggers, and replication.</span></span>  
  
 <span data-ttu-id="3463d-110">자세한 내용을 보려면 현재 사용하고 있는 SQL Server 버전에 해당하는 SQL Server 온라인 설명서 버전을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3463d-110">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="3463d-111">**SQL Server 온라인 설명서**</span><span class="sxs-lookup"><span data-stu-id="3463d-111">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="3463d-112">CLR 사용자 정의 형식</span><span class="sxs-lookup"><span data-stu-id="3463d-112">CLR User-Defined Types</span></span>](http://go.microsoft.com/fwlink/?LinkId=98366)  
  
## <a name="see-also"></a><span data-ttu-id="3463d-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3463d-113">See Also</span></span>  
 [<span data-ttu-id="3463d-114">관리 코드에서 SQL Server 2005 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="3463d-114">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="3463d-115">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="3463d-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
