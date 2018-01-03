---
title: "Null 값 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f18b288f-b265-4bbe-957f-c6833c0645ef
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 8467d1748cec216c01756049d889ea29f02c3c7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="handling-null-values"></a><span data-ttu-id="ce9a9-102">Null 값 처리</span><span class="sxs-lookup"><span data-stu-id="ce9a9-102">Handling Null Values</span></span>
<span data-ttu-id="ce9a9-103">관계형 데이터베이스에서 null 값은 열의 값이 없거나 알 수 없을 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-103">A null value in a relational database is used when the value in a column is unknown or missing.</span></span> <span data-ttu-id="ce9a9-104">null은 빈 문자열(문자 또는 datetime 데이터 형식의 경우)도 아니고 0 값(숫자 데이터 형식의 경우)도 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-104">A null is neither an empty string (for character or datetime data types) nor a zero value (for numeric data types).</span></span> <span data-ttu-id="ce9a9-105">ANSI SQL-92 사양에서는 모든 null이 일관성 있게 처리되도록 모든 데이터 형식에 대해 null이 동일해야 함을 규정하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-105">The ANSI SQL-92 specification states that a null must be the same for all data types, so that all nulls are handled consistently.</span></span> <span data-ttu-id="ce9a9-106"><xref:System.Data.SqlTypes> 네임스페이스에서는 <xref:System.Data.SqlTypes.INullable> 인터페이스를 구현함으로써 null 의미 체계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-106">The <xref:System.Data.SqlTypes> namespace provides null semantics by implementing the <xref:System.Data.SqlTypes.INullable> interface.</span></span> <span data-ttu-id="ce9a9-107"><xref:System.Data.SqlTypes>의 각 데이터 형식마다 해당 데이터 형식의 인스턴스에 할당할 수 있는 고유의 `IsNull` 속성과 `Null` 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-107">Each of the data types in <xref:System.Data.SqlTypes> has its own `IsNull` property and a `Null` value that can be assigned to an instance of that data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce9a9-108">.NET Framework 버전 2.0에는 null을 허용하는 형식에 대한 지원 기능이 도입되었습니다. 프로그래머는 이 기능을 사용하여 값 형식이 내부 형식의 모든 값을 나타내도록 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-108">The .NET Framework version 2.0 introduced support for nullable types, which allow programmers to extend a value type to represent all values of the underlying type.</span></span> <span data-ttu-id="ce9a9-109">이러한 CLR null 허용 형식은 <xref:System.Nullable> 구조체의 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-109">These CLR nullable types represent an instance of the <xref:System.Nullable> structure.</span></span> <span data-ttu-id="ce9a9-110">이 기능은 값 형식이 boxed 및 unboxed일 때 개체 형식과의 향상된 호환성을 제공하므로 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-110">This capability is especially useful when value types are boxed and unboxed, providing enhanced compatibility with object types.</span></span> <span data-ttu-id="ce9a9-111">ANSI SQL null은 `null` 참조(Visual Basic에서는 `Nothing`)와 동일한 방식으로 동작하지 않기 때문에 CLR null 허용 형식으로 데이터베이스 null을 저장할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-111">CLR nullable types are not intended for storage of database nulls because an ANSI SQL null does not behave the same way as a `null` reference (or `Nothing` in Visual Basic).</span></span> <span data-ttu-id="ce9a9-112">데이터베이스 ANSI SQL null 값을 처리하려면 <xref:System.Data.SqlTypes> 대신 <xref:System.Nullable> null을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-112">For working with database ANSI SQL null values, use <xref:System.Data.SqlTypes> nulls rather than <xref:System.Nullable>.</span></span> <span data-ttu-id="ce9a9-113">CLR 작업에 대 한 자세한 내용은 Visual Basic의 null 허용 형식 참조 [Nullable 값 형식](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md), 및 C# 참조에 대 한 [Nullable 형식을 사용 하 여](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-113">For more information on working with CLR nullable types in Visual Basic see [Nullable Value Types](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md), and for C# see [Using Nullable Types](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md).</span></span>  
  
## <a name="nulls-and-three-valued-logic"></a><span data-ttu-id="ce9a9-114">Null과 3중값 논리</span><span class="sxs-lookup"><span data-stu-id="ce9a9-114">Nulls and Three-Valued Logic</span></span>  
 <span data-ttu-id="ce9a9-115">열 정의에서 null 값을 허용하면 응용 프로그램에 3중값 논리가 도입됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-115">Allowing null values in column definitions introduces three-valued logic into your application.</span></span> <span data-ttu-id="ce9a9-116">비교는 다음 세 가지 조건 중 하나로 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-116">A comparison can evaluate to one of three conditions:</span></span>  
  
