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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 33e794559abd7f619f7431683f06e59705b57d41
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="b9dca-102">OLE DB 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="b9dca-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="b9dca-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 OLE DB 공급자에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dca-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="b9dca-104">Microsoft SQL Server OLE DB 공급자</span><span class="sxs-lookup"><span data-stu-id="b9dca-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="b9dca-105">Microsoft SQL Server OLE DB Driver에서는 공통 스키마 컬렉션을 비롯 하 여 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dca-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="b9dca-106">Tables</span><span class="sxs-lookup"><span data-stu-id="b9dca-106">Tables</span></span>  
  
-   <span data-ttu-id="b9dca-107">Columns</span><span class="sxs-lookup"><span data-stu-id="b9dca-107">Columns</span></span>  
  
-   <span data-ttu-id="b9dca-108">절차</span><span class="sxs-lookup"><span data-stu-id="b9dca-108">Procedures</span></span>  
  
-   <span data-ttu-id="b9dca-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="b9dca-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="b9dca-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="b9dca-110">Catalog</span></span>  
  
-   <span data-ttu-id="b9dca-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="b9dca-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="b9dca-112">Tables</span><span class="sxs-lookup"><span data-stu-id="b9dca-112">Tables</span></span>  
  
|<span data-ttu-id="b9dca-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-113">ColumnName</span></span>|<span data-ttu-id="b9dca-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-115">TABLE_CATALOG</span></span>|<span data-ttu-id="b9dca-116">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-116">String</span></span>|  
|<span data-ttu-id="b9dca-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="b9dca-118">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-118">String</span></span>|  
|<span data-ttu-id="b9dca-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-119">TABLE_NAME</span></span>|<span data-ttu-id="b9dca-120">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-120">String</span></span>|  
|<span data-ttu-id="b9dca-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="b9dca-121">TABLE_TYPE</span></span>|<span data-ttu-id="b9dca-122">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-122">String</span></span>|  
|<span data-ttu-id="b9dca-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="b9dca-123">TABLE_GUID</span></span>|<span data-ttu-id="b9dca-124">Guid</span><span class="sxs-lookup"><span data-stu-id="b9dca-124">Guid</span></span>|  
|<span data-ttu-id="b9dca-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9dca-125">DESCRIPTION</span></span>|<span data-ttu-id="b9dca-126">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-126">String</span></span>|  
|<span data-ttu-id="b9dca-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="b9dca-127">TABLE_PROPID</span></span>|<span data-ttu-id="b9dca-128">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-128">Int64</span></span>|  
|<span data-ttu-id="b9dca-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="b9dca-129">DATE_CREATED</span></span>|<span data-ttu-id="b9dca-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9dca-130">DateTime</span></span>|  
|<span data-ttu-id="b9dca-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="b9dca-131">DATE_MODIFIED</span></span>|<span data-ttu-id="b9dca-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9dca-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="b9dca-133">Columns</span><span class="sxs-lookup"><span data-stu-id="b9dca-133">Columns</span></span>  
  
|<span data-ttu-id="b9dca-134">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-134">ColumnName</span></span>|<span data-ttu-id="b9dca-135">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-136">TABLE_CATALOG</span></span>|<span data-ttu-id="b9dca-137">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-137">String</span></span>|  
|<span data-ttu-id="b9dca-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="b9dca-139">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-139">String</span></span>|  
|<span data-ttu-id="b9dca-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-140">TABLE_NAME</span></span>|<span data-ttu-id="b9dca-141">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-141">String</span></span>|  
|<span data-ttu-id="b9dca-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-142">COLUMN_NAME</span></span>|<span data-ttu-id="b9dca-143">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-143">String</span></span>|  
|<span data-ttu-id="b9dca-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="b9dca-144">COLUMN_GUID</span></span>|<span data-ttu-id="b9dca-145">Guid</span><span class="sxs-lookup"><span data-stu-id="b9dca-145">Guid</span></span>|  
|<span data-ttu-id="b9dca-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="b9dca-146">COLUMN_PROPID</span></span>|<span data-ttu-id="b9dca-147">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-147">Int64</span></span>|  
|<span data-ttu-id="b9dca-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b9dca-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="b9dca-149">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-149">Int64</span></span>|  
|<span data-ttu-id="b9dca-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="b9dca-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="b9dca-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-151">Boolean</span></span>|  
|<span data-ttu-id="b9dca-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="b9dca-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="b9dca-153">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-153">String</span></span>|  
|<span data-ttu-id="b9dca-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="b9dca-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="b9dca-155">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-155">Int64</span></span>|  
|<span data-ttu-id="b9dca-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b9dca-156">IS_NULLABLE</span></span>|<span data-ttu-id="b9dca-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-157">Boolean</span></span>|  
|<span data-ttu-id="b9dca-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b9dca-158">DATA_TYPE</span></span>|<span data-ttu-id="b9dca-159">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-159">Int32</span></span>|  
|<span data-ttu-id="b9dca-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="b9dca-160">TYPE_GUID</span></span>|<span data-ttu-id="b9dca-161">Guid</span><span class="sxs-lookup"><span data-stu-id="b9dca-161">Guid</span></span>|  
|<span data-ttu-id="b9dca-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b9dca-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="b9dca-163">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-163">Int64</span></span>|  
|<span data-ttu-id="b9dca-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b9dca-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="b9dca-165">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-165">Int64</span></span>|  
|<span data-ttu-id="b9dca-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="b9dca-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="b9dca-167">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-167">Int32</span></span>|  
|<span data-ttu-id="b9dca-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="b9dca-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="b9dca-169">Int16</span><span class="sxs-lookup"><span data-stu-id="b9dca-169">Int16</span></span>|  
|<span data-ttu-id="b9dca-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="b9dca-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="b9dca-171">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-171">Int64</span></span>|  
|<span data-ttu-id="b9dca-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="b9dca-173">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-173">String</span></span>|  
|<span data-ttu-id="b9dca-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="b9dca-175">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-175">String</span></span>|  
|<span data-ttu-id="b9dca-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="b9dca-177">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-177">String</span></span>|  
|<span data-ttu-id="b9dca-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="b9dca-179">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-179">String</span></span>|  
|<span data-ttu-id="b9dca-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="b9dca-181">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-181">String</span></span>|  
|<span data-ttu-id="b9dca-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-182">COLLATION_NAME</span></span>|<span data-ttu-id="b9dca-183">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-183">String</span></span>|  
|<span data-ttu-id="b9dca-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="b9dca-185">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-185">String</span></span>|  
|<span data-ttu-id="b9dca-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="b9dca-187">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-187">String</span></span>|  
|<span data-ttu-id="b9dca-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-188">DOMAIN_NAME</span></span>|<span data-ttu-id="b9dca-189">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-189">String</span></span>|  
|<span data-ttu-id="b9dca-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9dca-190">DESCRIPTION</span></span>|<span data-ttu-id="b9dca-191">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-191">String</span></span>|  
|<span data-ttu-id="b9dca-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="b9dca-192">COLUMN_LCID</span></span>|<span data-ttu-id="b9dca-193">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-193">Int32</span></span>|  
|<span data-ttu-id="b9dca-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="b9dca-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="b9dca-195">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-195">Int32</span></span>|  
|<span data-ttu-id="b9dca-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="b9dca-196">COLUMN_SORTID</span></span>|<span data-ttu-id="b9dca-197">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-197">Int32</span></span>|  
|<span data-ttu-id="b9dca-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="b9dca-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="b9dca-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="b9dca-199">Byte[]</span></span>|  
|<span data-ttu-id="b9dca-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="b9dca-200">IS_COMPUTED</span></span>|<span data-ttu-id="b9dca-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="b9dca-202">절차</span><span class="sxs-lookup"><span data-stu-id="b9dca-202">Procedures</span></span>  
  
