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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 45cfed80decc2336c5a2bacf24fd075c2b81c531
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="3f8c5-102">ODBC 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="3f8c5-102">ODBC Schema Collections</span></span>
<span data-ttu-id="3f8c5-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 ODBC 드라이버에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8c5-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="3f8c5-104">Microsoft SQL Server ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="3f8c5-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="3f8c5-105">Microsoft SQL Server ODBC Driver에서는 공통 스키마 컬렉션을 비롯 하 여 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8c5-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="3f8c5-106">Tables</span><span class="sxs-lookup"><span data-stu-id="3f8c5-106">Tables</span></span>  
  
-   <span data-ttu-id="3f8c5-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="3f8c5-107">Indexes</span></span>  
  
-   <span data-ttu-id="3f8c5-108">Columns</span><span class="sxs-lookup"><span data-stu-id="3f8c5-108">Columns</span></span>  
  
-   <span data-ttu-id="3f8c5-109">절차</span><span class="sxs-lookup"><span data-stu-id="3f8c5-109">Procedures</span></span>  
  
-   <span data-ttu-id="3f8c5-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3f8c5-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="3f8c5-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3f8c5-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="3f8c5-112">뷰</span><span class="sxs-lookup"><span data-stu-id="3f8c5-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="3f8c5-113">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="3f8c5-113">Tables and Views</span></span>  
  
|<span data-ttu-id="3f8c5-114">열 이름</span><span class="sxs-lookup"><span data-stu-id="3f8c5-114">ColumnName</span></span>|<span data-ttu-id="3f8c5-115">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f8c5-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3f8c5-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="3f8c5-116">TABLE_CAT</span></span>|<span data-ttu-id="3f8c5-117">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-117">String</span></span>|  
|<span data-ttu-id="3f8c5-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3f8c5-118">TABLE_SCHEM</span></span>|<span data-ttu-id="3f8c5-119">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-119">String</span></span>|  
|<span data-ttu-id="3f8c5-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-120">TABLE_NAME</span></span>|<span data-ttu-id="3f8c5-121">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-121">String</span></span>|  
|<span data-ttu-id="3f8c5-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-122">TABLE_TYPE</span></span>|<span data-ttu-id="3f8c5-123">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-123">String</span></span>|  
|<span data-ttu-id="3f8c5-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-124">REMARKS</span></span>|<span data-ttu-id="3f8c5-125">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="3f8c5-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="3f8c5-126">Indexes</span></span>  
  
|<span data-ttu-id="3f8c5-127">열 이름</span><span class="sxs-lookup"><span data-stu-id="3f8c5-127">ColumnName</span></span>|<span data-ttu-id="3f8c5-128">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f8c5-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3f8c5-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="3f8c5-129">TABLE_CAT</span></span>|<span data-ttu-id="3f8c5-130">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-130">String</span></span>|  
|<span data-ttu-id="3f8c5-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3f8c5-131">TABLE_SCHEM</span></span>|<span data-ttu-id="3f8c5-132">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-132">String</span></span>|  
|<span data-ttu-id="3f8c5-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-133">TABLE_NAME</span></span>|<span data-ttu-id="3f8c5-134">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-134">String</span></span>|  
|<span data-ttu-id="3f8c5-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-135">NON_UNIQUE</span></span>|<span data-ttu-id="3f8c5-136">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-136">Int16</span></span>|  
|<span data-ttu-id="3f8c5-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="3f8c5-138">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-138">String</span></span>|  
|<span data-ttu-id="3f8c5-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-139">INDEX_NAME</span></span>|<span data-ttu-id="3f8c5-140">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-140">String</span></span>|  
|<span data-ttu-id="3f8c5-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-141">TYPE</span></span>|<span data-ttu-id="3f8c5-142">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-142">Int16</span></span>|  
|<span data-ttu-id="3f8c5-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3f8c5-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="3f8c5-144">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-144">Int16</span></span>|  
|<span data-ttu-id="3f8c5-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-145">COLUMN_NAME</span></span>|<span data-ttu-id="3f8c5-146">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-146">String</span></span>|  
|<span data-ttu-id="3f8c5-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="3f8c5-147">ASC_OR_DESC</span></span>|<span data-ttu-id="3f8c5-148">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-148">String</span></span>|  
|<span data-ttu-id="3f8c5-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="3f8c5-149">CARDINATLITY</span></span>|<span data-ttu-id="3f8c5-150">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-150">Int32</span></span>|  
|<span data-ttu-id="3f8c5-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="3f8c5-151">PAGES</span></span>|<span data-ttu-id="3f8c5-152">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-152">Int32</span></span>|  
|<span data-ttu-id="3f8c5-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="3f8c5-153">FILTER_CONDITION</span></span>|<span data-ttu-id="3f8c5-154">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-154">String</span></span>|  
|<span data-ttu-id="3f8c5-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3f8c5-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="3f8c5-156">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-156">String</span></span>|  
|<span data-ttu-id="3f8c5-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="3f8c5-158">Byte</span><span class="sxs-lookup"><span data-stu-id="3f8c5-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="3f8c5-159">Columns</span><span class="sxs-lookup"><span data-stu-id="3f8c5-159">Columns</span></span>  
  
