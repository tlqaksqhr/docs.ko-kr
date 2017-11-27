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
ms.openlocfilehash: 889e84db39af1257d709ef049e18d4397ea700d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="926c1-102">ODBC 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="926c1-102">ODBC Schema Collections</span></span>
<span data-ttu-id="926c1-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 ODBC 드라이버에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="926c1-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="926c1-104">Microsoft SQL Server ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="926c1-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="926c1-105">Microsoft SQL Server ODBC Driver에서는 공통 스키마 컬렉션을 비롯 하 여 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="926c1-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="926c1-106">Tables</span><span class="sxs-lookup"><span data-stu-id="926c1-106">Tables</span></span>  
  
-   <span data-ttu-id="926c1-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="926c1-107">Indexes</span></span>  
  
-   <span data-ttu-id="926c1-108">Columns</span><span class="sxs-lookup"><span data-stu-id="926c1-108">Columns</span></span>  
  
-   <span data-ttu-id="926c1-109">절차</span><span class="sxs-lookup"><span data-stu-id="926c1-109">Procedures</span></span>  
  
-   <span data-ttu-id="926c1-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="926c1-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="926c1-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="926c1-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="926c1-112">뷰</span><span class="sxs-lookup"><span data-stu-id="926c1-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="926c1-113">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="926c1-113">Tables and Views</span></span>  
  
|<span data-ttu-id="926c1-114">열 이름</span><span class="sxs-lookup"><span data-stu-id="926c1-114">ColumnName</span></span>|<span data-ttu-id="926c1-115">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="926c1-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="926c1-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="926c1-116">TABLE_CAT</span></span>|<span data-ttu-id="926c1-117">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-117">String</span></span>|  
|<span data-ttu-id="926c1-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="926c1-118">TABLE_SCHEM</span></span>|<span data-ttu-id="926c1-119">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-119">String</span></span>|  
|<span data-ttu-id="926c1-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-120">TABLE_NAME</span></span>|<span data-ttu-id="926c1-121">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-121">String</span></span>|  
|<span data-ttu-id="926c1-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-122">TABLE_TYPE</span></span>|<span data-ttu-id="926c1-123">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-123">String</span></span>|  
|<span data-ttu-id="926c1-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="926c1-124">REMARKS</span></span>|<span data-ttu-id="926c1-125">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="926c1-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="926c1-126">Indexes</span></span>  
  
|<span data-ttu-id="926c1-127">열 이름</span><span class="sxs-lookup"><span data-stu-id="926c1-127">ColumnName</span></span>|<span data-ttu-id="926c1-128">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="926c1-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="926c1-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="926c1-129">TABLE_CAT</span></span>|<span data-ttu-id="926c1-130">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-130">String</span></span>|  
|<span data-ttu-id="926c1-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="926c1-131">TABLE_SCHEM</span></span>|<span data-ttu-id="926c1-132">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-132">String</span></span>|  
|<span data-ttu-id="926c1-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-133">TABLE_NAME</span></span>|<span data-ttu-id="926c1-134">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-134">String</span></span>|  
|<span data-ttu-id="926c1-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="926c1-135">NON_UNIQUE</span></span>|<span data-ttu-id="926c1-136">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-136">Int16</span></span>|  
|<span data-ttu-id="926c1-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="926c1-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="926c1-138">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-138">String</span></span>|  
|<span data-ttu-id="926c1-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-139">INDEX_NAME</span></span>|<span data-ttu-id="926c1-140">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-140">String</span></span>|  
|<span data-ttu-id="926c1-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-141">TYPE</span></span>|<span data-ttu-id="926c1-142">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-142">Int16</span></span>|  
|<span data-ttu-id="926c1-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="926c1-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="926c1-144">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-144">Int16</span></span>|  
|<span data-ttu-id="926c1-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-145">COLUMN_NAME</span></span>|<span data-ttu-id="926c1-146">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-146">String</span></span>|  
|<span data-ttu-id="926c1-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="926c1-147">ASC_OR_DESC</span></span>|<span data-ttu-id="926c1-148">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-148">String</span></span>|  
|<span data-ttu-id="926c1-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="926c1-149">CARDINATLITY</span></span>|<span data-ttu-id="926c1-150">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-150">Int32</span></span>|  
|<span data-ttu-id="926c1-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="926c1-151">PAGES</span></span>|<span data-ttu-id="926c1-152">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-152">Int32</span></span>|  
|<span data-ttu-id="926c1-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="926c1-153">FILTER_CONDITION</span></span>|<span data-ttu-id="926c1-154">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-154">String</span></span>|  
|<span data-ttu-id="926c1-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="926c1-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="926c1-156">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-156">String</span></span>|  
|<span data-ttu-id="926c1-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="926c1-158">Byte</span><span class="sxs-lookup"><span data-stu-id="926c1-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="926c1-159">Columns</span><span class="sxs-lookup"><span data-stu-id="926c1-159">Columns</span></span>  
  
