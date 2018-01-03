---
title: "ODBC 스키마 컬렉션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b8c31f4e8b1463c184c9a8ff1cf64808783f030d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="4a552-102">ODBC 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="4a552-102">ODBC Schema Collections</span></span>
<span data-ttu-id="4a552-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 ODBC 드라이버에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4a552-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="4a552-104">Microsoft SQL Server ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="4a552-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="4a552-105">Microsoft SQL Server ODBC Driver에서는 공통 스키마 컬렉션을 비롯 하 여 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4a552-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="4a552-106">Tables</span><span class="sxs-lookup"><span data-stu-id="4a552-106">Tables</span></span>  
  
-   <span data-ttu-id="4a552-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="4a552-107">Indexes</span></span>  
  
-   <span data-ttu-id="4a552-108">Columns</span><span class="sxs-lookup"><span data-stu-id="4a552-108">Columns</span></span>  
  
-   <span data-ttu-id="4a552-109">절차</span><span class="sxs-lookup"><span data-stu-id="4a552-109">Procedures</span></span>  
  
-   <span data-ttu-id="4a552-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="4a552-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="4a552-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="4a552-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="4a552-112">뷰</span><span class="sxs-lookup"><span data-stu-id="4a552-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="4a552-113">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="4a552-113">Tables and Views</span></span>  
  
|<span data-ttu-id="4a552-114">열 이름</span><span class="sxs-lookup"><span data-stu-id="4a552-114">ColumnName</span></span>|<span data-ttu-id="4a552-115">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4a552-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4a552-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="4a552-116">TABLE_CAT</span></span>|<span data-ttu-id="4a552-117">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-117">String</span></span>|  
|<span data-ttu-id="4a552-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="4a552-118">TABLE_SCHEM</span></span>|<span data-ttu-id="4a552-119">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-119">String</span></span>|  
|<span data-ttu-id="4a552-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-120">TABLE_NAME</span></span>|<span data-ttu-id="4a552-121">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-121">String</span></span>|  
|<span data-ttu-id="4a552-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-122">TABLE_TYPE</span></span>|<span data-ttu-id="4a552-123">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-123">String</span></span>|  
|<span data-ttu-id="4a552-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4a552-124">REMARKS</span></span>|<span data-ttu-id="4a552-125">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="4a552-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="4a552-126">Indexes</span></span>  
  
|<span data-ttu-id="4a552-127">열 이름</span><span class="sxs-lookup"><span data-stu-id="4a552-127">ColumnName</span></span>|<span data-ttu-id="4a552-128">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4a552-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4a552-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="4a552-129">TABLE_CAT</span></span>|<span data-ttu-id="4a552-130">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-130">String</span></span>|  
|<span data-ttu-id="4a552-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="4a552-131">TABLE_SCHEM</span></span>|<span data-ttu-id="4a552-132">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-132">String</span></span>|  
|<span data-ttu-id="4a552-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-133">TABLE_NAME</span></span>|<span data-ttu-id="4a552-134">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-134">String</span></span>|  
|<span data-ttu-id="4a552-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="4a552-135">NON_UNIQUE</span></span>|<span data-ttu-id="4a552-136">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-136">Int16</span></span>|  
|<span data-ttu-id="4a552-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4a552-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="4a552-138">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-138">String</span></span>|  
|<span data-ttu-id="4a552-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-139">INDEX_NAME</span></span>|<span data-ttu-id="4a552-140">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-140">String</span></span>|  
|<span data-ttu-id="4a552-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-141">TYPE</span></span>|<span data-ttu-id="4a552-142">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-142">Int16</span></span>|  
|<span data-ttu-id="4a552-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4a552-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="4a552-144">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-144">Int16</span></span>|  
|<span data-ttu-id="4a552-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-145">COLUMN_NAME</span></span>|<span data-ttu-id="4a552-146">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-146">String</span></span>|  
|<span data-ttu-id="4a552-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="4a552-147">ASC_OR_DESC</span></span>|<span data-ttu-id="4a552-148">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-148">String</span></span>|  
|<span data-ttu-id="4a552-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="4a552-149">CARDINATLITY</span></span>|<span data-ttu-id="4a552-150">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-150">Int32</span></span>|  
|<span data-ttu-id="4a552-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="4a552-151">PAGES</span></span>|<span data-ttu-id="4a552-152">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-152">Int32</span></span>|  
|<span data-ttu-id="4a552-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="4a552-153">FILTER_CONDITION</span></span>|<span data-ttu-id="4a552-154">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-154">String</span></span>|  
|<span data-ttu-id="4a552-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4a552-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="4a552-156">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-156">String</span></span>|  
|<span data-ttu-id="4a552-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="4a552-158">Byte</span><span class="sxs-lookup"><span data-stu-id="4a552-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="4a552-159">Columns</span><span class="sxs-lookup"><span data-stu-id="4a552-159">Columns</span></span>  
  
