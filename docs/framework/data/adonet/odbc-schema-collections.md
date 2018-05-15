---
title: ODBC 스키마 컬렉션
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: 36d0859b897bfcea33803c219ade14722ed90421
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="e8974-102">ODBC 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="e8974-102">ODBC Schema Collections</span></span>
<span data-ttu-id="e8974-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 ODBC 드라이버에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8974-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="e8974-104">Microsoft SQL Server ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="e8974-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="e8974-105">Microsoft SQL Server ODBC Driver에서는 공통 스키마 컬렉션을 비롯 하 여 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e8974-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e8974-106">Tables</span><span class="sxs-lookup"><span data-stu-id="e8974-106">Tables</span></span>  
  
-   <span data-ttu-id="e8974-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="e8974-107">Indexes</span></span>  
  
-   <span data-ttu-id="e8974-108">Columns</span><span class="sxs-lookup"><span data-stu-id="e8974-108">Columns</span></span>  
  
-   <span data-ttu-id="e8974-109">절차</span><span class="sxs-lookup"><span data-stu-id="e8974-109">Procedures</span></span>  
  
-   <span data-ttu-id="e8974-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e8974-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="e8974-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e8974-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="e8974-112">뷰</span><span class="sxs-lookup"><span data-stu-id="e8974-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="e8974-113">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="e8974-113">Tables and Views</span></span>  
  
|<span data-ttu-id="e8974-114">열 이름</span><span class="sxs-lookup"><span data-stu-id="e8974-114">ColumnName</span></span>|<span data-ttu-id="e8974-115">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8974-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e8974-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="e8974-116">TABLE_CAT</span></span>|<span data-ttu-id="e8974-117">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-117">String</span></span>|  
|<span data-ttu-id="e8974-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e8974-118">TABLE_SCHEM</span></span>|<span data-ttu-id="e8974-119">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-119">String</span></span>|  
|<span data-ttu-id="e8974-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-120">TABLE_NAME</span></span>|<span data-ttu-id="e8974-121">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-121">String</span></span>|  
|<span data-ttu-id="e8974-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-122">TABLE_TYPE</span></span>|<span data-ttu-id="e8974-123">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-123">String</span></span>|  
|<span data-ttu-id="e8974-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e8974-124">REMARKS</span></span>|<span data-ttu-id="e8974-125">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="e8974-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="e8974-126">Indexes</span></span>  
  
|<span data-ttu-id="e8974-127">열 이름</span><span class="sxs-lookup"><span data-stu-id="e8974-127">ColumnName</span></span>|<span data-ttu-id="e8974-128">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8974-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e8974-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="e8974-129">TABLE_CAT</span></span>|<span data-ttu-id="e8974-130">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-130">String</span></span>|  
|<span data-ttu-id="e8974-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e8974-131">TABLE_SCHEM</span></span>|<span data-ttu-id="e8974-132">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-132">String</span></span>|  
|<span data-ttu-id="e8974-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-133">TABLE_NAME</span></span>|<span data-ttu-id="e8974-134">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-134">String</span></span>|  
|<span data-ttu-id="e8974-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e8974-135">NON_UNIQUE</span></span>|<span data-ttu-id="e8974-136">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-136">Int16</span></span>|  
|<span data-ttu-id="e8974-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e8974-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="e8974-138">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-138">String</span></span>|  
|<span data-ttu-id="e8974-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-139">INDEX_NAME</span></span>|<span data-ttu-id="e8974-140">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-140">String</span></span>|  
|<span data-ttu-id="e8974-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-141">TYPE</span></span>|<span data-ttu-id="e8974-142">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-142">Int16</span></span>|  
|<span data-ttu-id="e8974-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e8974-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="e8974-144">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-144">Int16</span></span>|  
|<span data-ttu-id="e8974-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-145">COLUMN_NAME</span></span>|<span data-ttu-id="e8974-146">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-146">String</span></span>|  
|<span data-ttu-id="e8974-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="e8974-147">ASC_OR_DESC</span></span>|<span data-ttu-id="e8974-148">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-148">String</span></span>|  
|<span data-ttu-id="e8974-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="e8974-149">CARDINATLITY</span></span>|<span data-ttu-id="e8974-150">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-150">Int32</span></span>|  
|<span data-ttu-id="e8974-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="e8974-151">PAGES</span></span>|<span data-ttu-id="e8974-152">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-152">Int32</span></span>|  
|<span data-ttu-id="e8974-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="e8974-153">FILTER_CONDITION</span></span>|<span data-ttu-id="e8974-154">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-154">String</span></span>|  
|<span data-ttu-id="e8974-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e8974-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="e8974-156">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-156">String</span></span>|  
|<span data-ttu-id="e8974-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="e8974-158">Byte</span><span class="sxs-lookup"><span data-stu-id="e8974-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e8974-159">Columns</span><span class="sxs-lookup"><span data-stu-id="e8974-159">Columns</span></span>  
  
