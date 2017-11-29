---
title: "OLE DB 스키마 컬렉션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9b88308c5dad69ed1ba6f48f525931e94f13ef1a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="bd038-102">OLE DB 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="bd038-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="bd038-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 OLE DB 공급자에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bd038-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="bd038-104">Microsoft SQL Server OLE DB 공급자</span><span class="sxs-lookup"><span data-stu-id="bd038-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="bd038-105">Microsoft SQL Server OLE DB Driver에서는 공통 스키마 컬렉션을 비롯 하 여 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bd038-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="bd038-106">Tables</span><span class="sxs-lookup"><span data-stu-id="bd038-106">Tables</span></span>  
  
-   <span data-ttu-id="bd038-107">Columns</span><span class="sxs-lookup"><span data-stu-id="bd038-107">Columns</span></span>  
  
-   <span data-ttu-id="bd038-108">절차</span><span class="sxs-lookup"><span data-stu-id="bd038-108">Procedures</span></span>  
  
-   <span data-ttu-id="bd038-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="bd038-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="bd038-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="bd038-110">Catalog</span></span>  
  
-   <span data-ttu-id="bd038-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="bd038-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="bd038-112">Tables</span><span class="sxs-lookup"><span data-stu-id="bd038-112">Tables</span></span>  
  
|<span data-ttu-id="bd038-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-113">ColumnName</span></span>|<span data-ttu-id="bd038-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-115">TABLE_CATALOG</span></span>|<span data-ttu-id="bd038-116">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-116">String</span></span>|  
|<span data-ttu-id="bd038-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="bd038-118">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-118">String</span></span>|  
|<span data-ttu-id="bd038-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-119">TABLE_NAME</span></span>|<span data-ttu-id="bd038-120">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-120">String</span></span>|  
|<span data-ttu-id="bd038-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="bd038-121">TABLE_TYPE</span></span>|<span data-ttu-id="bd038-122">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-122">String</span></span>|  
|<span data-ttu-id="bd038-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="bd038-123">TABLE_GUID</span></span>|<span data-ttu-id="bd038-124">Guid</span><span class="sxs-lookup"><span data-stu-id="bd038-124">Guid</span></span>|  
|<span data-ttu-id="bd038-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd038-125">DESCRIPTION</span></span>|<span data-ttu-id="bd038-126">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-126">String</span></span>|  
|<span data-ttu-id="bd038-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="bd038-127">TABLE_PROPID</span></span>|<span data-ttu-id="bd038-128">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-128">Int64</span></span>|  
|<span data-ttu-id="bd038-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="bd038-129">DATE_CREATED</span></span>|<span data-ttu-id="bd038-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd038-130">DateTime</span></span>|  
|<span data-ttu-id="bd038-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="bd038-131">DATE_MODIFIED</span></span>|<span data-ttu-id="bd038-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd038-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="bd038-133">Columns</span><span class="sxs-lookup"><span data-stu-id="bd038-133">Columns</span></span>  
  
|<span data-ttu-id="bd038-134">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-134">ColumnName</span></span>|<span data-ttu-id="bd038-135">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-136">TABLE_CATALOG</span></span>|<span data-ttu-id="bd038-137">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-137">String</span></span>|  
|<span data-ttu-id="bd038-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="bd038-139">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-139">String</span></span>|  
|<span data-ttu-id="bd038-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-140">TABLE_NAME</span></span>|<span data-ttu-id="bd038-141">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-141">String</span></span>|  
|<span data-ttu-id="bd038-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-142">COLUMN_NAME</span></span>|<span data-ttu-id="bd038-143">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-143">String</span></span>|  
|<span data-ttu-id="bd038-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="bd038-144">COLUMN_GUID</span></span>|<span data-ttu-id="bd038-145">Guid</span><span class="sxs-lookup"><span data-stu-id="bd038-145">Guid</span></span>|  
|<span data-ttu-id="bd038-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="bd038-146">COLUMN_PROPID</span></span>|<span data-ttu-id="bd038-147">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-147">Int64</span></span>|  
|<span data-ttu-id="bd038-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="bd038-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="bd038-149">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-149">Int64</span></span>|  
|<span data-ttu-id="bd038-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="bd038-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="bd038-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-151">Boolean</span></span>|  
|<span data-ttu-id="bd038-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="bd038-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="bd038-153">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-153">String</span></span>|  
|<span data-ttu-id="bd038-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="bd038-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="bd038-155">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-155">Int64</span></span>|  
|<span data-ttu-id="bd038-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="bd038-156">IS_NULLABLE</span></span>|<span data-ttu-id="bd038-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-157">Boolean</span></span>|  
|<span data-ttu-id="bd038-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="bd038-158">DATA_TYPE</span></span>|<span data-ttu-id="bd038-159">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-159">Int32</span></span>|  
|<span data-ttu-id="bd038-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="bd038-160">TYPE_GUID</span></span>|<span data-ttu-id="bd038-161">Guid</span><span class="sxs-lookup"><span data-stu-id="bd038-161">Guid</span></span>|  
|<span data-ttu-id="bd038-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="bd038-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="bd038-163">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-163">Int64</span></span>|  
|<span data-ttu-id="bd038-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="bd038-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="bd038-165">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-165">Int64</span></span>|  
|<span data-ttu-id="bd038-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="bd038-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="bd038-167">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-167">Int32</span></span>|  
|<span data-ttu-id="bd038-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="bd038-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="bd038-169">Int16</span><span class="sxs-lookup"><span data-stu-id="bd038-169">Int16</span></span>|  
|<span data-ttu-id="bd038-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="bd038-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="bd038-171">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-171">Int64</span></span>|  
|<span data-ttu-id="bd038-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="bd038-173">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-173">String</span></span>|  
|<span data-ttu-id="bd038-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="bd038-175">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-175">String</span></span>|  
|<span data-ttu-id="bd038-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="bd038-177">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-177">String</span></span>|  
|<span data-ttu-id="bd038-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="bd038-179">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-179">String</span></span>|  
|<span data-ttu-id="bd038-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="bd038-181">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-181">String</span></span>|  
|<span data-ttu-id="bd038-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-182">COLLATION_NAME</span></span>|<span data-ttu-id="bd038-183">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-183">String</span></span>|  
|<span data-ttu-id="bd038-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="bd038-185">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-185">String</span></span>|  
|<span data-ttu-id="bd038-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="bd038-187">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-187">String</span></span>|  
|<span data-ttu-id="bd038-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-188">DOMAIN_NAME</span></span>|<span data-ttu-id="bd038-189">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-189">String</span></span>|  
|<span data-ttu-id="bd038-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd038-190">DESCRIPTION</span></span>|<span data-ttu-id="bd038-191">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-191">String</span></span>|  
|<span data-ttu-id="bd038-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="bd038-192">COLUMN_LCID</span></span>|<span data-ttu-id="bd038-193">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-193">Int32</span></span>|  
|<span data-ttu-id="bd038-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="bd038-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="bd038-195">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-195">Int32</span></span>|  
|<span data-ttu-id="bd038-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="bd038-196">COLUMN_SORTID</span></span>|<span data-ttu-id="bd038-197">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-197">Int32</span></span>|  
|<span data-ttu-id="bd038-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="bd038-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="bd038-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="bd038-199">Byte[]</span></span>|  
|<span data-ttu-id="bd038-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="bd038-200">IS_COMPUTED</span></span>|<span data-ttu-id="bd038-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="bd038-202">절차</span><span class="sxs-lookup"><span data-stu-id="bd038-202">Procedures</span></span>  
  