|<span data-ttu-id="b9dca-203">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-203">ColumnName</span></span>|<span data-ttu-id="b9dca-204">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="b9dca-206">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-206">String</span></span>|  
|<span data-ttu-id="b9dca-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="b9dca-208">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-208">String</span></span>|  
|<span data-ttu-id="b9dca-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="b9dca-210">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-210">String</span></span>|  
|<span data-ttu-id="b9dca-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="b9dca-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="b9dca-212">Int16</span><span class="sxs-lookup"><span data-stu-id="b9dca-212">Int16</span></span>|  
|<span data-ttu-id="b9dca-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="b9dca-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="b9dca-214">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-214">String</span></span>|  
|<span data-ttu-id="b9dca-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9dca-215">DESCRIPTION</span></span>|<span data-ttu-id="b9dca-216">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-216">String</span></span>|  
|<span data-ttu-id="b9dca-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="b9dca-217">DATE_CREATED</span></span>|<span data-ttu-id="b9dca-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9dca-218">DateTime</span></span>|  
|<span data-ttu-id="b9dca-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="b9dca-219">DATE_MODIFIED</span></span>|<span data-ttu-id="b9dca-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9dca-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="b9dca-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="b9dca-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="b9dca-222">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-222">ColumnName</span></span>|<span data-ttu-id="b9dca-223">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="b9dca-225">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-225">String</span></span>|  
|<span data-ttu-id="b9dca-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="b9dca-227">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-227">String</span></span>|  
|<span data-ttu-id="b9dca-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="b9dca-229">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-229">String</span></span>|  
|<span data-ttu-id="b9dca-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-230">PARAMETER_NAME</span></span>|<span data-ttu-id="b9dca-231">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-231">String</span></span>|  
|<span data-ttu-id="b9dca-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b9dca-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="b9dca-233">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-233">Int32</span></span>|  
|<span data-ttu-id="b9dca-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="b9dca-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="b9dca-235">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-235">Int32</span></span>|  
|<span data-ttu-id="b9dca-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="b9dca-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="b9dca-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-237">Boolean</span></span>|  
|<span data-ttu-id="b9dca-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="b9dca-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="b9dca-239">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-239">String</span></span>|  
|<span data-ttu-id="b9dca-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b9dca-240">IS_NULLABLE</span></span>|<span data-ttu-id="b9dca-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-241">Boolean</span></span>|  
|<span data-ttu-id="b9dca-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b9dca-242">DATA_TYPE</span></span>|<span data-ttu-id="b9dca-243">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-243">Int32</span></span>|  
|<span data-ttu-id="b9dca-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b9dca-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="b9dca-245">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-245">Int64</span></span>|  
|<span data-ttu-id="b9dca-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b9dca-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="b9dca-247">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-247">Int64</span></span>|  
|<span data-ttu-id="b9dca-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="b9dca-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="b9dca-249">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-249">Int32</span></span>|  
|<span data-ttu-id="b9dca-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="b9dca-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="b9dca-251">Int16</span><span class="sxs-lookup"><span data-stu-id="b9dca-251">Int16</span></span>|  
|<span data-ttu-id="b9dca-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9dca-252">DESCRIPTION</span></span>|<span data-ttu-id="b9dca-253">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-253">String</span></span>|  
|<span data-ttu-id="b9dca-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-254">TYPE_NAME</span></span>|<span data-ttu-id="b9dca-255">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-255">String</span></span>|  
|<span data-ttu-id="b9dca-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="b9dca-257">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="b9dca-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="b9dca-258">Catalog</span></span>  
  
|<span data-ttu-id="b9dca-259">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-259">ColumnName</span></span>|<span data-ttu-id="b9dca-260">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-261">CATALOG_NAME</span></span>|<span data-ttu-id="b9dca-262">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-262">String</span></span>|  
|<span data-ttu-id="b9dca-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9dca-263">DESCRIPTION</span></span>|<span data-ttu-id="b9dca-264">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="b9dca-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="b9dca-265">Indexes</span></span>  
  