|<span data-ttu-id="e8974-160">열 이름</span><span class="sxs-lookup"><span data-stu-id="e8974-160">ColumnName</span></span>|<span data-ttu-id="e8974-161">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8974-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e8974-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="e8974-162">TABLE_CAT</span></span>|<span data-ttu-id="e8974-163">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-163">String</span></span>|  
|<span data-ttu-id="e8974-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e8974-164">TABLE_SCHEM</span></span>|<span data-ttu-id="e8974-165">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-165">String</span></span>|  
|<span data-ttu-id="e8974-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-166">TABLE_NAME</span></span>|<span data-ttu-id="e8974-167">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-167">String</span></span>|  
|<span data-ttu-id="e8974-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-168">COLUMN_NAME</span></span>|<span data-ttu-id="e8974-169">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-169">String</span></span>|  
|<span data-ttu-id="e8974-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-170">DATA_TYPE</span></span>|<span data-ttu-id="e8974-171">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-171">Int16</span></span>|  
|<span data-ttu-id="e8974-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-172">TYPE_NAME</span></span>|<span data-ttu-id="e8974-173">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-173">String</span></span>|  
|<span data-ttu-id="e8974-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="e8974-174">COLUMN_SIZE</span></span>|<span data-ttu-id="e8974-175">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-175">Int32</span></span>|  
|<span data-ttu-id="e8974-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e8974-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="e8974-177">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-177">Int32</span></span>|  
|<span data-ttu-id="e8974-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="e8974-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="e8974-179">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-179">Int16</span></span>|  
|<span data-ttu-id="e8974-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="e8974-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="e8974-181">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-181">Int16</span></span>|  
|<span data-ttu-id="e8974-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e8974-182">NULLABLE</span></span>|<span data-ttu-id="e8974-183">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-183">Int16</span></span>|  
|<span data-ttu-id="e8974-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e8974-184">REMARKS</span></span>|<span data-ttu-id="e8974-185">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-185">String</span></span>|  
|<span data-ttu-id="e8974-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="e8974-186">COLUMN_DEF</span></span>|<span data-ttu-id="e8974-187">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-187">String</span></span>|  
|<span data-ttu-id="e8974-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="e8974-189">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-189">Int16</span></span>|  
|<span data-ttu-id="e8974-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="e8974-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="e8974-191">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-191">Int16</span></span>|  
|<span data-ttu-id="e8974-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e8974-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="e8974-193">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-193">Int32</span></span>|  
|<span data-ttu-id="e8974-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e8974-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="e8974-195">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-195">Int32</span></span>|  
|<span data-ttu-id="e8974-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e8974-196">IS_NULLABLE</span></span>|<span data-ttu-id="e8974-197">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-197">String</span></span>|  
|<span data-ttu-id="e8974-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e8974-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="e8974-199">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-199">String</span></span>|  
|<span data-ttu-id="e8974-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e8974-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="e8974-201">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-201">String</span></span>|  
|<span data-ttu-id="e8974-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="e8974-203">Byte</span><span class="sxs-lookup"><span data-stu-id="e8974-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e8974-204">절차</span><span class="sxs-lookup"><span data-stu-id="e8974-204">Procedures</span></span>  
  
