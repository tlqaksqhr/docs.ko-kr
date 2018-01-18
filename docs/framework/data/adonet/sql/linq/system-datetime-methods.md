---
title: "System.DateTime 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f80700c-e83f-4ab6-af0f-1c9a606e1133
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 74c07a2f873d715bd82fba19499b36e8ed305dcc
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="systemdatetime-methods"></a><span data-ttu-id="6a818-102">System.DateTime 메서드</span><span class="sxs-lookup"><span data-stu-id="6a818-102">System.DateTime Methods</span></span>
<span data-ttu-id="6a818-103">다음과 같은 LINQ to SQL 지원 메서드, 연산자 및 속성을 LINQ to SQL 쿼리에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a818-103">The following LINQ to SQL-supported methods, operators, and properties are available to use in LINQ to SQL queries.</span></span> <span data-ttu-id="6a818-104">메서드, 연산자 또는 속성이 지원되지 않는 경우 LINQ to SQL에서는 해당 멤버를 SQL Server에서 실행하기 위해 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a818-104">When a method, operator or property is unsupported, LINQ to SQL cannot translate the member for execution on the SQL Server.</span></span> <span data-ttu-id="6a818-105">이러한 멤버를 코드에 사용할 수 있지만 쿼리를 Transact-SQL로 변환하기 전이나 데이터베이스에서 결과가 검색된 후에 반드시 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a818-105">You may use these members in your code, however, they must be evaluated before the query is translated to Transact-SQL or after the results have been retrieved from the database.</span></span>  
  
## <a name="supported-systemdatetime-members"></a><span data-ttu-id="6a818-106">지원되는 System.DateTime 멤버</span><span class="sxs-lookup"><span data-stu-id="6a818-106">Supported System.DateTime Members</span></span>  
 <span data-ttu-id="6a818-107">개체 모델 또는 외부 매핑 파일에 매핑된 경우 LINQ to SQL에서 LINQ to SQL 쿼리 내부의 다음 <xref:System.DateTime?displayProperty=nameWithType> 멤버를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a818-107">Once mapped in the object model or external mapping file, LINQ to SQL allows you to call the following <xref:System.DateTime?displayProperty=nameWithType> members inside LINQ to SQL queries.</span></span>  
  
|<span data-ttu-id="6a818-108">지원되는 <xref:System.DateTime> 메서드</span><span class="sxs-lookup"><span data-stu-id="6a818-108">Supported <xref:System.DateTime> Methods</span></span>|<span data-ttu-id="6a818-109">지원되는 <xref:System.DateTime> 연산자</span><span class="sxs-lookup"><span data-stu-id="6a818-109">Supported <xref:System.DateTime> Operators</span></span>|<span data-ttu-id="6a818-110">지원되는 <xref:System.DateTime> 속성</span><span class="sxs-lookup"><span data-stu-id="6a818-110">Supported <xref:System.DateTime> Properties</span></span>|  
|------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.DateTime.Add%2A>|<xref:System.DateTime.op_Addition%2A>|<xref:System.DateTime.Date%2A>|  
|<xref:System.DateTime.AddDays%2A>|<xref:System.DateTime.op_Equality%2A>|<xref:System.DateTime.Day%2A>|  
|<xref:System.DateTime.AddHours%2A>|<xref:System.DateTime.op_GreaterThan%2A>|<xref:System.DateTime.DayOfWeek%2A>|  
|<xref:System.DateTime.AddMilliseconds%2A>|<xref:System.DateTime.op_GreaterThanOrEqual%2A>|<xref:System.DateTime.DayOfYear%2A>|  
|<xref:System.DateTime.AddMinutes%2A>|<xref:System.DateTime.op_Inequality%2A>|<xref:System.DateTime.Hour%2A>|  
|<xref:System.DateTime.AddMonths%2A>|<xref:System.DateTime.op_LessThan%2A>|<xref:System.DateTime.Millisecond%2A>|  
|<xref:System.DateTime.AddSeconds%2A>|<xref:System.DateTime.op_LessThanOrEqual%2A>|<xref:System.DateTime.Minute%2A>|  
|<xref:System.DateTime.AddTicks%2A>|<xref:System.DateTime.op_Subtraction%2A>|<xref:System.DateTime.Month%2A>|  
|<xref:System.DateTime.AddYears%2A>||<xref:System.DateTime.Now%2A>|  
|<xref:System.DateTime.Compare%2A>||<xref:System.DateTime.Second%2A>|  
|<xref:System.DateTime.CompareTo%28System.DateTime%29>||<xref:System.DateTime.TimeOfDay%2A>|  
|<xref:System.DateTime.Equals%28System.DateTime%29>||<xref:System.DateTime.Today%2A>|  
|||<xref:System.DateTime.Year%2A>|  
  