|<span data-ttu-id="3f8c5-160">열 이름</span><span class="sxs-lookup"><span data-stu-id="3f8c5-160">ColumnName</span></span>|<span data-ttu-id="3f8c5-161">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f8c5-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3f8c5-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="3f8c5-162">TABLE_CAT</span></span>|<span data-ttu-id="3f8c5-163">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-163">String</span></span>|  
|<span data-ttu-id="3f8c5-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3f8c5-164">TABLE_SCHEM</span></span>|<span data-ttu-id="3f8c5-165">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-165">String</span></span>|  
|<span data-ttu-id="3f8c5-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-166">TABLE_NAME</span></span>|<span data-ttu-id="3f8c5-167">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-167">String</span></span>|  
|<span data-ttu-id="3f8c5-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-168">COLUMN_NAME</span></span>|<span data-ttu-id="3f8c5-169">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-169">String</span></span>|  
|<span data-ttu-id="3f8c5-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-170">DATA_TYPE</span></span>|<span data-ttu-id="3f8c5-171">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-171">Int16</span></span>|  
|<span data-ttu-id="3f8c5-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-172">TYPE_NAME</span></span>|<span data-ttu-id="3f8c5-173">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-173">String</span></span>|  
|<span data-ttu-id="3f8c5-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-174">COLUMN_SIZE</span></span>|<span data-ttu-id="3f8c5-175">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-175">Int32</span></span>|  
|<span data-ttu-id="3f8c5-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3f8c5-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="3f8c5-177">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-177">Int32</span></span>|  
|<span data-ttu-id="3f8c5-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="3f8c5-179">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-179">Int16</span></span>|  
|<span data-ttu-id="3f8c5-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="3f8c5-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="3f8c5-181">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-181">Int16</span></span>|  
|<span data-ttu-id="3f8c5-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-182">NULLABLE</span></span>|<span data-ttu-id="3f8c5-183">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-183">Int16</span></span>|  
|<span data-ttu-id="3f8c5-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-184">REMARKS</span></span>|<span data-ttu-id="3f8c5-185">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-185">String</span></span>|  
|<span data-ttu-id="3f8c5-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="3f8c5-186">COLUMN_DEF</span></span>|<span data-ttu-id="3f8c5-187">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-187">String</span></span>|  
|<span data-ttu-id="3f8c5-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="3f8c5-189">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-189">Int16</span></span>|  
|<span data-ttu-id="3f8c5-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="3f8c5-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="3f8c5-191">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-191">Int16</span></span>|  
|<span data-ttu-id="3f8c5-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3f8c5-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="3f8c5-193">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-193">Int32</span></span>|  
|<span data-ttu-id="3f8c5-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3f8c5-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="3f8c5-195">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-195">Int32</span></span>|  
|<span data-ttu-id="3f8c5-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-196">IS_NULLABLE</span></span>|<span data-ttu-id="3f8c5-197">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-197">String</span></span>|  
|<span data-ttu-id="3f8c5-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3f8c5-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="3f8c5-199">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-199">String</span></span>|  
|<span data-ttu-id="3f8c5-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3f8c5-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="3f8c5-201">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-201">String</span></span>|  
|<span data-ttu-id="3f8c5-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="3f8c5-203">Byte</span><span class="sxs-lookup"><span data-stu-id="3f8c5-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="3f8c5-204">절차</span><span class="sxs-lookup"><span data-stu-id="3f8c5-204">Procedures</span></span>  
  