|<span data-ttu-id="b9dca-266">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-266">ColumnName</span></span>|<span data-ttu-id="b9dca-267">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-268">TABLE_CATALOG</span></span>|<span data-ttu-id="b9dca-269">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-269">String</span></span>|  
|<span data-ttu-id="b9dca-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="b9dca-271">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-271">String</span></span>|  
|<span data-ttu-id="b9dca-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-272">TABLE_NAME</span></span>|<span data-ttu-id="b9dca-273">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-273">String</span></span>|  
|<span data-ttu-id="b9dca-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-274">INDEX_CATALOG</span></span>|<span data-ttu-id="b9dca-275">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-275">String</span></span>|  
|<span data-ttu-id="b9dca-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="b9dca-277">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-277">String</span></span>|  
|<span data-ttu-id="b9dca-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-278">INDEX_NAME</span></span>|<span data-ttu-id="b9dca-279">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-279">String</span></span>|  
|<span data-ttu-id="b9dca-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="b9dca-280">PRIMARY_KEY</span></span>|<span data-ttu-id="b9dca-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-281">Boolean</span></span>|  
|<span data-ttu-id="b9dca-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="b9dca-282">UNIQUE</span></span>|<span data-ttu-id="b9dca-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-283">Boolean</span></span>|  
|<span data-ttu-id="b9dca-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="b9dca-284">CLUSTERED</span></span>|<span data-ttu-id="b9dca-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-285">Boolean</span></span>|  
|<span data-ttu-id="b9dca-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="b9dca-286">TYPE</span></span>|<span data-ttu-id="b9dca-287">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-287">Int32</span></span>|  
|<span data-ttu-id="b9dca-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="b9dca-288">FILL_FACTOR</span></span>|<span data-ttu-id="b9dca-289">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-289">Int32</span></span>|  
|<span data-ttu-id="b9dca-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="b9dca-290">INITIAL_SIZE</span></span>|<span data-ttu-id="b9dca-291">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-291">Int32</span></span>|  
|<span data-ttu-id="b9dca-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="b9dca-292">NULLS</span></span>|<span data-ttu-id="b9dca-293">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-293">Int32</span></span>|  
|<span data-ttu-id="b9dca-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="b9dca-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="b9dca-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-295">Boolean</span></span>|  
|<span data-ttu-id="b9dca-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="b9dca-296">AUTO_UPDATE</span></span>|<span data-ttu-id="b9dca-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-297">Boolean</span></span>|  
|<span data-ttu-id="b9dca-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="b9dca-298">NULL_COLLATION</span></span>|<span data-ttu-id="b9dca-299">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-299">Int32</span></span>|  
|<span data-ttu-id="b9dca-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b9dca-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="b9dca-301">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-301">Int64</span></span>|  
|<span data-ttu-id="b9dca-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-302">COLUMN_NAME</span></span>|<span data-ttu-id="b9dca-303">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-303">String</span></span>|  
|<span data-ttu-id="b9dca-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="b9dca-304">COLUMN_GUID</span></span>|<span data-ttu-id="b9dca-305">Guid</span><span class="sxs-lookup"><span data-stu-id="b9dca-305">Guid</span></span>|  
|<span data-ttu-id="b9dca-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="b9dca-306">COLUMN_PROPID</span></span>|<span data-ttu-id="b9dca-307">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-307">Int64</span></span>|  
|<span data-ttu-id="b9dca-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="b9dca-308">COLLATION</span></span>|<span data-ttu-id="b9dca-309">Int16</span><span class="sxs-lookup"><span data-stu-id="b9dca-309">Int16</span></span>|  
|<span data-ttu-id="b9dca-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="b9dca-310">CARDINALITY</span></span>|<span data-ttu-id="b9dca-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="b9dca-311">Decimal</span></span>|  
|<span data-ttu-id="b9dca-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="b9dca-312">PAGES</span></span>|<span data-ttu-id="b9dca-313">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-313">Int32</span></span>|  
|<span data-ttu-id="b9dca-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="b9dca-314">FILTER_CONDITION</span></span>|<span data-ttu-id="b9dca-315">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-315">String</span></span>|  
|<span data-ttu-id="b9dca-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="b9dca-316">INTEGRATED</span></span>|<span data-ttu-id="b9dca-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="b9dca-318">Microsoft Oracle OLE DB    </span><span class="sxs-lookup"><span data-stu-id="b9dca-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="b9dca-319">Microsoft Oracle OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="b9dca-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="b9dca-320">Tables</span><span class="sxs-lookup"><span data-stu-id="b9dca-320">Tables</span></span>  
  
-   <span data-ttu-id="b9dca-321">Columns</span><span class="sxs-lookup"><span data-stu-id="b9dca-321">Columns</span></span>  
  
-   <span data-ttu-id="b9dca-322">절차</span><span class="sxs-lookup"><span data-stu-id="b9dca-322">Procedures</span></span>  
  
-   <span data-ttu-id="b9dca-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="b9dca-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="b9dca-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="b9dca-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="b9dca-325">뷰</span><span class="sxs-lookup"><span data-stu-id="b9dca-325">Views</span></span>  
  
-   <span data-ttu-id="b9dca-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="b9dca-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="b9dca-327">Tables</span><span class="sxs-lookup"><span data-stu-id="b9dca-327">Tables</span></span>  
  
