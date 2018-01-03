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
ms.workload: dotnet
ms.openlocfilehash: e120ea532b6da455e31ce7345b6c4b2be1ec975f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="9ca14-102">OLE DB 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="9ca14-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="9ca14-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 OLE DB 공급자에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca14-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="9ca14-104">Microsoft SQL Server OLE DB 공급자</span><span class="sxs-lookup"><span data-stu-id="9ca14-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="9ca14-105">Microsoft SQL Server OLE DB Driver에서는 공통 스키마 컬렉션을 비롯 하 여 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca14-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9ca14-106">Tables</span><span class="sxs-lookup"><span data-stu-id="9ca14-106">Tables</span></span>  
  
-   <span data-ttu-id="9ca14-107">Columns</span><span class="sxs-lookup"><span data-stu-id="9ca14-107">Columns</span></span>  
  
-   <span data-ttu-id="9ca14-108">절차</span><span class="sxs-lookup"><span data-stu-id="9ca14-108">Procedures</span></span>  
  
-   <span data-ttu-id="9ca14-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9ca14-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="9ca14-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="9ca14-110">Catalog</span></span>  
  
-   <span data-ttu-id="9ca14-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="9ca14-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="9ca14-112">Tables</span><span class="sxs-lookup"><span data-stu-id="9ca14-112">Tables</span></span>  
  
|<span data-ttu-id="9ca14-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-113">ColumnName</span></span>|<span data-ttu-id="9ca14-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-115">TABLE_CATALOG</span></span>|<span data-ttu-id="9ca14-116">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-116">String</span></span>|  
|<span data-ttu-id="9ca14-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="9ca14-118">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-118">String</span></span>|  
|<span data-ttu-id="9ca14-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-119">TABLE_NAME</span></span>|<span data-ttu-id="9ca14-120">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-120">String</span></span>|  
|<span data-ttu-id="9ca14-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ca14-121">TABLE_TYPE</span></span>|<span data-ttu-id="9ca14-122">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-122">String</span></span>|  
|<span data-ttu-id="9ca14-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="9ca14-123">TABLE_GUID</span></span>|<span data-ttu-id="9ca14-124">Guid</span><span class="sxs-lookup"><span data-stu-id="9ca14-124">Guid</span></span>|  
|<span data-ttu-id="9ca14-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ca14-125">DESCRIPTION</span></span>|<span data-ttu-id="9ca14-126">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-126">String</span></span>|  
|<span data-ttu-id="9ca14-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="9ca14-127">TABLE_PROPID</span></span>|<span data-ttu-id="9ca14-128">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-128">Int64</span></span>|  
|<span data-ttu-id="9ca14-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9ca14-129">DATE_CREATED</span></span>|<span data-ttu-id="9ca14-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca14-130">DateTime</span></span>|  
|<span data-ttu-id="9ca14-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9ca14-131">DATE_MODIFIED</span></span>|<span data-ttu-id="9ca14-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca14-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9ca14-133">Columns</span><span class="sxs-lookup"><span data-stu-id="9ca14-133">Columns</span></span>  
  
|<span data-ttu-id="9ca14-134">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-134">ColumnName</span></span>|<span data-ttu-id="9ca14-135">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-136">TABLE_CATALOG</span></span>|<span data-ttu-id="9ca14-137">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-137">String</span></span>|  
|<span data-ttu-id="9ca14-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="9ca14-139">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-139">String</span></span>|  
|<span data-ttu-id="9ca14-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-140">TABLE_NAME</span></span>|<span data-ttu-id="9ca14-141">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-141">String</span></span>|  
|<span data-ttu-id="9ca14-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-142">COLUMN_NAME</span></span>|<span data-ttu-id="9ca14-143">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-143">String</span></span>|  
|<span data-ttu-id="9ca14-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9ca14-144">COLUMN_GUID</span></span>|<span data-ttu-id="9ca14-145">Guid</span><span class="sxs-lookup"><span data-stu-id="9ca14-145">Guid</span></span>|  
|<span data-ttu-id="9ca14-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9ca14-146">COLUMN_PROPID</span></span>|<span data-ttu-id="9ca14-147">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-147">Int64</span></span>|  
|<span data-ttu-id="9ca14-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ca14-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ca14-149">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-149">Int64</span></span>|  
|<span data-ttu-id="9ca14-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9ca14-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="9ca14-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-151">Boolean</span></span>|  
|<span data-ttu-id="9ca14-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9ca14-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="9ca14-153">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-153">String</span></span>|  
|<span data-ttu-id="9ca14-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="9ca14-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="9ca14-155">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-155">Int64</span></span>|  
|<span data-ttu-id="9ca14-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ca14-156">IS_NULLABLE</span></span>|<span data-ttu-id="9ca14-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-157">Boolean</span></span>|  
|<span data-ttu-id="9ca14-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ca14-158">DATA_TYPE</span></span>|<span data-ttu-id="9ca14-159">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-159">Int32</span></span>|  
|<span data-ttu-id="9ca14-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9ca14-160">TYPE_GUID</span></span>|<span data-ttu-id="9ca14-161">Guid</span><span class="sxs-lookup"><span data-stu-id="9ca14-161">Guid</span></span>|  
|<span data-ttu-id="9ca14-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ca14-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9ca14-163">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-163">Int64</span></span>|  
|<span data-ttu-id="9ca14-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ca14-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9ca14-165">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-165">Int64</span></span>|  
|<span data-ttu-id="9ca14-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9ca14-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9ca14-167">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-167">Int32</span></span>|  
|<span data-ttu-id="9ca14-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9ca14-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="9ca14-169">Int16</span><span class="sxs-lookup"><span data-stu-id="9ca14-169">Int16</span></span>|  
|<span data-ttu-id="9ca14-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9ca14-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="9ca14-171">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-171">Int64</span></span>|  
|<span data-ttu-id="9ca14-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="9ca14-173">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-173">String</span></span>|  
|<span data-ttu-id="9ca14-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="9ca14-175">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-175">String</span></span>|  
|<span data-ttu-id="9ca14-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="9ca14-177">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-177">String</span></span>|  
|<span data-ttu-id="9ca14-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="9ca14-179">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-179">String</span></span>|  
|<span data-ttu-id="9ca14-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="9ca14-181">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-181">String</span></span>|  
|<span data-ttu-id="9ca14-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-182">COLLATION_NAME</span></span>|<span data-ttu-id="9ca14-183">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-183">String</span></span>|  
|<span data-ttu-id="9ca14-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="9ca14-185">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-185">String</span></span>|  
|<span data-ttu-id="9ca14-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="9ca14-187">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-187">String</span></span>|  
|<span data-ttu-id="9ca14-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-188">DOMAIN_NAME</span></span>|<span data-ttu-id="9ca14-189">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-189">String</span></span>|  
|<span data-ttu-id="9ca14-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ca14-190">DESCRIPTION</span></span>|<span data-ttu-id="9ca14-191">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-191">String</span></span>|  
|<span data-ttu-id="9ca14-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="9ca14-192">COLUMN_LCID</span></span>|<span data-ttu-id="9ca14-193">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-193">Int32</span></span>|  
|<span data-ttu-id="9ca14-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="9ca14-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="9ca14-195">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-195">Int32</span></span>|  
|<span data-ttu-id="9ca14-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="9ca14-196">COLUMN_SORTID</span></span>|<span data-ttu-id="9ca14-197">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-197">Int32</span></span>|  
|<span data-ttu-id="9ca14-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="9ca14-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="9ca14-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="9ca14-199">Byte[]</span></span>|  
|<span data-ttu-id="9ca14-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="9ca14-200">IS_COMPUTED</span></span>|<span data-ttu-id="9ca14-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9ca14-202">절차</span><span class="sxs-lookup"><span data-stu-id="9ca14-202">Procedures</span></span>  
  