|<span data-ttu-id="e8974-205">열 이름</span><span class="sxs-lookup"><span data-stu-id="e8974-205">ColumnName</span></span>|<span data-ttu-id="e8974-206">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8974-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e8974-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="e8974-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="e8974-208">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-208">String</span></span>|  
|<span data-ttu-id="e8974-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e8974-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="e8974-210">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-210">String</span></span>|  
|<span data-ttu-id="e8974-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="e8974-212">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-212">String</span></span>|  
|<span data-ttu-id="e8974-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e8974-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="e8974-214">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-214">Int32</span></span>|  
|<span data-ttu-id="e8974-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e8974-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="e8974-216">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-216">Int32</span></span>|  
|<span data-ttu-id="e8974-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="e8974-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="e8974-218">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-218">Int32</span></span>|  
|<span data-ttu-id="e8974-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e8974-219">REMARKS</span></span>|<span data-ttu-id="e8974-220">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-220">String</span></span>|  
|<span data-ttu-id="e8974-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e8974-222">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="e8974-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e8974-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="e8974-224">열 이름</span><span class="sxs-lookup"><span data-stu-id="e8974-224">ColumnName</span></span>|<span data-ttu-id="e8974-225">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8974-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e8974-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="e8974-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="e8974-227">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-227">String</span></span>|  
|<span data-ttu-id="e8974-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e8974-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="e8974-229">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-229">String</span></span>|  
|<span data-ttu-id="e8974-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="e8974-231">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-231">String</span></span>|  
|<span data-ttu-id="e8974-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-232">COLUMN_NAME</span></span>|<span data-ttu-id="e8974-233">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-233">String</span></span>|  
|<span data-ttu-id="e8974-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-234">COLUMN_TYPE</span></span>|<span data-ttu-id="e8974-235">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-235">Int16</span></span>|  
|<span data-ttu-id="e8974-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-236">DATA_TYPE</span></span>|<span data-ttu-id="e8974-237">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-237">Int16</span></span>|  
|<span data-ttu-id="e8974-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-238">TYPE_NAME</span></span>|<span data-ttu-id="e8974-239">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-239">String</span></span>|  
|<span data-ttu-id="e8974-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="e8974-240">COLUMN_SIZE</span></span>|<span data-ttu-id="e8974-241">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-241">Int32</span></span>|  
|<span data-ttu-id="e8974-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e8974-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="e8974-243">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-243">Int32</span></span>|  
|<span data-ttu-id="e8974-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="e8974-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="e8974-245">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-245">Int16</span></span>|  
|<span data-ttu-id="e8974-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="e8974-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="e8974-247">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-247">Int16</span></span>|  
|<span data-ttu-id="e8974-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e8974-248">NULLABLE</span></span>|<span data-ttu-id="e8974-249">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-249">Int16</span></span>|  
|<span data-ttu-id="e8974-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e8974-250">REMARKS</span></span>|<span data-ttu-id="e8974-251">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-251">String</span></span>|  
|<span data-ttu-id="e8974-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="e8974-252">COLUMN_DEF</span></span>|<span data-ttu-id="e8974-253">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-253">String</span></span>|  
|<span data-ttu-id="e8974-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="e8974-255">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-255">Int16</span></span>|  
|<span data-ttu-id="e8974-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="e8974-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="e8974-257">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-257">Int16</span></span>|  
|<span data-ttu-id="e8974-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e8974-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="e8974-259">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-259">Int32</span></span>|  
|<span data-ttu-id="e8974-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e8974-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="e8974-261">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-261">Int32</span></span>|  
|<span data-ttu-id="e8974-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e8974-262">IS_NULLABLE</span></span>|<span data-ttu-id="e8974-263">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-263">String</span></span>|  
|<span data-ttu-id="e8974-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e8974-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="e8974-265">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-265">String</span></span>|  
|<span data-ttu-id="e8974-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e8974-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="e8974-267">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-267">String</span></span>|  
|<span data-ttu-id="e8974-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="e8974-269">Byte</span><span class="sxs-lookup"><span data-stu-id="e8974-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="e8974-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e8974-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="e8974-271">열 이름</span><span class="sxs-lookup"><span data-stu-id="e8974-271">ColumnName</span></span>|<span data-ttu-id="e8974-272">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8974-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e8974-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="e8974-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="e8974-274">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-274">String</span></span>|  
|<span data-ttu-id="e8974-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e8974-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="e8974-276">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-276">String</span></span>|  
|<span data-ttu-id="e8974-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="e8974-278">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-278">String</span></span>|  
|<span data-ttu-id="e8974-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-279">COLUMN_NAME</span></span>|<span data-ttu-id="e8974-280">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-280">String</span></span>|  
|<span data-ttu-id="e8974-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-281">COLUMN_TYPE</span></span>|<span data-ttu-id="e8974-282">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-282">Int16</span></span>|  
|<span data-ttu-id="e8974-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-283">DATA_TYPE</span></span>|<span data-ttu-id="e8974-284">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-284">Int16</span></span>|  
|<span data-ttu-id="e8974-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-285">TYPE_NAME</span></span>|<span data-ttu-id="e8974-286">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-286">String</span></span>|  
|<span data-ttu-id="e8974-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="e8974-287">COLUMN_SIZE</span></span>|<span data-ttu-id="e8974-288">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-288">Int32</span></span>|  
|<span data-ttu-id="e8974-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e8974-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="e8974-290">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-290">Int32</span></span>|  
|<span data-ttu-id="e8974-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="e8974-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="e8974-292">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-292">Int16</span></span>|  
|<span data-ttu-id="e8974-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="e8974-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="e8974-294">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-294">Int16</span></span>|  
|<span data-ttu-id="e8974-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e8974-295">NULLABLE</span></span>|<span data-ttu-id="e8974-296">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-296">Int16</span></span>|  
|<span data-ttu-id="e8974-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e8974-297">REMARKS</span></span>|<span data-ttu-id="e8974-298">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-298">String</span></span>|  
|<span data-ttu-id="e8974-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="e8974-299">COLUMN_DEF</span></span>|<span data-ttu-id="e8974-300">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-300">String</span></span>|  
|<span data-ttu-id="e8974-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="e8974-302">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-302">Int16</span></span>|  
|<span data-ttu-id="e8974-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="e8974-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="e8974-304">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-304">Int16</span></span>|  
|<span data-ttu-id="e8974-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e8974-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="e8974-306">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-306">Int32</span></span>|  
|<span data-ttu-id="e8974-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e8974-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="e8974-308">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-308">Int32</span></span>|  
|<span data-ttu-id="e8974-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e8974-309">IS_NULLABLE</span></span>|<span data-ttu-id="e8974-310">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-310">String</span></span>|  
|<span data-ttu-id="e8974-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e8974-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="e8974-312">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-312">String</span></span>|  
|<span data-ttu-id="e8974-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e8974-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="e8974-314">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-314">String</span></span>|  
|<span data-ttu-id="e8974-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="e8974-316">Byte</span><span class="sxs-lookup"><span data-stu-id="e8974-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="e8974-317">Microsoft Oracle ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="e8974-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="e8974-318">Microsoft SQL Server Oracle ODBC Driver에서는 공통 스키마 컬렉션을 비롯 하 여 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e8974-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e8974-319">Tables</span><span class="sxs-lookup"><span data-stu-id="e8974-319">Tables</span></span>  
  