|<span data-ttu-id="b9dca-328">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-328">ColumnName</span></span>|<span data-ttu-id="b9dca-329">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-330">TABLE_CATALOG</span></span>|<span data-ttu-id="b9dca-331">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-331">String</span></span>|  
|<span data-ttu-id="b9dca-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="b9dca-333">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-333">String</span></span>|  
|<span data-ttu-id="b9dca-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-334">TABLE_NAME</span></span>|<span data-ttu-id="b9dca-335">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-335">String</span></span>|  
|<span data-ttu-id="b9dca-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="b9dca-336">TABLE_TYPE</span></span>|<span data-ttu-id="b9dca-337">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-337">String</span></span>|  
|<span data-ttu-id="b9dca-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="b9dca-338">TABLE_GUID</span></span>|<span data-ttu-id="b9dca-339">Guid</span><span class="sxs-lookup"><span data-stu-id="b9dca-339">Guid</span></span>|  
|<span data-ttu-id="b9dca-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9dca-340">DESCRIPTION</span></span>|<span data-ttu-id="b9dca-341">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-341">String</span></span>|  
|<span data-ttu-id="b9dca-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="b9dca-342">TABLE_PROPID</span></span>|<span data-ttu-id="b9dca-343">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-343">Int64</span></span>|  
|<span data-ttu-id="b9dca-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="b9dca-344">DATE_CREATED</span></span>|<span data-ttu-id="b9dca-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9dca-345">DateTime</span></span>|  
|<span data-ttu-id="b9dca-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="b9dca-346">DATE_MODIFIED</span></span>|<span data-ttu-id="b9dca-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9dca-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="b9dca-348">Columns</span><span class="sxs-lookup"><span data-stu-id="b9dca-348">Columns</span></span>  
  
|<span data-ttu-id="b9dca-349">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-349">ColumnName</span></span>|<span data-ttu-id="b9dca-350">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-351">TABLE_CATALOG</span></span>|<span data-ttu-id="b9dca-352">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-352">String</span></span>|  
|<span data-ttu-id="b9dca-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="b9dca-354">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-354">String</span></span>|  
|<span data-ttu-id="b9dca-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-355">TABLE_NAME</span></span>|<span data-ttu-id="b9dca-356">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-356">String</span></span>|  
|<span data-ttu-id="b9dca-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-357">COLUMN_NAME</span></span>|<span data-ttu-id="b9dca-358">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-358">String</span></span>|  
|<span data-ttu-id="b9dca-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="b9dca-359">COLUMN_GUID</span></span>|<span data-ttu-id="b9dca-360">Guid</span><span class="sxs-lookup"><span data-stu-id="b9dca-360">Guid</span></span>|  
|<span data-ttu-id="b9dca-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="b9dca-361">COLUMN_PROPID</span></span>|<span data-ttu-id="b9dca-362">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-362">Int64</span></span>|  
|<span data-ttu-id="b9dca-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b9dca-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="b9dca-364">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-364">Int64</span></span>|  
|<span data-ttu-id="b9dca-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="b9dca-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="b9dca-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-366">Boolean</span></span>|  
|<span data-ttu-id="b9dca-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="b9dca-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="b9dca-368">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-368">String</span></span>|  
|<span data-ttu-id="b9dca-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="b9dca-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="b9dca-370">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-370">Int64</span></span>|  
|<span data-ttu-id="b9dca-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b9dca-371">IS_NULLABLE</span></span>|<span data-ttu-id="b9dca-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-372">Boolean</span></span>|  
|<span data-ttu-id="b9dca-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b9dca-373">DATA_TYPE</span></span>|<span data-ttu-id="b9dca-374">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-374">Int32</span></span>|  
|<span data-ttu-id="b9dca-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="b9dca-375">TYPE_GUID</span></span>|<span data-ttu-id="b9dca-376">Guid</span><span class="sxs-lookup"><span data-stu-id="b9dca-376">Guid</span></span>|  
|<span data-ttu-id="b9dca-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b9dca-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="b9dca-378">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-378">Int64</span></span>|  
|<span data-ttu-id="b9dca-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b9dca-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="b9dca-380">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-380">Int64</span></span>|  
|<span data-ttu-id="b9dca-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="b9dca-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="b9dca-382">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-382">Int32</span></span>|  
|<span data-ttu-id="b9dca-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="b9dca-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="b9dca-384">Int16</span><span class="sxs-lookup"><span data-stu-id="b9dca-384">Int16</span></span>|  
|<span data-ttu-id="b9dca-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="b9dca-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="b9dca-386">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-386">Int64</span></span>|  
|<span data-ttu-id="b9dca-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="b9dca-388">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-388">String</span></span>|  
|<span data-ttu-id="b9dca-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="b9dca-390">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-390">String</span></span>|  
|<span data-ttu-id="b9dca-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="b9dca-392">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-392">String</span></span>|  
|<span data-ttu-id="b9dca-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="b9dca-394">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-394">String</span></span>|  
|<span data-ttu-id="b9dca-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="b9dca-396">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-396">String</span></span>|  
|<span data-ttu-id="b9dca-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-397">COLLATION_NAME</span></span>|<span data-ttu-id="b9dca-398">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-398">String</span></span>|  
|<span data-ttu-id="b9dca-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="b9dca-400">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-400">String</span></span>|  
|<span data-ttu-id="b9dca-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="b9dca-402">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-402">String</span></span>|  
|<span data-ttu-id="b9dca-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-403">DOMAIN_NAME</span></span>|<span data-ttu-id="b9dca-404">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-404">String</span></span>|  
|<span data-ttu-id="b9dca-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9dca-405">DESCRIPTION</span></span>|<span data-ttu-id="b9dca-406">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="b9dca-407">절차</span><span class="sxs-lookup"><span data-stu-id="b9dca-407">Procedures</span></span>  
  