|<span data-ttu-id="4a552-160">열 이름</span><span class="sxs-lookup"><span data-stu-id="4a552-160">ColumnName</span></span>|<span data-ttu-id="4a552-161">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4a552-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4a552-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="4a552-162">TABLE_CAT</span></span>|<span data-ttu-id="4a552-163">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-163">String</span></span>|  
|<span data-ttu-id="4a552-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="4a552-164">TABLE_SCHEM</span></span>|<span data-ttu-id="4a552-165">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-165">String</span></span>|  
|<span data-ttu-id="4a552-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-166">TABLE_NAME</span></span>|<span data-ttu-id="4a552-167">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-167">String</span></span>|  
|<span data-ttu-id="4a552-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-168">COLUMN_NAME</span></span>|<span data-ttu-id="4a552-169">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-169">String</span></span>|  
|<span data-ttu-id="4a552-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-170">DATA_TYPE</span></span>|<span data-ttu-id="4a552-171">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-171">Int16</span></span>|  
|<span data-ttu-id="4a552-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-172">TYPE_NAME</span></span>|<span data-ttu-id="4a552-173">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-173">String</span></span>|  
|<span data-ttu-id="4a552-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="4a552-174">COLUMN_SIZE</span></span>|<span data-ttu-id="4a552-175">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-175">Int32</span></span>|  
|<span data-ttu-id="4a552-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4a552-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="4a552-177">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-177">Int32</span></span>|  
|<span data-ttu-id="4a552-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="4a552-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="4a552-179">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-179">Int16</span></span>|  
|<span data-ttu-id="4a552-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="4a552-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="4a552-181">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-181">Int16</span></span>|  
|<span data-ttu-id="4a552-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4a552-182">NULLABLE</span></span>|<span data-ttu-id="4a552-183">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-183">Int16</span></span>|  
|<span data-ttu-id="4a552-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4a552-184">REMARKS</span></span>|<span data-ttu-id="4a552-185">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-185">String</span></span>|  
|<span data-ttu-id="4a552-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="4a552-186">COLUMN_DEF</span></span>|<span data-ttu-id="4a552-187">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-187">String</span></span>|  
|<span data-ttu-id="4a552-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="4a552-189">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-189">Int16</span></span>|  
|<span data-ttu-id="4a552-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="4a552-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="4a552-191">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-191">Int16</span></span>|  
|<span data-ttu-id="4a552-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4a552-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="4a552-193">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-193">Int32</span></span>|  
|<span data-ttu-id="4a552-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4a552-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="4a552-195">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-195">Int32</span></span>|  
|<span data-ttu-id="4a552-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4a552-196">IS_NULLABLE</span></span>|<span data-ttu-id="4a552-197">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-197">String</span></span>|  
|<span data-ttu-id="4a552-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4a552-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="4a552-199">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-199">String</span></span>|  
|<span data-ttu-id="4a552-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4a552-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="4a552-201">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-201">String</span></span>|  
|<span data-ttu-id="4a552-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="4a552-203">Byte</span><span class="sxs-lookup"><span data-stu-id="4a552-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="4a552-204">절차</span><span class="sxs-lookup"><span data-stu-id="4a552-204">Procedures</span></span>  
  