|<span data-ttu-id="9ca14-203">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-203">ColumnName</span></span>|<span data-ttu-id="9ca14-204">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9ca14-206">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-206">String</span></span>|  
|<span data-ttu-id="9ca14-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9ca14-208">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-208">String</span></span>|  
|<span data-ttu-id="9ca14-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="9ca14-210">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-210">String</span></span>|  
|<span data-ttu-id="9ca14-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ca14-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9ca14-212">Int16</span><span class="sxs-lookup"><span data-stu-id="9ca14-212">Int16</span></span>|  
|<span data-ttu-id="9ca14-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9ca14-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="9ca14-214">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-214">String</span></span>|  
|<span data-ttu-id="9ca14-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ca14-215">DESCRIPTION</span></span>|<span data-ttu-id="9ca14-216">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-216">String</span></span>|  
|<span data-ttu-id="9ca14-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9ca14-217">DATE_CREATED</span></span>|<span data-ttu-id="9ca14-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca14-218">DateTime</span></span>|  
|<span data-ttu-id="9ca14-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9ca14-219">DATE_MODIFIED</span></span>|<span data-ttu-id="9ca14-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca14-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="9ca14-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9ca14-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="9ca14-222">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-222">ColumnName</span></span>|<span data-ttu-id="9ca14-223">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9ca14-225">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-225">String</span></span>|  
|<span data-ttu-id="9ca14-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9ca14-227">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-227">String</span></span>|  
|<span data-ttu-id="9ca14-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="9ca14-229">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-229">String</span></span>|  
|<span data-ttu-id="9ca14-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-230">PARAMETER_NAME</span></span>|<span data-ttu-id="9ca14-231">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-231">String</span></span>|  
|<span data-ttu-id="9ca14-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ca14-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ca14-233">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-233">Int32</span></span>|  
|<span data-ttu-id="9ca14-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ca14-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="9ca14-235">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-235">Int32</span></span>|  
|<span data-ttu-id="9ca14-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9ca14-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="9ca14-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-237">Boolean</span></span>|  
|<span data-ttu-id="9ca14-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9ca14-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="9ca14-239">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-239">String</span></span>|  
|<span data-ttu-id="9ca14-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ca14-240">IS_NULLABLE</span></span>|<span data-ttu-id="9ca14-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-241">Boolean</span></span>|  
|<span data-ttu-id="9ca14-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ca14-242">DATA_TYPE</span></span>|<span data-ttu-id="9ca14-243">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-243">Int32</span></span>|  
|<span data-ttu-id="9ca14-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ca14-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9ca14-245">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-245">Int64</span></span>|  
|<span data-ttu-id="9ca14-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ca14-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9ca14-247">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-247">Int64</span></span>|  
|<span data-ttu-id="9ca14-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9ca14-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9ca14-249">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-249">Int32</span></span>|  
|<span data-ttu-id="9ca14-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9ca14-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="9ca14-251">Int16</span><span class="sxs-lookup"><span data-stu-id="9ca14-251">Int16</span></span>|  
|<span data-ttu-id="9ca14-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ca14-252">DESCRIPTION</span></span>|<span data-ttu-id="9ca14-253">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-253">String</span></span>|  
|<span data-ttu-id="9ca14-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-254">TYPE_NAME</span></span>|<span data-ttu-id="9ca14-255">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-255">String</span></span>|  
|<span data-ttu-id="9ca14-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="9ca14-257">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="9ca14-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="9ca14-258">Catalog</span></span>  
  
|<span data-ttu-id="9ca14-259">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-259">ColumnName</span></span>|<span data-ttu-id="9ca14-260">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-261">CATALOG_NAME</span></span>|<span data-ttu-id="9ca14-262">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-262">String</span></span>|  
|<span data-ttu-id="9ca14-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ca14-263">DESCRIPTION</span></span>|<span data-ttu-id="9ca14-264">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9ca14-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="9ca14-265">Indexes</span></span>  
  