-   <span data-ttu-id="ce9a9-117">True</span><span class="sxs-lookup"><span data-stu-id="ce9a9-117">True</span></span>  
  
-   <span data-ttu-id="ce9a9-118">False</span><span class="sxs-lookup"><span data-stu-id="ce9a9-118">False</span></span>  
  
-   <span data-ttu-id="ce9a9-119">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="ce9a9-119">Unknown</span></span>  
  
 <span data-ttu-id="ce9a9-120">null은 알 수 없는 상태로 간주되기 때문에 서로 비교되는 두 개의 null 값은 같은 값으로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-120">Because null is considered to be unknown, two null values compared to each other are not considered to be equal.</span></span> <span data-ttu-id="ce9a9-121">산술 연산자를 사용하는 식에서 피연산자 중 하나가 null이면 그 결과도 null입니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-121">In expressions using arithmetic operators, if any of the operands is null, the result is null as well.</span></span>  
  
## <a name="nulls-and-sqlboolean"></a><span data-ttu-id="ce9a9-122">Null과 SqlBoolean</span><span class="sxs-lookup"><span data-stu-id="ce9a9-122">Nulls and SqlBoolean</span></span>  
 <span data-ttu-id="ce9a9-123">모든 <xref:System.Data.SqlTypes> 간의 비교는 <xref:System.Data.SqlTypes.SqlBoolean>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-123">Comparison between any <xref:System.Data.SqlTypes> will return a <xref:System.Data.SqlTypes.SqlBoolean>.</span></span> <span data-ttu-id="ce9a9-124">각 `IsNull`의 `SqlType` 함수는 <xref:System.Data.SqlTypes.SqlBoolean>을 반환하며 null 값을 검사하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-124">The `IsNull` function for each `SqlType` returns a <xref:System.Data.SqlTypes.SqlBoolean> and can be used to check for null values.</span></span> <span data-ttu-id="ce9a9-125">다음 진위표는 AND, OR 및 NOT 연산자가 null 값이 있을 때 어떻게 작용하는지 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-125">The following truth tables show how the AND, OR, and NOT operators function in the presence of a null value.</span></span> <span data-ttu-id="ce9a9-126">(T=true, F=false, U=unknown 또는 null)</span><span class="sxs-lookup"><span data-stu-id="ce9a9-126">(T=true, F=false, and U=unknown, or null.)</span></span>  
  
 <span data-ttu-id="ce9a9-127">![진리표](../../../../../docs/framework/data/adonet/sql/media/truthtable-bpuedev11.gif "TruthTable_bpuedev11")</span><span class="sxs-lookup"><span data-stu-id="ce9a9-127">![Truth Table](../../../../../docs/framework/data/adonet/sql/media/truthtable-bpuedev11.gif "TruthTable_bpuedev11")</span></span>  
  