|<span data-ttu-id="926c1-160">열 이름</span><span class="sxs-lookup"><span data-stu-id="926c1-160">ColumnName</span></span>|<span data-ttu-id="926c1-161">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="926c1-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="926c1-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="926c1-162">TABLE_CAT</span></span>|<span data-ttu-id="926c1-163">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-163">String</span></span>|  
|<span data-ttu-id="926c1-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="926c1-164">TABLE_SCHEM</span></span>|<span data-ttu-id="926c1-165">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-165">String</span></span>|  
|<span data-ttu-id="926c1-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-166">TABLE_NAME</span></span>|<span data-ttu-id="926c1-167">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-167">String</span></span>|  
|<span data-ttu-id="926c1-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-168">COLUMN_NAME</span></span>|<span data-ttu-id="926c1-169">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-169">String</span></span>|  
|<span data-ttu-id="926c1-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-170">DATA_TYPE</span></span>|<span data-ttu-id="926c1-171">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-171">Int16</span></span>|  
|<span data-ttu-id="926c1-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-172">TYPE_NAME</span></span>|<span data-ttu-id="926c1-173">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-173">String</span></span>|  
|<span data-ttu-id="926c1-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="926c1-174">COLUMN_SIZE</span></span>|<span data-ttu-id="926c1-175">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-175">Int32</span></span>|  
|<span data-ttu-id="926c1-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="926c1-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="926c1-177">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-177">Int32</span></span>|  
|<span data-ttu-id="926c1-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="926c1-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="926c1-179">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-179">Int16</span></span>|  
|<span data-ttu-id="926c1-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="926c1-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="926c1-181">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-181">Int16</span></span>|  
|<span data-ttu-id="926c1-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="926c1-182">NULLABLE</span></span>|<span data-ttu-id="926c1-183">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-183">Int16</span></span>|  
|<span data-ttu-id="926c1-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="926c1-184">REMARKS</span></span>|<span data-ttu-id="926c1-185">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-185">String</span></span>|  
|<span data-ttu-id="926c1-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="926c1-186">COLUMN_DEF</span></span>|<span data-ttu-id="926c1-187">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-187">String</span></span>|  
|<span data-ttu-id="926c1-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="926c1-189">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-189">Int16</span></span>|  
|<span data-ttu-id="926c1-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="926c1-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="926c1-191">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-191">Int16</span></span>|  
|<span data-ttu-id="926c1-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="926c1-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="926c1-193">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-193">Int32</span></span>|  
|<span data-ttu-id="926c1-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="926c1-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="926c1-195">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-195">Int32</span></span>|  
|<span data-ttu-id="926c1-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="926c1-196">IS_NULLABLE</span></span>|<span data-ttu-id="926c1-197">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-197">String</span></span>|  
|<span data-ttu-id="926c1-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="926c1-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="926c1-199">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-199">String</span></span>|  
|<span data-ttu-id="926c1-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="926c1-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="926c1-201">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-201">String</span></span>|  
|<span data-ttu-id="926c1-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="926c1-203">Byte</span><span class="sxs-lookup"><span data-stu-id="926c1-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="926c1-204">절차</span><span class="sxs-lookup"><span data-stu-id="926c1-204">Procedures</span></span>  
  