|<span data-ttu-id="3f8c5-205">열 이름</span><span class="sxs-lookup"><span data-stu-id="3f8c5-205">ColumnName</span></span>|<span data-ttu-id="3f8c5-206">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f8c5-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3f8c5-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="3f8c5-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="3f8c5-208">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-208">String</span></span>|  
|<span data-ttu-id="3f8c5-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3f8c5-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="3f8c5-210">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-210">String</span></span>|  
|<span data-ttu-id="3f8c5-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="3f8c5-212">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-212">String</span></span>|  
|<span data-ttu-id="3f8c5-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="3f8c5-214">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-214">Int32</span></span>|  
|<span data-ttu-id="3f8c5-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="3f8c5-216">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-216">Int32</span></span>|  
|<span data-ttu-id="3f8c5-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="3f8c5-218">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-218">Int32</span></span>|  
|<span data-ttu-id="3f8c5-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-219">REMARKS</span></span>|<span data-ttu-id="3f8c5-220">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-220">String</span></span>|  
|<span data-ttu-id="3f8c5-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="3f8c5-222">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="3f8c5-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3f8c5-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="3f8c5-224">열 이름</span><span class="sxs-lookup"><span data-stu-id="3f8c5-224">ColumnName</span></span>|<span data-ttu-id="3f8c5-225">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f8c5-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3f8c5-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="3f8c5-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="3f8c5-227">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-227">String</span></span>|  
|<span data-ttu-id="3f8c5-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3f8c5-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="3f8c5-229">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-229">String</span></span>|  
|<span data-ttu-id="3f8c5-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="3f8c5-231">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-231">String</span></span>|  
|<span data-ttu-id="3f8c5-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-232">COLUMN_NAME</span></span>|<span data-ttu-id="3f8c5-233">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-233">String</span></span>|  
|<span data-ttu-id="3f8c5-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-234">COLUMN_TYPE</span></span>|<span data-ttu-id="3f8c5-235">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-235">Int16</span></span>|  
|<span data-ttu-id="3f8c5-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-236">DATA_TYPE</span></span>|<span data-ttu-id="3f8c5-237">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-237">Int16</span></span>|  
|<span data-ttu-id="3f8c5-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-238">TYPE_NAME</span></span>|<span data-ttu-id="3f8c5-239">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-239">String</span></span>|  
|<span data-ttu-id="3f8c5-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-240">COLUMN_SIZE</span></span>|<span data-ttu-id="3f8c5-241">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-241">Int32</span></span>|  
|<span data-ttu-id="3f8c5-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3f8c5-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="3f8c5-243">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-243">Int32</span></span>|  
|<span data-ttu-id="3f8c5-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="3f8c5-245">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-245">Int16</span></span>|  
|<span data-ttu-id="3f8c5-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="3f8c5-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="3f8c5-247">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-247">Int16</span></span>|  
|<span data-ttu-id="3f8c5-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-248">NULLABLE</span></span>|<span data-ttu-id="3f8c5-249">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-249">Int16</span></span>|  
|<span data-ttu-id="3f8c5-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-250">REMARKS</span></span>|<span data-ttu-id="3f8c5-251">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-251">String</span></span>|  
|<span data-ttu-id="3f8c5-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="3f8c5-252">COLUMN_DEF</span></span>|<span data-ttu-id="3f8c5-253">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-253">String</span></span>|  
|<span data-ttu-id="3f8c5-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="3f8c5-255">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-255">Int16</span></span>|  
|<span data-ttu-id="3f8c5-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="3f8c5-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="3f8c5-257">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-257">Int16</span></span>|  
|<span data-ttu-id="3f8c5-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3f8c5-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="3f8c5-259">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-259">Int32</span></span>|  
|<span data-ttu-id="3f8c5-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3f8c5-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="3f8c5-261">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-261">Int32</span></span>|  
|<span data-ttu-id="3f8c5-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-262">IS_NULLABLE</span></span>|<span data-ttu-id="3f8c5-263">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-263">String</span></span>|  
|<span data-ttu-id="3f8c5-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3f8c5-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="3f8c5-265">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-265">String</span></span>|  
|<span data-ttu-id="3f8c5-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3f8c5-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="3f8c5-267">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-267">String</span></span>|  
|<span data-ttu-id="3f8c5-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="3f8c5-269">Byte</span><span class="sxs-lookup"><span data-stu-id="3f8c5-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="3f8c5-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3f8c5-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="3f8c5-271">열 이름</span><span class="sxs-lookup"><span data-stu-id="3f8c5-271">ColumnName</span></span>|<span data-ttu-id="3f8c5-272">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f8c5-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3f8c5-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="3f8c5-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="3f8c5-274">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-274">String</span></span>|  
|<span data-ttu-id="3f8c5-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3f8c5-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="3f8c5-276">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-276">String</span></span>|  
|<span data-ttu-id="3f8c5-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="3f8c5-278">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-278">String</span></span>|  
|<span data-ttu-id="3f8c5-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-279">COLUMN_NAME</span></span>|<span data-ttu-id="3f8c5-280">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-280">String</span></span>|  
|<span data-ttu-id="3f8c5-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-281">COLUMN_TYPE</span></span>|<span data-ttu-id="3f8c5-282">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-282">Int16</span></span>|  
|<span data-ttu-id="3f8c5-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-283">DATA_TYPE</span></span>|<span data-ttu-id="3f8c5-284">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-284">Int16</span></span>|  
|<span data-ttu-id="3f8c5-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-285">TYPE_NAME</span></span>|<span data-ttu-id="3f8c5-286">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-286">String</span></span>|  
|<span data-ttu-id="3f8c5-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-287">COLUMN_SIZE</span></span>|<span data-ttu-id="3f8c5-288">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-288">Int32</span></span>|  
|<span data-ttu-id="3f8c5-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3f8c5-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="3f8c5-290">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-290">Int32</span></span>|  
|<span data-ttu-id="3f8c5-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="3f8c5-292">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-292">Int16</span></span>|  
|<span data-ttu-id="3f8c5-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="3f8c5-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="3f8c5-294">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-294">Int16</span></span>|  
|<span data-ttu-id="3f8c5-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-295">NULLABLE</span></span>|<span data-ttu-id="3f8c5-296">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-296">Int16</span></span>|  
|<span data-ttu-id="3f8c5-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-297">REMARKS</span></span>|<span data-ttu-id="3f8c5-298">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-298">String</span></span>|  
|<span data-ttu-id="3f8c5-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="3f8c5-299">COLUMN_DEF</span></span>|<span data-ttu-id="3f8c5-300">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-300">String</span></span>|  
|<span data-ttu-id="3f8c5-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="3f8c5-302">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-302">Int16</span></span>|  
|<span data-ttu-id="3f8c5-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="3f8c5-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="3f8c5-304">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-304">Int16</span></span>|  
|<span data-ttu-id="3f8c5-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3f8c5-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="3f8c5-306">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-306">Int32</span></span>|  
|<span data-ttu-id="3f8c5-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3f8c5-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="3f8c5-308">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-308">Int32</span></span>|  
|<span data-ttu-id="3f8c5-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-309">IS_NULLABLE</span></span>|<span data-ttu-id="3f8c5-310">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-310">String</span></span>|  
|<span data-ttu-id="3f8c5-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3f8c5-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="3f8c5-312">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-312">String</span></span>|  
|<span data-ttu-id="3f8c5-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3f8c5-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="3f8c5-314">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-314">String</span></span>|  
|<span data-ttu-id="3f8c5-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="3f8c5-316">Byte</span><span class="sxs-lookup"><span data-stu-id="3f8c5-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="3f8c5-317">Microsoft Oracle ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="3f8c5-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="3f8c5-318">Microsoft SQL Server Oracle ODBC Driver에서는 공통 스키마 컬렉션을 비롯 하 여 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8c5-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="3f8c5-319">Tables</span><span class="sxs-lookup"><span data-stu-id="3f8c5-319">Tables</span></span>  
  