|<span data-ttu-id="4a552-205">열 이름</span><span class="sxs-lookup"><span data-stu-id="4a552-205">ColumnName</span></span>|<span data-ttu-id="4a552-206">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4a552-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4a552-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="4a552-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="4a552-208">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-208">String</span></span>|  
|<span data-ttu-id="4a552-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="4a552-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="4a552-210">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-210">String</span></span>|  
|<span data-ttu-id="4a552-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="4a552-212">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-212">String</span></span>|  
|<span data-ttu-id="4a552-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="4a552-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="4a552-214">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-214">Int32</span></span>|  
|<span data-ttu-id="4a552-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="4a552-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="4a552-216">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-216">Int32</span></span>|  
|<span data-ttu-id="4a552-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="4a552-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="4a552-218">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-218">Int32</span></span>|  
|<span data-ttu-id="4a552-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4a552-219">REMARKS</span></span>|<span data-ttu-id="4a552-220">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-220">String</span></span>|  
|<span data-ttu-id="4a552-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="4a552-222">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="4a552-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="4a552-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="4a552-224">열 이름</span><span class="sxs-lookup"><span data-stu-id="4a552-224">ColumnName</span></span>|<span data-ttu-id="4a552-225">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4a552-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4a552-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="4a552-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="4a552-227">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-227">String</span></span>|  
|<span data-ttu-id="4a552-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="4a552-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="4a552-229">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-229">String</span></span>|  
|<span data-ttu-id="4a552-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="4a552-231">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-231">String</span></span>|  
|<span data-ttu-id="4a552-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-232">COLUMN_NAME</span></span>|<span data-ttu-id="4a552-233">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-233">String</span></span>|  
|<span data-ttu-id="4a552-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-234">COLUMN_TYPE</span></span>|<span data-ttu-id="4a552-235">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-235">Int16</span></span>|  
|<span data-ttu-id="4a552-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-236">DATA_TYPE</span></span>|<span data-ttu-id="4a552-237">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-237">Int16</span></span>|  
|<span data-ttu-id="4a552-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-238">TYPE_NAME</span></span>|<span data-ttu-id="4a552-239">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-239">String</span></span>|  
|<span data-ttu-id="4a552-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="4a552-240">COLUMN_SIZE</span></span>|<span data-ttu-id="4a552-241">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-241">Int32</span></span>|  
|<span data-ttu-id="4a552-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4a552-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="4a552-243">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-243">Int32</span></span>|  
|<span data-ttu-id="4a552-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="4a552-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="4a552-245">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-245">Int16</span></span>|  
|<span data-ttu-id="4a552-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="4a552-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="4a552-247">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-247">Int16</span></span>|  
|<span data-ttu-id="4a552-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4a552-248">NULLABLE</span></span>|<span data-ttu-id="4a552-249">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-249">Int16</span></span>|  
|<span data-ttu-id="4a552-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4a552-250">REMARKS</span></span>|<span data-ttu-id="4a552-251">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-251">String</span></span>|  
|<span data-ttu-id="4a552-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="4a552-252">COLUMN_DEF</span></span>|<span data-ttu-id="4a552-253">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-253">String</span></span>|  
|<span data-ttu-id="4a552-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="4a552-255">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-255">Int16</span></span>|  
|<span data-ttu-id="4a552-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="4a552-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="4a552-257">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-257">Int16</span></span>|  
|<span data-ttu-id="4a552-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4a552-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="4a552-259">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-259">Int32</span></span>|  
|<span data-ttu-id="4a552-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4a552-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="4a552-261">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-261">Int32</span></span>|  
|<span data-ttu-id="4a552-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4a552-262">IS_NULLABLE</span></span>|<span data-ttu-id="4a552-263">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-263">String</span></span>|  
|<span data-ttu-id="4a552-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4a552-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="4a552-265">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-265">String</span></span>|  
|<span data-ttu-id="4a552-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4a552-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="4a552-267">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-267">String</span></span>|  
|<span data-ttu-id="4a552-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="4a552-269">Byte</span><span class="sxs-lookup"><span data-stu-id="4a552-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="4a552-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="4a552-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="4a552-271">열 이름</span><span class="sxs-lookup"><span data-stu-id="4a552-271">ColumnName</span></span>|<span data-ttu-id="4a552-272">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4a552-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4a552-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="4a552-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="4a552-274">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-274">String</span></span>|  
|<span data-ttu-id="4a552-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="4a552-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="4a552-276">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-276">String</span></span>|  
|<span data-ttu-id="4a552-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="4a552-278">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-278">String</span></span>|  
|<span data-ttu-id="4a552-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-279">COLUMN_NAME</span></span>|<span data-ttu-id="4a552-280">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-280">String</span></span>|  
|<span data-ttu-id="4a552-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-281">COLUMN_TYPE</span></span>|<span data-ttu-id="4a552-282">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-282">Int16</span></span>|  
|<span data-ttu-id="4a552-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-283">DATA_TYPE</span></span>|<span data-ttu-id="4a552-284">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-284">Int16</span></span>|  
|<span data-ttu-id="4a552-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-285">TYPE_NAME</span></span>|<span data-ttu-id="4a552-286">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-286">String</span></span>|  
|<span data-ttu-id="4a552-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="4a552-287">COLUMN_SIZE</span></span>|<span data-ttu-id="4a552-288">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-288">Int32</span></span>|  
|<span data-ttu-id="4a552-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4a552-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="4a552-290">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-290">Int32</span></span>|  
|<span data-ttu-id="4a552-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="4a552-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="4a552-292">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-292">Int16</span></span>|  
|<span data-ttu-id="4a552-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="4a552-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="4a552-294">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-294">Int16</span></span>|  
|<span data-ttu-id="4a552-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4a552-295">NULLABLE</span></span>|<span data-ttu-id="4a552-296">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-296">Int16</span></span>|  
|<span data-ttu-id="4a552-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4a552-297">REMARKS</span></span>|<span data-ttu-id="4a552-298">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-298">String</span></span>|  
|<span data-ttu-id="4a552-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="4a552-299">COLUMN_DEF</span></span>|<span data-ttu-id="4a552-300">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-300">String</span></span>|  
|<span data-ttu-id="4a552-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="4a552-302">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-302">Int16</span></span>|  
|<span data-ttu-id="4a552-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="4a552-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="4a552-304">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-304">Int16</span></span>|  
|<span data-ttu-id="4a552-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4a552-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="4a552-306">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-306">Int32</span></span>|  
|<span data-ttu-id="4a552-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4a552-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="4a552-308">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-308">Int32</span></span>|  
|<span data-ttu-id="4a552-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4a552-309">IS_NULLABLE</span></span>|<span data-ttu-id="4a552-310">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-310">String</span></span>|  
|<span data-ttu-id="4a552-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4a552-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="4a552-312">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-312">String</span></span>|  
|<span data-ttu-id="4a552-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4a552-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="4a552-314">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-314">String</span></span>|  
|<span data-ttu-id="4a552-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="4a552-316">Byte</span><span class="sxs-lookup"><span data-stu-id="4a552-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="4a552-317">Microsoft Oracle ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="4a552-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="4a552-318">Microsoft SQL Server Oracle ODBC Driver에서는 공통 스키마 컬렉션을 비롯 하 여 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4a552-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="4a552-319">Tables</span><span class="sxs-lookup"><span data-stu-id="4a552-319">Tables</span></span>  
  
