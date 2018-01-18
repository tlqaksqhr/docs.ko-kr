---
title: "연결 풀링"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 7205bc307af6a4a9f307b84a7b3875b77dadb765
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="connection-pooling"></a><span data-ttu-id="cd8b4-102">연결 풀링</span><span class="sxs-lookup"><span data-stu-id="cd8b4-102">Connection Pooling</span></span>
<span data-ttu-id="cd8b4-103">데이터 소스에 연결하는 작업은 시간이 많이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd8b4-103">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="cd8b4-104">ADO.NET 연결을 여는 비용을 최소화 하려면 이라는 최적화 기법을 사용 *연결 풀링*를 반복적으로 열고 연결을 닫는의 비용 최소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd8b4-104">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="cd8b4-105">연결 풀링은 .NET Framework 데이터 공급자마다 각각 다른 방식으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd8b4-105">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd8b4-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="cd8b4-106">In This Section</span></span>  
 [<span data-ttu-id="cd8b4-107">SQL Server 연결 풀링(ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="cd8b4-107">SQL Server Connection Pooling (ADO.NET)</span></span>](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)  
 <span data-ttu-id="cd8b4-108">연결 풀링에 대해 간략하게 설명하고 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]에서 연결 풀링이 작동하는 방식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cd8b4-108">Provides an overview of connection pooling and describes how connection pooling works in [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="cd8b4-109">OLE DB, ODBC 및 Oracle 연결 풀링</span><span class="sxs-lookup"><span data-stu-id="cd8b4-109">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="cd8b4-110">.NET Framework Data Provider for OLE DB, .NET Framework Data Provider for ODBC 및 .NET Framework Data Provider for Oracle의 연결 풀링에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cd8b4-110">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd8b4-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd8b4-111">See Also</span></span>  
 [<span data-ttu-id="cd8b4-112">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="cd8b4-112">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="cd8b4-113">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="cd8b4-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