-   <span data-ttu-id="3f8c5-320">Columns</span><span class="sxs-lookup"><span data-stu-id="3f8c5-320">Columns</span></span>  
  
-   <span data-ttu-id="3f8c5-321">절차</span><span class="sxs-lookup"><span data-stu-id="3f8c5-321">Procedures</span></span>  
  
-   <span data-ttu-id="3f8c5-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3f8c5-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="3f8c5-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3f8c5-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="3f8c5-324">뷰</span><span class="sxs-lookup"><span data-stu-id="3f8c5-324">Views</span></span>  
  
-   <span data-ttu-id="3f8c5-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="3f8c5-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="3f8c5-326">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="3f8c5-326">Tables and Views</span></span>  
  
|<span data-ttu-id="3f8c5-327">열 이름</span><span class="sxs-lookup"><span data-stu-id="3f8c5-327">ColumnName</span></span>|<span data-ttu-id="3f8c5-328">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f8c5-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3f8c5-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="3f8c5-330">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-330">String</span></span>|  
|<span data-ttu-id="3f8c5-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-331">TABLE_OWNER</span></span>|<span data-ttu-id="3f8c5-332">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-332">String</span></span>|  
|<span data-ttu-id="3f8c5-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-333">TABLE_NAME</span></span>|<span data-ttu-id="3f8c5-334">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-334">String</span></span>|  
|<span data-ttu-id="3f8c5-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-335">TABLE_TYPE</span></span>|<span data-ttu-id="3f8c5-336">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-336">String</span></span>|  
|<span data-ttu-id="3f8c5-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-337">REMARKS</span></span>|<span data-ttu-id="3f8c5-338">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="3f8c5-339">Columns</span><span class="sxs-lookup"><span data-stu-id="3f8c5-339">Columns</span></span>  
  