|<span data-ttu-id="bd038-203">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-203">ColumnName</span></span>|<span data-ttu-id="bd038-204">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="bd038-206">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-206">String</span></span>|  
|<span data-ttu-id="bd038-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="bd038-208">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-208">String</span></span>|  
|<span data-ttu-id="bd038-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="bd038-210">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-210">String</span></span>|  
|<span data-ttu-id="bd038-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="bd038-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="bd038-212">Int16</span><span class="sxs-lookup"><span data-stu-id="bd038-212">Int16</span></span>|  
|<span data-ttu-id="bd038-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="bd038-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="bd038-214">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-214">String</span></span>|  
|<span data-ttu-id="bd038-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd038-215">DESCRIPTION</span></span>|<span data-ttu-id="bd038-216">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-216">String</span></span>|  
|<span data-ttu-id="bd038-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="bd038-217">DATE_CREATED</span></span>|<span data-ttu-id="bd038-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd038-218">DateTime</span></span>|  
|<span data-ttu-id="bd038-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="bd038-219">DATE_MODIFIED</span></span>|<span data-ttu-id="bd038-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd038-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="bd038-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="bd038-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="bd038-222">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-222">ColumnName</span></span>|<span data-ttu-id="bd038-223">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="bd038-225">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-225">String</span></span>|  
|<span data-ttu-id="bd038-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="bd038-227">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-227">String</span></span>|  
|<span data-ttu-id="bd038-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="bd038-229">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-229">String</span></span>|  
|<span data-ttu-id="bd038-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-230">PARAMETER_NAME</span></span>|<span data-ttu-id="bd038-231">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-231">String</span></span>|  
|<span data-ttu-id="bd038-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="bd038-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="bd038-233">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-233">Int32</span></span>|  
|<span data-ttu-id="bd038-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="bd038-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="bd038-235">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-235">Int32</span></span>|  
|<span data-ttu-id="bd038-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="bd038-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="bd038-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-237">Boolean</span></span>|  
|<span data-ttu-id="bd038-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="bd038-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="bd038-239">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-239">String</span></span>|  
|<span data-ttu-id="bd038-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="bd038-240">IS_NULLABLE</span></span>|<span data-ttu-id="bd038-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-241">Boolean</span></span>|  
|<span data-ttu-id="bd038-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="bd038-242">DATA_TYPE</span></span>|<span data-ttu-id="bd038-243">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-243">Int32</span></span>|  
|<span data-ttu-id="bd038-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="bd038-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="bd038-245">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-245">Int64</span></span>|  
|<span data-ttu-id="bd038-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="bd038-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="bd038-247">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-247">Int64</span></span>|  
|<span data-ttu-id="bd038-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="bd038-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="bd038-249">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-249">Int32</span></span>|  
|<span data-ttu-id="bd038-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="bd038-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="bd038-251">Int16</span><span class="sxs-lookup"><span data-stu-id="bd038-251">Int16</span></span>|  
|<span data-ttu-id="bd038-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd038-252">DESCRIPTION</span></span>|<span data-ttu-id="bd038-253">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-253">String</span></span>|  
|<span data-ttu-id="bd038-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-254">TYPE_NAME</span></span>|<span data-ttu-id="bd038-255">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-255">String</span></span>|  
|<span data-ttu-id="bd038-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="bd038-257">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="bd038-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="bd038-258">Catalog</span></span>  
  
|<span data-ttu-id="bd038-259">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-259">ColumnName</span></span>|<span data-ttu-id="bd038-260">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-261">CATALOG_NAME</span></span>|<span data-ttu-id="bd038-262">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-262">String</span></span>|  
|<span data-ttu-id="bd038-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd038-263">DESCRIPTION</span></span>|<span data-ttu-id="bd038-264">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="bd038-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="bd038-265">Indexes</span></span>  
  