|<span data-ttu-id="9ca14-266">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-266">ColumnName</span></span>|<span data-ttu-id="9ca14-267">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-268">TABLE_CATALOG</span></span>|<span data-ttu-id="9ca14-269">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-269">String</span></span>|  
|<span data-ttu-id="9ca14-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="9ca14-271">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-271">String</span></span>|  
|<span data-ttu-id="9ca14-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-272">TABLE_NAME</span></span>|<span data-ttu-id="9ca14-273">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-273">String</span></span>|  
|<span data-ttu-id="9ca14-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-274">INDEX_CATALOG</span></span>|<span data-ttu-id="9ca14-275">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-275">String</span></span>|  
|<span data-ttu-id="9ca14-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="9ca14-277">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-277">String</span></span>|  
|<span data-ttu-id="9ca14-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-278">INDEX_NAME</span></span>|<span data-ttu-id="9ca14-279">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-279">String</span></span>|  
|<span data-ttu-id="9ca14-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="9ca14-280">PRIMARY_KEY</span></span>|<span data-ttu-id="9ca14-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-281">Boolean</span></span>|  
|<span data-ttu-id="9ca14-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9ca14-282">UNIQUE</span></span>|<span data-ttu-id="9ca14-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-283">Boolean</span></span>|  
|<span data-ttu-id="9ca14-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="9ca14-284">CLUSTERED</span></span>|<span data-ttu-id="9ca14-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-285">Boolean</span></span>|  
|<span data-ttu-id="9ca14-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="9ca14-286">TYPE</span></span>|<span data-ttu-id="9ca14-287">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-287">Int32</span></span>|  
|<span data-ttu-id="9ca14-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="9ca14-288">FILL_FACTOR</span></span>|<span data-ttu-id="9ca14-289">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-289">Int32</span></span>|  
|<span data-ttu-id="9ca14-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="9ca14-290">INITIAL_SIZE</span></span>|<span data-ttu-id="9ca14-291">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-291">Int32</span></span>|  
|<span data-ttu-id="9ca14-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="9ca14-292">NULLS</span></span>|<span data-ttu-id="9ca14-293">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-293">Int32</span></span>|  
|<span data-ttu-id="9ca14-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9ca14-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="9ca14-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-295">Boolean</span></span>|  
|<span data-ttu-id="9ca14-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="9ca14-296">AUTO_UPDATE</span></span>|<span data-ttu-id="9ca14-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-297">Boolean</span></span>|  
|<span data-ttu-id="9ca14-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="9ca14-298">NULL_COLLATION</span></span>|<span data-ttu-id="9ca14-299">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-299">Int32</span></span>|  
|<span data-ttu-id="9ca14-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ca14-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ca14-301">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-301">Int64</span></span>|  
|<span data-ttu-id="9ca14-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-302">COLUMN_NAME</span></span>|<span data-ttu-id="9ca14-303">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-303">String</span></span>|  
|<span data-ttu-id="9ca14-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9ca14-304">COLUMN_GUID</span></span>|<span data-ttu-id="9ca14-305">Guid</span><span class="sxs-lookup"><span data-stu-id="9ca14-305">Guid</span></span>|  
|<span data-ttu-id="9ca14-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9ca14-306">COLUMN_PROPID</span></span>|<span data-ttu-id="9ca14-307">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-307">Int64</span></span>|  
|<span data-ttu-id="9ca14-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9ca14-308">COLLATION</span></span>|<span data-ttu-id="9ca14-309">Int16</span><span class="sxs-lookup"><span data-stu-id="9ca14-309">Int16</span></span>|  
|<span data-ttu-id="9ca14-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="9ca14-310">CARDINALITY</span></span>|<span data-ttu-id="9ca14-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="9ca14-311">Decimal</span></span>|  
|<span data-ttu-id="9ca14-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="9ca14-312">PAGES</span></span>|<span data-ttu-id="9ca14-313">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-313">Int32</span></span>|  
|<span data-ttu-id="9ca14-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9ca14-314">FILTER_CONDITION</span></span>|<span data-ttu-id="9ca14-315">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-315">String</span></span>|  
|<span data-ttu-id="9ca14-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="9ca14-316">INTEGRATED</span></span>|<span data-ttu-id="9ca14-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="9ca14-318">Microsoft Oracle OLE DB    </span><span class="sxs-lookup"><span data-stu-id="9ca14-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="9ca14-319">Microsoft Oracle OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="9ca14-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9ca14-320">Tables</span><span class="sxs-lookup"><span data-stu-id="9ca14-320">Tables</span></span>  
  
-   <span data-ttu-id="9ca14-321">Columns</span><span class="sxs-lookup"><span data-stu-id="9ca14-321">Columns</span></span>  
  
-   <span data-ttu-id="9ca14-322">절차</span><span class="sxs-lookup"><span data-stu-id="9ca14-322">Procedures</span></span>  
  
-   <span data-ttu-id="9ca14-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9ca14-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="9ca14-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9ca14-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="9ca14-325">뷰</span><span class="sxs-lookup"><span data-stu-id="9ca14-325">Views</span></span>  
  
-   <span data-ttu-id="9ca14-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="9ca14-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="9ca14-327">Tables</span><span class="sxs-lookup"><span data-stu-id="9ca14-327">Tables</span></span>  
  