|<span data-ttu-id="3f8c5-340">열 이름</span><span class="sxs-lookup"><span data-stu-id="3f8c5-340">ColumnName</span></span>|<span data-ttu-id="3f8c5-341">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f8c5-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3f8c5-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="3f8c5-343">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-343">String</span></span>|  
|<span data-ttu-id="3f8c5-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-344">TABLE_OWNER</span></span>|<span data-ttu-id="3f8c5-345">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-345">String</span></span>|  
|<span data-ttu-id="3f8c5-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-346">TABLE_NAME</span></span>|<span data-ttu-id="3f8c5-347">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-347">String</span></span>|  
|<span data-ttu-id="3f8c5-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-348">COLUMN_NAME</span></span>|<span data-ttu-id="3f8c5-349">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-349">String</span></span>|  
|<span data-ttu-id="3f8c5-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-350">DATA_TYPE</span></span>|<span data-ttu-id="3f8c5-351">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-351">Int16</span></span>|  
|<span data-ttu-id="3f8c5-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-352">TYPE_NAME</span></span>|<span data-ttu-id="3f8c5-353">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-353">String</span></span>|  
|<span data-ttu-id="3f8c5-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="3f8c5-354">PRECISION</span></span>|<span data-ttu-id="3f8c5-355">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-355">Int32</span></span>|  
|<span data-ttu-id="3f8c5-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="3f8c5-356">LENGTH</span></span>|<span data-ttu-id="3f8c5-357">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-357">Int32</span></span>|  
|<span data-ttu-id="3f8c5-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-358">SCALE</span></span>|<span data-ttu-id="3f8c5-359">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-359">Int16</span></span>|  
|<span data-ttu-id="3f8c5-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="3f8c5-360">RADIX</span></span>|<span data-ttu-id="3f8c5-361">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-361">Int16</span></span>|  
|<span data-ttu-id="3f8c5-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-362">NULLABLE</span></span>|<span data-ttu-id="3f8c5-363">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-363">Int16</span></span>|  
|<span data-ttu-id="3f8c5-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-364">REMARKS</span></span>|<span data-ttu-id="3f8c5-365">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-365">String</span></span>|  
|<span data-ttu-id="3f8c5-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3f8c5-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="3f8c5-367">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="3f8c5-368">절차</span><span class="sxs-lookup"><span data-stu-id="3f8c5-368">Procedures</span></span>  
  