|<span data-ttu-id="bd038-266">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-266">ColumnName</span></span>|<span data-ttu-id="bd038-267">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-268">TABLE_CATALOG</span></span>|<span data-ttu-id="bd038-269">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-269">String</span></span>|  
|<span data-ttu-id="bd038-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="bd038-271">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-271">String</span></span>|  
|<span data-ttu-id="bd038-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-272">TABLE_NAME</span></span>|<span data-ttu-id="bd038-273">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-273">String</span></span>|  
|<span data-ttu-id="bd038-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-274">INDEX_CATALOG</span></span>|<span data-ttu-id="bd038-275">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-275">String</span></span>|  
|<span data-ttu-id="bd038-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="bd038-277">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-277">String</span></span>|  
|<span data-ttu-id="bd038-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-278">INDEX_NAME</span></span>|<span data-ttu-id="bd038-279">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-279">String</span></span>|  
|<span data-ttu-id="bd038-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="bd038-280">PRIMARY_KEY</span></span>|<span data-ttu-id="bd038-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-281">Boolean</span></span>|  
|<span data-ttu-id="bd038-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="bd038-282">UNIQUE</span></span>|<span data-ttu-id="bd038-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-283">Boolean</span></span>|  
|<span data-ttu-id="bd038-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="bd038-284">CLUSTERED</span></span>|<span data-ttu-id="bd038-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-285">Boolean</span></span>|  
|<span data-ttu-id="bd038-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="bd038-286">TYPE</span></span>|<span data-ttu-id="bd038-287">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-287">Int32</span></span>|  
|<span data-ttu-id="bd038-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="bd038-288">FILL_FACTOR</span></span>|<span data-ttu-id="bd038-289">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-289">Int32</span></span>|  
|<span data-ttu-id="bd038-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="bd038-290">INITIAL_SIZE</span></span>|<span data-ttu-id="bd038-291">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-291">Int32</span></span>|  
|<span data-ttu-id="bd038-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="bd038-292">NULLS</span></span>|<span data-ttu-id="bd038-293">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-293">Int32</span></span>|  
|<span data-ttu-id="bd038-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="bd038-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="bd038-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-295">Boolean</span></span>|  
|<span data-ttu-id="bd038-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="bd038-296">AUTO_UPDATE</span></span>|<span data-ttu-id="bd038-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-297">Boolean</span></span>|  
|<span data-ttu-id="bd038-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="bd038-298">NULL_COLLATION</span></span>|<span data-ttu-id="bd038-299">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-299">Int32</span></span>|  
|<span data-ttu-id="bd038-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="bd038-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="bd038-301">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-301">Int64</span></span>|  
|<span data-ttu-id="bd038-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-302">COLUMN_NAME</span></span>|<span data-ttu-id="bd038-303">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-303">String</span></span>|  
|<span data-ttu-id="bd038-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="bd038-304">COLUMN_GUID</span></span>|<span data-ttu-id="bd038-305">Guid</span><span class="sxs-lookup"><span data-stu-id="bd038-305">Guid</span></span>|  
|<span data-ttu-id="bd038-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="bd038-306">COLUMN_PROPID</span></span>|<span data-ttu-id="bd038-307">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-307">Int64</span></span>|  
|<span data-ttu-id="bd038-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="bd038-308">COLLATION</span></span>|<span data-ttu-id="bd038-309">Int16</span><span class="sxs-lookup"><span data-stu-id="bd038-309">Int16</span></span>|  
|<span data-ttu-id="bd038-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="bd038-310">CARDINALITY</span></span>|<span data-ttu-id="bd038-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="bd038-311">Decimal</span></span>|  
|<span data-ttu-id="bd038-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="bd038-312">PAGES</span></span>|<span data-ttu-id="bd038-313">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-313">Int32</span></span>|  
|<span data-ttu-id="bd038-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="bd038-314">FILTER_CONDITION</span></span>|<span data-ttu-id="bd038-315">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-315">String</span></span>|  
|<span data-ttu-id="bd038-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="bd038-316">INTEGRATED</span></span>|<span data-ttu-id="bd038-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="bd038-318">Microsoft Oracle OLE DB    </span><span class="sxs-lookup"><span data-stu-id="bd038-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="bd038-319">Microsoft Oracle OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="bd038-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="bd038-320">Tables</span><span class="sxs-lookup"><span data-stu-id="bd038-320">Tables</span></span>  
  
-   <span data-ttu-id="bd038-321">Columns</span><span class="sxs-lookup"><span data-stu-id="bd038-321">Columns</span></span>  
  
-   <span data-ttu-id="bd038-322">절차</span><span class="sxs-lookup"><span data-stu-id="bd038-322">Procedures</span></span>  
  
-   <span data-ttu-id="bd038-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="bd038-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="bd038-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="bd038-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="bd038-325">뷰</span><span class="sxs-lookup"><span data-stu-id="bd038-325">Views</span></span>  
  
-   <span data-ttu-id="bd038-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="bd038-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="bd038-327">Tables</span><span class="sxs-lookup"><span data-stu-id="bd038-327">Tables</span></span>  
  