|<span data-ttu-id="926c1-205">열 이름</span><span class="sxs-lookup"><span data-stu-id="926c1-205">ColumnName</span></span>|<span data-ttu-id="926c1-206">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="926c1-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="926c1-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="926c1-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="926c1-208">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-208">String</span></span>|  
|<span data-ttu-id="926c1-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="926c1-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="926c1-210">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-210">String</span></span>|  
|<span data-ttu-id="926c1-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="926c1-212">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-212">String</span></span>|  
|<span data-ttu-id="926c1-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="926c1-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="926c1-214">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-214">Int32</span></span>|  
|<span data-ttu-id="926c1-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="926c1-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="926c1-216">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-216">Int32</span></span>|  
|<span data-ttu-id="926c1-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="926c1-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="926c1-218">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-218">Int32</span></span>|  
|<span data-ttu-id="926c1-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="926c1-219">REMARKS</span></span>|<span data-ttu-id="926c1-220">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-220">String</span></span>|  
|<span data-ttu-id="926c1-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="926c1-222">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="926c1-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="926c1-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="926c1-224">열 이름</span><span class="sxs-lookup"><span data-stu-id="926c1-224">ColumnName</span></span>|<span data-ttu-id="926c1-225">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="926c1-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="926c1-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="926c1-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="926c1-227">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-227">String</span></span>|  
|<span data-ttu-id="926c1-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="926c1-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="926c1-229">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-229">String</span></span>|  
|<span data-ttu-id="926c1-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="926c1-231">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-231">String</span></span>|  
|<span data-ttu-id="926c1-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-232">COLUMN_NAME</span></span>|<span data-ttu-id="926c1-233">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-233">String</span></span>|  
|<span data-ttu-id="926c1-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-234">COLUMN_TYPE</span></span>|<span data-ttu-id="926c1-235">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-235">Int16</span></span>|  
|<span data-ttu-id="926c1-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-236">DATA_TYPE</span></span>|<span data-ttu-id="926c1-237">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-237">Int16</span></span>|  
|<span data-ttu-id="926c1-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-238">TYPE_NAME</span></span>|<span data-ttu-id="926c1-239">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-239">String</span></span>|  
|<span data-ttu-id="926c1-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="926c1-240">COLUMN_SIZE</span></span>|<span data-ttu-id="926c1-241">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-241">Int32</span></span>|  
|<span data-ttu-id="926c1-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="926c1-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="926c1-243">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-243">Int32</span></span>|  
|<span data-ttu-id="926c1-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="926c1-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="926c1-245">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-245">Int16</span></span>|  
|<span data-ttu-id="926c1-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="926c1-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="926c1-247">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-247">Int16</span></span>|  
|<span data-ttu-id="926c1-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="926c1-248">NULLABLE</span></span>|<span data-ttu-id="926c1-249">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-249">Int16</span></span>|  
|<span data-ttu-id="926c1-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="926c1-250">REMARKS</span></span>|<span data-ttu-id="926c1-251">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-251">String</span></span>|  
|<span data-ttu-id="926c1-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="926c1-252">COLUMN_DEF</span></span>|<span data-ttu-id="926c1-253">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-253">String</span></span>|  
|<span data-ttu-id="926c1-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="926c1-255">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-255">Int16</span></span>|  
|<span data-ttu-id="926c1-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="926c1-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="926c1-257">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-257">Int16</span></span>|  
|<span data-ttu-id="926c1-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="926c1-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="926c1-259">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-259">Int32</span></span>|  
|<span data-ttu-id="926c1-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="926c1-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="926c1-261">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-261">Int32</span></span>|  
|<span data-ttu-id="926c1-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="926c1-262">IS_NULLABLE</span></span>|<span data-ttu-id="926c1-263">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-263">String</span></span>|  
|<span data-ttu-id="926c1-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="926c1-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="926c1-265">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-265">String</span></span>|  
|<span data-ttu-id="926c1-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="926c1-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="926c1-267">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-267">String</span></span>|  
|<span data-ttu-id="926c1-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="926c1-269">Byte</span><span class="sxs-lookup"><span data-stu-id="926c1-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="926c1-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="926c1-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="926c1-271">열 이름</span><span class="sxs-lookup"><span data-stu-id="926c1-271">ColumnName</span></span>|<span data-ttu-id="926c1-272">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="926c1-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="926c1-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="926c1-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="926c1-274">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-274">String</span></span>|  
|<span data-ttu-id="926c1-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="926c1-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="926c1-276">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-276">String</span></span>|  
|<span data-ttu-id="926c1-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="926c1-278">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-278">String</span></span>|  
|<span data-ttu-id="926c1-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-279">COLUMN_NAME</span></span>|<span data-ttu-id="926c1-280">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-280">String</span></span>|  
|<span data-ttu-id="926c1-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-281">COLUMN_TYPE</span></span>|<span data-ttu-id="926c1-282">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-282">Int16</span></span>|  
|<span data-ttu-id="926c1-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-283">DATA_TYPE</span></span>|<span data-ttu-id="926c1-284">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-284">Int16</span></span>|  
|<span data-ttu-id="926c1-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-285">TYPE_NAME</span></span>|<span data-ttu-id="926c1-286">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-286">String</span></span>|  
|<span data-ttu-id="926c1-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="926c1-287">COLUMN_SIZE</span></span>|<span data-ttu-id="926c1-288">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-288">Int32</span></span>|  
|<span data-ttu-id="926c1-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="926c1-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="926c1-290">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-290">Int32</span></span>|  
|<span data-ttu-id="926c1-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="926c1-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="926c1-292">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-292">Int16</span></span>|  
|<span data-ttu-id="926c1-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="926c1-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="926c1-294">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-294">Int16</span></span>|  
|<span data-ttu-id="926c1-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="926c1-295">NULLABLE</span></span>|<span data-ttu-id="926c1-296">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-296">Int16</span></span>|  
|<span data-ttu-id="926c1-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="926c1-297">REMARKS</span></span>|<span data-ttu-id="926c1-298">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-298">String</span></span>|  
|<span data-ttu-id="926c1-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="926c1-299">COLUMN_DEF</span></span>|<span data-ttu-id="926c1-300">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-300">String</span></span>|  
|<span data-ttu-id="926c1-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="926c1-302">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-302">Int16</span></span>|  
|<span data-ttu-id="926c1-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="926c1-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="926c1-304">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-304">Int16</span></span>|  
|<span data-ttu-id="926c1-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="926c1-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="926c1-306">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-306">Int32</span></span>|  
|<span data-ttu-id="926c1-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="926c1-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="926c1-308">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-308">Int32</span></span>|  
|<span data-ttu-id="926c1-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="926c1-309">IS_NULLABLE</span></span>|<span data-ttu-id="926c1-310">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-310">String</span></span>|  
|<span data-ttu-id="926c1-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="926c1-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="926c1-312">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-312">String</span></span>|  
|<span data-ttu-id="926c1-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="926c1-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="926c1-314">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-314">String</span></span>|  
|<span data-ttu-id="926c1-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="926c1-316">Byte</span><span class="sxs-lookup"><span data-stu-id="926c1-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="926c1-317">Microsoft Oracle ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="926c1-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="926c1-318">Microsoft SQL Server Oracle ODBC Driver에서는 공통 스키마 컬렉션을 비롯 하 여 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="926c1-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="926c1-319">Tables</span><span class="sxs-lookup"><span data-stu-id="926c1-319">Tables</span></span>  
  