### <a name="understanding-the-ansinulls-option"></a><span data-ttu-id="ce9a9-128">ANSI_NULLS 옵션 이해</span><span class="sxs-lookup"><span data-stu-id="ce9a9-128">Understanding the ANSI_NULLS Option</span></span>  
 <span data-ttu-id="ce9a9-129"><xref:System.Data.SqlTypes>는 SQL Server에서 ANSI_NULLS 옵션이 설정되어 있을 때와 동일한 의미 체계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-129"><xref:System.Data.SqlTypes> provides the same semantics as when the ANSI_NULLS option is set on in SQL Server.</span></span> <span data-ttu-id="ce9a9-130">모든 산술 연산자 (+,-, *, /, %), 비트 연산자 (~, &, &#124;), 대부분의 함수는 피연산자 또는 인수 중 하나라도 null 속성을 제외한 모든 null 돌아와 `IsNull`합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-130">All arithmetic operators (+, -, *, /, %), bitwise operators (~, &, &#124;), and most functions return null if any of the operands or arguments is null, except for the property `IsNull`.</span></span>  
  
 <span data-ttu-id="ce9a9-131">ANSI sql-92 표준에서는 지원 하지 *columnName* = WHERE 절에서 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-131">The ANSI SQL-92 standard does not support *columnName* = NULL in a WHERE clause.</span></span> <span data-ttu-id="ce9a9-132">SQL Server에서는 ANSI_NULLS 옵션이 데이터베이스의 기본 null 허용 여부와 null 값에 대한 비교 평가를 모두 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-132">In SQL Server, the ANSI_NULLS option controls both default nullability in the database and evaluation of comparisons against null values.</span></span> <span data-ttu-id="ce9a9-133">ANSI_NULLS를 사용하는 경우(기본값)에는 null 값을 테스트할 때 식에서 IS NULL 연산자를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-133">If ANSI_NULLS is turned on (the default), the IS NULL operator must be used in expressions when testing for null values.</span></span> <span data-ttu-id="ce9a9-134">예를 들어, 다음 비교는 ANSI_NULLS가 사용될 때 항상 알 수 없음 상태를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-134">For example, the following comparison always yields unknown when ANSI_NULLS is on:</span></span>  
  
```  
colname > NULL  
```  
  
 <span data-ttu-id="ce9a9-135">null 값을 포함하는 변수와의 비교 역시 알 수 없음 상태를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-135">Comparison to a variable containing a null value also yields unknown:</span></span>  
  
```  
colname > @MyVariable  
```  
  
 <span data-ttu-id="ce9a9-136">null 값을 테스트하려면 IS NULL 또는 IS NOT NULL 조건부를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-136">Use the IS NULL or IS NOT NULL predicate to test for a null value.</span></span> <span data-ttu-id="ce9a9-137">그러면 WHERE 절이 복잡해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-137">This can add complexity to the WHERE clause.</span></span> <span data-ttu-id="ce9a9-138">예를 들어, AdventureWorks Customer 테이블의 TerritoryID 열에서는 null 값을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-138">For example, the TerritoryID column in the AdventureWorks Customer table allows null values.</span></span> <span data-ttu-id="ce9a9-139">SELECT 문에서 다른 값은 물론 null 값도 테스트해야 하는 경우에는 다음과 같이 IS NULL 조건부가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-139">If a SELECT statement is to test for null values in addition to others, it must include an IS NULL predicate:</span></span>  
  
```  
SELECT CustomerID, AccountNumber, TerritoryID  
FROM AdventureWorks.Sales.Customer  
WHERE TerritoryID IN (1, 2, 3)  
   OR TerritoryID IS NULL  
```  
  
 <span data-ttu-id="ce9a9-140">SQL Server에서 ANSI_NULLS가 사용되지 않도록 설정하면 등호 연산자를 사용하여 null을 비교하는 식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-140">If you set ANSI_NULLS off in SQL Server, you can create expressions that use the equality operator to compare to null.</span></span> <span data-ttu-id="ce9a9-141">그러나 다른 연결에서 해당 연결에 대해 null 옵션을 설정하게 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-141">However, you can't prevent different connections from setting null options for that connection.</span></span> <span data-ttu-id="ce9a9-142">연결에 대한 ANSI_NULLS 설정과 상관없이 null 값을 테스트할 목적으로 IS NULL을 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-142">Using IS NULL to test for null values always works, regardless of the ANSI_NULLS settings for a connection.</span></span>  
  
 <span data-ttu-id="ce9a9-143">`DataSet`에서는 null 값을 처리할 때 항상 ANSI SQL-92 표준을 따르기 때문에 <xref:System.Data.SqlTypes>에서는 ANSI_NULLS가 사용되지 않도록 설정할 수 있는 기능이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-143">Setting ANSI_NULLS off is not supported in a `DataSet`, which always follows the ANSI SQL-92 standard for handling null values in <xref:System.Data.SqlTypes>.</span></span>  
  
## <a name="assigning-null-values"></a><span data-ttu-id="ce9a9-144">Null 값 할당</span><span class="sxs-lookup"><span data-stu-id="ce9a9-144">Assigning Null Values</span></span>  
 <span data-ttu-id="ce9a9-145">Null 값은 특수하며, 해당 저장소 및 할당 의미 체계도 다양한 형식 시스템 및 저장소 시스템에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-145">Null values are special, and their storage and assignment semantics differ across different type systems and storage systems.</span></span> <span data-ttu-id="ce9a9-146">`Dataset`은 다양한 형식 및 저장소 시스템에서 사용하도록 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-146">A `Dataset` is designed to be used with different type and storage systems.</span></span>  
  
 <span data-ttu-id="ce9a9-147">이 단원에서는 다양한 형식 시스템에서 null 값을 <xref:System.Data.DataColumn>의 <xref:System.Data.DataRow>에 할당하기 위한 null 의미 체계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-147">This section describes the null semantics for assigning null values to a <xref:System.Data.DataColumn> in a <xref:System.Data.DataRow> across the different type systems.</span></span>  
  
 `DBNull.Value`  
 <span data-ttu-id="ce9a9-148">이 할당은 모든 형식의 `DataColumn`에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-148">This assignment is valid for a `DataColumn` of any type.</span></span> <span data-ttu-id="ce9a9-149">해당 형식에서 `INullable`을 구현하는 경우 `DBNull.Value`는 강력한 형식의 적절한 Null 값으로 강제 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-149">If the type implements `INullable`, `DBNull.Value` is coerced into the appropriate strongly typed Null value.</span></span>  
  
 `SqlType.Null`  
 <span data-ttu-id="ce9a9-150">모든 <xref:System.Data.SqlTypes> 데이터 형식에서 INullable`INullable`을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-150">All <xref:System.Data.SqlTypes> data types implement `INullable`.</span></span> <span data-ttu-id="ce9a9-151">암시적 캐스트 연산자를 사용하여 강력한 형식의 null 값을 열의 데이터 형식으로 변환할 수 있는 경우에는 할당이 수행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-151">If the strongly typed null value can be converted into the column's data type using implicit cast operators, the assignment should go through.</span></span> <span data-ttu-id="ce9a9-152">그렇지 않으면 잘못된 캐스팅 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-152">Otherwise an invalid cast exception is thrown.</span></span>  
  
 `null`  
 <span data-ttu-id="ce9a9-153">주어진 `DataColumn` 데이터 형식에 대해 'null'이 올바른 값인 경우 이 값은 적절한 `DbNull.Value` 또는 `Null` 형식과 연결된 `INullable`(`SqlType.Null`)로 강제 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-153">If 'null' is a legal value for the given `DataColumn` data type, it is coerced into the appropriate `DbNull.Value` or `Null` associated with the `INullable` type (`SqlType.Null`)</span></span>  
  
 `derivedUdt.Null`  
 <span data-ttu-id="ce9a9-154">UDT 열의 경우, null은 항상 `DataColumn`과 연결된 형식에 따라 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-154">For UDT columns, nulls are always stored based on the type associated with the `DataColumn`.</span></span> <span data-ttu-id="ce9a9-155">하위 클래스에서 수행하는 동안 `DataColumn`을 구현하지 않는 `INullable`에 연결된 UDT의 경우를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-155">Consider the case of a UDT associated with a `DataColumn` that does not implement `INullable` while its sub-class does.</span></span> <span data-ttu-id="ce9a9-156">이 경우 파생 클래스에 연결된 강력한 형식의 null 값이 할당되면 null 저장소가 항상 DataColumn의 데이터 형식과 일관되므로 이 값은 형식화되지 않은 `DbNull.Value`로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-156">In this case, if a strongly typed null value associated with the derived class is assigned, it is stored as an untyped `DbNull.Value`, because null storage is always consistent with the DataColumn's data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce9a9-157">`Nullable<T>` 또는 <xref:System.Nullable> 구조체는 현재 `DataSet`에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-157">The `Nullable<T>` or <xref:System.Nullable> structure is not currently supported in the `DataSet`.</span></span>  
  
### <a name="multiple-column-row-assignment"></a><span data-ttu-id="ce9a9-158">여러 열(행) 할당</span><span class="sxs-lookup"><span data-stu-id="ce9a9-158">Multiple Column (Row) Assignment</span></span>  
 <span data-ttu-id="ce9a9-159">`DataTable.Add`, `DataTable.LoadDataRow` 또는 행으로 매핑되는 <xref:System.Data.DataRow.ItemArray%2A>를 허용하는 그 밖의 API는 'null'을 DataColumn의 기본값으로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-159">`DataTable.Add`, `DataTable.LoadDataRow`, or other APIs that accept an <xref:System.Data.DataRow.ItemArray%2A> that gets mapped to a row, map 'null' to the DataColumn's default value.</span></span> <span data-ttu-id="ce9a9-160">배열의 개체가 `DbNull.Value` 또는 이에 해당하는 강력한 형식의 값을 포함하는 경우 위에서 설명한 것과 동일한 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-160">If an object in the array contains `DbNull.Value` or its strongly typed counterpart, the same rules as described above are applied.</span></span>  
  
 <span data-ttu-id="ce9a9-161">또한 다음 규칙은 `DataRow.["columnName"]` null 할당의 인스턴스에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-161">In addition, the following rules apply for an instance of `DataRow.["columnName"]` null assignments:</span></span>  
  
1.  <span data-ttu-id="ce9a9-162">기본 *기본* 값은 `DbNull.Value` 위치 하는 것이 적절 한 강력한 형식의 null 열을 형식화 된 null 값 제외한 모든 열에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-162">The default *default* value is `DbNull.Value` for all except the strongly typed null columns where it is the appropriate strongly typed null value.</span></span>  
  
2.  <span data-ttu-id="ce9a9-163">Null 값은 "xsi:nil"에서와 같이 XML 파일과의 직렬화 중에는 작성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-163">Null values are never written out during serialization to XML files (as in "xsi:nil").</span></span>  
  
3.  <span data-ttu-id="ce9a9-164">기본값을 포함하여 null이 아닌 모든 값은 항상 XML에 대한 직렬화 중에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-164">All non-null values, including defaults, are always written out while serializing to XML.</span></span> <span data-ttu-id="ce9a9-165">이 경우는 null 값(xsi:nil)이 명시적이고 기본값이 암시적인 XSD/XML 의미 체계와는 달리, 기본값이 XML에 없으면 유효성 검사 파서가 연결된 XSD 스키마에서 해당 기본값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-165">This is unlike XSD/XML semantics where a null value (xsi:nil) is explicit and the default value is implicit (if not present in XML, a validating parser can get it from an associated XSD schema).</span></span> <span data-ttu-id="ce9a9-166">`DataTable`의 경우에는 이와 반대로 null 값이 암시적이고 기본값이 명시적입니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-166">The opposite is true for a `DataTable`: a null value is implicit and the default value is explicit.</span></span>  
  
4.  <span data-ttu-id="ce9a9-167">XML 입력에서 읽어온 행에 대해 누락된 모든 열 값에는 NULL이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-167">All missing column values for rows read from XML input are assigned NULL.</span></span> <span data-ttu-id="ce9a9-168"><xref:System.Data.DataTable.NewRow%2A> 또는 이와 유사한 메서드를 사용하여 만들어진 행에는 DataColumn의 기본값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-168">Rows created using <xref:System.Data.DataTable.NewRow%2A> or similar methods are assigned the DataColumn's default value.</span></span>  
  
5.  <span data-ttu-id="ce9a9-169"><xref:System.Data.DataRow.IsNull%2A> 메서드는 `true`와 `DbNull.Value`에 대해 모두 `INullable.Null`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-169">The <xref:System.Data.DataRow.IsNull%2A> method returns `true` for both `DbNull.Value` and `INullable.Null`.</span></span>  
  
## <a name="assigning-null-values"></a><span data-ttu-id="ce9a9-170">Null 값 할당</span><span class="sxs-lookup"><span data-stu-id="ce9a9-170">Assigning Null Values</span></span>  
 <span data-ttu-id="ce9a9-171">모든 <xref:System.Data.SqlTypes> 인스턴스의 기본값은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-171">The default value for any <xref:System.Data.SqlTypes> instance is null.</span></span>  
  
 <span data-ttu-id="ce9a9-172"><xref:System.Data.SqlTypes>의 Null은 형식마다 다르며 `DbNull`과 같은 단일 값으로 표현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-172">Nulls in <xref:System.Data.SqlTypes> are type-specific and cannot be represented by a single value, such as `DbNull`.</span></span> <span data-ttu-id="ce9a9-173">`IsNull` 속성을 사용하여 null을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-173">Use the `IsNull` property to check for nulls.</span></span>  
  
 <span data-ttu-id="ce9a9-174">다음 코드 예제와 같이 Null 값을 <xref:System.Data.DataColumn>에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-174">Null values can be assigned to a <xref:System.Data.DataColumn> as shown in the following code example.</span></span> <span data-ttu-id="ce9a9-175">예외를 트리거하지 않고 null 값을 `SqlTypes` 변수에 직접 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-175">You can directly assign null values to `SqlTypes` variables without triggering an exception.</span></span>  
  
### <a name="example"></a><span data-ttu-id="ce9a9-176">예제</span><span class="sxs-lookup"><span data-stu-id="ce9a9-176">Example</span></span>  
 <span data-ttu-id="ce9a9-177">다음 코드 예제에서는 <xref:System.Data.DataTable> 및 <xref:System.Data.SqlTypes.SqlInt32>으로 정의된 두 개의 열이 포함된 <xref:System.Data.SqlTypes.SqlString>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-177">The following code example creates a <xref:System.Data.DataTable> with two columns defined as <xref:System.Data.SqlTypes.SqlInt32> and <xref:System.Data.SqlTypes.SqlString>.</span></span> <span data-ttu-id="ce9a9-178">이 코드는 값이 알려져 있는 행과 null 값의 행을 하나씩 추가한 다음 변수에 값을 할당하고 콘솔 창에 출력을 표시하여 <xref:System.Data.DataTable>을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-178">The code adds one row of known values, one row of null values and then iterates through the <xref:System.Data.DataTable>, assigning the values to variables and displaying the output in the console window.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/VB/source.vb#1)]  
  
 <span data-ttu-id="ce9a9-179">이 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-179">This example displays the following results:</span></span>  
  
```  
isColumnNull=False, ID=123, Description=Side Mirror  
isColumnNull=True, ID=Null, Description=Null  
```  
  
## <a name="comparing-null-values-with-sqltypes-and-clr-types"></a><span data-ttu-id="ce9a9-180">SqlTypes 및 CLR 형식을 사용하여 Null 값 비교</span><span class="sxs-lookup"><span data-stu-id="ce9a9-180">Comparing Null Values with SqlTypes and CLR Types</span></span>  
 <span data-ttu-id="ce9a9-181">null 값을 비교할 때는 `Equals` 메서드가 <xref:System.Data.SqlTypes>에서 null 값을 평가하는 방식과 CLR 형식을 사용하는 방식을 비교하여 그 차이를 반드시 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-181">When comparing null values, it is important to understand the difference between the way the `Equals` method evaluates null values in <xref:System.Data.SqlTypes> as compared with the way it works with CLR types.</span></span> <span data-ttu-id="ce9a9-182">모든 <xref:System.Data.SqlTypes>`Equals` 메서드에서는 null 값을 평가하는 데 데이터베이스 의미 체계를 사용합니다. 하나의 값 또는 두 값 모두 null이면 비교 결과는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-182">All of the <xref:System.Data.SqlTypes>`Equals` methods use database semantics for evaluating null values: if either or both of the values is null, the comparison yields null.</span></span> <span data-ttu-id="ce9a9-183">한편, 두 `Equals`에 대해 CLR <xref:System.Data.SqlTypes> 메서드를 사용하면 둘 다 null인 경우 결과는 true입니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-183">On the other hand, using the CLR `Equals` method on two <xref:System.Data.SqlTypes> will yield true if both are null.</span></span> <span data-ttu-id="ce9a9-184">이는 CLR `String.Equals` 메서드와 같은 인스턴스 메서드 사용과 정적/공유 메서드인 `SqlString.Equals` 사용 간의 차이를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-184">This reflects the difference between using an instance method such as the CLR `String.Equals` method, and using the static/shared method, `SqlString.Equals`.</span></span>  
  
 <span data-ttu-id="ce9a9-185">다음 예제에서는 각각의 `SqlString.Equals` 메서드와 `String.Equals` 메서드에 null 값 쌍이 전달된 후 빈 문자열 쌍이 전달될 때 두 메서드의 결과 차이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-185">The following example demonstrates the difference in results between the `SqlString.Equals` method and the `String.Equals` method when each is passed a pair of null values and then a pair of empty strings.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/VB/source.vb#1)]  
  
 <span data-ttu-id="ce9a9-186">이 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9a9-186">The code produces the following output:</span></span>  
  
```  
SqlString.Equals shared/static method:  
  Two nulls=Null  
  
String.Equals instance method:  
  Two nulls=True  
  
SqlString.Equals shared/static method:  
  Two empty strings=True  
  
String.Equals instance method:  
  Two empty strings=True   
```  
  
## <a name="see-also"></a><span data-ttu-id="ce9a9-187">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce9a9-187">See Also</span></span>  
 [<span data-ttu-id="ce9a9-188">SQL Server 데이터 형식 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ce9a9-188">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="ce9a9-189">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="ce9a9-189">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