|<span data-ttu-id="bd038-328">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-328">ColumnName</span></span>|<span data-ttu-id="bd038-329">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-330">TABLE_CATALOG</span></span>|<span data-ttu-id="bd038-331">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-331">String</span></span>|  
|<span data-ttu-id="bd038-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="bd038-333">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-333">String</span></span>|  
|<span data-ttu-id="bd038-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-334">TABLE_NAME</span></span>|<span data-ttu-id="bd038-335">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-335">String</span></span>|  
|<span data-ttu-id="bd038-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="bd038-336">TABLE_TYPE</span></span>|<span data-ttu-id="bd038-337">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-337">String</span></span>|  
|<span data-ttu-id="bd038-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="bd038-338">TABLE_GUID</span></span>|<span data-ttu-id="bd038-339">Guid</span><span class="sxs-lookup"><span data-stu-id="bd038-339">Guid</span></span>|  
|<span data-ttu-id="bd038-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd038-340">DESCRIPTION</span></span>|<span data-ttu-id="bd038-341">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-341">String</span></span>|  
|<span data-ttu-id="bd038-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="bd038-342">TABLE_PROPID</span></span>|<span data-ttu-id="bd038-343">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-343">Int64</span></span>|  
|<span data-ttu-id="bd038-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="bd038-344">DATE_CREATED</span></span>|<span data-ttu-id="bd038-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd038-345">DateTime</span></span>|  
|<span data-ttu-id="bd038-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="bd038-346">DATE_MODIFIED</span></span>|<span data-ttu-id="bd038-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd038-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="bd038-348">Columns</span><span class="sxs-lookup"><span data-stu-id="bd038-348">Columns</span></span>  
  
|<span data-ttu-id="bd038-349">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-349">ColumnName</span></span>|<span data-ttu-id="bd038-350">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-351">TABLE_CATALOG</span></span>|<span data-ttu-id="bd038-352">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-352">String</span></span>|  
|<span data-ttu-id="bd038-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="bd038-354">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-354">String</span></span>|  
|<span data-ttu-id="bd038-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-355">TABLE_NAME</span></span>|<span data-ttu-id="bd038-356">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-356">String</span></span>|  
|<span data-ttu-id="bd038-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-357">COLUMN_NAME</span></span>|<span data-ttu-id="bd038-358">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-358">String</span></span>|  
|<span data-ttu-id="bd038-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="bd038-359">COLUMN_GUID</span></span>|<span data-ttu-id="bd038-360">Guid</span><span class="sxs-lookup"><span data-stu-id="bd038-360">Guid</span></span>|  
|<span data-ttu-id="bd038-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="bd038-361">COLUMN_PROPID</span></span>|<span data-ttu-id="bd038-362">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-362">Int64</span></span>|  
|<span data-ttu-id="bd038-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="bd038-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="bd038-364">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-364">Int64</span></span>|  
|<span data-ttu-id="bd038-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="bd038-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="bd038-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-366">Boolean</span></span>|  
|<span data-ttu-id="bd038-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="bd038-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="bd038-368">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-368">String</span></span>|  
|<span data-ttu-id="bd038-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="bd038-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="bd038-370">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-370">Int64</span></span>|  
|<span data-ttu-id="bd038-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="bd038-371">IS_NULLABLE</span></span>|<span data-ttu-id="bd038-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-372">Boolean</span></span>|  
|<span data-ttu-id="bd038-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="bd038-373">DATA_TYPE</span></span>|<span data-ttu-id="bd038-374">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-374">Int32</span></span>|  
|<span data-ttu-id="bd038-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="bd038-375">TYPE_GUID</span></span>|<span data-ttu-id="bd038-376">Guid</span><span class="sxs-lookup"><span data-stu-id="bd038-376">Guid</span></span>|  
|<span data-ttu-id="bd038-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="bd038-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="bd038-378">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-378">Int64</span></span>|  
|<span data-ttu-id="bd038-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="bd038-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="bd038-380">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-380">Int64</span></span>|  
|<span data-ttu-id="bd038-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="bd038-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="bd038-382">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-382">Int32</span></span>|  
|<span data-ttu-id="bd038-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="bd038-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="bd038-384">Int16</span><span class="sxs-lookup"><span data-stu-id="bd038-384">Int16</span></span>|  
|<span data-ttu-id="bd038-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="bd038-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="bd038-386">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-386">Int64</span></span>|  
|<span data-ttu-id="bd038-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="bd038-388">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-388">String</span></span>|  
|<span data-ttu-id="bd038-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="bd038-390">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-390">String</span></span>|  
|<span data-ttu-id="bd038-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="bd038-392">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-392">String</span></span>|  
|<span data-ttu-id="bd038-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="bd038-394">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-394">String</span></span>|  
|<span data-ttu-id="bd038-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="bd038-396">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-396">String</span></span>|  
|<span data-ttu-id="bd038-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-397">COLLATION_NAME</span></span>|<span data-ttu-id="bd038-398">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-398">String</span></span>|  
|<span data-ttu-id="bd038-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="bd038-400">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-400">String</span></span>|  
|<span data-ttu-id="bd038-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="bd038-402">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-402">String</span></span>|  
|<span data-ttu-id="bd038-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-403">DOMAIN_NAME</span></span>|<span data-ttu-id="bd038-404">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-404">String</span></span>|  
|<span data-ttu-id="bd038-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd038-405">DESCRIPTION</span></span>|<span data-ttu-id="bd038-406">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="bd038-407">절차</span><span class="sxs-lookup"><span data-stu-id="bd038-407">Procedures</span></span>  
  