|<span data-ttu-id="b9dca-408">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-408">ColumnName</span></span>|<span data-ttu-id="b9dca-409">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="b9dca-411">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-411">String</span></span>|  
|<span data-ttu-id="b9dca-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="b9dca-413">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-413">String</span></span>|  
|<span data-ttu-id="b9dca-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="b9dca-415">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-415">String</span></span>|  
|<span data-ttu-id="b9dca-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="b9dca-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="b9dca-417">Int16</span><span class="sxs-lookup"><span data-stu-id="b9dca-417">Int16</span></span>|  
|<span data-ttu-id="b9dca-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="b9dca-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="b9dca-419">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-419">String</span></span>|  
|<span data-ttu-id="b9dca-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9dca-420">DESCRIPTION</span></span>|<span data-ttu-id="b9dca-421">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-421">String</span></span>|  
|<span data-ttu-id="b9dca-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="b9dca-422">DATE_CREATED</span></span>|<span data-ttu-id="b9dca-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9dca-423">DateTime</span></span>|  
|<span data-ttu-id="b9dca-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="b9dca-424">DATE_MODIFIED</span></span>|<span data-ttu-id="b9dca-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9dca-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="b9dca-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="b9dca-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="b9dca-427">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-427">ColumnName</span></span>|<span data-ttu-id="b9dca-428">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="b9dca-430">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-430">String</span></span>|  
|<span data-ttu-id="b9dca-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="b9dca-432">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-432">String</span></span>|  
|<span data-ttu-id="b9dca-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="b9dca-434">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-434">String</span></span>|  
|<span data-ttu-id="b9dca-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-435">COLUMN_NAME</span></span>|<span data-ttu-id="b9dca-436">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-436">String</span></span>|  
|<span data-ttu-id="b9dca-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="b9dca-437">COLUMN_GUID</span></span>|<span data-ttu-id="b9dca-438">Guid</span><span class="sxs-lookup"><span data-stu-id="b9dca-438">Guid</span></span>|  
|<span data-ttu-id="b9dca-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="b9dca-439">COLUMN_PROPID</span></span>|<span data-ttu-id="b9dca-440">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-440">Int64</span></span>|  
|<span data-ttu-id="b9dca-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="b9dca-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="b9dca-442">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-442">Int64</span></span>|  
|<span data-ttu-id="b9dca-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b9dca-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="b9dca-444">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-444">Int64</span></span>|  
|<span data-ttu-id="b9dca-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b9dca-445">IS_NULLABLE</span></span>|<span data-ttu-id="b9dca-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-446">Boolean</span></span>|  
|<span data-ttu-id="b9dca-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b9dca-447">DATA_TYPE</span></span>|<span data-ttu-id="b9dca-448">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-448">Int32</span></span>|  
|<span data-ttu-id="b9dca-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="b9dca-449">TYPE_GUID</span></span>|<span data-ttu-id="b9dca-450">Guid</span><span class="sxs-lookup"><span data-stu-id="b9dca-450">Guid</span></span>|  
|<span data-ttu-id="b9dca-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b9dca-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="b9dca-452">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-452">Int64</span></span>|  
|<span data-ttu-id="b9dca-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b9dca-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="b9dca-454">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-454">Int64</span></span>|  
|<span data-ttu-id="b9dca-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="b9dca-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="b9dca-456">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-456">Int32</span></span>|  
|<span data-ttu-id="b9dca-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="b9dca-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="b9dca-458">Int16</span><span class="sxs-lookup"><span data-stu-id="b9dca-458">Int16</span></span>|  
|<span data-ttu-id="b9dca-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9dca-459">DESCRIPTION</span></span>|<span data-ttu-id="b9dca-460">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-460">String</span></span>|  
|<span data-ttu-id="b9dca-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="b9dca-461">OVERLOAD</span></span>|<span data-ttu-id="b9dca-462">Int16</span><span class="sxs-lookup"><span data-stu-id="b9dca-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="b9dca-463">뷰</span><span class="sxs-lookup"><span data-stu-id="b9dca-463">Views</span></span>  
  
|<span data-ttu-id="b9dca-464">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-464">ColumnName</span></span>|<span data-ttu-id="b9dca-465">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-466">TABLE_CATALOG</span></span>|<span data-ttu-id="b9dca-467">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-467">String</span></span>|  
|<span data-ttu-id="b9dca-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="b9dca-469">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-469">String</span></span>|  
|<span data-ttu-id="b9dca-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-470">TABLE_NAME</span></span>|<span data-ttu-id="b9dca-471">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-471">String</span></span>|  
|<span data-ttu-id="b9dca-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="b9dca-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="b9dca-473">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-473">String</span></span>|  
|<span data-ttu-id="b9dca-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="b9dca-474">CHECK_OPTION</span></span>|<span data-ttu-id="b9dca-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-475">Boolean</span></span>|  
|<span data-ttu-id="b9dca-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="b9dca-476">IS_UPDATABLE</span></span>|<span data-ttu-id="b9dca-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-477">Boolean</span></span>|  
|<span data-ttu-id="b9dca-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9dca-478">DESCRIPTION</span></span>|<span data-ttu-id="b9dca-479">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-479">String</span></span>|  
|<span data-ttu-id="b9dca-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="b9dca-480">DATE_CREATED</span></span>|<span data-ttu-id="b9dca-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9dca-481">DateTime</span></span>|  
|<span data-ttu-id="b9dca-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="b9dca-482">DATE_MODIFIED</span></span>|<span data-ttu-id="b9dca-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9dca-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="b9dca-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="b9dca-484">Indexes</span></span>  
  