|<span data-ttu-id="9ca14-328">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-328">ColumnName</span></span>|<span data-ttu-id="9ca14-329">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-330">TABLE_CATALOG</span></span>|<span data-ttu-id="9ca14-331">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-331">String</span></span>|  
|<span data-ttu-id="9ca14-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="9ca14-333">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-333">String</span></span>|  
|<span data-ttu-id="9ca14-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-334">TABLE_NAME</span></span>|<span data-ttu-id="9ca14-335">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-335">String</span></span>|  
|<span data-ttu-id="9ca14-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ca14-336">TABLE_TYPE</span></span>|<span data-ttu-id="9ca14-337">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-337">String</span></span>|  
|<span data-ttu-id="9ca14-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="9ca14-338">TABLE_GUID</span></span>|<span data-ttu-id="9ca14-339">Guid</span><span class="sxs-lookup"><span data-stu-id="9ca14-339">Guid</span></span>|  
|<span data-ttu-id="9ca14-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ca14-340">DESCRIPTION</span></span>|<span data-ttu-id="9ca14-341">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-341">String</span></span>|  
|<span data-ttu-id="9ca14-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="9ca14-342">TABLE_PROPID</span></span>|<span data-ttu-id="9ca14-343">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-343">Int64</span></span>|  
|<span data-ttu-id="9ca14-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9ca14-344">DATE_CREATED</span></span>|<span data-ttu-id="9ca14-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca14-345">DateTime</span></span>|  
|<span data-ttu-id="9ca14-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9ca14-346">DATE_MODIFIED</span></span>|<span data-ttu-id="9ca14-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca14-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9ca14-348">Columns</span><span class="sxs-lookup"><span data-stu-id="9ca14-348">Columns</span></span>  
  
|<span data-ttu-id="9ca14-349">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-349">ColumnName</span></span>|<span data-ttu-id="9ca14-350">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-351">TABLE_CATALOG</span></span>|<span data-ttu-id="9ca14-352">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-352">String</span></span>|  
|<span data-ttu-id="9ca14-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="9ca14-354">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-354">String</span></span>|  
|<span data-ttu-id="9ca14-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-355">TABLE_NAME</span></span>|<span data-ttu-id="9ca14-356">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-356">String</span></span>|  
|<span data-ttu-id="9ca14-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-357">COLUMN_NAME</span></span>|<span data-ttu-id="9ca14-358">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-358">String</span></span>|  
|<span data-ttu-id="9ca14-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9ca14-359">COLUMN_GUID</span></span>|<span data-ttu-id="9ca14-360">Guid</span><span class="sxs-lookup"><span data-stu-id="9ca14-360">Guid</span></span>|  
|<span data-ttu-id="9ca14-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9ca14-361">COLUMN_PROPID</span></span>|<span data-ttu-id="9ca14-362">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-362">Int64</span></span>|  
|<span data-ttu-id="9ca14-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ca14-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ca14-364">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-364">Int64</span></span>|  
|<span data-ttu-id="9ca14-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9ca14-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="9ca14-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-366">Boolean</span></span>|  
|<span data-ttu-id="9ca14-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9ca14-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="9ca14-368">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-368">String</span></span>|  
|<span data-ttu-id="9ca14-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="9ca14-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="9ca14-370">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-370">Int64</span></span>|  
|<span data-ttu-id="9ca14-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ca14-371">IS_NULLABLE</span></span>|<span data-ttu-id="9ca14-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-372">Boolean</span></span>|  
|<span data-ttu-id="9ca14-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ca14-373">DATA_TYPE</span></span>|<span data-ttu-id="9ca14-374">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-374">Int32</span></span>|  
|<span data-ttu-id="9ca14-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9ca14-375">TYPE_GUID</span></span>|<span data-ttu-id="9ca14-376">Guid</span><span class="sxs-lookup"><span data-stu-id="9ca14-376">Guid</span></span>|  
|<span data-ttu-id="9ca14-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ca14-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9ca14-378">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-378">Int64</span></span>|  
|<span data-ttu-id="9ca14-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ca14-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9ca14-380">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-380">Int64</span></span>|  
|<span data-ttu-id="9ca14-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9ca14-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9ca14-382">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-382">Int32</span></span>|  
|<span data-ttu-id="9ca14-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9ca14-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="9ca14-384">Int16</span><span class="sxs-lookup"><span data-stu-id="9ca14-384">Int16</span></span>|  
|<span data-ttu-id="9ca14-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9ca14-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="9ca14-386">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-386">Int64</span></span>|  
|<span data-ttu-id="9ca14-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="9ca14-388">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-388">String</span></span>|  
|<span data-ttu-id="9ca14-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="9ca14-390">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-390">String</span></span>|  
|<span data-ttu-id="9ca14-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="9ca14-392">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-392">String</span></span>|  
|<span data-ttu-id="9ca14-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="9ca14-394">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-394">String</span></span>|  
|<span data-ttu-id="9ca14-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="9ca14-396">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-396">String</span></span>|  
|<span data-ttu-id="9ca14-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-397">COLLATION_NAME</span></span>|<span data-ttu-id="9ca14-398">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-398">String</span></span>|  
|<span data-ttu-id="9ca14-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="9ca14-400">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-400">String</span></span>|  
|<span data-ttu-id="9ca14-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="9ca14-402">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-402">String</span></span>|  
|<span data-ttu-id="9ca14-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-403">DOMAIN_NAME</span></span>|<span data-ttu-id="9ca14-404">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-404">String</span></span>|  
|<span data-ttu-id="9ca14-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ca14-405">DESCRIPTION</span></span>|<span data-ttu-id="9ca14-406">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9ca14-407">절차</span><span class="sxs-lookup"><span data-stu-id="9ca14-407">Procedures</span></span>  
  