|<span data-ttu-id="bd038-408">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-408">ColumnName</span></span>|<span data-ttu-id="bd038-409">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="bd038-411">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-411">String</span></span>|  
|<span data-ttu-id="bd038-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="bd038-413">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-413">String</span></span>|  
|<span data-ttu-id="bd038-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="bd038-415">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-415">String</span></span>|  
|<span data-ttu-id="bd038-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="bd038-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="bd038-417">Int16</span><span class="sxs-lookup"><span data-stu-id="bd038-417">Int16</span></span>|  
|<span data-ttu-id="bd038-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="bd038-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="bd038-419">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-419">String</span></span>|  
|<span data-ttu-id="bd038-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd038-420">DESCRIPTION</span></span>|<span data-ttu-id="bd038-421">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-421">String</span></span>|  
|<span data-ttu-id="bd038-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="bd038-422">DATE_CREATED</span></span>|<span data-ttu-id="bd038-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd038-423">DateTime</span></span>|  
|<span data-ttu-id="bd038-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="bd038-424">DATE_MODIFIED</span></span>|<span data-ttu-id="bd038-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd038-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="bd038-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="bd038-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="bd038-427">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-427">ColumnName</span></span>|<span data-ttu-id="bd038-428">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="bd038-430">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-430">String</span></span>|  
|<span data-ttu-id="bd038-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="bd038-432">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-432">String</span></span>|  
|<span data-ttu-id="bd038-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="bd038-434">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-434">String</span></span>|  
|<span data-ttu-id="bd038-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-435">COLUMN_NAME</span></span>|<span data-ttu-id="bd038-436">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-436">String</span></span>|  
|<span data-ttu-id="bd038-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="bd038-437">COLUMN_GUID</span></span>|<span data-ttu-id="bd038-438">Guid</span><span class="sxs-lookup"><span data-stu-id="bd038-438">Guid</span></span>|  
|<span data-ttu-id="bd038-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="bd038-439">COLUMN_PROPID</span></span>|<span data-ttu-id="bd038-440">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-440">Int64</span></span>|  
|<span data-ttu-id="bd038-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="bd038-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="bd038-442">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-442">Int64</span></span>|  
|<span data-ttu-id="bd038-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="bd038-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="bd038-444">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-444">Int64</span></span>|  
|<span data-ttu-id="bd038-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="bd038-445">IS_NULLABLE</span></span>|<span data-ttu-id="bd038-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-446">Boolean</span></span>|  
|<span data-ttu-id="bd038-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="bd038-447">DATA_TYPE</span></span>|<span data-ttu-id="bd038-448">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-448">Int32</span></span>|  
|<span data-ttu-id="bd038-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="bd038-449">TYPE_GUID</span></span>|<span data-ttu-id="bd038-450">Guid</span><span class="sxs-lookup"><span data-stu-id="bd038-450">Guid</span></span>|  
|<span data-ttu-id="bd038-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="bd038-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="bd038-452">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-452">Int64</span></span>|  
|<span data-ttu-id="bd038-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="bd038-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="bd038-454">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-454">Int64</span></span>|  
|<span data-ttu-id="bd038-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="bd038-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="bd038-456">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-456">Int32</span></span>|  
|<span data-ttu-id="bd038-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="bd038-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="bd038-458">Int16</span><span class="sxs-lookup"><span data-stu-id="bd038-458">Int16</span></span>|  
|<span data-ttu-id="bd038-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd038-459">DESCRIPTION</span></span>|<span data-ttu-id="bd038-460">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-460">String</span></span>|  
|<span data-ttu-id="bd038-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="bd038-461">OVERLOAD</span></span>|<span data-ttu-id="bd038-462">Int16</span><span class="sxs-lookup"><span data-stu-id="bd038-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="bd038-463">뷰</span><span class="sxs-lookup"><span data-stu-id="bd038-463">Views</span></span>  
  
|<span data-ttu-id="bd038-464">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-464">ColumnName</span></span>|<span data-ttu-id="bd038-465">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-466">TABLE_CATALOG</span></span>|<span data-ttu-id="bd038-467">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-467">String</span></span>|  
|<span data-ttu-id="bd038-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="bd038-469">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-469">String</span></span>|  
|<span data-ttu-id="bd038-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-470">TABLE_NAME</span></span>|<span data-ttu-id="bd038-471">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-471">String</span></span>|  
|<span data-ttu-id="bd038-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="bd038-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="bd038-473">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-473">String</span></span>|  
|<span data-ttu-id="bd038-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="bd038-474">CHECK_OPTION</span></span>|<span data-ttu-id="bd038-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-475">Boolean</span></span>|  
|<span data-ttu-id="bd038-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="bd038-476">IS_UPDATABLE</span></span>|<span data-ttu-id="bd038-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-477">Boolean</span></span>|  
|<span data-ttu-id="bd038-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd038-478">DESCRIPTION</span></span>|<span data-ttu-id="bd038-479">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-479">String</span></span>|  
|<span data-ttu-id="bd038-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="bd038-480">DATE_CREATED</span></span>|<span data-ttu-id="bd038-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd038-481">DateTime</span></span>|  
|<span data-ttu-id="bd038-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="bd038-482">DATE_MODIFIED</span></span>|<span data-ttu-id="bd038-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd038-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="bd038-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="bd038-484">Indexes</span></span>  
  