-   <span data-ttu-id="4a552-320">Columns</span><span class="sxs-lookup"><span data-stu-id="4a552-320">Columns</span></span>  
  
-   <span data-ttu-id="4a552-321">절차</span><span class="sxs-lookup"><span data-stu-id="4a552-321">Procedures</span></span>  
  
-   <span data-ttu-id="4a552-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="4a552-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="4a552-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="4a552-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="4a552-324">뷰</span><span class="sxs-lookup"><span data-stu-id="4a552-324">Views</span></span>  
  
-   <span data-ttu-id="4a552-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="4a552-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="4a552-326">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="4a552-326">Tables and Views</span></span>  
  
|<span data-ttu-id="4a552-327">열 이름</span><span class="sxs-lookup"><span data-stu-id="4a552-327">ColumnName</span></span>|<span data-ttu-id="4a552-328">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4a552-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4a552-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4a552-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="4a552-330">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-330">String</span></span>|  
|<span data-ttu-id="4a552-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a552-331">TABLE_OWNER</span></span>|<span data-ttu-id="4a552-332">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-332">String</span></span>|  
|<span data-ttu-id="4a552-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-333">TABLE_NAME</span></span>|<span data-ttu-id="4a552-334">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-334">String</span></span>|  
|<span data-ttu-id="4a552-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-335">TABLE_TYPE</span></span>|<span data-ttu-id="4a552-336">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-336">String</span></span>|  
|<span data-ttu-id="4a552-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4a552-337">REMARKS</span></span>|<span data-ttu-id="4a552-338">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="4a552-339">Columns</span><span class="sxs-lookup"><span data-stu-id="4a552-339">Columns</span></span>  
  