|<span data-ttu-id="3f8c5-369">열 이름</span><span class="sxs-lookup"><span data-stu-id="3f8c5-369">ColumnName</span></span>|<span data-ttu-id="3f8c5-370">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f8c5-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3f8c5-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="3f8c5-372">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-372">String</span></span>|  
|<span data-ttu-id="3f8c5-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="3f8c5-374">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-374">String</span></span>|  
|<span data-ttu-id="3f8c5-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="3f8c5-376">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-376">String</span></span>|  
|<span data-ttu-id="3f8c5-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="3f8c5-378">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-378">Int16</span></span>|  
|<span data-ttu-id="3f8c5-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="3f8c5-380">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-380">Int16</span></span>|  
|<span data-ttu-id="3f8c5-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="3f8c5-382">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-382">Int16</span></span>|  
|<span data-ttu-id="3f8c5-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-383">REMARKS</span></span>|<span data-ttu-id="3f8c5-384">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-384">String</span></span>|  
|<span data-ttu-id="3f8c5-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="3f8c5-386">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="3f8c5-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3f8c5-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="3f8c5-388">열 이름</span><span class="sxs-lookup"><span data-stu-id="3f8c5-388">ColumnName</span></span>|<span data-ttu-id="3f8c5-389">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f8c5-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3f8c5-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="3f8c5-391">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-391">String</span></span>|  
|<span data-ttu-id="3f8c5-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="3f8c5-393">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-393">String</span></span>|  
|<span data-ttu-id="3f8c5-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="3f8c5-395">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-395">String</span></span>|  
|<span data-ttu-id="3f8c5-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-396">COLUMN_NAME</span></span>|<span data-ttu-id="3f8c5-397">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-397">String</span></span>|  
|<span data-ttu-id="3f8c5-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-398">COLUMN_TYPE</span></span>|<span data-ttu-id="3f8c5-399">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-399">Int16</span></span>|  
|<span data-ttu-id="3f8c5-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-400">DATA_TYPE</span></span>|<span data-ttu-id="3f8c5-401">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-401">Int16</span></span>|  
|<span data-ttu-id="3f8c5-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-402">TYPE_NAME</span></span>|<span data-ttu-id="3f8c5-403">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-403">String</span></span>|  
|<span data-ttu-id="3f8c5-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="3f8c5-404">PRECISION</span></span>|<span data-ttu-id="3f8c5-405">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-405">Int32</span></span>|  
|<span data-ttu-id="3f8c5-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="3f8c5-406">LENGTH</span></span>|<span data-ttu-id="3f8c5-407">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-407">Int32</span></span>|  
|<span data-ttu-id="3f8c5-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-408">SCALE</span></span>|<span data-ttu-id="3f8c5-409">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-409">Int16</span></span>|  
|<span data-ttu-id="3f8c5-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="3f8c5-410">RADIX</span></span>|<span data-ttu-id="3f8c5-411">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-411">Int16</span></span>|  
|<span data-ttu-id="3f8c5-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-412">NULLABLE</span></span>|<span data-ttu-id="3f8c5-413">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-413">Int16</span></span>|  
|<span data-ttu-id="3f8c5-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-414">REMARKS</span></span>|<span data-ttu-id="3f8c5-415">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-415">String</span></span>|  
|<span data-ttu-id="3f8c5-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="3f8c5-416">OVERLOAD</span></span>|<span data-ttu-id="3f8c5-417">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-417">Int32</span></span>|  
|<span data-ttu-id="3f8c5-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3f8c5-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="3f8c5-419">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="3f8c5-420">Microsoft Jet ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="3f8c5-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="3f8c5-421">Microsoft Jet ODBC Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="3f8c5-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="3f8c5-422">Tables</span><span class="sxs-lookup"><span data-stu-id="3f8c5-422">Tables</span></span>  
  
-   <span data-ttu-id="3f8c5-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="3f8c5-423">Indexes</span></span>  
  
-   <span data-ttu-id="3f8c5-424">Columns</span><span class="sxs-lookup"><span data-stu-id="3f8c5-424">Columns</span></span>  
  
-   <span data-ttu-id="3f8c5-425">절차</span><span class="sxs-lookup"><span data-stu-id="3f8c5-425">Procedures</span></span>  
  
-   <span data-ttu-id="3f8c5-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3f8c5-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="3f8c5-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3f8c5-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="3f8c5-428">뷰</span><span class="sxs-lookup"><span data-stu-id="3f8c5-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="3f8c5-429">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="3f8c5-429">Tables and Views</span></span>  
  
|<span data-ttu-id="3f8c5-430">열 이름</span><span class="sxs-lookup"><span data-stu-id="3f8c5-430">ColumnName</span></span>|<span data-ttu-id="3f8c5-431">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f8c5-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3f8c5-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="3f8c5-433">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-433">String</span></span>|  
|<span data-ttu-id="3f8c5-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-434">TABLE_OWNER</span></span>|<span data-ttu-id="3f8c5-435">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-435">String</span></span>|  
|<span data-ttu-id="3f8c5-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-436">TABLE_NAME</span></span>|<span data-ttu-id="3f8c5-437">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-437">String</span></span>|  
|<span data-ttu-id="3f8c5-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-438">TABLE_TYPE</span></span>|<span data-ttu-id="3f8c5-439">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-439">String</span></span>|  
|<span data-ttu-id="3f8c5-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-440">REMARKS</span></span>|<span data-ttu-id="3f8c5-441">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="3f8c5-442">Columns</span><span class="sxs-lookup"><span data-stu-id="3f8c5-442">Columns</span></span>  
  