|<span data-ttu-id="9ca14-408">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-408">ColumnName</span></span>|<span data-ttu-id="9ca14-409">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9ca14-411">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-411">String</span></span>|  
|<span data-ttu-id="9ca14-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9ca14-413">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-413">String</span></span>|  
|<span data-ttu-id="9ca14-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="9ca14-415">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-415">String</span></span>|  
|<span data-ttu-id="9ca14-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ca14-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9ca14-417">Int16</span><span class="sxs-lookup"><span data-stu-id="9ca14-417">Int16</span></span>|  
|<span data-ttu-id="9ca14-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9ca14-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="9ca14-419">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-419">String</span></span>|  
|<span data-ttu-id="9ca14-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ca14-420">DESCRIPTION</span></span>|<span data-ttu-id="9ca14-421">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-421">String</span></span>|  
|<span data-ttu-id="9ca14-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9ca14-422">DATE_CREATED</span></span>|<span data-ttu-id="9ca14-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca14-423">DateTime</span></span>|  
|<span data-ttu-id="9ca14-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9ca14-424">DATE_MODIFIED</span></span>|<span data-ttu-id="9ca14-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca14-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="9ca14-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9ca14-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="9ca14-427">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-427">ColumnName</span></span>|<span data-ttu-id="9ca14-428">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9ca14-430">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-430">String</span></span>|  
|<span data-ttu-id="9ca14-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9ca14-432">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-432">String</span></span>|  
|<span data-ttu-id="9ca14-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="9ca14-434">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-434">String</span></span>|  
|<span data-ttu-id="9ca14-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-435">COLUMN_NAME</span></span>|<span data-ttu-id="9ca14-436">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-436">String</span></span>|  
|<span data-ttu-id="9ca14-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9ca14-437">COLUMN_GUID</span></span>|<span data-ttu-id="9ca14-438">Guid</span><span class="sxs-lookup"><span data-stu-id="9ca14-438">Guid</span></span>|  
|<span data-ttu-id="9ca14-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9ca14-439">COLUMN_PROPID</span></span>|<span data-ttu-id="9ca14-440">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-440">Int64</span></span>|  
|<span data-ttu-id="9ca14-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="9ca14-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="9ca14-442">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-442">Int64</span></span>|  
|<span data-ttu-id="9ca14-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ca14-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ca14-444">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-444">Int64</span></span>|  
|<span data-ttu-id="9ca14-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ca14-445">IS_NULLABLE</span></span>|<span data-ttu-id="9ca14-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-446">Boolean</span></span>|  
|<span data-ttu-id="9ca14-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ca14-447">DATA_TYPE</span></span>|<span data-ttu-id="9ca14-448">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-448">Int32</span></span>|  
|<span data-ttu-id="9ca14-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9ca14-449">TYPE_GUID</span></span>|<span data-ttu-id="9ca14-450">Guid</span><span class="sxs-lookup"><span data-stu-id="9ca14-450">Guid</span></span>|  
|<span data-ttu-id="9ca14-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ca14-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9ca14-452">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-452">Int64</span></span>|  
|<span data-ttu-id="9ca14-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ca14-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9ca14-454">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-454">Int64</span></span>|  
|<span data-ttu-id="9ca14-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9ca14-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9ca14-456">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-456">Int32</span></span>|  
|<span data-ttu-id="9ca14-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9ca14-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="9ca14-458">Int16</span><span class="sxs-lookup"><span data-stu-id="9ca14-458">Int16</span></span>|  
|<span data-ttu-id="9ca14-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ca14-459">DESCRIPTION</span></span>|<span data-ttu-id="9ca14-460">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-460">String</span></span>|  
|<span data-ttu-id="9ca14-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="9ca14-461">OVERLOAD</span></span>|<span data-ttu-id="9ca14-462">Int16</span><span class="sxs-lookup"><span data-stu-id="9ca14-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="9ca14-463">뷰</span><span class="sxs-lookup"><span data-stu-id="9ca14-463">Views</span></span>  
  
|<span data-ttu-id="9ca14-464">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-464">ColumnName</span></span>|<span data-ttu-id="9ca14-465">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-466">TABLE_CATALOG</span></span>|<span data-ttu-id="9ca14-467">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-467">String</span></span>|  
|<span data-ttu-id="9ca14-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="9ca14-469">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-469">String</span></span>|  
|<span data-ttu-id="9ca14-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-470">TABLE_NAME</span></span>|<span data-ttu-id="9ca14-471">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-471">String</span></span>|  
|<span data-ttu-id="9ca14-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9ca14-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="9ca14-473">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-473">String</span></span>|  
|<span data-ttu-id="9ca14-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="9ca14-474">CHECK_OPTION</span></span>|<span data-ttu-id="9ca14-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-475">Boolean</span></span>|  
|<span data-ttu-id="9ca14-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="9ca14-476">IS_UPDATABLE</span></span>|<span data-ttu-id="9ca14-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-477">Boolean</span></span>|  
|<span data-ttu-id="9ca14-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ca14-478">DESCRIPTION</span></span>|<span data-ttu-id="9ca14-479">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-479">String</span></span>|  
|<span data-ttu-id="9ca14-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9ca14-480">DATE_CREATED</span></span>|<span data-ttu-id="9ca14-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca14-481">DateTime</span></span>|  
|<span data-ttu-id="9ca14-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9ca14-482">DATE_MODIFIED</span></span>|<span data-ttu-id="9ca14-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca14-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9ca14-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="9ca14-484">Indexes</span></span>  
  
