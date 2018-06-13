---
title: SQL Server의 CLR 통합 보안
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: 8df8a19850e9cce28b1f09e80908dafb8bfedaf6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361004"
---
# <a name="clr-integration-security-in-sql-server"></a><span data-ttu-id="5122a-102">SQL Server의 CLR 통합 보안</span><span class="sxs-lookup"><span data-stu-id="5122a-102">CLR Integration Security in SQL Server</span></span>
<span data-ttu-id="5122a-103">Microsoft SQL Server에는 .NET Framework의 CLR(공용 언어 런타임) 구성 요소가 통합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5122a-103">Microsoft SQL Server provides the integration of the common language runtime (CLR) component of the .NET Framework.</span></span> <span data-ttu-id="5122a-104">따라서 이제는 Microsoft Visual Basic .NET 또는 Microsoft Visual C#을 비롯한 모든 .NET Framework 언어를 사용하여 저장 프로시저, 트리거, 사용자 정의 형식, 사용자 정의 함수, 사용자 정의 집계 및 스트리밍 테이블 반환 함수를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5122a-104">CLR integration allows you to write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, such as Microsoft Visual Basic .NET or Microsoft Visual C#.</span></span>  
  
 <span data-ttu-id="5122a-105">CLR은 관리 코드에 대해 CAS(코드 액세스 보안)라는 보안 모델을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5122a-105">The CLR supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="5122a-106">이 모델에서는 코드를 통해 메타데이터로 제공되는 증명 정보를 기준으로 어셈블리에 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="5122a-106">In this model, permissions are granted to assemblies based on evidence supplied by the code in metadata.</span></span> <span data-ttu-id="5122a-107">SQL Server에서는 SQL Server의 사용자 기반 보안 모델을 CLR의 코드 액세스 기반 보안 모델과 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="5122a-107">SQL Server integrates the user-based security model of SQL Server with the code access-based security model of the CLR.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="5122a-108">외부 리소스</span><span class="sxs-lookup"><span data-stu-id="5122a-108">External Resources</span></span>  
 <span data-ttu-id="5122a-109">CLR과 SQL Server 통합에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5122a-109">For more information on CLR integration with SQL Server, see the following resources.</span></span>  
  
|<span data-ttu-id="5122a-110">리소스</span><span class="sxs-lookup"><span data-stu-id="5122a-110">Resource</span></span>|<span data-ttu-id="5122a-111">설명</span><span class="sxs-lookup"><span data-stu-id="5122a-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="5122a-112">코드 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="5122a-112">Code Access Security</span></span>](http://msdn.microsoft.com/library/23a20143-241d-4fe5-9d9f-3933fd594c03)|<span data-ttu-id="5122a-113">.NET Framework의 CAS에 대해 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5122a-113">Contains topics describing CAS in the .NET Framework.</span></span>|  
|[<span data-ttu-id="5122a-114">CLR 통합 보안</span><span class="sxs-lookup"><span data-stu-id="5122a-114">CLR Integration Security</span></span>](http://go.microsoft.com/fwlink/?LinkId=59998)|<span data-ttu-id="5122a-115">SQL Server 내에서 실행되는 관리 코드를 위한 보안 모델에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5122a-115">Discusses the security model for managed code executing inside of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5122a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5122a-116">See Also</span></span>  
 [<span data-ttu-id="5122a-117">ADO.NET 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="5122a-117">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="5122a-118">SQL Server의 응용 프로그램 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="5122a-118">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="5122a-119">SQL Server 공용 언어 런타임 통합</span><span class="sxs-lookup"><span data-stu-id="5122a-119">SQL Server Common Language Runtime Integration</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 [<span data-ttu-id="5122a-120">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="5122a-120">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
