---
title: DbProviderFactory
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: 8692dc761f00e0ddc8ec9fad5a5df66b7fda7916
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762301"
---
# <a name="dbproviderfactories"></a><span data-ttu-id="929a7-102">DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="929a7-102">DbProviderFactories</span></span>
<span data-ttu-id="929a7-103"><xref:System.Data.Common> 네임스페이스에서는 특정 데이터 소스를 사용하기 위해 <xref:System.Data.Common.DbProviderFactory> 인스턴스를 만드는 데 필요한 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="929a7-103">The <xref:System.Data.Common> namespace provides classes for creating <xref:System.Data.Common.DbProviderFactory> instances to work with specific data sources.</span></span> <span data-ttu-id="929a7-104"><xref:System.Data.Common.DbProviderFactory> 인스턴스를 만든 다음 이 인스턴스에 데이터 공급자에 대한 정보를 전달하면 `DbProviderFactory`에서 제공된 정보에 따라 반환할 강력한 형식의 올바른 연결 개체를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929a7-104">When you create a <xref:System.Data.Common.DbProviderFactory> instance and pass it information about the data provider, the `DbProviderFactory` can determine the correct, strongly typed connection object to return based on the information it has been provided.</span></span>  
  
 <span data-ttu-id="929a7-105">.NET Framework 버전 4부터는 <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> 및 <xref:System.Data.OracleClient> 등의 데이터 공급자는 더 이상 제공되지 않지만 사용자 지정 공급자는 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="929a7-105">Beginning in the .NET Framework version 4, data providers such as <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient>, and <xref:System.Data.OracleClient> are no longer listed in machine.config file, but custom providers will continue to be listed there.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="929a7-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="929a7-106">In This Section</span></span>  
 [<span data-ttu-id="929a7-107">팩터리 모델 개요</span><span class="sxs-lookup"><span data-stu-id="929a7-107">Factory Model Overview</span></span>](../../../../docs/framework/data/adonet/factory-model-overview.md)  
 <span data-ttu-id="929a7-108">팩터리 디자인 패턴 및 프로그래밍 인터페이스를 간략히 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="929a7-108">Provides an overview of the factory design pattern and programming interface.</span></span>  
  
 [<span data-ttu-id="929a7-109">DbProviderFactory 가져오기</span><span class="sxs-lookup"><span data-stu-id="929a7-109">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 <span data-ttu-id="929a7-110">설치된 데이터 공급자를 나열하고 <xref:System.Data.Common.DbConnection>에서 `DbProviderFactory`을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="929a7-110">Demonstrates how to list the installed data providers and create a <xref:System.Data.Common.DbConnection> from a `DbProviderFactory`.</span></span>  
  
 [<span data-ttu-id="929a7-111">DbConnection, DbCommand 및 DbException</span><span class="sxs-lookup"><span data-stu-id="929a7-111">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 <span data-ttu-id="929a7-112"><xref:System.Data.Common.DbCommand> 및 <xref:System.Data.Common.DbDataReader>를 만들고 <xref:System.Data.Common.DbException>을 사용하여 데이터 오류를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="929a7-112">Demonstrates how to create a <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbDataReader>, and how to handle data errors using <xref:System.Data.Common.DbException>.</span></span>  
  
 [<span data-ttu-id="929a7-113">DbDataAdapter로 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="929a7-113">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 <span data-ttu-id="929a7-114"><xref:System.Data.Common.DbCommandBuilder>를 <xref:System.Data.Common.DbDataAdapter>와 함께 사용하여 데이터를 검색 및 수정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="929a7-114">Demonstrates how to use a <xref:System.Data.Common.DbCommandBuilder> with a <xref:System.Data.Common.DbDataAdapter> to retrieve and modify data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="929a7-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="929a7-115">See Also</span></span>  
 [<span data-ttu-id="929a7-116">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="929a7-116">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="929a7-117">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="929a7-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