|<span data-ttu-id="9ca14-485">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-485">ColumnName</span></span>|<span data-ttu-id="9ca14-486">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-487">TABLE_CATALOG</span></span>|<span data-ttu-id="9ca14-488">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-488">String</span></span>|  
|<span data-ttu-id="9ca14-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="9ca14-490">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-490">String</span></span>|  
|<span data-ttu-id="9ca14-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-491">TABLE_NAME</span></span>|<span data-ttu-id="9ca14-492">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-492">String</span></span>|  
|<span data-ttu-id="9ca14-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-493">INDEX_CATALOG</span></span>|<span data-ttu-id="9ca14-494">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-494">String</span></span>|  
|<span data-ttu-id="9ca14-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="9ca14-496">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-496">String</span></span>|  
|<span data-ttu-id="9ca14-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-497">INDEX_NAME</span></span>|<span data-ttu-id="9ca14-498">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-498">String</span></span>|  
|<span data-ttu-id="9ca14-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="9ca14-499">PRIMARY_KEY</span></span>|<span data-ttu-id="9ca14-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-500">Boolean</span></span>|  
|<span data-ttu-id="9ca14-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9ca14-501">UNIQUE</span></span>|<span data-ttu-id="9ca14-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-502">Boolean</span></span>|  
|<span data-ttu-id="9ca14-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="9ca14-503">CLUSTERED</span></span>|<span data-ttu-id="9ca14-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-504">Boolean</span></span>|  
|<span data-ttu-id="9ca14-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="9ca14-505">TYPE</span></span>|<span data-ttu-id="9ca14-506">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-506">Int32</span></span>|  
|<span data-ttu-id="9ca14-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="9ca14-507">FILL_FACTOR</span></span>|<span data-ttu-id="9ca14-508">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-508">Int32</span></span>|  
|<span data-ttu-id="9ca14-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="9ca14-509">INITIAL_SIZE</span></span>|<span data-ttu-id="9ca14-510">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-510">Int32</span></span>|  
|<span data-ttu-id="9ca14-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="9ca14-511">NULLS</span></span>|<span data-ttu-id="9ca14-512">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-512">Int32</span></span>|  
|<span data-ttu-id="9ca14-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9ca14-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="9ca14-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-514">Boolean</span></span>|  
|<span data-ttu-id="9ca14-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="9ca14-515">AUTO_UPDATE</span></span>|<span data-ttu-id="9ca14-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-516">Boolean</span></span>|  
|<span data-ttu-id="9ca14-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="9ca14-517">NULL_COLLATION</span></span>|<span data-ttu-id="9ca14-518">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-518">Int32</span></span>|  
|<span data-ttu-id="9ca14-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ca14-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ca14-520">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-520">Int64</span></span>|  
|<span data-ttu-id="9ca14-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-521">COLUMN_NAME</span></span>|<span data-ttu-id="9ca14-522">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-522">String</span></span>|  
|<span data-ttu-id="9ca14-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9ca14-523">COLUMN_GUID</span></span>|<span data-ttu-id="9ca14-524">Guid</span><span class="sxs-lookup"><span data-stu-id="9ca14-524">Guid</span></span>|  
|<span data-ttu-id="9ca14-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9ca14-525">COLUMN_PROPID</span></span>|<span data-ttu-id="9ca14-526">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-526">Int64</span></span>|  
|<span data-ttu-id="9ca14-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9ca14-527">COLLATION</span></span>|<span data-ttu-id="9ca14-528">Int16</span><span class="sxs-lookup"><span data-stu-id="9ca14-528">Int16</span></span>|  
|<span data-ttu-id="9ca14-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="9ca14-529">CARDINALITY</span></span>|<span data-ttu-id="9ca14-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="9ca14-530">Decimal</span></span>|  
|<span data-ttu-id="9ca14-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="9ca14-531">PAGES</span></span>|<span data-ttu-id="9ca14-532">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-532">Int32</span></span>|  
|<span data-ttu-id="9ca14-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9ca14-533">FILTER_CONDITION</span></span>|<span data-ttu-id="9ca14-534">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-534">String</span></span>|  
|<span data-ttu-id="9ca14-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="9ca14-535">INTEGRATED</span></span>|<span data-ttu-id="9ca14-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="9ca14-537">Microsoft Jet OLE DB    </span><span class="sxs-lookup"><span data-stu-id="9ca14-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="9ca14-538">Microsoft Jet OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="9ca14-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9ca14-539">Tables</span><span class="sxs-lookup"><span data-stu-id="9ca14-539">Tables</span></span>  
  
-   <span data-ttu-id="9ca14-540">Columns</span><span class="sxs-lookup"><span data-stu-id="9ca14-540">Columns</span></span>  
  
-   <span data-ttu-id="9ca14-541">절차</span><span class="sxs-lookup"><span data-stu-id="9ca14-541">Procedures</span></span>  
  
-   <span data-ttu-id="9ca14-542">뷰</span><span class="sxs-lookup"><span data-stu-id="9ca14-542">Views</span></span>  
  
-   <span data-ttu-id="9ca14-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="9ca14-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="9ca14-544">Tables</span><span class="sxs-lookup"><span data-stu-id="9ca14-544">Tables</span></span>  
  
|<span data-ttu-id="9ca14-545">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-545">ColumnName</span></span>|<span data-ttu-id="9ca14-546">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-547">TABLE_CATALOG</span></span>|<span data-ttu-id="9ca14-548">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-548">String</span></span>|  
|<span data-ttu-id="9ca14-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="9ca14-550">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-550">String</span></span>|  
|<span data-ttu-id="9ca14-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-551">TABLE_NAME</span></span>|<span data-ttu-id="9ca14-552">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-552">String</span></span>|  
|<span data-ttu-id="9ca14-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ca14-553">TABLE_TYPE</span></span>|<span data-ttu-id="9ca14-554">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-554">String</span></span>|  
|<span data-ttu-id="9ca14-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="9ca14-555">TABLE_GUID</span></span>|<span data-ttu-id="9ca14-556">Guid</span><span class="sxs-lookup"><span data-stu-id="9ca14-556">Guid</span></span>|  
|<span data-ttu-id="9ca14-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ca14-557">DESCRIPTION</span></span>|<span data-ttu-id="9ca14-558">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-558">String</span></span>|  
|<span data-ttu-id="9ca14-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="9ca14-559">TABLE_PROPID</span></span>|<span data-ttu-id="9ca14-560">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-560">Int64</span></span>|  
|<span data-ttu-id="9ca14-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9ca14-561">DATE_CREATED</span></span>|<span data-ttu-id="9ca14-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca14-562">DateTime</span></span>|  
|<span data-ttu-id="9ca14-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9ca14-563">DATE_MODIFIED</span></span>|<span data-ttu-id="9ca14-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca14-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9ca14-565">Columns</span><span class="sxs-lookup"><span data-stu-id="9ca14-565">Columns</span></span>  
  
