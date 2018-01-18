---
title: "ADO.NET의 연결 문자열"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6737b451a0ccb42dfb83dda487e351a9fafde398
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="a9d83-102">ADO.NET의 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="a9d83-102">Connection Strings in ADO.NET</span></span>
<span data-ttu-id="a9d83-103">.NET Framework 2.0에서는 연결 문자열 작성기 클래스에 새로운 키워드를 추가하는 기능을 비롯하여 연결 문자열로 작업하는 데 사용할 수 있는 새로운 기능을 지원합니다. 이러한 기능을 사용하여 런타임에 유효한 연결 문자열을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-103">The .NET Framework 2.0 introduced new capabilities for working with connection strings, including the introduction of new keywords to the connection string builder classes, which facilitate creating valid connection strings at run time.</span></span>  
  
 <span data-ttu-id="a9d83-104">연결 문자열에는 데이터 공급자에서 데이터 소스에 매개 변수로 전달되는 초기화 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-104">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="a9d83-105">연결 문자열 구문은 데이터 공급자에 따라 다르며 연결을 여는 동안 연결 문자열이 구문 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-105">The syntax depends on the data provider, and the connection string is parsed during the attempt to open a connection.</span></span> <span data-ttu-id="a9d83-106">구문 오류가 있으면 런타임 예외가 발생하지만, 다른 오류는 데이터 소스에서 연결 정보를 받은 후에만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-106">Syntax errors generate a run-time exception, but other errors occur only after the data source receives connection information.</span></span> <span data-ttu-id="a9d83-107">유효성을 검사한 후 데이터 소스에서 연결 문자열에 지정된 옵션을 적용하고 연결을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-107">Once validated, the data source applies the options specified in the connection string and opens the connection.</span></span>  
  
 <span data-ttu-id="a9d83-108">연결 문자열 형식은 키/값 매개 변수 쌍의 세미콜론으로 구분된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-108">The format of a connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>  
  
 `keyword1=value; keyword2=value;`  
  
 <span data-ttu-id="a9d83-109">키워드는 대/소문자를 구분하지 않으며 키/값 쌍 간의 공백은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-109">Keywords are not case sensitive, and spaces between key/value pairs are ignored.</span></span> <span data-ttu-id="a9d83-110">하지만 값은 데이터 소스에 따라 대/소문자를 구분해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-110">However, values may be case sensitive, depending on the data source.</span></span> <span data-ttu-id="a9d83-111">세미콜론, 작은따옴표 또는 큰따옴표가 포함된 값은 큰따옴표로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-111">Any values containing a semicolon, single quotation marks, or double quotation marks must be enclosed in double quotation marks.</span></span>  
  
 <span data-ttu-id="a9d83-112">유효한 연결 문자열 구문은 공급자에 따라 다르며 ODBC와 유사한 초기 API에서부터 수년에 걸쳐 발전해 왔습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-112">Valid connection string syntax depends on the provider, and has evolved over the years from earlier APIs like ODBC.</span></span> <span data-ttu-id="a9d83-113">.NET Framework Data Provider for SQL Server(SqlClient)는 이전 구문의 많은 요소를 통합하므로 대개 일반적인 연결 문자열 구문보다 융통성이 뛰어납니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-113">The .NET Framework Data Provider for SQL Server (SqlClient) incorporates many elements from older syntax and is generally more flexible with common connection string syntax.</span></span> <span data-ttu-id="a9d83-114">연결 문자열 구문 요소에는 유효하게 사용할 수 있는 동의어가 많지만 구문과 맞춤법을 잘못 입력하는 일부 경우에는 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-114">There are frequently equally valid synonyms for connection string syntax elements, but some syntax and spelling errors can cause problems.</span></span> <span data-ttu-id="a9d83-115">예를 들어 "`Integrated Security=true`"는 유효하지만 "`IntegratedSecurity=true`"는 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-115">For example, "`Integrated Security=true`" is valid, whereas "`IntegratedSecurity=true`" causes an error.</span></span> <span data-ttu-id="a9d83-116">또한 유효성이 검증되지 않은 사용자 입력을 통해 런타임에 구성된 연결 문자열은 문자열 삽입 공격으로 이어져 데이터 소스의 보안을 위협할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-116">In addition, connection strings constructed at run time from unvalidated user input can lead to string injection attacks, jeopardizing security at the data source.</span></span>  
  
 <span data-ttu-id="a9d83-117">이러한 문제를 해결하기 위해 ADO.NET 2.0에서는 각 .NET Framework 데이터 공급자에 사용할 수 있는 새로운 연결 문자열 작성기가 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-117">To address these problems, ADO.NET 2.0 introduced new connection string builders for each .NET Framework data provider.</span></span> <span data-ttu-id="a9d83-118">키워드는 속성으로 노출되므로 데이터 소스에 제출하기 전에 연결 문자열 구문의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-118">Keywords are exposed as properties, enabling connection string syntax to be validated before submission to the data source.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a9d83-119">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a9d83-119">In This Section</span></span>  
 [<span data-ttu-id="a9d83-120">연결 문자열 작성기</span><span class="sxs-lookup"><span data-stu-id="a9d83-120">Connection String Builders</span></span>](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 <span data-ttu-id="a9d83-121">`ConnectionStringBuilder` 클래스를 사용하여 런타임에 유효한 연결 문자열을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-121">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>  
  
 [<span data-ttu-id="a9d83-122">연결 문자열 및 구성 파일</span><span class="sxs-lookup"><span data-stu-id="a9d83-122">Connection Strings and Configuration Files</span></span>](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)  
 <span data-ttu-id="a9d83-123">구성 파일에서 연결 문자열을 저장하고 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-123">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>  
  
 [<span data-ttu-id="a9d83-124">연결 문자열 구문</span><span class="sxs-lookup"><span data-stu-id="a9d83-124">Connection String Syntax</span></span>](../../../../docs/framework/data/adonet/connection-string-syntax.md)  
 <span data-ttu-id="a9d83-125">`SqlClient`, `OracleClient`, `OleDb` 및 `Odbc`에 대한 공급자별 연결 문자열을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-125">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>  
  
 [<span data-ttu-id="a9d83-126">연결 정보 보호</span><span class="sxs-lookup"><span data-stu-id="a9d83-126">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 <span data-ttu-id="a9d83-127">데이터 소스 연결에 사용되는 정보를 보호하는 기법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9d83-127">Demonstrates techniques for protecting information used to connect to a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9d83-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9d83-128">See Also</span></span>  
 [<span data-ttu-id="a9d83-129">데이터 소스에 연결</span><span class="sxs-lookup"><span data-stu-id="a9d83-129">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)  
 [<span data-ttu-id="a9d83-130">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="a9d83-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