-   <span data-ttu-id="926c1-320">Columns</span><span class="sxs-lookup"><span data-stu-id="926c1-320">Columns</span></span>  
  
-   <span data-ttu-id="926c1-321">절차</span><span class="sxs-lookup"><span data-stu-id="926c1-321">Procedures</span></span>  
  
-   <span data-ttu-id="926c1-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="926c1-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="926c1-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="926c1-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="926c1-324">뷰</span><span class="sxs-lookup"><span data-stu-id="926c1-324">Views</span></span>  
  
-   <span data-ttu-id="926c1-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="926c1-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="926c1-326">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="926c1-326">Tables and Views</span></span>  
  
|<span data-ttu-id="926c1-327">열 이름</span><span class="sxs-lookup"><span data-stu-id="926c1-327">ColumnName</span></span>|<span data-ttu-id="926c1-328">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="926c1-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="926c1-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="926c1-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="926c1-330">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-330">String</span></span>|  
|<span data-ttu-id="926c1-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="926c1-331">TABLE_OWNER</span></span>|<span data-ttu-id="926c1-332">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-332">String</span></span>|  
|<span data-ttu-id="926c1-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-333">TABLE_NAME</span></span>|<span data-ttu-id="926c1-334">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-334">String</span></span>|  
|<span data-ttu-id="926c1-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-335">TABLE_TYPE</span></span>|<span data-ttu-id="926c1-336">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-336">String</span></span>|  
|<span data-ttu-id="926c1-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="926c1-337">REMARKS</span></span>|<span data-ttu-id="926c1-338">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="926c1-339">Columns</span><span class="sxs-lookup"><span data-stu-id="926c1-339">Columns</span></span>  
  