|<span data-ttu-id="b9dca-485">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-485">ColumnName</span></span>|<span data-ttu-id="b9dca-486">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-487">TABLE_CATALOG</span></span>|<span data-ttu-id="b9dca-488">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-488">String</span></span>|  
|<span data-ttu-id="b9dca-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="b9dca-490">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-490">String</span></span>|  
|<span data-ttu-id="b9dca-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-491">TABLE_NAME</span></span>|<span data-ttu-id="b9dca-492">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-492">String</span></span>|  
|<span data-ttu-id="b9dca-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-493">INDEX_CATALOG</span></span>|<span data-ttu-id="b9dca-494">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-494">String</span></span>|  
|<span data-ttu-id="b9dca-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="b9dca-496">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-496">String</span></span>|  
|<span data-ttu-id="b9dca-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-497">INDEX_NAME</span></span>|<span data-ttu-id="b9dca-498">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-498">String</span></span>|  
|<span data-ttu-id="b9dca-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="b9dca-499">PRIMARY_KEY</span></span>|<span data-ttu-id="b9dca-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-500">Boolean</span></span>|  
|<span data-ttu-id="b9dca-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="b9dca-501">UNIQUE</span></span>|<span data-ttu-id="b9dca-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-502">Boolean</span></span>|  
|<span data-ttu-id="b9dca-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="b9dca-503">CLUSTERED</span></span>|<span data-ttu-id="b9dca-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-504">Boolean</span></span>|  
|<span data-ttu-id="b9dca-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="b9dca-505">TYPE</span></span>|<span data-ttu-id="b9dca-506">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-506">Int32</span></span>|  
|<span data-ttu-id="b9dca-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="b9dca-507">FILL_FACTOR</span></span>|<span data-ttu-id="b9dca-508">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-508">Int32</span></span>|  
|<span data-ttu-id="b9dca-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="b9dca-509">INITIAL_SIZE</span></span>|<span data-ttu-id="b9dca-510">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-510">Int32</span></span>|  
|<span data-ttu-id="b9dca-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="b9dca-511">NULLS</span></span>|<span data-ttu-id="b9dca-512">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-512">Int32</span></span>|  
|<span data-ttu-id="b9dca-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="b9dca-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="b9dca-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-514">Boolean</span></span>|  
|<span data-ttu-id="b9dca-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="b9dca-515">AUTO_UPDATE</span></span>|<span data-ttu-id="b9dca-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-516">Boolean</span></span>|  
|<span data-ttu-id="b9dca-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="b9dca-517">NULL_COLLATION</span></span>|<span data-ttu-id="b9dca-518">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-518">Int32</span></span>|  
|<span data-ttu-id="b9dca-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b9dca-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="b9dca-520">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-520">Int64</span></span>|  
|<span data-ttu-id="b9dca-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-521">COLUMN_NAME</span></span>|<span data-ttu-id="b9dca-522">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-522">String</span></span>|  
|<span data-ttu-id="b9dca-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="b9dca-523">COLUMN_GUID</span></span>|<span data-ttu-id="b9dca-524">Guid</span><span class="sxs-lookup"><span data-stu-id="b9dca-524">Guid</span></span>|  
|<span data-ttu-id="b9dca-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="b9dca-525">COLUMN_PROPID</span></span>|<span data-ttu-id="b9dca-526">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-526">Int64</span></span>|  
|<span data-ttu-id="b9dca-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="b9dca-527">COLLATION</span></span>|<span data-ttu-id="b9dca-528">Int16</span><span class="sxs-lookup"><span data-stu-id="b9dca-528">Int16</span></span>|  
|<span data-ttu-id="b9dca-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="b9dca-529">CARDINALITY</span></span>|<span data-ttu-id="b9dca-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="b9dca-530">Decimal</span></span>|  
|<span data-ttu-id="b9dca-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="b9dca-531">PAGES</span></span>|<span data-ttu-id="b9dca-532">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-532">Int32</span></span>|  
|<span data-ttu-id="b9dca-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="b9dca-533">FILTER_CONDITION</span></span>|<span data-ttu-id="b9dca-534">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-534">String</span></span>|  
|<span data-ttu-id="b9dca-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="b9dca-535">INTEGRATED</span></span>|<span data-ttu-id="b9dca-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="b9dca-537">Microsoft Jet OLE DB    </span><span class="sxs-lookup"><span data-stu-id="b9dca-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="b9dca-538">Microsoft Jet OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="b9dca-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="b9dca-539">Tables</span><span class="sxs-lookup"><span data-stu-id="b9dca-539">Tables</span></span>  
  
-   <span data-ttu-id="b9dca-540">Columns</span><span class="sxs-lookup"><span data-stu-id="b9dca-540">Columns</span></span>  
  
-   <span data-ttu-id="b9dca-541">절차</span><span class="sxs-lookup"><span data-stu-id="b9dca-541">Procedures</span></span>  
  
-   <span data-ttu-id="b9dca-542">뷰</span><span class="sxs-lookup"><span data-stu-id="b9dca-542">Views</span></span>  
  
-   <span data-ttu-id="b9dca-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="b9dca-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="b9dca-544">Tables</span><span class="sxs-lookup"><span data-stu-id="b9dca-544">Tables</span></span>  
  
|<span data-ttu-id="b9dca-545">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-545">ColumnName</span></span>|<span data-ttu-id="b9dca-546">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-547">TABLE_CATALOG</span></span>|<span data-ttu-id="b9dca-548">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-548">String</span></span>|  
|<span data-ttu-id="b9dca-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="b9dca-550">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-550">String</span></span>|  
|<span data-ttu-id="b9dca-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-551">TABLE_NAME</span></span>|<span data-ttu-id="b9dca-552">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-552">String</span></span>|  
|<span data-ttu-id="b9dca-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="b9dca-553">TABLE_TYPE</span></span>|<span data-ttu-id="b9dca-554">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-554">String</span></span>|  
|<span data-ttu-id="b9dca-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="b9dca-555">TABLE_GUID</span></span>|<span data-ttu-id="b9dca-556">Guid</span><span class="sxs-lookup"><span data-stu-id="b9dca-556">Guid</span></span>|  
|<span data-ttu-id="b9dca-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9dca-557">DESCRIPTION</span></span>|<span data-ttu-id="b9dca-558">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-558">String</span></span>|  
|<span data-ttu-id="b9dca-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="b9dca-559">TABLE_PROPID</span></span>|<span data-ttu-id="b9dca-560">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-560">Int64</span></span>|  
|<span data-ttu-id="b9dca-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="b9dca-561">DATE_CREATED</span></span>|<span data-ttu-id="b9dca-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9dca-562">DateTime</span></span>|  
|<span data-ttu-id="b9dca-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="b9dca-563">DATE_MODIFIED</span></span>|<span data-ttu-id="b9dca-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9dca-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="b9dca-565">Columns</span><span class="sxs-lookup"><span data-stu-id="b9dca-565">Columns</span></span>  
  