|<span data-ttu-id="bd038-485">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-485">ColumnName</span></span>|<span data-ttu-id="bd038-486">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-487">TABLE_CATALOG</span></span>|<span data-ttu-id="bd038-488">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-488">String</span></span>|  
|<span data-ttu-id="bd038-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="bd038-490">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-490">String</span></span>|  
|<span data-ttu-id="bd038-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-491">TABLE_NAME</span></span>|<span data-ttu-id="bd038-492">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-492">String</span></span>|  
|<span data-ttu-id="bd038-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-493">INDEX_CATALOG</span></span>|<span data-ttu-id="bd038-494">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-494">String</span></span>|  
|<span data-ttu-id="bd038-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="bd038-496">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-496">String</span></span>|  
|<span data-ttu-id="bd038-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-497">INDEX_NAME</span></span>|<span data-ttu-id="bd038-498">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-498">String</span></span>|  
|<span data-ttu-id="bd038-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="bd038-499">PRIMARY_KEY</span></span>|<span data-ttu-id="bd038-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-500">Boolean</span></span>|  
|<span data-ttu-id="bd038-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="bd038-501">UNIQUE</span></span>|<span data-ttu-id="bd038-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-502">Boolean</span></span>|  
|<span data-ttu-id="bd038-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="bd038-503">CLUSTERED</span></span>|<span data-ttu-id="bd038-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-504">Boolean</span></span>|  
|<span data-ttu-id="bd038-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="bd038-505">TYPE</span></span>|<span data-ttu-id="bd038-506">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-506">Int32</span></span>|  
|<span data-ttu-id="bd038-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="bd038-507">FILL_FACTOR</span></span>|<span data-ttu-id="bd038-508">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-508">Int32</span></span>|  
|<span data-ttu-id="bd038-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="bd038-509">INITIAL_SIZE</span></span>|<span data-ttu-id="bd038-510">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-510">Int32</span></span>|  
|<span data-ttu-id="bd038-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="bd038-511">NULLS</span></span>|<span data-ttu-id="bd038-512">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-512">Int32</span></span>|  
|<span data-ttu-id="bd038-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="bd038-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="bd038-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-514">Boolean</span></span>|  
|<span data-ttu-id="bd038-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="bd038-515">AUTO_UPDATE</span></span>|<span data-ttu-id="bd038-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-516">Boolean</span></span>|  
|<span data-ttu-id="bd038-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="bd038-517">NULL_COLLATION</span></span>|<span data-ttu-id="bd038-518">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-518">Int32</span></span>|  
|<span data-ttu-id="bd038-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="bd038-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="bd038-520">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-520">Int64</span></span>|  
|<span data-ttu-id="bd038-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-521">COLUMN_NAME</span></span>|<span data-ttu-id="bd038-522">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-522">String</span></span>|  
|<span data-ttu-id="bd038-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="bd038-523">COLUMN_GUID</span></span>|<span data-ttu-id="bd038-524">Guid</span><span class="sxs-lookup"><span data-stu-id="bd038-524">Guid</span></span>|  
|<span data-ttu-id="bd038-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="bd038-525">COLUMN_PROPID</span></span>|<span data-ttu-id="bd038-526">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-526">Int64</span></span>|  
|<span data-ttu-id="bd038-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="bd038-527">COLLATION</span></span>|<span data-ttu-id="bd038-528">Int16</span><span class="sxs-lookup"><span data-stu-id="bd038-528">Int16</span></span>|  
|<span data-ttu-id="bd038-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="bd038-529">CARDINALITY</span></span>|<span data-ttu-id="bd038-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="bd038-530">Decimal</span></span>|  
|<span data-ttu-id="bd038-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="bd038-531">PAGES</span></span>|<span data-ttu-id="bd038-532">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-532">Int32</span></span>|  
|<span data-ttu-id="bd038-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="bd038-533">FILTER_CONDITION</span></span>|<span data-ttu-id="bd038-534">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-534">String</span></span>|  
|<span data-ttu-id="bd038-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="bd038-535">INTEGRATED</span></span>|<span data-ttu-id="bd038-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="bd038-537">Microsoft Jet OLE DB    </span><span class="sxs-lookup"><span data-stu-id="bd038-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="bd038-538">Microsoft Jet OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="bd038-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="bd038-539">Tables</span><span class="sxs-lookup"><span data-stu-id="bd038-539">Tables</span></span>  
  
-   <span data-ttu-id="bd038-540">Columns</span><span class="sxs-lookup"><span data-stu-id="bd038-540">Columns</span></span>  
  
-   <span data-ttu-id="bd038-541">절차</span><span class="sxs-lookup"><span data-stu-id="bd038-541">Procedures</span></span>  
  
-   <span data-ttu-id="bd038-542">뷰</span><span class="sxs-lookup"><span data-stu-id="bd038-542">Views</span></span>  
  
-   <span data-ttu-id="bd038-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="bd038-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="bd038-544">Tables</span><span class="sxs-lookup"><span data-stu-id="bd038-544">Tables</span></span>  
  
|<span data-ttu-id="bd038-545">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-545">ColumnName</span></span>|<span data-ttu-id="bd038-546">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-547">TABLE_CATALOG</span></span>|<span data-ttu-id="bd038-548">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-548">String</span></span>|  
|<span data-ttu-id="bd038-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="bd038-550">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-550">String</span></span>|  
|<span data-ttu-id="bd038-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-551">TABLE_NAME</span></span>|<span data-ttu-id="bd038-552">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-552">String</span></span>|  
|<span data-ttu-id="bd038-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="bd038-553">TABLE_TYPE</span></span>|<span data-ttu-id="bd038-554">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-554">String</span></span>|  
|<span data-ttu-id="bd038-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="bd038-555">TABLE_GUID</span></span>|<span data-ttu-id="bd038-556">Guid</span><span class="sxs-lookup"><span data-stu-id="bd038-556">Guid</span></span>|  
|<span data-ttu-id="bd038-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd038-557">DESCRIPTION</span></span>|<span data-ttu-id="bd038-558">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-558">String</span></span>|  
|<span data-ttu-id="bd038-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="bd038-559">TABLE_PROPID</span></span>|<span data-ttu-id="bd038-560">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-560">Int64</span></span>|  
|<span data-ttu-id="bd038-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="bd038-561">DATE_CREATED</span></span>|<span data-ttu-id="bd038-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd038-562">DateTime</span></span>|  
|<span data-ttu-id="bd038-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="bd038-563">DATE_MODIFIED</span></span>|<span data-ttu-id="bd038-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd038-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="bd038-565">Columns</span><span class="sxs-lookup"><span data-stu-id="bd038-565">Columns</span></span>  
  