|<span data-ttu-id="926c1-340">열 이름</span><span class="sxs-lookup"><span data-stu-id="926c1-340">ColumnName</span></span>|<span data-ttu-id="926c1-341">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="926c1-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="926c1-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="926c1-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="926c1-343">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-343">String</span></span>|  
|<span data-ttu-id="926c1-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="926c1-344">TABLE_OWNER</span></span>|<span data-ttu-id="926c1-345">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-345">String</span></span>|  
|<span data-ttu-id="926c1-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-346">TABLE_NAME</span></span>|<span data-ttu-id="926c1-347">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-347">String</span></span>|  
|<span data-ttu-id="926c1-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-348">COLUMN_NAME</span></span>|<span data-ttu-id="926c1-349">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-349">String</span></span>|  
|<span data-ttu-id="926c1-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-350">DATA_TYPE</span></span>|<span data-ttu-id="926c1-351">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-351">Int16</span></span>|  
|<span data-ttu-id="926c1-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-352">TYPE_NAME</span></span>|<span data-ttu-id="926c1-353">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-353">String</span></span>|  
|<span data-ttu-id="926c1-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="926c1-354">PRECISION</span></span>|<span data-ttu-id="926c1-355">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-355">Int32</span></span>|  
|<span data-ttu-id="926c1-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="926c1-356">LENGTH</span></span>|<span data-ttu-id="926c1-357">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-357">Int32</span></span>|  
|<span data-ttu-id="926c1-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="926c1-358">SCALE</span></span>|<span data-ttu-id="926c1-359">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-359">Int16</span></span>|  
|<span data-ttu-id="926c1-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="926c1-360">RADIX</span></span>|<span data-ttu-id="926c1-361">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-361">Int16</span></span>|  
|<span data-ttu-id="926c1-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="926c1-362">NULLABLE</span></span>|<span data-ttu-id="926c1-363">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-363">Int16</span></span>|  
|<span data-ttu-id="926c1-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="926c1-364">REMARKS</span></span>|<span data-ttu-id="926c1-365">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-365">String</span></span>|  
|<span data-ttu-id="926c1-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="926c1-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="926c1-367">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="926c1-368">절차</span><span class="sxs-lookup"><span data-stu-id="926c1-368">Procedures</span></span>  
  