|<span data-ttu-id="4a552-340">열 이름</span><span class="sxs-lookup"><span data-stu-id="4a552-340">ColumnName</span></span>|<span data-ttu-id="4a552-341">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4a552-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4a552-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4a552-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="4a552-343">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-343">String</span></span>|  
|<span data-ttu-id="4a552-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a552-344">TABLE_OWNER</span></span>|<span data-ttu-id="4a552-345">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-345">String</span></span>|  
|<span data-ttu-id="4a552-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-346">TABLE_NAME</span></span>|<span data-ttu-id="4a552-347">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-347">String</span></span>|  
|<span data-ttu-id="4a552-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-348">COLUMN_NAME</span></span>|<span data-ttu-id="4a552-349">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-349">String</span></span>|  
|<span data-ttu-id="4a552-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-350">DATA_TYPE</span></span>|<span data-ttu-id="4a552-351">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-351">Int16</span></span>|  
|<span data-ttu-id="4a552-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-352">TYPE_NAME</span></span>|<span data-ttu-id="4a552-353">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-353">String</span></span>|  
|<span data-ttu-id="4a552-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="4a552-354">PRECISION</span></span>|<span data-ttu-id="4a552-355">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-355">Int32</span></span>|  
|<span data-ttu-id="4a552-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="4a552-356">LENGTH</span></span>|<span data-ttu-id="4a552-357">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-357">Int32</span></span>|  
|<span data-ttu-id="4a552-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="4a552-358">SCALE</span></span>|<span data-ttu-id="4a552-359">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-359">Int16</span></span>|  
|<span data-ttu-id="4a552-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="4a552-360">RADIX</span></span>|<span data-ttu-id="4a552-361">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-361">Int16</span></span>|  
|<span data-ttu-id="4a552-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4a552-362">NULLABLE</span></span>|<span data-ttu-id="4a552-363">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-363">Int16</span></span>|  
|<span data-ttu-id="4a552-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4a552-364">REMARKS</span></span>|<span data-ttu-id="4a552-365">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-365">String</span></span>|  
|<span data-ttu-id="4a552-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4a552-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="4a552-367">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="4a552-368">절차</span><span class="sxs-lookup"><span data-stu-id="4a552-368">Procedures</span></span>  
  