-   <span data-ttu-id="e8974-320">Columns</span><span class="sxs-lookup"><span data-stu-id="e8974-320">Columns</span></span>  
  
-   <span data-ttu-id="e8974-321">절차</span><span class="sxs-lookup"><span data-stu-id="e8974-321">Procedures</span></span>  
  
-   <span data-ttu-id="e8974-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e8974-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="e8974-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e8974-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="e8974-324">뷰</span><span class="sxs-lookup"><span data-stu-id="e8974-324">Views</span></span>  
  
-   <span data-ttu-id="e8974-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="e8974-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="e8974-326">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="e8974-326">Tables and Views</span></span>  
  
|<span data-ttu-id="e8974-327">열 이름</span><span class="sxs-lookup"><span data-stu-id="e8974-327">ColumnName</span></span>|<span data-ttu-id="e8974-328">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8974-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e8974-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e8974-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="e8974-330">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-330">String</span></span>|  
|<span data-ttu-id="e8974-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e8974-331">TABLE_OWNER</span></span>|<span data-ttu-id="e8974-332">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-332">String</span></span>|  
|<span data-ttu-id="e8974-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-333">TABLE_NAME</span></span>|<span data-ttu-id="e8974-334">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-334">String</span></span>|  
|<span data-ttu-id="e8974-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-335">TABLE_TYPE</span></span>|<span data-ttu-id="e8974-336">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-336">String</span></span>|  
|<span data-ttu-id="e8974-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e8974-337">REMARKS</span></span>|<span data-ttu-id="e8974-338">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e8974-339">Columns</span><span class="sxs-lookup"><span data-stu-id="e8974-339">Columns</span></span>  
  