|<span data-ttu-id="926c1-369">열 이름</span><span class="sxs-lookup"><span data-stu-id="926c1-369">ColumnName</span></span>|<span data-ttu-id="926c1-370">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="926c1-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="926c1-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="926c1-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="926c1-372">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-372">String</span></span>|  
|<span data-ttu-id="926c1-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="926c1-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="926c1-374">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-374">String</span></span>|  
|<span data-ttu-id="926c1-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="926c1-376">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-376">String</span></span>|  
|<span data-ttu-id="926c1-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="926c1-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="926c1-378">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-378">Int16</span></span>|  
|<span data-ttu-id="926c1-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="926c1-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="926c1-380">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-380">Int16</span></span>|  
|<span data-ttu-id="926c1-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="926c1-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="926c1-382">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-382">Int16</span></span>|  
|<span data-ttu-id="926c1-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="926c1-383">REMARKS</span></span>|<span data-ttu-id="926c1-384">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-384">String</span></span>|  
|<span data-ttu-id="926c1-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="926c1-386">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="926c1-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="926c1-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="926c1-388">열 이름</span><span class="sxs-lookup"><span data-stu-id="926c1-388">ColumnName</span></span>|<span data-ttu-id="926c1-389">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="926c1-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="926c1-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="926c1-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="926c1-391">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-391">String</span></span>|  
|<span data-ttu-id="926c1-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="926c1-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="926c1-393">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-393">String</span></span>|  
|<span data-ttu-id="926c1-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="926c1-395">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-395">String</span></span>|  
|<span data-ttu-id="926c1-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-396">COLUMN_NAME</span></span>|<span data-ttu-id="926c1-397">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-397">String</span></span>|  
|<span data-ttu-id="926c1-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-398">COLUMN_TYPE</span></span>|<span data-ttu-id="926c1-399">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-399">Int16</span></span>|  
|<span data-ttu-id="926c1-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-400">DATA_TYPE</span></span>|<span data-ttu-id="926c1-401">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-401">Int16</span></span>|  
|<span data-ttu-id="926c1-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-402">TYPE_NAME</span></span>|<span data-ttu-id="926c1-403">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-403">String</span></span>|  
|<span data-ttu-id="926c1-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="926c1-404">PRECISION</span></span>|<span data-ttu-id="926c1-405">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-405">Int32</span></span>|  
|<span data-ttu-id="926c1-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="926c1-406">LENGTH</span></span>|<span data-ttu-id="926c1-407">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-407">Int32</span></span>|  
|<span data-ttu-id="926c1-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="926c1-408">SCALE</span></span>|<span data-ttu-id="926c1-409">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-409">Int16</span></span>|  
|<span data-ttu-id="926c1-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="926c1-410">RADIX</span></span>|<span data-ttu-id="926c1-411">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-411">Int16</span></span>|  
|<span data-ttu-id="926c1-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="926c1-412">NULLABLE</span></span>|<span data-ttu-id="926c1-413">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-413">Int16</span></span>|  
|<span data-ttu-id="926c1-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="926c1-414">REMARKS</span></span>|<span data-ttu-id="926c1-415">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-415">String</span></span>|  
|<span data-ttu-id="926c1-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="926c1-416">OVERLOAD</span></span>|<span data-ttu-id="926c1-417">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-417">Int32</span></span>|  
|<span data-ttu-id="926c1-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="926c1-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="926c1-419">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="926c1-420">Microsoft Jet ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="926c1-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="926c1-421">Microsoft Jet ODBC Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="926c1-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="926c1-422">Tables</span><span class="sxs-lookup"><span data-stu-id="926c1-422">Tables</span></span>  
  
-   <span data-ttu-id="926c1-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="926c1-423">Indexes</span></span>  
  
-   <span data-ttu-id="926c1-424">Columns</span><span class="sxs-lookup"><span data-stu-id="926c1-424">Columns</span></span>  
  
-   <span data-ttu-id="926c1-425">절차</span><span class="sxs-lookup"><span data-stu-id="926c1-425">Procedures</span></span>  
  
-   <span data-ttu-id="926c1-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="926c1-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="926c1-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="926c1-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="926c1-428">뷰</span><span class="sxs-lookup"><span data-stu-id="926c1-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="926c1-429">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="926c1-429">Tables and Views</span></span>  
  
|<span data-ttu-id="926c1-430">열 이름</span><span class="sxs-lookup"><span data-stu-id="926c1-430">ColumnName</span></span>|<span data-ttu-id="926c1-431">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="926c1-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="926c1-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="926c1-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="926c1-433">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-433">String</span></span>|  
|<span data-ttu-id="926c1-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="926c1-434">TABLE_OWNER</span></span>|<span data-ttu-id="926c1-435">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-435">String</span></span>|  
|<span data-ttu-id="926c1-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-436">TABLE_NAME</span></span>|<span data-ttu-id="926c1-437">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-437">String</span></span>|  
|<span data-ttu-id="926c1-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-438">TABLE_TYPE</span></span>|<span data-ttu-id="926c1-439">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-439">String</span></span>|  
|<span data-ttu-id="926c1-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="926c1-440">REMARKS</span></span>|<span data-ttu-id="926c1-441">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="926c1-442">Columns</span><span class="sxs-lookup"><span data-stu-id="926c1-442">Columns</span></span>  
  