|<span data-ttu-id="4a552-369">열 이름</span><span class="sxs-lookup"><span data-stu-id="4a552-369">ColumnName</span></span>|<span data-ttu-id="4a552-370">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4a552-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4a552-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4a552-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="4a552-372">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-372">String</span></span>|  
|<span data-ttu-id="4a552-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a552-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="4a552-374">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-374">String</span></span>|  
|<span data-ttu-id="4a552-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="4a552-376">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-376">String</span></span>|  
|<span data-ttu-id="4a552-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="4a552-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="4a552-378">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-378">Int16</span></span>|  
|<span data-ttu-id="4a552-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="4a552-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="4a552-380">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-380">Int16</span></span>|  
|<span data-ttu-id="4a552-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="4a552-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="4a552-382">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-382">Int16</span></span>|  
|<span data-ttu-id="4a552-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4a552-383">REMARKS</span></span>|<span data-ttu-id="4a552-384">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-384">String</span></span>|  
|<span data-ttu-id="4a552-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="4a552-386">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="4a552-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="4a552-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="4a552-388">열 이름</span><span class="sxs-lookup"><span data-stu-id="4a552-388">ColumnName</span></span>|<span data-ttu-id="4a552-389">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4a552-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4a552-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4a552-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="4a552-391">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-391">String</span></span>|  
|<span data-ttu-id="4a552-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a552-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="4a552-393">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-393">String</span></span>|  
|<span data-ttu-id="4a552-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="4a552-395">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-395">String</span></span>|  
|<span data-ttu-id="4a552-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-396">COLUMN_NAME</span></span>|<span data-ttu-id="4a552-397">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-397">String</span></span>|  
|<span data-ttu-id="4a552-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-398">COLUMN_TYPE</span></span>|<span data-ttu-id="4a552-399">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-399">Int16</span></span>|  
|<span data-ttu-id="4a552-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-400">DATA_TYPE</span></span>|<span data-ttu-id="4a552-401">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-401">Int16</span></span>|  
|<span data-ttu-id="4a552-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-402">TYPE_NAME</span></span>|<span data-ttu-id="4a552-403">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-403">String</span></span>|  
|<span data-ttu-id="4a552-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="4a552-404">PRECISION</span></span>|<span data-ttu-id="4a552-405">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-405">Int32</span></span>|  
|<span data-ttu-id="4a552-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="4a552-406">LENGTH</span></span>|<span data-ttu-id="4a552-407">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-407">Int32</span></span>|  
|<span data-ttu-id="4a552-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="4a552-408">SCALE</span></span>|<span data-ttu-id="4a552-409">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-409">Int16</span></span>|  
|<span data-ttu-id="4a552-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="4a552-410">RADIX</span></span>|<span data-ttu-id="4a552-411">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-411">Int16</span></span>|  
|<span data-ttu-id="4a552-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4a552-412">NULLABLE</span></span>|<span data-ttu-id="4a552-413">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-413">Int16</span></span>|  
|<span data-ttu-id="4a552-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4a552-414">REMARKS</span></span>|<span data-ttu-id="4a552-415">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-415">String</span></span>|  
|<span data-ttu-id="4a552-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="4a552-416">OVERLOAD</span></span>|<span data-ttu-id="4a552-417">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-417">Int32</span></span>|  
|<span data-ttu-id="4a552-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4a552-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="4a552-419">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="4a552-420">Microsoft Jet ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="4a552-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="4a552-421">Microsoft Jet ODBC Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="4a552-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="4a552-422">Tables</span><span class="sxs-lookup"><span data-stu-id="4a552-422">Tables</span></span>  
  
-   <span data-ttu-id="4a552-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="4a552-423">Indexes</span></span>  
  
-   <span data-ttu-id="4a552-424">Columns</span><span class="sxs-lookup"><span data-stu-id="4a552-424">Columns</span></span>  
  
-   <span data-ttu-id="4a552-425">절차</span><span class="sxs-lookup"><span data-stu-id="4a552-425">Procedures</span></span>  
  
-   <span data-ttu-id="4a552-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="4a552-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="4a552-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="4a552-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="4a552-428">뷰</span><span class="sxs-lookup"><span data-stu-id="4a552-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="4a552-429">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="4a552-429">Tables and Views</span></span>  
  
|<span data-ttu-id="4a552-430">열 이름</span><span class="sxs-lookup"><span data-stu-id="4a552-430">ColumnName</span></span>|<span data-ttu-id="4a552-431">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4a552-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4a552-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4a552-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="4a552-433">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-433">String</span></span>|  
|<span data-ttu-id="4a552-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a552-434">TABLE_OWNER</span></span>|<span data-ttu-id="4a552-435">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-435">String</span></span>|  
|<span data-ttu-id="4a552-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-436">TABLE_NAME</span></span>|<span data-ttu-id="4a552-437">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-437">String</span></span>|  
|<span data-ttu-id="4a552-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-438">TABLE_TYPE</span></span>|<span data-ttu-id="4a552-439">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-439">String</span></span>|  
|<span data-ttu-id="4a552-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4a552-440">REMARKS</span></span>|<span data-ttu-id="4a552-441">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="4a552-442">Columns</span><span class="sxs-lookup"><span data-stu-id="4a552-442">Columns</span></span>  
  