|<span data-ttu-id="e8974-340">열 이름</span><span class="sxs-lookup"><span data-stu-id="e8974-340">ColumnName</span></span>|<span data-ttu-id="e8974-341">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8974-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e8974-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e8974-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="e8974-343">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-343">String</span></span>|  
|<span data-ttu-id="e8974-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e8974-344">TABLE_OWNER</span></span>|<span data-ttu-id="e8974-345">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-345">String</span></span>|  
|<span data-ttu-id="e8974-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-346">TABLE_NAME</span></span>|<span data-ttu-id="e8974-347">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-347">String</span></span>|  
|<span data-ttu-id="e8974-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-348">COLUMN_NAME</span></span>|<span data-ttu-id="e8974-349">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-349">String</span></span>|  
|<span data-ttu-id="e8974-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-350">DATA_TYPE</span></span>|<span data-ttu-id="e8974-351">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-351">Int16</span></span>|  
|<span data-ttu-id="e8974-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-352">TYPE_NAME</span></span>|<span data-ttu-id="e8974-353">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-353">String</span></span>|  
|<span data-ttu-id="e8974-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="e8974-354">PRECISION</span></span>|<span data-ttu-id="e8974-355">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-355">Int32</span></span>|  
|<span data-ttu-id="e8974-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="e8974-356">LENGTH</span></span>|<span data-ttu-id="e8974-357">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-357">Int32</span></span>|  
|<span data-ttu-id="e8974-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="e8974-358">SCALE</span></span>|<span data-ttu-id="e8974-359">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-359">Int16</span></span>|  
|<span data-ttu-id="e8974-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="e8974-360">RADIX</span></span>|<span data-ttu-id="e8974-361">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-361">Int16</span></span>|  
|<span data-ttu-id="e8974-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e8974-362">NULLABLE</span></span>|<span data-ttu-id="e8974-363">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-363">Int16</span></span>|  
|<span data-ttu-id="e8974-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e8974-364">REMARKS</span></span>|<span data-ttu-id="e8974-365">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-365">String</span></span>|  
|<span data-ttu-id="e8974-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e8974-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="e8974-367">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e8974-368">절차</span><span class="sxs-lookup"><span data-stu-id="e8974-368">Procedures</span></span>  
  