## <a name="members-not-supported-by-linq-to-sql"></a><span data-ttu-id="6a818-111">LINQ to SQL에서 지원되지 않는 멤버</span><span class="sxs-lookup"><span data-stu-id="6a818-111">Members Not Supported by LINQ to SQL</span></span>  
 <span data-ttu-id="6a818-112">LINQ to SQL 쿼리 내에서는 다음 멤버가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a818-112">The following members are not supported inside LINQ to SQL queries.</span></span>  
  
|||  
|-|-|  
|<xref:System.DateTime.IsDaylightSavingTime%2A>|<xref:System.DateTime.IsLeapYear%2A>|  
|<xref:System.DateTime.DaysInMonth%2A>|<xref:System.DateTime.ToBinary%2A>|  
|<xref:System.DateTime.ToFileTime%2A>|<xref:System.DateTime.ToFileTimeUtc%2A>|  
|<xref:System.DateTime.ToLongDateString%2A>|<xref:System.DateTime.ToLongTimeString%2A>|  
|<xref:System.DateTime.ToOADate%2A>|<xref:System.DateTime.ToShortDateString%2A>|  
|<xref:System.DateTime.ToShortTimeString%2A>|<xref:System.DateTime.ToUniversalTime%2A>|  
|<xref:System.DateTime.FromBinary%2A>|<xref:System.DateTime.UtcNow%2A>|  
|<xref:System.DateTime.FromFileTime%2A>|<xref:System.DateTime.FromFileTimeUtc%2A>|  
|<xref:System.DateTime.FromOADate%2A>|<xref:System.DateTime.GetDateTimeFormats%2A>|  
  
## <a name="method-translation-example"></a><span data-ttu-id="6a818-113">메서드 변환 예제</span><span class="sxs-lookup"><span data-stu-id="6a818-113">Method Translation Example</span></span>  
 <span data-ttu-id="6a818-114">LINQ to SQL에서 지원하는 모든 메서드는 SQL Server로 전달되기 전에 Transact-SQL로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a818-114">All methods supported by LINQ to SQL are translated to Transact-SQL before they are sent to   SQL Server.</span></span> <span data-ttu-id="6a818-115">예를 들어 다음 패턴을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="6a818-115">For example, consider the following pattern.</span></span>  
  
 `(dateTime1 – dateTime2).{Days, Hours, Milliseconds, Minutes, Months, Seconds, Years}`  
  
 <span data-ttu-id="6a818-116">이 패턴은 인식될 경우 다음과 같이 SQL Server `DATEDIFF` 함수에 대한 직접 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a818-116">When it is recognized, it is translated into a direct call to the SQL Server `DATEDIFF` function, as follows:</span></span>  
  
 `DATEDIFF({DatePart}, @dateTime1, @dateTime2)`  
  
## <a name="sqlmethods-date-and-time-methods"></a><span data-ttu-id="6a818-117">SQLMethod 날짜 및 시간 메서드</span><span class="sxs-lookup"><span data-stu-id="6a818-117">SQLMethods Date and Time Methods</span></span>  
 <span data-ttu-id="6a818-118">LINQ to SQL에서는 <xref:System.DateTime> 구조에서 제공하는 메서드 외에도 날짜 및 시간 작업을 위해 <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> 클래스의 메서드를 다음 표와 같이 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6a818-118">In addition to the methods offered by the <xref:System.DateTime> structure, LINQ to SQL offers the methods listed in the following table from the <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> class for working with date and time.</span></span>  
  
||||  
|-|-|-|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffDay%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMillisecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffNanosecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffHour%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMinute%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffSecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMicrosecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMonth%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffYear%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="6a818-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a818-119">See Also</span></span>  
 [<span data-ttu-id="6a818-120">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="6a818-120">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [<span data-ttu-id="6a818-121">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="6a818-121">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [<span data-ttu-id="6a818-122">SQL-CLR 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="6a818-122">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)  
 [<span data-ttu-id="6a818-123">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="6a818-123">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
