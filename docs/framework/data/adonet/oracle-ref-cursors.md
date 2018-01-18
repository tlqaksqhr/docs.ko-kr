---
title: Oracle REF CURSOR
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f01ace7bc7dfe1191dac8990210032b60e16f255
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="oracle-ref-cursors"></a><span data-ttu-id="3a768-102">Oracle REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="3a768-102">Oracle REF CURSORs</span></span>
<span data-ttu-id="3a768-103">.NET Framework Data Provider for Oracle은 Oracle 지원 **REF CURSOR** 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-103">The .NET Framework Data Provider for Oracle supports the Oracle **REF CURSOR** data type.</span></span> <span data-ttu-id="3a768-104">Oracle REF CURSOR를 사용하는 데이터 공급자를 사용할 경우 다음 동작을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-104">When using the data provider to work with Oracle REF CURSORs, you should consider the following behaviors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a768-105">일부 동작이 MSDAORA(Microsoft OLE DB Provider for Oracle)의 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-105">Some behaviors differ from those of the Microsoft OLE DB Provider for Oracle (MSDAORA).</span></span>  
  
-   <span data-ttu-id="3a768-106">성능상의 이유로 Data Provider for Oracle 자동으로 바인딩할 수 없으면 **REF CURSOR** 있는 데이터 형식으로 MSDAORA 에서처럼 명시적으로 지정 하지 않는 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-106">For performance reasons, the Data Provider for Oracle does not automatically bind **REF CURSOR** data types, as MSDAORA does, unless you explicitly specify them.</span></span>  
  
-   <span data-ttu-id="3a768-107">데이터 공급자는 REF CURSOR 매개 변수를 지정하는 데 사용되는 {resultset} 이스케이프를 포함하여 ODBC 이스케이프 시퀀스를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-107">The data provider does not support any ODBC escape sequences, including the {resultset} escape used to specify REF CURSOR parameters.</span></span>  
  
-   <span data-ttu-id="3a768-108">REF Cursor를 반환 하는 저장된 프로시저를 실행 하려면 매개 변수를 정의 해야는 <xref:System.Data.OracleClient.OracleParameterCollection> 와 <xref:System.Data.OracleClient.OracleType> 의 **커서** 및 <xref:System.Data.OracleClient.OracleParameter.Direction%2A> 의 **출력**합니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-108">To execute a stored procedure that returns REF CURSORs, you must define the parameters in the <xref:System.Data.OracleClient.OracleParameterCollection> with an <xref:System.Data.OracleClient.OracleType> of **Cursor** and a <xref:System.Data.OracleClient.OracleParameter.Direction%2A> of **Output**.</span></span> <span data-ttu-id="3a768-109">데이터 공급자는 REF CURSOR를 출력 매개 변수로만 바인딩하는 것을 지원하며</span><span class="sxs-lookup"><span data-stu-id="3a768-109">The data provider supports binding REF CURSORs as output parameters only.</span></span> <span data-ttu-id="3a768-110">REF CURSOR를 입력 매개 변수로 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-110">The provider does not support REF CURSORs as input parameters.</span></span>  
  
-   <span data-ttu-id="3a768-111">매개 변수 값에서 <xref:System.Data.OracleClient.OracleDataReader>를 가져오는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-111">Obtaining an <xref:System.Data.OracleClient.OracleDataReader> from the parameter value is not supported.</span></span> <span data-ttu-id="3a768-112">값의 형식은 명령이 실행된 후의 <xref:System.DBNull>입니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-112">The values are of type <xref:System.DBNull> after command execution.</span></span>  
  
-   <span data-ttu-id="3a768-113">유일한 **CommandBehavior** REF Cursor를 사용 하는 열거형 값 (호출 하는 경우에 예를 들어 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>)은 **CloseConnection**; 나머지는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-113">The only **CommandBehavior** enumeration value that works with REF CURSORs (for example, when calling <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) is **CloseConnection**; all others are ignored.</span></span>  
  
-   <span data-ttu-id="3a768-114">에 REF Cursor의 순서는 **OracleDataReader** 의 매개 변수 순서에 따라 달라는 **OracleParameterCollection**합니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-114">The order of REF CURSORs in the **OracleDataReader** depends on the order of the parameters in the **OracleParameterCollection**.</span></span> <span data-ttu-id="3a768-115"><xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> 속성은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-115">The <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> property is ignored.</span></span>  
  
-   <span data-ttu-id="3a768-116">PL/SQL **테이블** 데이터 형식이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-116">The PL/SQL **TABLE** data type is not supported.</span></span> <span data-ttu-id="3a768-117">그러나 REF CURSOR가 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-117">However, REF CURSORs are more efficient.</span></span> <span data-ttu-id="3a768-118">사용 해야 하는 경우는 **테이블** 데이터 형식, OLE DB.NET Data Provider와 MSDAORA를 함께 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-118">If you must use a **TABLE** data type, use the OLE DB .NET Data Provider with MSDAORA.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3a768-119">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="3a768-119">In This Section</span></span>  
 [<span data-ttu-id="3a768-120">REF CURSOR 예제</span><span class="sxs-lookup"><span data-stu-id="3a768-120">REF CURSOR Examples</span></span>](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 <span data-ttu-id="3a768-121">REF CURSOR의 사용을 보여 주는 세 가지 예제가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-121">Contains three examples that demonstrate using REF CURSORs.</span></span>  
  
 [<span data-ttu-id="3a768-122">OracleDataReader의 REF CURSOR 매개 변수</span><span class="sxs-lookup"><span data-stu-id="3a768-122">REF CURSOR Parameters in an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 <span data-ttu-id="3a768-123">로 서의 값을 읽고 REF CURSOR 매개 변수를 반환 하는 PL/SQL 저장 프로시저를 실행 하는 방법을 보여 줍니다.는 **OracleDataReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-123">Demonstrates how to execute a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="3a768-124">OracleDataReader를 사용하여 여러 REF CURSOR에서 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="3a768-124">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 <span data-ttu-id="3a768-125">두 개의 REF CURSOR 매개 변수를 반환 하 고 사용 하 여 값을 읽고 하는 PL/SQL 저장 프로시저를 실행 하는 방법을 보여 줍니다.는 **OracleDataReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-125">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="3a768-126">하나 이상의 REF CURSOR를 사용하여 데이터 집합 채우기</span><span class="sxs-lookup"><span data-stu-id="3a768-126">Filling a DataSet Using One or More REF CURSORs</span></span>](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 <span data-ttu-id="3a768-127">두 개의 REF CURSOR 매개 변수를 반환하는 PL/SQL 저장 프로시저를 실행하여 반환되는 행으로 <xref:System.Data.DataSet>을 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a768-127">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a768-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a768-128">See Also</span></span>  
 [<span data-ttu-id="3a768-129">Oracle 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3a768-129">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="3a768-130">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="3a768-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