|<span data-ttu-id="e8974-369">열 이름</span><span class="sxs-lookup"><span data-stu-id="e8974-369">ColumnName</span></span>|<span data-ttu-id="e8974-370">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8974-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e8974-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e8974-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="e8974-372">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-372">String</span></span>|  
|<span data-ttu-id="e8974-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e8974-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="e8974-374">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-374">String</span></span>|  
|<span data-ttu-id="e8974-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="e8974-376">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-376">String</span></span>|  
|<span data-ttu-id="e8974-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e8974-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="e8974-378">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-378">Int16</span></span>|  
|<span data-ttu-id="e8974-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e8974-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="e8974-380">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-380">Int16</span></span>|  
|<span data-ttu-id="e8974-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="e8974-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="e8974-382">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-382">Int16</span></span>|  
|<span data-ttu-id="e8974-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e8974-383">REMARKS</span></span>|<span data-ttu-id="e8974-384">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-384">String</span></span>|  
|<span data-ttu-id="e8974-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e8974-386">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="e8974-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e8974-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="e8974-388">열 이름</span><span class="sxs-lookup"><span data-stu-id="e8974-388">ColumnName</span></span>|<span data-ttu-id="e8974-389">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8974-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e8974-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e8974-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="e8974-391">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-391">String</span></span>|  
|<span data-ttu-id="e8974-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e8974-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="e8974-393">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-393">String</span></span>|  
|<span data-ttu-id="e8974-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="e8974-395">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-395">String</span></span>|  
|<span data-ttu-id="e8974-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-396">COLUMN_NAME</span></span>|<span data-ttu-id="e8974-397">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-397">String</span></span>|  
|<span data-ttu-id="e8974-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-398">COLUMN_TYPE</span></span>|<span data-ttu-id="e8974-399">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-399">Int16</span></span>|  
|<span data-ttu-id="e8974-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-400">DATA_TYPE</span></span>|<span data-ttu-id="e8974-401">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-401">Int16</span></span>|  
|<span data-ttu-id="e8974-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-402">TYPE_NAME</span></span>|<span data-ttu-id="e8974-403">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-403">String</span></span>|  
|<span data-ttu-id="e8974-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="e8974-404">PRECISION</span></span>|<span data-ttu-id="e8974-405">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-405">Int32</span></span>|  
|<span data-ttu-id="e8974-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="e8974-406">LENGTH</span></span>|<span data-ttu-id="e8974-407">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-407">Int32</span></span>|  
|<span data-ttu-id="e8974-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="e8974-408">SCALE</span></span>|<span data-ttu-id="e8974-409">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-409">Int16</span></span>|  
|<span data-ttu-id="e8974-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="e8974-410">RADIX</span></span>|<span data-ttu-id="e8974-411">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-411">Int16</span></span>|  
|<span data-ttu-id="e8974-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e8974-412">NULLABLE</span></span>|<span data-ttu-id="e8974-413">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-413">Int16</span></span>|  
|<span data-ttu-id="e8974-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e8974-414">REMARKS</span></span>|<span data-ttu-id="e8974-415">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-415">String</span></span>|  
|<span data-ttu-id="e8974-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="e8974-416">OVERLOAD</span></span>|<span data-ttu-id="e8974-417">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-417">Int32</span></span>|  
|<span data-ttu-id="e8974-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e8974-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="e8974-419">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="e8974-420">Microsoft Jet ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="e8974-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="e8974-421">Microsoft Jet ODBC Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="e8974-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e8974-422">Tables</span><span class="sxs-lookup"><span data-stu-id="e8974-422">Tables</span></span>  
  
-   <span data-ttu-id="e8974-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="e8974-423">Indexes</span></span>  
  
-   <span data-ttu-id="e8974-424">Columns</span><span class="sxs-lookup"><span data-stu-id="e8974-424">Columns</span></span>  
  
-   <span data-ttu-id="e8974-425">절차</span><span class="sxs-lookup"><span data-stu-id="e8974-425">Procedures</span></span>  
  
-   <span data-ttu-id="e8974-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e8974-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="e8974-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e8974-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="e8974-428">뷰</span><span class="sxs-lookup"><span data-stu-id="e8974-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="e8974-429">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="e8974-429">Tables and Views</span></span>  
  
|<span data-ttu-id="e8974-430">열 이름</span><span class="sxs-lookup"><span data-stu-id="e8974-430">ColumnName</span></span>|<span data-ttu-id="e8974-431">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8974-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e8974-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e8974-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="e8974-433">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-433">String</span></span>|  
|<span data-ttu-id="e8974-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e8974-434">TABLE_OWNER</span></span>|<span data-ttu-id="e8974-435">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-435">String</span></span>|  
|<span data-ttu-id="e8974-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-436">TABLE_NAME</span></span>|<span data-ttu-id="e8974-437">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-437">String</span></span>|  
|<span data-ttu-id="e8974-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-438">TABLE_TYPE</span></span>|<span data-ttu-id="e8974-439">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-439">String</span></span>|  
|<span data-ttu-id="e8974-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e8974-440">REMARKS</span></span>|<span data-ttu-id="e8974-441">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e8974-442">Columns</span><span class="sxs-lookup"><span data-stu-id="e8974-442">Columns</span></span>  
  