|<span data-ttu-id="bd038-566">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-566">ColumnName</span></span>|<span data-ttu-id="bd038-567">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-568">TABLE_CATALOG</span></span>|<span data-ttu-id="bd038-569">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-569">String</span></span>|  
|<span data-ttu-id="bd038-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="bd038-571">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-571">String</span></span>|  
|<span data-ttu-id="bd038-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-572">TABLE_NAME</span></span>|<span data-ttu-id="bd038-573">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-573">String</span></span>|  
|<span data-ttu-id="bd038-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-574">COLUMN_NAME</span></span>|<span data-ttu-id="bd038-575">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-575">String</span></span>|  
|<span data-ttu-id="bd038-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="bd038-576">COLUMN_GUID</span></span>|<span data-ttu-id="bd038-577">Guid</span><span class="sxs-lookup"><span data-stu-id="bd038-577">Guid</span></span>|  
|<span data-ttu-id="bd038-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="bd038-578">COLUMN_PROPID</span></span>|<span data-ttu-id="bd038-579">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-579">Int64</span></span>|  
|<span data-ttu-id="bd038-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="bd038-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="bd038-581">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-581">Int64</span></span>|  
|<span data-ttu-id="bd038-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="bd038-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="bd038-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-583">Boolean</span></span>|  
|<span data-ttu-id="bd038-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="bd038-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="bd038-585">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-585">String</span></span>|  
|<span data-ttu-id="bd038-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="bd038-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="bd038-587">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-587">Int64</span></span>|  
|<span data-ttu-id="bd038-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="bd038-588">IS_NULLABLE</span></span>|<span data-ttu-id="bd038-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-589">Boolean</span></span>|  
|<span data-ttu-id="bd038-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="bd038-590">DATA_TYPE</span></span>|<span data-ttu-id="bd038-591">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-591">Int32</span></span>|  
|<span data-ttu-id="bd038-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="bd038-592">TYPE_GUID</span></span>|<span data-ttu-id="bd038-593">Guid</span><span class="sxs-lookup"><span data-stu-id="bd038-593">Guid</span></span>|  
|<span data-ttu-id="bd038-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="bd038-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="bd038-595">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-595">Int64</span></span>|  
|<span data-ttu-id="bd038-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="bd038-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="bd038-597">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-597">Int64</span></span>|  
|<span data-ttu-id="bd038-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="bd038-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="bd038-599">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-599">Int32</span></span>|  
|<span data-ttu-id="bd038-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="bd038-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="bd038-601">Int16</span><span class="sxs-lookup"><span data-stu-id="bd038-601">Int16</span></span>|  
|<span data-ttu-id="bd038-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="bd038-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="bd038-603">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-603">Int64</span></span>|  
|<span data-ttu-id="bd038-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="bd038-605">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-605">String</span></span>|  
|<span data-ttu-id="bd038-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="bd038-607">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-607">String</span></span>|  
|<span data-ttu-id="bd038-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="bd038-609">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-609">String</span></span>|  
|<span data-ttu-id="bd038-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="bd038-611">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-611">String</span></span>|  
|<span data-ttu-id="bd038-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="bd038-613">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-613">String</span></span>|  
|<span data-ttu-id="bd038-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-614">COLLATION_NAME</span></span>|<span data-ttu-id="bd038-615">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-615">String</span></span>|  
|<span data-ttu-id="bd038-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="bd038-617">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-617">String</span></span>|  
|<span data-ttu-id="bd038-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="bd038-619">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-619">String</span></span>|  
|<span data-ttu-id="bd038-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-620">DOMAIN_NAME</span></span>|<span data-ttu-id="bd038-621">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-621">String</span></span>|  
|<span data-ttu-id="bd038-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd038-622">DESCRIPTION</span></span>|<span data-ttu-id="bd038-623">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="bd038-624">절차</span><span class="sxs-lookup"><span data-stu-id="bd038-624">Procedures</span></span>  
  
|<span data-ttu-id="bd038-625">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-625">ColumnName</span></span>|<span data-ttu-id="bd038-626">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="bd038-628">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-628">String</span></span>|  
|<span data-ttu-id="bd038-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="bd038-630">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-630">String</span></span>|  
|<span data-ttu-id="bd038-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="bd038-632">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-632">String</span></span>|  
|<span data-ttu-id="bd038-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="bd038-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="bd038-634">Int16</span><span class="sxs-lookup"><span data-stu-id="bd038-634">Int16</span></span>|  
|<span data-ttu-id="bd038-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="bd038-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="bd038-636">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-636">String</span></span>|  
|<span data-ttu-id="bd038-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd038-637">DESCRIPTION</span></span>|<span data-ttu-id="bd038-638">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-638">String</span></span>|  
|<span data-ttu-id="bd038-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="bd038-639">DATE_CREATED</span></span>|<span data-ttu-id="bd038-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd038-640">DateTime</span></span>|  
|<span data-ttu-id="bd038-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="bd038-641">DATE_MODIFIED</span></span>|<span data-ttu-id="bd038-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd038-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="bd038-643">뷰</span><span class="sxs-lookup"><span data-stu-id="bd038-643">Views</span></span>  
  