|<span data-ttu-id="3f8c5-443">열 이름</span><span class="sxs-lookup"><span data-stu-id="3f8c5-443">ColumnName</span></span>|<span data-ttu-id="3f8c5-444">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f8c5-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3f8c5-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="3f8c5-446">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-446">String</span></span>|  
|<span data-ttu-id="3f8c5-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-447">TABLE_OWNER</span></span>|<span data-ttu-id="3f8c5-448">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-448">String</span></span>|  
|<span data-ttu-id="3f8c5-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-449">TABLE_NAME</span></span>|<span data-ttu-id="3f8c5-450">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-450">String</span></span>|  
|<span data-ttu-id="3f8c5-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-451">COLUMN_NAME</span></span>|<span data-ttu-id="3f8c5-452">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-452">String</span></span>|  
|<span data-ttu-id="3f8c5-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-453">DATA_TYPE</span></span>|<span data-ttu-id="3f8c5-454">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-454">Int16</span></span>|  
|<span data-ttu-id="3f8c5-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-455">TYPE_NAME</span></span>|<span data-ttu-id="3f8c5-456">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-456">String</span></span>|  
|<span data-ttu-id="3f8c5-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="3f8c5-457">PRECISION</span></span>|<span data-ttu-id="3f8c5-458">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-458">Int32</span></span>|  
|<span data-ttu-id="3f8c5-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="3f8c5-459">LENGTH</span></span>|<span data-ttu-id="3f8c5-460">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-460">Int32</span></span>|  
|<span data-ttu-id="3f8c5-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-461">SCALE</span></span>|<span data-ttu-id="3f8c5-462">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-462">Int16</span></span>|  
|<span data-ttu-id="3f8c5-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="3f8c5-463">RADIX</span></span>|<span data-ttu-id="3f8c5-464">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-464">Int16</span></span>|  
|<span data-ttu-id="3f8c5-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-465">NULLABLE</span></span>|<span data-ttu-id="3f8c5-466">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-466">Int16</span></span>|  
|<span data-ttu-id="3f8c5-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-467">REMARKS</span></span>|<span data-ttu-id="3f8c5-468">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-468">String</span></span>|  
|<span data-ttu-id="3f8c5-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3f8c5-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="3f8c5-470">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="3f8c5-471">절차</span><span class="sxs-lookup"><span data-stu-id="3f8c5-471">Procedures</span></span>  
  