|<span data-ttu-id="e8974-443">열 이름</span><span class="sxs-lookup"><span data-stu-id="e8974-443">ColumnName</span></span>|<span data-ttu-id="e8974-444">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8974-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e8974-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e8974-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="e8974-446">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-446">String</span></span>|  
|<span data-ttu-id="e8974-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e8974-447">TABLE_OWNER</span></span>|<span data-ttu-id="e8974-448">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-448">String</span></span>|  
|<span data-ttu-id="e8974-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-449">TABLE_NAME</span></span>|<span data-ttu-id="e8974-450">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-450">String</span></span>|  
|<span data-ttu-id="e8974-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-451">COLUMN_NAME</span></span>|<span data-ttu-id="e8974-452">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-452">String</span></span>|  
|<span data-ttu-id="e8974-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-453">DATA_TYPE</span></span>|<span data-ttu-id="e8974-454">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-454">Int16</span></span>|  
|<span data-ttu-id="e8974-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-455">TYPE_NAME</span></span>|<span data-ttu-id="e8974-456">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-456">String</span></span>|  
|<span data-ttu-id="e8974-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="e8974-457">PRECISION</span></span>|<span data-ttu-id="e8974-458">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-458">Int32</span></span>|  
|<span data-ttu-id="e8974-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="e8974-459">LENGTH</span></span>|<span data-ttu-id="e8974-460">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-460">Int32</span></span>|  
|<span data-ttu-id="e8974-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="e8974-461">SCALE</span></span>|<span data-ttu-id="e8974-462">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-462">Int16</span></span>|  
|<span data-ttu-id="e8974-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="e8974-463">RADIX</span></span>|<span data-ttu-id="e8974-464">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-464">Int16</span></span>|  
|<span data-ttu-id="e8974-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e8974-465">NULLABLE</span></span>|<span data-ttu-id="e8974-466">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-466">Int16</span></span>|  
|<span data-ttu-id="e8974-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e8974-467">REMARKS</span></span>|<span data-ttu-id="e8974-468">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-468">String</span></span>|  
|<span data-ttu-id="e8974-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e8974-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="e8974-470">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e8974-471">절차</span><span class="sxs-lookup"><span data-stu-id="e8974-471">Procedures</span></span>  
  