|<span data-ttu-id="926c1-443">열 이름</span><span class="sxs-lookup"><span data-stu-id="926c1-443">ColumnName</span></span>|<span data-ttu-id="926c1-444">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="926c1-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="926c1-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="926c1-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="926c1-446">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-446">String</span></span>|  
|<span data-ttu-id="926c1-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="926c1-447">TABLE_OWNER</span></span>|<span data-ttu-id="926c1-448">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-448">String</span></span>|  
|<span data-ttu-id="926c1-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-449">TABLE_NAME</span></span>|<span data-ttu-id="926c1-450">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-450">String</span></span>|  
|<span data-ttu-id="926c1-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-451">COLUMN_NAME</span></span>|<span data-ttu-id="926c1-452">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-452">String</span></span>|  
|<span data-ttu-id="926c1-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-453">DATA_TYPE</span></span>|<span data-ttu-id="926c1-454">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-454">Int16</span></span>|  
|<span data-ttu-id="926c1-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-455">TYPE_NAME</span></span>|<span data-ttu-id="926c1-456">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-456">String</span></span>|  
|<span data-ttu-id="926c1-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="926c1-457">PRECISION</span></span>|<span data-ttu-id="926c1-458">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-458">Int32</span></span>|  
|<span data-ttu-id="926c1-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="926c1-459">LENGTH</span></span>|<span data-ttu-id="926c1-460">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-460">Int32</span></span>|  
|<span data-ttu-id="926c1-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="926c1-461">SCALE</span></span>|<span data-ttu-id="926c1-462">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-462">Int16</span></span>|  
|<span data-ttu-id="926c1-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="926c1-463">RADIX</span></span>|<span data-ttu-id="926c1-464">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-464">Int16</span></span>|  
|<span data-ttu-id="926c1-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="926c1-465">NULLABLE</span></span>|<span data-ttu-id="926c1-466">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-466">Int16</span></span>|  
|<span data-ttu-id="926c1-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="926c1-467">REMARKS</span></span>|<span data-ttu-id="926c1-468">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-468">String</span></span>|  
|<span data-ttu-id="926c1-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="926c1-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="926c1-470">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="926c1-471">절차</span><span class="sxs-lookup"><span data-stu-id="926c1-471">Procedures</span></span>  
  