|<span data-ttu-id="9ca14-566">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-566">ColumnName</span></span>|<span data-ttu-id="9ca14-567">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-568">TABLE_CATALOG</span></span>|<span data-ttu-id="9ca14-569">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-569">String</span></span>|  
|<span data-ttu-id="9ca14-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="9ca14-571">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-571">String</span></span>|  
|<span data-ttu-id="9ca14-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-572">TABLE_NAME</span></span>|<span data-ttu-id="9ca14-573">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-573">String</span></span>|  
|<span data-ttu-id="9ca14-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-574">COLUMN_NAME</span></span>|<span data-ttu-id="9ca14-575">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-575">String</span></span>|  
|<span data-ttu-id="9ca14-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9ca14-576">COLUMN_GUID</span></span>|<span data-ttu-id="9ca14-577">Guid</span><span class="sxs-lookup"><span data-stu-id="9ca14-577">Guid</span></span>|  
|<span data-ttu-id="9ca14-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9ca14-578">COLUMN_PROPID</span></span>|<span data-ttu-id="9ca14-579">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-579">Int64</span></span>|  
|<span data-ttu-id="9ca14-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ca14-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ca14-581">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-581">Int64</span></span>|  
|<span data-ttu-id="9ca14-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9ca14-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="9ca14-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-583">Boolean</span></span>|  
|<span data-ttu-id="9ca14-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9ca14-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="9ca14-585">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-585">String</span></span>|  
|<span data-ttu-id="9ca14-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="9ca14-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="9ca14-587">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-587">Int64</span></span>|  
|<span data-ttu-id="9ca14-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ca14-588">IS_NULLABLE</span></span>|<span data-ttu-id="9ca14-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-589">Boolean</span></span>|  
|<span data-ttu-id="9ca14-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ca14-590">DATA_TYPE</span></span>|<span data-ttu-id="9ca14-591">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-591">Int32</span></span>|  
|<span data-ttu-id="9ca14-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9ca14-592">TYPE_GUID</span></span>|<span data-ttu-id="9ca14-593">Guid</span><span class="sxs-lookup"><span data-stu-id="9ca14-593">Guid</span></span>|  
|<span data-ttu-id="9ca14-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ca14-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9ca14-595">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-595">Int64</span></span>|  
|<span data-ttu-id="9ca14-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ca14-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9ca14-597">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-597">Int64</span></span>|  
|<span data-ttu-id="9ca14-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9ca14-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9ca14-599">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-599">Int32</span></span>|  
|<span data-ttu-id="9ca14-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9ca14-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="9ca14-601">Int16</span><span class="sxs-lookup"><span data-stu-id="9ca14-601">Int16</span></span>|  
|<span data-ttu-id="9ca14-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9ca14-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="9ca14-603">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-603">Int64</span></span>|  
|<span data-ttu-id="9ca14-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="9ca14-605">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-605">String</span></span>|  
|<span data-ttu-id="9ca14-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="9ca14-607">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-607">String</span></span>|  
|<span data-ttu-id="9ca14-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="9ca14-609">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-609">String</span></span>|  
|<span data-ttu-id="9ca14-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="9ca14-611">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-611">String</span></span>|  
|<span data-ttu-id="9ca14-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="9ca14-613">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-613">String</span></span>|  
|<span data-ttu-id="9ca14-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-614">COLLATION_NAME</span></span>|<span data-ttu-id="9ca14-615">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-615">String</span></span>|  
|<span data-ttu-id="9ca14-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="9ca14-617">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-617">String</span></span>|  
|<span data-ttu-id="9ca14-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="9ca14-619">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-619">String</span></span>|  
|<span data-ttu-id="9ca14-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-620">DOMAIN_NAME</span></span>|<span data-ttu-id="9ca14-621">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-621">String</span></span>|  
|<span data-ttu-id="9ca14-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ca14-622">DESCRIPTION</span></span>|<span data-ttu-id="9ca14-623">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9ca14-624">절차</span><span class="sxs-lookup"><span data-stu-id="9ca14-624">Procedures</span></span>  
  
|<span data-ttu-id="9ca14-625">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-625">ColumnName</span></span>|<span data-ttu-id="9ca14-626">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9ca14-628">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-628">String</span></span>|  
|<span data-ttu-id="9ca14-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9ca14-630">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-630">String</span></span>|  
|<span data-ttu-id="9ca14-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="9ca14-632">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-632">String</span></span>|  
|<span data-ttu-id="9ca14-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ca14-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9ca14-634">Int16</span><span class="sxs-lookup"><span data-stu-id="9ca14-634">Int16</span></span>|  
|<span data-ttu-id="9ca14-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9ca14-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="9ca14-636">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-636">String</span></span>|  
|<span data-ttu-id="9ca14-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ca14-637">DESCRIPTION</span></span>|<span data-ttu-id="9ca14-638">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-638">String</span></span>|  
|<span data-ttu-id="9ca14-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9ca14-639">DATE_CREATED</span></span>|<span data-ttu-id="9ca14-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca14-640">DateTime</span></span>|  
|<span data-ttu-id="9ca14-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9ca14-641">DATE_MODIFIED</span></span>|<span data-ttu-id="9ca14-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca14-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="9ca14-643">뷰</span><span class="sxs-lookup"><span data-stu-id="9ca14-643">Views</span></span>  
  