|<span data-ttu-id="b9dca-566">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-566">ColumnName</span></span>|<span data-ttu-id="b9dca-567">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-568">TABLE_CATALOG</span></span>|<span data-ttu-id="b9dca-569">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-569">String</span></span>|  
|<span data-ttu-id="b9dca-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="b9dca-571">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-571">String</span></span>|  
|<span data-ttu-id="b9dca-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-572">TABLE_NAME</span></span>|<span data-ttu-id="b9dca-573">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-573">String</span></span>|  
|<span data-ttu-id="b9dca-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-574">COLUMN_NAME</span></span>|<span data-ttu-id="b9dca-575">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-575">String</span></span>|  
|<span data-ttu-id="b9dca-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="b9dca-576">COLUMN_GUID</span></span>|<span data-ttu-id="b9dca-577">Guid</span><span class="sxs-lookup"><span data-stu-id="b9dca-577">Guid</span></span>|  
|<span data-ttu-id="b9dca-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="b9dca-578">COLUMN_PROPID</span></span>|<span data-ttu-id="b9dca-579">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-579">Int64</span></span>|  
|<span data-ttu-id="b9dca-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b9dca-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="b9dca-581">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-581">Int64</span></span>|  
|<span data-ttu-id="b9dca-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="b9dca-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="b9dca-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-583">Boolean</span></span>|  
|<span data-ttu-id="b9dca-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="b9dca-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="b9dca-585">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-585">String</span></span>|  
|<span data-ttu-id="b9dca-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="b9dca-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="b9dca-587">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-587">Int64</span></span>|  
|<span data-ttu-id="b9dca-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b9dca-588">IS_NULLABLE</span></span>|<span data-ttu-id="b9dca-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-589">Boolean</span></span>|  
|<span data-ttu-id="b9dca-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b9dca-590">DATA_TYPE</span></span>|<span data-ttu-id="b9dca-591">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-591">Int32</span></span>|  
|<span data-ttu-id="b9dca-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="b9dca-592">TYPE_GUID</span></span>|<span data-ttu-id="b9dca-593">Guid</span><span class="sxs-lookup"><span data-stu-id="b9dca-593">Guid</span></span>|  
|<span data-ttu-id="b9dca-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b9dca-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="b9dca-595">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-595">Int64</span></span>|  
|<span data-ttu-id="b9dca-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b9dca-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="b9dca-597">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-597">Int64</span></span>|  
|<span data-ttu-id="b9dca-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="b9dca-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="b9dca-599">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-599">Int32</span></span>|  
|<span data-ttu-id="b9dca-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="b9dca-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="b9dca-601">Int16</span><span class="sxs-lookup"><span data-stu-id="b9dca-601">Int16</span></span>|  
|<span data-ttu-id="b9dca-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="b9dca-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="b9dca-603">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-603">Int64</span></span>|  
|<span data-ttu-id="b9dca-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="b9dca-605">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-605">String</span></span>|  
|<span data-ttu-id="b9dca-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="b9dca-607">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-607">String</span></span>|  
|<span data-ttu-id="b9dca-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="b9dca-609">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-609">String</span></span>|  
|<span data-ttu-id="b9dca-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="b9dca-611">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-611">String</span></span>|  
|<span data-ttu-id="b9dca-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="b9dca-613">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-613">String</span></span>|  
|<span data-ttu-id="b9dca-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-614">COLLATION_NAME</span></span>|<span data-ttu-id="b9dca-615">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-615">String</span></span>|  
|<span data-ttu-id="b9dca-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="b9dca-617">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-617">String</span></span>|  
|<span data-ttu-id="b9dca-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="b9dca-619">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-619">String</span></span>|  
|<span data-ttu-id="b9dca-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-620">DOMAIN_NAME</span></span>|<span data-ttu-id="b9dca-621">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-621">String</span></span>|  
|<span data-ttu-id="b9dca-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9dca-622">DESCRIPTION</span></span>|<span data-ttu-id="b9dca-623">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="b9dca-624">절차</span><span class="sxs-lookup"><span data-stu-id="b9dca-624">Procedures</span></span>  
  
|<span data-ttu-id="b9dca-625">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-625">ColumnName</span></span>|<span data-ttu-id="b9dca-626">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="b9dca-628">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-628">String</span></span>|  
|<span data-ttu-id="b9dca-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="b9dca-630">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-630">String</span></span>|  
|<span data-ttu-id="b9dca-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="b9dca-632">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-632">String</span></span>|  
|<span data-ttu-id="b9dca-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="b9dca-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="b9dca-634">Int16</span><span class="sxs-lookup"><span data-stu-id="b9dca-634">Int16</span></span>|  
|<span data-ttu-id="b9dca-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="b9dca-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="b9dca-636">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-636">String</span></span>|  
|<span data-ttu-id="b9dca-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9dca-637">DESCRIPTION</span></span>|<span data-ttu-id="b9dca-638">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-638">String</span></span>|  
|<span data-ttu-id="b9dca-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="b9dca-639">DATE_CREATED</span></span>|<span data-ttu-id="b9dca-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9dca-640">DateTime</span></span>|  
|<span data-ttu-id="b9dca-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="b9dca-641">DATE_MODIFIED</span></span>|<span data-ttu-id="b9dca-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9dca-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="b9dca-643">뷰</span><span class="sxs-lookup"><span data-stu-id="b9dca-643">Views</span></span>  
  