|<span data-ttu-id="e8974-472">열 이름</span><span class="sxs-lookup"><span data-stu-id="e8974-472">ColumnName</span></span>|<span data-ttu-id="e8974-473">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8974-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e8974-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e8974-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="e8974-475">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-475">String</span></span>|  
|<span data-ttu-id="e8974-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e8974-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="e8974-477">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-477">String</span></span>|  
|<span data-ttu-id="e8974-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="e8974-479">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-479">String</span></span>|  
|<span data-ttu-id="e8974-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e8974-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="e8974-481">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-481">Int16</span></span>|  
|<span data-ttu-id="e8974-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e8974-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="e8974-483">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-483">Int16</span></span>|  
|<span data-ttu-id="e8974-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="e8974-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="e8974-485">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-485">Int16</span></span>|  
|<span data-ttu-id="e8974-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e8974-486">REMARKS</span></span>|<span data-ttu-id="e8974-487">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-487">String</span></span>|  
|<span data-ttu-id="e8974-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e8974-489">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="e8974-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e8974-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="e8974-491">열 이름</span><span class="sxs-lookup"><span data-stu-id="e8974-491">ColumnName</span></span>|<span data-ttu-id="e8974-492">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8974-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e8974-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e8974-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="e8974-494">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-494">String</span></span>|  
|<span data-ttu-id="e8974-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e8974-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="e8974-496">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-496">String</span></span>|  
|<span data-ttu-id="e8974-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="e8974-498">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-498">String</span></span>|  
|<span data-ttu-id="e8974-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-499">COLUMN_NAME</span></span>|<span data-ttu-id="e8974-500">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-500">String</span></span>|  
|<span data-ttu-id="e8974-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-501">COLUMN_TYPE</span></span>|<span data-ttu-id="e8974-502">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-502">Int16</span></span>|  
|<span data-ttu-id="e8974-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-503">DATA_TYPE</span></span>|<span data-ttu-id="e8974-504">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-504">Int16</span></span>|  
|<span data-ttu-id="e8974-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-505">TYPE_NAME</span></span>|<span data-ttu-id="e8974-506">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-506">String</span></span>|  
|<span data-ttu-id="e8974-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="e8974-507">PRECISION</span></span>|<span data-ttu-id="e8974-508">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-508">Int32</span></span>|  
|<span data-ttu-id="e8974-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="e8974-509">LENGTH</span></span>|<span data-ttu-id="e8974-510">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-510">Int32</span></span>|  
|<span data-ttu-id="e8974-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="e8974-511">SCALE</span></span>|<span data-ttu-id="e8974-512">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-512">Int16</span></span>|  
|<span data-ttu-id="e8974-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="e8974-513">RADIX</span></span>|<span data-ttu-id="e8974-514">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-514">Int16</span></span>|  
|<span data-ttu-id="e8974-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e8974-515">NULLABLE</span></span>|<span data-ttu-id="e8974-516">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-516">Int16</span></span>|  
|<span data-ttu-id="e8974-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e8974-517">REMARKS</span></span>|<span data-ttu-id="e8974-518">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-518">String</span></span>|  
|<span data-ttu-id="e8974-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="e8974-519">OVERLOAD</span></span>|<span data-ttu-id="e8974-520">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-520">Int32</span></span>|  
|<span data-ttu-id="e8974-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e8974-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="e8974-522">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="e8974-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e8974-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="e8974-524">열 이름</span><span class="sxs-lookup"><span data-stu-id="e8974-524">ColumnName</span></span>|<span data-ttu-id="e8974-525">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8974-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e8974-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="e8974-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="e8974-527">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-527">String</span></span>|  
|<span data-ttu-id="e8974-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e8974-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="e8974-529">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-529">String</span></span>|  
|<span data-ttu-id="e8974-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="e8974-531">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-531">String</span></span>|  
|<span data-ttu-id="e8974-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-532">COLUMN_NAME</span></span>|<span data-ttu-id="e8974-533">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-533">String</span></span>|  
|<span data-ttu-id="e8974-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-534">COLUMN_TYPE</span></span>|<span data-ttu-id="e8974-535">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-535">Int16</span></span>|  
|<span data-ttu-id="e8974-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-536">DATA_TYPE</span></span>|<span data-ttu-id="e8974-537">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-537">Int16</span></span>|  
|<span data-ttu-id="e8974-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8974-538">TYPE_NAME</span></span>|<span data-ttu-id="e8974-539">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-539">String</span></span>|  
|<span data-ttu-id="e8974-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="e8974-540">COLUMN_SIZE</span></span>|<span data-ttu-id="e8974-541">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-541">Int32</span></span>|  
|<span data-ttu-id="e8974-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e8974-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="e8974-543">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-543">Int32</span></span>|  
|<span data-ttu-id="e8974-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="e8974-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="e8974-545">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-545">Int16</span></span>|  
|<span data-ttu-id="e8974-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="e8974-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="e8974-547">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-547">Int16</span></span>|  
|<span data-ttu-id="e8974-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e8974-548">NULLABLE</span></span>|<span data-ttu-id="e8974-549">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-549">Int16</span></span>|  
|<span data-ttu-id="e8974-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e8974-550">REMARKS</span></span>|<span data-ttu-id="e8974-551">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-551">String</span></span>|  
|<span data-ttu-id="e8974-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="e8974-552">COLUMN_DEF</span></span>|<span data-ttu-id="e8974-553">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-553">String</span></span>|  
|<span data-ttu-id="e8974-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8974-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="e8974-555">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-555">Int16</span></span>|  
|<span data-ttu-id="e8974-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="e8974-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="e8974-557">Int16</span><span class="sxs-lookup"><span data-stu-id="e8974-557">Int16</span></span>|  
|<span data-ttu-id="e8974-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e8974-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="e8974-559">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-559">Int32</span></span>|  
|<span data-ttu-id="e8974-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e8974-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="e8974-561">Int32</span><span class="sxs-lookup"><span data-stu-id="e8974-561">Int32</span></span>|  
|<span data-ttu-id="e8974-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e8974-562">IS_NULLABLE</span></span>|<span data-ttu-id="e8974-563">문자열</span><span class="sxs-lookup"><span data-stu-id="e8974-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8974-564">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8974-564">See Also</span></span>  
 [<span data-ttu-id="e8974-565">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="e8974-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