|<span data-ttu-id="4a552-443">열 이름</span><span class="sxs-lookup"><span data-stu-id="4a552-443">ColumnName</span></span>|<span data-ttu-id="4a552-444">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4a552-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4a552-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4a552-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="4a552-446">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-446">String</span></span>|  
|<span data-ttu-id="4a552-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a552-447">TABLE_OWNER</span></span>|<span data-ttu-id="4a552-448">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-448">String</span></span>|  
|<span data-ttu-id="4a552-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-449">TABLE_NAME</span></span>|<span data-ttu-id="4a552-450">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-450">String</span></span>|  
|<span data-ttu-id="4a552-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-451">COLUMN_NAME</span></span>|<span data-ttu-id="4a552-452">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-452">String</span></span>|  
|<span data-ttu-id="4a552-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-453">DATA_TYPE</span></span>|<span data-ttu-id="4a552-454">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-454">Int16</span></span>|  
|<span data-ttu-id="4a552-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-455">TYPE_NAME</span></span>|<span data-ttu-id="4a552-456">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-456">String</span></span>|  
|<span data-ttu-id="4a552-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="4a552-457">PRECISION</span></span>|<span data-ttu-id="4a552-458">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-458">Int32</span></span>|  
|<span data-ttu-id="4a552-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="4a552-459">LENGTH</span></span>|<span data-ttu-id="4a552-460">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-460">Int32</span></span>|  
|<span data-ttu-id="4a552-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="4a552-461">SCALE</span></span>|<span data-ttu-id="4a552-462">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-462">Int16</span></span>|  
|<span data-ttu-id="4a552-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="4a552-463">RADIX</span></span>|<span data-ttu-id="4a552-464">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-464">Int16</span></span>|  
|<span data-ttu-id="4a552-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4a552-465">NULLABLE</span></span>|<span data-ttu-id="4a552-466">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-466">Int16</span></span>|  
|<span data-ttu-id="4a552-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4a552-467">REMARKS</span></span>|<span data-ttu-id="4a552-468">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-468">String</span></span>|  
|<span data-ttu-id="4a552-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4a552-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="4a552-470">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="4a552-471">절차</span><span class="sxs-lookup"><span data-stu-id="4a552-471">Procedures</span></span>  
  