|<span data-ttu-id="3f8c5-472">열 이름</span><span class="sxs-lookup"><span data-stu-id="3f8c5-472">ColumnName</span></span>|<span data-ttu-id="3f8c5-473">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f8c5-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3f8c5-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="3f8c5-475">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-475">String</span></span>|  
|<span data-ttu-id="3f8c5-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="3f8c5-477">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-477">String</span></span>|  
|<span data-ttu-id="3f8c5-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="3f8c5-479">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-479">String</span></span>|  
|<span data-ttu-id="3f8c5-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="3f8c5-481">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-481">Int16</span></span>|  
|<span data-ttu-id="3f8c5-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="3f8c5-483">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-483">Int16</span></span>|  
|<span data-ttu-id="3f8c5-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="3f8c5-485">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-485">Int16</span></span>|  
|<span data-ttu-id="3f8c5-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-486">REMARKS</span></span>|<span data-ttu-id="3f8c5-487">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-487">String</span></span>|  
|<span data-ttu-id="3f8c5-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="3f8c5-489">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="3f8c5-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3f8c5-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="3f8c5-491">열 이름</span><span class="sxs-lookup"><span data-stu-id="3f8c5-491">ColumnName</span></span>|<span data-ttu-id="3f8c5-492">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f8c5-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3f8c5-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="3f8c5-494">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-494">String</span></span>|  
|<span data-ttu-id="3f8c5-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f8c5-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="3f8c5-496">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-496">String</span></span>|  
|<span data-ttu-id="3f8c5-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="3f8c5-498">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-498">String</span></span>|  
|<span data-ttu-id="3f8c5-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-499">COLUMN_NAME</span></span>|<span data-ttu-id="3f8c5-500">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-500">String</span></span>|  
|<span data-ttu-id="3f8c5-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-501">COLUMN_TYPE</span></span>|<span data-ttu-id="3f8c5-502">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-502">Int16</span></span>|  
|<span data-ttu-id="3f8c5-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-503">DATA_TYPE</span></span>|<span data-ttu-id="3f8c5-504">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-504">Int16</span></span>|  
|<span data-ttu-id="3f8c5-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-505">TYPE_NAME</span></span>|<span data-ttu-id="3f8c5-506">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-506">String</span></span>|  
|<span data-ttu-id="3f8c5-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="3f8c5-507">PRECISION</span></span>|<span data-ttu-id="3f8c5-508">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-508">Int32</span></span>|  
|<span data-ttu-id="3f8c5-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="3f8c5-509">LENGTH</span></span>|<span data-ttu-id="3f8c5-510">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-510">Int32</span></span>|  
|<span data-ttu-id="3f8c5-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-511">SCALE</span></span>|<span data-ttu-id="3f8c5-512">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-512">Int16</span></span>|  
|<span data-ttu-id="3f8c5-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="3f8c5-513">RADIX</span></span>|<span data-ttu-id="3f8c5-514">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-514">Int16</span></span>|  
|<span data-ttu-id="3f8c5-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-515">NULLABLE</span></span>|<span data-ttu-id="3f8c5-516">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-516">Int16</span></span>|  
|<span data-ttu-id="3f8c5-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-517">REMARKS</span></span>|<span data-ttu-id="3f8c5-518">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-518">String</span></span>|  
|<span data-ttu-id="3f8c5-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="3f8c5-519">OVERLOAD</span></span>|<span data-ttu-id="3f8c5-520">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-520">Int32</span></span>|  
|<span data-ttu-id="3f8c5-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3f8c5-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="3f8c5-522">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="3f8c5-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3f8c5-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="3f8c5-524">열 이름</span><span class="sxs-lookup"><span data-stu-id="3f8c5-524">ColumnName</span></span>|<span data-ttu-id="3f8c5-525">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f8c5-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3f8c5-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="3f8c5-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="3f8c5-527">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-527">String</span></span>|  
|<span data-ttu-id="3f8c5-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3f8c5-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="3f8c5-529">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-529">String</span></span>|  
|<span data-ttu-id="3f8c5-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="3f8c5-531">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-531">String</span></span>|  
|<span data-ttu-id="3f8c5-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-532">COLUMN_NAME</span></span>|<span data-ttu-id="3f8c5-533">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-533">String</span></span>|  
|<span data-ttu-id="3f8c5-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-534">COLUMN_TYPE</span></span>|<span data-ttu-id="3f8c5-535">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-535">Int16</span></span>|  
|<span data-ttu-id="3f8c5-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-536">DATA_TYPE</span></span>|<span data-ttu-id="3f8c5-537">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-537">Int16</span></span>|  
|<span data-ttu-id="3f8c5-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3f8c5-538">TYPE_NAME</span></span>|<span data-ttu-id="3f8c5-539">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-539">String</span></span>|  
|<span data-ttu-id="3f8c5-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-540">COLUMN_SIZE</span></span>|<span data-ttu-id="3f8c5-541">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-541">Int32</span></span>|  
|<span data-ttu-id="3f8c5-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3f8c5-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="3f8c5-543">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-543">Int32</span></span>|  
|<span data-ttu-id="3f8c5-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="3f8c5-545">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-545">Int16</span></span>|  
|<span data-ttu-id="3f8c5-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="3f8c5-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="3f8c5-547">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-547">Int16</span></span>|  
|<span data-ttu-id="3f8c5-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-548">NULLABLE</span></span>|<span data-ttu-id="3f8c5-549">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-549">Int16</span></span>|  
|<span data-ttu-id="3f8c5-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3f8c5-550">REMARKS</span></span>|<span data-ttu-id="3f8c5-551">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-551">String</span></span>|  
|<span data-ttu-id="3f8c5-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="3f8c5-552">COLUMN_DEF</span></span>|<span data-ttu-id="3f8c5-553">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-553">String</span></span>|  
|<span data-ttu-id="3f8c5-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="3f8c5-555">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-555">Int16</span></span>|  
|<span data-ttu-id="3f8c5-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="3f8c5-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="3f8c5-557">Int16</span><span class="sxs-lookup"><span data-stu-id="3f8c5-557">Int16</span></span>|  
|<span data-ttu-id="3f8c5-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3f8c5-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="3f8c5-559">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-559">Int32</span></span>|  
|<span data-ttu-id="3f8c5-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3f8c5-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="3f8c5-561">Int32</span><span class="sxs-lookup"><span data-stu-id="3f8c5-561">Int32</span></span>|  
|<span data-ttu-id="3f8c5-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3f8c5-562">IS_NULLABLE</span></span>|<span data-ttu-id="3f8c5-563">문자열</span><span class="sxs-lookup"><span data-stu-id="3f8c5-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f8c5-564">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f8c5-564">See Also</span></span>  
 [<span data-ttu-id="3f8c5-565">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="3f8c5-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