|<span data-ttu-id="926c1-472">열 이름</span><span class="sxs-lookup"><span data-stu-id="926c1-472">ColumnName</span></span>|<span data-ttu-id="926c1-473">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="926c1-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="926c1-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="926c1-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="926c1-475">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-475">String</span></span>|  
|<span data-ttu-id="926c1-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="926c1-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="926c1-477">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-477">String</span></span>|  
|<span data-ttu-id="926c1-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="926c1-479">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-479">String</span></span>|  
|<span data-ttu-id="926c1-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="926c1-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="926c1-481">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-481">Int16</span></span>|  
|<span data-ttu-id="926c1-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="926c1-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="926c1-483">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-483">Int16</span></span>|  
|<span data-ttu-id="926c1-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="926c1-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="926c1-485">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-485">Int16</span></span>|  
|<span data-ttu-id="926c1-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="926c1-486">REMARKS</span></span>|<span data-ttu-id="926c1-487">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-487">String</span></span>|  
|<span data-ttu-id="926c1-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="926c1-489">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="926c1-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="926c1-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="926c1-491">열 이름</span><span class="sxs-lookup"><span data-stu-id="926c1-491">ColumnName</span></span>|<span data-ttu-id="926c1-492">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="926c1-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="926c1-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="926c1-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="926c1-494">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-494">String</span></span>|  
|<span data-ttu-id="926c1-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="926c1-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="926c1-496">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-496">String</span></span>|  
|<span data-ttu-id="926c1-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="926c1-498">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-498">String</span></span>|  
|<span data-ttu-id="926c1-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-499">COLUMN_NAME</span></span>|<span data-ttu-id="926c1-500">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-500">String</span></span>|  
|<span data-ttu-id="926c1-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-501">COLUMN_TYPE</span></span>|<span data-ttu-id="926c1-502">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-502">Int16</span></span>|  
|<span data-ttu-id="926c1-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-503">DATA_TYPE</span></span>|<span data-ttu-id="926c1-504">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-504">Int16</span></span>|  
|<span data-ttu-id="926c1-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-505">TYPE_NAME</span></span>|<span data-ttu-id="926c1-506">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-506">String</span></span>|  
|<span data-ttu-id="926c1-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="926c1-507">PRECISION</span></span>|<span data-ttu-id="926c1-508">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-508">Int32</span></span>|  
|<span data-ttu-id="926c1-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="926c1-509">LENGTH</span></span>|<span data-ttu-id="926c1-510">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-510">Int32</span></span>|  
|<span data-ttu-id="926c1-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="926c1-511">SCALE</span></span>|<span data-ttu-id="926c1-512">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-512">Int16</span></span>|  
|<span data-ttu-id="926c1-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="926c1-513">RADIX</span></span>|<span data-ttu-id="926c1-514">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-514">Int16</span></span>|  
|<span data-ttu-id="926c1-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="926c1-515">NULLABLE</span></span>|<span data-ttu-id="926c1-516">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-516">Int16</span></span>|  
|<span data-ttu-id="926c1-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="926c1-517">REMARKS</span></span>|<span data-ttu-id="926c1-518">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-518">String</span></span>|  
|<span data-ttu-id="926c1-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="926c1-519">OVERLOAD</span></span>|<span data-ttu-id="926c1-520">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-520">Int32</span></span>|  
|<span data-ttu-id="926c1-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="926c1-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="926c1-522">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="926c1-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="926c1-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="926c1-524">열 이름</span><span class="sxs-lookup"><span data-stu-id="926c1-524">ColumnName</span></span>|<span data-ttu-id="926c1-525">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="926c1-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="926c1-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="926c1-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="926c1-527">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-527">String</span></span>|  
|<span data-ttu-id="926c1-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="926c1-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="926c1-529">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-529">String</span></span>|  
|<span data-ttu-id="926c1-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="926c1-531">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-531">String</span></span>|  
|<span data-ttu-id="926c1-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-532">COLUMN_NAME</span></span>|<span data-ttu-id="926c1-533">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-533">String</span></span>|  
|<span data-ttu-id="926c1-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-534">COLUMN_TYPE</span></span>|<span data-ttu-id="926c1-535">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-535">Int16</span></span>|  
|<span data-ttu-id="926c1-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-536">DATA_TYPE</span></span>|<span data-ttu-id="926c1-537">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-537">Int16</span></span>|  
|<span data-ttu-id="926c1-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="926c1-538">TYPE_NAME</span></span>|<span data-ttu-id="926c1-539">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-539">String</span></span>|  
|<span data-ttu-id="926c1-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="926c1-540">COLUMN_SIZE</span></span>|<span data-ttu-id="926c1-541">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-541">Int32</span></span>|  
|<span data-ttu-id="926c1-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="926c1-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="926c1-543">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-543">Int32</span></span>|  
|<span data-ttu-id="926c1-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="926c1-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="926c1-545">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-545">Int16</span></span>|  
|<span data-ttu-id="926c1-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="926c1-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="926c1-547">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-547">Int16</span></span>|  
|<span data-ttu-id="926c1-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="926c1-548">NULLABLE</span></span>|<span data-ttu-id="926c1-549">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-549">Int16</span></span>|  
|<span data-ttu-id="926c1-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="926c1-550">REMARKS</span></span>|<span data-ttu-id="926c1-551">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-551">String</span></span>|  
|<span data-ttu-id="926c1-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="926c1-552">COLUMN_DEF</span></span>|<span data-ttu-id="926c1-553">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-553">String</span></span>|  
|<span data-ttu-id="926c1-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="926c1-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="926c1-555">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-555">Int16</span></span>|  
|<span data-ttu-id="926c1-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="926c1-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="926c1-557">Int16</span><span class="sxs-lookup"><span data-stu-id="926c1-557">Int16</span></span>|  
|<span data-ttu-id="926c1-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="926c1-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="926c1-559">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-559">Int32</span></span>|  
|<span data-ttu-id="926c1-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="926c1-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="926c1-561">Int32</span><span class="sxs-lookup"><span data-stu-id="926c1-561">Int32</span></span>|  
|<span data-ttu-id="926c1-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="926c1-562">IS_NULLABLE</span></span>|<span data-ttu-id="926c1-563">문자열</span><span class="sxs-lookup"><span data-stu-id="926c1-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="926c1-564">참고 항목</span><span class="sxs-lookup"><span data-stu-id="926c1-564">See Also</span></span>  
 [<span data-ttu-id="926c1-565">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="926c1-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