|<span data-ttu-id="4a552-472">열 이름</span><span class="sxs-lookup"><span data-stu-id="4a552-472">ColumnName</span></span>|<span data-ttu-id="4a552-473">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4a552-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4a552-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4a552-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="4a552-475">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-475">String</span></span>|  
|<span data-ttu-id="4a552-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a552-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="4a552-477">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-477">String</span></span>|  
|<span data-ttu-id="4a552-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="4a552-479">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-479">String</span></span>|  
|<span data-ttu-id="4a552-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="4a552-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="4a552-481">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-481">Int16</span></span>|  
|<span data-ttu-id="4a552-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="4a552-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="4a552-483">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-483">Int16</span></span>|  
|<span data-ttu-id="4a552-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="4a552-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="4a552-485">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-485">Int16</span></span>|  
|<span data-ttu-id="4a552-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4a552-486">REMARKS</span></span>|<span data-ttu-id="4a552-487">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-487">String</span></span>|  
|<span data-ttu-id="4a552-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="4a552-489">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="4a552-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="4a552-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="4a552-491">열 이름</span><span class="sxs-lookup"><span data-stu-id="4a552-491">ColumnName</span></span>|<span data-ttu-id="4a552-492">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4a552-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4a552-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4a552-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="4a552-494">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-494">String</span></span>|  
|<span data-ttu-id="4a552-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a552-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="4a552-496">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-496">String</span></span>|  
|<span data-ttu-id="4a552-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="4a552-498">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-498">String</span></span>|  
|<span data-ttu-id="4a552-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-499">COLUMN_NAME</span></span>|<span data-ttu-id="4a552-500">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-500">String</span></span>|  
|<span data-ttu-id="4a552-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-501">COLUMN_TYPE</span></span>|<span data-ttu-id="4a552-502">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-502">Int16</span></span>|  
|<span data-ttu-id="4a552-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-503">DATA_TYPE</span></span>|<span data-ttu-id="4a552-504">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-504">Int16</span></span>|  
|<span data-ttu-id="4a552-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-505">TYPE_NAME</span></span>|<span data-ttu-id="4a552-506">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-506">String</span></span>|  
|<span data-ttu-id="4a552-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="4a552-507">PRECISION</span></span>|<span data-ttu-id="4a552-508">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-508">Int32</span></span>|  
|<span data-ttu-id="4a552-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="4a552-509">LENGTH</span></span>|<span data-ttu-id="4a552-510">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-510">Int32</span></span>|  
|<span data-ttu-id="4a552-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="4a552-511">SCALE</span></span>|<span data-ttu-id="4a552-512">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-512">Int16</span></span>|  
|<span data-ttu-id="4a552-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="4a552-513">RADIX</span></span>|<span data-ttu-id="4a552-514">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-514">Int16</span></span>|  
|<span data-ttu-id="4a552-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4a552-515">NULLABLE</span></span>|<span data-ttu-id="4a552-516">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-516">Int16</span></span>|  
|<span data-ttu-id="4a552-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4a552-517">REMARKS</span></span>|<span data-ttu-id="4a552-518">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-518">String</span></span>|  
|<span data-ttu-id="4a552-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="4a552-519">OVERLOAD</span></span>|<span data-ttu-id="4a552-520">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-520">Int32</span></span>|  
|<span data-ttu-id="4a552-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4a552-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="4a552-522">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="4a552-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="4a552-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="4a552-524">열 이름</span><span class="sxs-lookup"><span data-stu-id="4a552-524">ColumnName</span></span>|<span data-ttu-id="4a552-525">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4a552-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4a552-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="4a552-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="4a552-527">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-527">String</span></span>|  
|<span data-ttu-id="4a552-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="4a552-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="4a552-529">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-529">String</span></span>|  
|<span data-ttu-id="4a552-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="4a552-531">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-531">String</span></span>|  
|<span data-ttu-id="4a552-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-532">COLUMN_NAME</span></span>|<span data-ttu-id="4a552-533">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-533">String</span></span>|  
|<span data-ttu-id="4a552-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-534">COLUMN_TYPE</span></span>|<span data-ttu-id="4a552-535">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-535">Int16</span></span>|  
|<span data-ttu-id="4a552-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-536">DATA_TYPE</span></span>|<span data-ttu-id="4a552-537">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-537">Int16</span></span>|  
|<span data-ttu-id="4a552-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a552-538">TYPE_NAME</span></span>|<span data-ttu-id="4a552-539">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-539">String</span></span>|  
|<span data-ttu-id="4a552-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="4a552-540">COLUMN_SIZE</span></span>|<span data-ttu-id="4a552-541">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-541">Int32</span></span>|  
|<span data-ttu-id="4a552-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4a552-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="4a552-543">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-543">Int32</span></span>|  
|<span data-ttu-id="4a552-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="4a552-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="4a552-545">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-545">Int16</span></span>|  
|<span data-ttu-id="4a552-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="4a552-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="4a552-547">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-547">Int16</span></span>|  
|<span data-ttu-id="4a552-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4a552-548">NULLABLE</span></span>|<span data-ttu-id="4a552-549">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-549">Int16</span></span>|  
|<span data-ttu-id="4a552-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4a552-550">REMARKS</span></span>|<span data-ttu-id="4a552-551">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-551">String</span></span>|  
|<span data-ttu-id="4a552-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="4a552-552">COLUMN_DEF</span></span>|<span data-ttu-id="4a552-553">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-553">String</span></span>|  
|<span data-ttu-id="4a552-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a552-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="4a552-555">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-555">Int16</span></span>|  
|<span data-ttu-id="4a552-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="4a552-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="4a552-557">Int16</span><span class="sxs-lookup"><span data-stu-id="4a552-557">Int16</span></span>|  
|<span data-ttu-id="4a552-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4a552-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="4a552-559">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-559">Int32</span></span>|  
|<span data-ttu-id="4a552-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4a552-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="4a552-561">Int32</span><span class="sxs-lookup"><span data-stu-id="4a552-561">Int32</span></span>|  
|<span data-ttu-id="4a552-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4a552-562">IS_NULLABLE</span></span>|<span data-ttu-id="4a552-563">문자열</span><span class="sxs-lookup"><span data-stu-id="4a552-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a552-564">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a552-564">See Also</span></span>  
 [<span data-ttu-id="4a552-565">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="4a552-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