|<span data-ttu-id="bd038-644">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-644">ColumnName</span></span>|<span data-ttu-id="bd038-645">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-646">TABLE_CATALOG</span></span>|<span data-ttu-id="bd038-647">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-647">String</span></span>|  
|<span data-ttu-id="bd038-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="bd038-649">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-649">String</span></span>|  
|<span data-ttu-id="bd038-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-650">TABLE_NAME</span></span>|<span data-ttu-id="bd038-651">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-651">String</span></span>|  
|<span data-ttu-id="bd038-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="bd038-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="bd038-653">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-653">String</span></span>|  
|<span data-ttu-id="bd038-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="bd038-654">CHECK_OPTION</span></span>|<span data-ttu-id="bd038-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-655">Boolean</span></span>|  
|<span data-ttu-id="bd038-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="bd038-656">IS_UPDATABLE</span></span>|<span data-ttu-id="bd038-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-657">Boolean</span></span>|  
|<span data-ttu-id="bd038-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd038-658">DESCRIPTION</span></span>|<span data-ttu-id="bd038-659">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-659">String</span></span>|  
|<span data-ttu-id="bd038-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="bd038-660">DATE_CREATED</span></span>|<span data-ttu-id="bd038-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd038-661">DateTime</span></span>|  
|<span data-ttu-id="bd038-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="bd038-662">DATE_MODIFIED</span></span>|<span data-ttu-id="bd038-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd038-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="bd038-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="bd038-664">Indexes</span></span>  
  
|<span data-ttu-id="bd038-665">열 이름</span><span class="sxs-lookup"><span data-stu-id="bd038-665">ColumnName</span></span>|<span data-ttu-id="bd038-666">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd038-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="bd038-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-667">TABLE_CATALOG</span></span>|<span data-ttu-id="bd038-668">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-668">String</span></span>|  
|<span data-ttu-id="bd038-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="bd038-670">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-670">String</span></span>|  
|<span data-ttu-id="bd038-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-671">TABLE_NAME</span></span>|<span data-ttu-id="bd038-672">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-672">String</span></span>|  
|<span data-ttu-id="bd038-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bd038-673">INDEX_CATALOG</span></span>|<span data-ttu-id="bd038-674">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-674">String</span></span>|  
|<span data-ttu-id="bd038-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="bd038-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="bd038-676">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-676">String</span></span>|  
|<span data-ttu-id="bd038-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-677">INDEX_NAME</span></span>|<span data-ttu-id="bd038-678">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-678">String</span></span>|  
|<span data-ttu-id="bd038-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="bd038-679">PRIMARY_KEY</span></span>|<span data-ttu-id="bd038-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-680">Boolean</span></span>|  
|<span data-ttu-id="bd038-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="bd038-681">UNIQUE</span></span>|<span data-ttu-id="bd038-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-682">Boolean</span></span>|  
|<span data-ttu-id="bd038-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="bd038-683">CLUSTERED</span></span>|<span data-ttu-id="bd038-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-684">Boolean</span></span>|  
|<span data-ttu-id="bd038-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="bd038-685">TYPE</span></span>|<span data-ttu-id="bd038-686">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-686">Int32</span></span>|  
|<span data-ttu-id="bd038-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="bd038-687">FILL_FACTOR</span></span>|<span data-ttu-id="bd038-688">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-688">Int32</span></span>|  
|<span data-ttu-id="bd038-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="bd038-689">INITIAL_SIZE</span></span>|<span data-ttu-id="bd038-690">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-690">Int32</span></span>|  
|<span data-ttu-id="bd038-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="bd038-691">NULLS</span></span>|<span data-ttu-id="bd038-692">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-692">Int32</span></span>|  
|<span data-ttu-id="bd038-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="bd038-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="bd038-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-694">Boolean</span></span>|  
|<span data-ttu-id="bd038-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="bd038-695">AUTO_UPDATE</span></span>|<span data-ttu-id="bd038-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="bd038-696">Boolean</span></span>|  
|<span data-ttu-id="bd038-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="bd038-697">NULL_COLLATION</span></span>|<span data-ttu-id="bd038-698">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-698">Int32</span></span>|  
|<span data-ttu-id="bd038-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="bd038-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="bd038-700">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-700">Int64</span></span>|  
|<span data-ttu-id="bd038-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="bd038-701">COLUMN_NAME</span></span>|<span data-ttu-id="bd038-702">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-702">String</span></span>|  
|<span data-ttu-id="bd038-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="bd038-703">COLUMN_GUID</span></span>|<span data-ttu-id="bd038-704">Guid</span><span class="sxs-lookup"><span data-stu-id="bd038-704">Guid</span></span>|  
|<span data-ttu-id="bd038-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="bd038-705">COLUMN_PROPID</span></span>|<span data-ttu-id="bd038-706">Int64</span><span class="sxs-lookup"><span data-stu-id="bd038-706">Int64</span></span>|  
|<span data-ttu-id="bd038-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="bd038-707">COLLATION</span></span>|<span data-ttu-id="bd038-708">Int16</span><span class="sxs-lookup"><span data-stu-id="bd038-708">Int16</span></span>|  
|<span data-ttu-id="bd038-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="bd038-709">CARDINALITY</span></span>|<span data-ttu-id="bd038-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="bd038-710">Decimal</span></span>|  
|<span data-ttu-id="bd038-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="bd038-711">PAGES</span></span>|<span data-ttu-id="bd038-712">Int32</span><span class="sxs-lookup"><span data-stu-id="bd038-712">Int32</span></span>|  
|<span data-ttu-id="bd038-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="bd038-713">FILTER_CONDITION</span></span>|<span data-ttu-id="bd038-714">문자열</span><span class="sxs-lookup"><span data-stu-id="bd038-714">String</span></span>|  
|<span data-ttu-id="bd038-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="bd038-715">INTEGRATED</span></span>|<span data-ttu-id="bd038-716">부울</span><span class="sxs-lookup"><span data-stu-id="bd038-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd038-717">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd038-717">See Also</span></span>  
 [<span data-ttu-id="bd038-718">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="bd038-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
