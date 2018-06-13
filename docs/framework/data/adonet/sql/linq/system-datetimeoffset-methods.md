---
title: System.DateTimeOffset 메서드
ms.date: 03/30/2017
ms.assetid: 25b3e5c0-7603-4a70-b3e5-2149e3da69a2
ms.openlocfilehash: 7fc6502f899e953637d23c0d54cc5fe615c38eea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33363314"
---
# <a name="systemdatetimeoffset-methods"></a><span data-ttu-id="cec2b-102">System.DateTimeOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="cec2b-102">System.DateTimeOffset Methods</span></span>
<span data-ttu-id="cec2b-103">개체 모델 또는 외부 매핑 파일에 매핑된 경우 LINQ to SQL에서는 LINQ to SQL 쿼리의 <xref:System.DateTimeOffset?displayProperty=nameWithType> 메서드, 연산자 및 속성 대부분을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cec2b-103">Once mapped in the object model or external mapping file, LINQ to SQL allows you to call most of the <xref:System.DateTimeOffset?displayProperty=nameWithType> methods, operators, and properties from within your LINQ to SQL queries.</span></span>  
  
 <span data-ttu-id="cec2b-104">지원되지 않는 유일한 메서드는 <xref:System.Object?displayProperty=nameWithType>, `Finalize`, `GetHashCode` 및 `GetType`과 같이 LINQ to SQL 쿼리의 컨텍스트에서 인식되지 않는 `MemberwiseClone`에서 상속된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="cec2b-104">The only methods not supported are those inherited from <xref:System.Object?displayProperty=nameWithType> that do not make sense in the context of LINQ to SQL queries, such as: `Finalize`, `GetHashCode`, `GetType`, and `MemberwiseClone`.</span></span> <span data-ttu-id="cec2b-105">SQL Server에서 실행하기 위해 LINQ to SQL에서 변환하지 못하는 이러한 메서드는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cec2b-105">These methods are not supported because LINQ to SQL cannot translate them for execution on the SQL Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cec2b-106">CLR(공용 언어 런타임) <xref:System.DateTimeOffset?displayProperty=nameWithType> 구조 및 LINQ to SQL을 사용하여 이 구조를 SQL `DATETIMEOFFSET` 열에 매핑하는 기능을 사용하려면 .NET Framework 3.5 SP1 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cec2b-106">The common language runtime (CLR) <xref:System.DateTimeOffset?displayProperty=nameWithType> structure, and the ability to map it to a SQL `DATETIMEOFFSET` column with LINQ to SQL, requires the .NET Framework 3.5 SP1 or beyond.</span></span> <span data-ttu-id="cec2b-107">SQL `DATETIMEOFFSET` 열은 Microsoft SQL Server 2008 이상에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cec2b-107">The SQL `DATETIMEOFFSET` column is only available in Microsoft SQL Server 2008 and beyond.</span></span>  
  
## <a name="sqlmethods-date-and-time-methods"></a><span data-ttu-id="cec2b-108">SQLMethod 날짜 및 시간 메서드</span><span class="sxs-lookup"><span data-stu-id="cec2b-108">SQLMethods Date and Time Methods</span></span>  
 <span data-ttu-id="cec2b-109">LINQ to SQL에서는 <xref:System.DateTimeOffset> 구조에서 제공하는 메서드 외에도 날짜 및 시간 작업을 위해 <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> 클래스의 메서드를 다음 표와 같이 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cec2b-109">In addition to the methods offered by the <xref:System.DateTimeOffset> structure, LINQ to SQL offers the methods listed in the following table from the <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> class for working with date and time.</span></span>  
  
||||  
|-|-|-|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffDay%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMillisecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffNanosecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffHour%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMinute%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffSecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMicrosecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMonth%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffYear%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="cec2b-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cec2b-110">See Also</span></span>  
 [<span data-ttu-id="cec2b-111">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="cec2b-111">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [<span data-ttu-id="cec2b-112">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="cec2b-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [<span data-ttu-id="cec2b-113">SQL-CLR 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="cec2b-113">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