|<span data-ttu-id="9ca14-644">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-644">ColumnName</span></span>|<span data-ttu-id="9ca14-645">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-646">TABLE_CATALOG</span></span>|<span data-ttu-id="9ca14-647">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-647">String</span></span>|  
|<span data-ttu-id="9ca14-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="9ca14-649">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-649">String</span></span>|  
|<span data-ttu-id="9ca14-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-650">TABLE_NAME</span></span>|<span data-ttu-id="9ca14-651">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-651">String</span></span>|  
|<span data-ttu-id="9ca14-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9ca14-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="9ca14-653">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-653">String</span></span>|  
|<span data-ttu-id="9ca14-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="9ca14-654">CHECK_OPTION</span></span>|<span data-ttu-id="9ca14-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-655">Boolean</span></span>|  
|<span data-ttu-id="9ca14-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="9ca14-656">IS_UPDATABLE</span></span>|<span data-ttu-id="9ca14-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-657">Boolean</span></span>|  
|<span data-ttu-id="9ca14-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ca14-658">DESCRIPTION</span></span>|<span data-ttu-id="9ca14-659">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-659">String</span></span>|  
|<span data-ttu-id="9ca14-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9ca14-660">DATE_CREATED</span></span>|<span data-ttu-id="9ca14-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca14-661">DateTime</span></span>|  
|<span data-ttu-id="9ca14-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9ca14-662">DATE_MODIFIED</span></span>|<span data-ttu-id="9ca14-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca14-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9ca14-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="9ca14-664">Indexes</span></span>  
  
|<span data-ttu-id="9ca14-665">열 이름</span><span class="sxs-lookup"><span data-stu-id="9ca14-665">ColumnName</span></span>|<span data-ttu-id="9ca14-666">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ca14-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ca14-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-667">TABLE_CATALOG</span></span>|<span data-ttu-id="9ca14-668">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-668">String</span></span>|  
|<span data-ttu-id="9ca14-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="9ca14-670">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-670">String</span></span>|  
|<span data-ttu-id="9ca14-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-671">TABLE_NAME</span></span>|<span data-ttu-id="9ca14-672">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-672">String</span></span>|  
|<span data-ttu-id="9ca14-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ca14-673">INDEX_CATALOG</span></span>|<span data-ttu-id="9ca14-674">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-674">String</span></span>|  
|<span data-ttu-id="9ca14-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ca14-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="9ca14-676">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-676">String</span></span>|  
|<span data-ttu-id="9ca14-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-677">INDEX_NAME</span></span>|<span data-ttu-id="9ca14-678">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-678">String</span></span>|  
|<span data-ttu-id="9ca14-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="9ca14-679">PRIMARY_KEY</span></span>|<span data-ttu-id="9ca14-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-680">Boolean</span></span>|  
|<span data-ttu-id="9ca14-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9ca14-681">UNIQUE</span></span>|<span data-ttu-id="9ca14-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-682">Boolean</span></span>|  
|<span data-ttu-id="9ca14-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="9ca14-683">CLUSTERED</span></span>|<span data-ttu-id="9ca14-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-684">Boolean</span></span>|  
|<span data-ttu-id="9ca14-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="9ca14-685">TYPE</span></span>|<span data-ttu-id="9ca14-686">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-686">Int32</span></span>|  
|<span data-ttu-id="9ca14-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="9ca14-687">FILL_FACTOR</span></span>|<span data-ttu-id="9ca14-688">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-688">Int32</span></span>|  
|<span data-ttu-id="9ca14-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="9ca14-689">INITIAL_SIZE</span></span>|<span data-ttu-id="9ca14-690">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-690">Int32</span></span>|  
|<span data-ttu-id="9ca14-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="9ca14-691">NULLS</span></span>|<span data-ttu-id="9ca14-692">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-692">Int32</span></span>|  
|<span data-ttu-id="9ca14-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9ca14-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="9ca14-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-694">Boolean</span></span>|  
|<span data-ttu-id="9ca14-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="9ca14-695">AUTO_UPDATE</span></span>|<span data-ttu-id="9ca14-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="9ca14-696">Boolean</span></span>|  
|<span data-ttu-id="9ca14-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="9ca14-697">NULL_COLLATION</span></span>|<span data-ttu-id="9ca14-698">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-698">Int32</span></span>|  
|<span data-ttu-id="9ca14-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ca14-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ca14-700">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-700">Int64</span></span>|  
|<span data-ttu-id="9ca14-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ca14-701">COLUMN_NAME</span></span>|<span data-ttu-id="9ca14-702">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-702">String</span></span>|  
|<span data-ttu-id="9ca14-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9ca14-703">COLUMN_GUID</span></span>|<span data-ttu-id="9ca14-704">Guid</span><span class="sxs-lookup"><span data-stu-id="9ca14-704">Guid</span></span>|  
|<span data-ttu-id="9ca14-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9ca14-705">COLUMN_PROPID</span></span>|<span data-ttu-id="9ca14-706">Int64</span><span class="sxs-lookup"><span data-stu-id="9ca14-706">Int64</span></span>|  
|<span data-ttu-id="9ca14-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9ca14-707">COLLATION</span></span>|<span data-ttu-id="9ca14-708">Int16</span><span class="sxs-lookup"><span data-stu-id="9ca14-708">Int16</span></span>|  
|<span data-ttu-id="9ca14-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="9ca14-709">CARDINALITY</span></span>|<span data-ttu-id="9ca14-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="9ca14-710">Decimal</span></span>|  
|<span data-ttu-id="9ca14-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="9ca14-711">PAGES</span></span>|<span data-ttu-id="9ca14-712">Int32</span><span class="sxs-lookup"><span data-stu-id="9ca14-712">Int32</span></span>|  
|<span data-ttu-id="9ca14-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9ca14-713">FILTER_CONDITION</span></span>|<span data-ttu-id="9ca14-714">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca14-714">String</span></span>|  
|<span data-ttu-id="9ca14-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="9ca14-715">INTEGRATED</span></span>|<span data-ttu-id="9ca14-716">부울</span><span class="sxs-lookup"><span data-stu-id="9ca14-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ca14-717">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ca14-717">See Also</span></span>  
 [<span data-ttu-id="9ca14-718">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="9ca14-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