|<span data-ttu-id="b9dca-644">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-644">ColumnName</span></span>|<span data-ttu-id="b9dca-645">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-646">TABLE_CATALOG</span></span>|<span data-ttu-id="b9dca-647">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-647">String</span></span>|  
|<span data-ttu-id="b9dca-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="b9dca-649">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-649">String</span></span>|  
|<span data-ttu-id="b9dca-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-650">TABLE_NAME</span></span>|<span data-ttu-id="b9dca-651">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-651">String</span></span>|  
|<span data-ttu-id="b9dca-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="b9dca-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="b9dca-653">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-653">String</span></span>|  
|<span data-ttu-id="b9dca-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="b9dca-654">CHECK_OPTION</span></span>|<span data-ttu-id="b9dca-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-655">Boolean</span></span>|  
|<span data-ttu-id="b9dca-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="b9dca-656">IS_UPDATABLE</span></span>|<span data-ttu-id="b9dca-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-657">Boolean</span></span>|  
|<span data-ttu-id="b9dca-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9dca-658">DESCRIPTION</span></span>|<span data-ttu-id="b9dca-659">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-659">String</span></span>|  
|<span data-ttu-id="b9dca-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="b9dca-660">DATE_CREATED</span></span>|<span data-ttu-id="b9dca-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9dca-661">DateTime</span></span>|  
|<span data-ttu-id="b9dca-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="b9dca-662">DATE_MODIFIED</span></span>|<span data-ttu-id="b9dca-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9dca-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="b9dca-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="b9dca-664">Indexes</span></span>  
  
|<span data-ttu-id="b9dca-665">열 이름</span><span class="sxs-lookup"><span data-stu-id="b9dca-665">ColumnName</span></span>|<span data-ttu-id="b9dca-666">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9dca-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="b9dca-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-667">TABLE_CATALOG</span></span>|<span data-ttu-id="b9dca-668">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-668">String</span></span>|  
|<span data-ttu-id="b9dca-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="b9dca-670">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-670">String</span></span>|  
|<span data-ttu-id="b9dca-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-671">TABLE_NAME</span></span>|<span data-ttu-id="b9dca-672">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-672">String</span></span>|  
|<span data-ttu-id="b9dca-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b9dca-673">INDEX_CATALOG</span></span>|<span data-ttu-id="b9dca-674">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-674">String</span></span>|  
|<span data-ttu-id="b9dca-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b9dca-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="b9dca-676">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-676">String</span></span>|  
|<span data-ttu-id="b9dca-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-677">INDEX_NAME</span></span>|<span data-ttu-id="b9dca-678">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-678">String</span></span>|  
|<span data-ttu-id="b9dca-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="b9dca-679">PRIMARY_KEY</span></span>|<span data-ttu-id="b9dca-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-680">Boolean</span></span>|  
|<span data-ttu-id="b9dca-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="b9dca-681">UNIQUE</span></span>|<span data-ttu-id="b9dca-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-682">Boolean</span></span>|  
|<span data-ttu-id="b9dca-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="b9dca-683">CLUSTERED</span></span>|<span data-ttu-id="b9dca-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-684">Boolean</span></span>|  
|<span data-ttu-id="b9dca-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="b9dca-685">TYPE</span></span>|<span data-ttu-id="b9dca-686">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-686">Int32</span></span>|  
|<span data-ttu-id="b9dca-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="b9dca-687">FILL_FACTOR</span></span>|<span data-ttu-id="b9dca-688">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-688">Int32</span></span>|  
|<span data-ttu-id="b9dca-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="b9dca-689">INITIAL_SIZE</span></span>|<span data-ttu-id="b9dca-690">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-690">Int32</span></span>|  
|<span data-ttu-id="b9dca-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="b9dca-691">NULLS</span></span>|<span data-ttu-id="b9dca-692">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-692">Int32</span></span>|  
|<span data-ttu-id="b9dca-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="b9dca-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="b9dca-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-694">Boolean</span></span>|  
|<span data-ttu-id="b9dca-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="b9dca-695">AUTO_UPDATE</span></span>|<span data-ttu-id="b9dca-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="b9dca-696">Boolean</span></span>|  
|<span data-ttu-id="b9dca-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="b9dca-697">NULL_COLLATION</span></span>|<span data-ttu-id="b9dca-698">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-698">Int32</span></span>|  
|<span data-ttu-id="b9dca-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b9dca-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="b9dca-700">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-700">Int64</span></span>|  
|<span data-ttu-id="b9dca-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="b9dca-701">COLUMN_NAME</span></span>|<span data-ttu-id="b9dca-702">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-702">String</span></span>|  
|<span data-ttu-id="b9dca-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="b9dca-703">COLUMN_GUID</span></span>|<span data-ttu-id="b9dca-704">Guid</span><span class="sxs-lookup"><span data-stu-id="b9dca-704">Guid</span></span>|  
|<span data-ttu-id="b9dca-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="b9dca-705">COLUMN_PROPID</span></span>|<span data-ttu-id="b9dca-706">Int64</span><span class="sxs-lookup"><span data-stu-id="b9dca-706">Int64</span></span>|  
|<span data-ttu-id="b9dca-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="b9dca-707">COLLATION</span></span>|<span data-ttu-id="b9dca-708">Int16</span><span class="sxs-lookup"><span data-stu-id="b9dca-708">Int16</span></span>|  
|<span data-ttu-id="b9dca-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="b9dca-709">CARDINALITY</span></span>|<span data-ttu-id="b9dca-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="b9dca-710">Decimal</span></span>|  
|<span data-ttu-id="b9dca-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="b9dca-711">PAGES</span></span>|<span data-ttu-id="b9dca-712">Int32</span><span class="sxs-lookup"><span data-stu-id="b9dca-712">Int32</span></span>|  
|<span data-ttu-id="b9dca-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="b9dca-713">FILTER_CONDITION</span></span>|<span data-ttu-id="b9dca-714">문자열</span><span class="sxs-lookup"><span data-stu-id="b9dca-714">String</span></span>|  
|<span data-ttu-id="b9dca-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="b9dca-715">INTEGRATED</span></span>|<span data-ttu-id="b9dca-716">부울</span><span class="sxs-lookup"><span data-stu-id="b9dca-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b9dca-717">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9dca-717">See Also</span></span>  
 [<span data-ttu-id="b9dca-718">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="b9dca-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
