---
title: OLE DB 스키마 컬렉션
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: f1cb5e1fe967088b44fa4045dfe50c1c57d963eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766935"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="1ca01-102">OLE DB 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="1ca01-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="1ca01-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 OLE DB 공급자에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca01-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="1ca01-104">Microsoft SQL Server OLE DB 공급자</span><span class="sxs-lookup"><span data-stu-id="1ca01-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="1ca01-105">Microsoft SQL Server OLE DB Driver에서는 공통 스키마 컬렉션을 비롯 하 여 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca01-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="1ca01-106">Tables</span><span class="sxs-lookup"><span data-stu-id="1ca01-106">Tables</span></span>  
  
-   <span data-ttu-id="1ca01-107">Columns</span><span class="sxs-lookup"><span data-stu-id="1ca01-107">Columns</span></span>  
  
-   <span data-ttu-id="1ca01-108">절차</span><span class="sxs-lookup"><span data-stu-id="1ca01-108">Procedures</span></span>  
  
-   <span data-ttu-id="1ca01-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="1ca01-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="1ca01-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="1ca01-110">Catalog</span></span>  
  
-   <span data-ttu-id="1ca01-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="1ca01-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="1ca01-112">Tables</span><span class="sxs-lookup"><span data-stu-id="1ca01-112">Tables</span></span>  
  
|<span data-ttu-id="1ca01-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-113">ColumnName</span></span>|<span data-ttu-id="1ca01-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-115">TABLE_CATALOG</span></span>|<span data-ttu-id="1ca01-116">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-116">String</span></span>|  
|<span data-ttu-id="1ca01-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="1ca01-118">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-118">String</span></span>|  
|<span data-ttu-id="1ca01-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-119">TABLE_NAME</span></span>|<span data-ttu-id="1ca01-120">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-120">String</span></span>|  
|<span data-ttu-id="1ca01-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1ca01-121">TABLE_TYPE</span></span>|<span data-ttu-id="1ca01-122">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-122">String</span></span>|  
|<span data-ttu-id="1ca01-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="1ca01-123">TABLE_GUID</span></span>|<span data-ttu-id="1ca01-124">Guid</span><span class="sxs-lookup"><span data-stu-id="1ca01-124">Guid</span></span>|  
|<span data-ttu-id="1ca01-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ca01-125">DESCRIPTION</span></span>|<span data-ttu-id="1ca01-126">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-126">String</span></span>|  
|<span data-ttu-id="1ca01-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="1ca01-127">TABLE_PROPID</span></span>|<span data-ttu-id="1ca01-128">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-128">Int64</span></span>|  
|<span data-ttu-id="1ca01-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1ca01-129">DATE_CREATED</span></span>|<span data-ttu-id="1ca01-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ca01-130">DateTime</span></span>|  
|<span data-ttu-id="1ca01-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1ca01-131">DATE_MODIFIED</span></span>|<span data-ttu-id="1ca01-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ca01-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="1ca01-133">Columns</span><span class="sxs-lookup"><span data-stu-id="1ca01-133">Columns</span></span>  
  
|<span data-ttu-id="1ca01-134">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-134">ColumnName</span></span>|<span data-ttu-id="1ca01-135">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-136">TABLE_CATALOG</span></span>|<span data-ttu-id="1ca01-137">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-137">String</span></span>|  
|<span data-ttu-id="1ca01-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="1ca01-139">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-139">String</span></span>|  
|<span data-ttu-id="1ca01-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-140">TABLE_NAME</span></span>|<span data-ttu-id="1ca01-141">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-141">String</span></span>|  
|<span data-ttu-id="1ca01-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-142">COLUMN_NAME</span></span>|<span data-ttu-id="1ca01-143">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-143">String</span></span>|  
|<span data-ttu-id="1ca01-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1ca01-144">COLUMN_GUID</span></span>|<span data-ttu-id="1ca01-145">Guid</span><span class="sxs-lookup"><span data-stu-id="1ca01-145">Guid</span></span>|  
|<span data-ttu-id="1ca01-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1ca01-146">COLUMN_PROPID</span></span>|<span data-ttu-id="1ca01-147">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-147">Int64</span></span>|  
|<span data-ttu-id="1ca01-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1ca01-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="1ca01-149">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-149">Int64</span></span>|  
|<span data-ttu-id="1ca01-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1ca01-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="1ca01-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-151">Boolean</span></span>|  
|<span data-ttu-id="1ca01-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1ca01-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="1ca01-153">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-153">String</span></span>|  
|<span data-ttu-id="1ca01-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1ca01-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="1ca01-155">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-155">Int64</span></span>|  
|<span data-ttu-id="1ca01-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1ca01-156">IS_NULLABLE</span></span>|<span data-ttu-id="1ca01-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-157">Boolean</span></span>|  
|<span data-ttu-id="1ca01-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1ca01-158">DATA_TYPE</span></span>|<span data-ttu-id="1ca01-159">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-159">Int32</span></span>|  
|<span data-ttu-id="1ca01-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="1ca01-160">TYPE_GUID</span></span>|<span data-ttu-id="1ca01-161">Guid</span><span class="sxs-lookup"><span data-stu-id="1ca01-161">Guid</span></span>|  
|<span data-ttu-id="1ca01-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1ca01-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1ca01-163">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-163">Int64</span></span>|  
|<span data-ttu-id="1ca01-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1ca01-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1ca01-165">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-165">Int64</span></span>|  
|<span data-ttu-id="1ca01-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1ca01-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1ca01-167">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-167">Int32</span></span>|  
|<span data-ttu-id="1ca01-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1ca01-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="1ca01-169">Int16</span><span class="sxs-lookup"><span data-stu-id="1ca01-169">Int16</span></span>|  
|<span data-ttu-id="1ca01-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1ca01-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="1ca01-171">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-171">Int64</span></span>|  
|<span data-ttu-id="1ca01-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="1ca01-173">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-173">String</span></span>|  
|<span data-ttu-id="1ca01-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="1ca01-175">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-175">String</span></span>|  
|<span data-ttu-id="1ca01-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="1ca01-177">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-177">String</span></span>|  
|<span data-ttu-id="1ca01-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="1ca01-179">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-179">String</span></span>|  
|<span data-ttu-id="1ca01-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="1ca01-181">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-181">String</span></span>|  
|<span data-ttu-id="1ca01-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-182">COLLATION_NAME</span></span>|<span data-ttu-id="1ca01-183">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-183">String</span></span>|  
|<span data-ttu-id="1ca01-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="1ca01-185">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-185">String</span></span>|  
|<span data-ttu-id="1ca01-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="1ca01-187">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-187">String</span></span>|  
|<span data-ttu-id="1ca01-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-188">DOMAIN_NAME</span></span>|<span data-ttu-id="1ca01-189">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-189">String</span></span>|  
|<span data-ttu-id="1ca01-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ca01-190">DESCRIPTION</span></span>|<span data-ttu-id="1ca01-191">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-191">String</span></span>|  
|<span data-ttu-id="1ca01-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="1ca01-192">COLUMN_LCID</span></span>|<span data-ttu-id="1ca01-193">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-193">Int32</span></span>|  
|<span data-ttu-id="1ca01-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="1ca01-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="1ca01-195">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-195">Int32</span></span>|  
|<span data-ttu-id="1ca01-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="1ca01-196">COLUMN_SORTID</span></span>|<span data-ttu-id="1ca01-197">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-197">Int32</span></span>|  
|<span data-ttu-id="1ca01-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="1ca01-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="1ca01-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="1ca01-199">Byte[]</span></span>|  
|<span data-ttu-id="1ca01-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="1ca01-200">IS_COMPUTED</span></span>|<span data-ttu-id="1ca01-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="1ca01-202">절차</span><span class="sxs-lookup"><span data-stu-id="1ca01-202">Procedures</span></span>  
  
|<span data-ttu-id="1ca01-203">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-203">ColumnName</span></span>|<span data-ttu-id="1ca01-204">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1ca01-206">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-206">String</span></span>|  
|<span data-ttu-id="1ca01-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1ca01-208">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-208">String</span></span>|  
|<span data-ttu-id="1ca01-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="1ca01-210">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-210">String</span></span>|  
|<span data-ttu-id="1ca01-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1ca01-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="1ca01-212">Int16</span><span class="sxs-lookup"><span data-stu-id="1ca01-212">Int16</span></span>|  
|<span data-ttu-id="1ca01-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1ca01-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="1ca01-214">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-214">String</span></span>|  
|<span data-ttu-id="1ca01-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ca01-215">DESCRIPTION</span></span>|<span data-ttu-id="1ca01-216">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-216">String</span></span>|  
|<span data-ttu-id="1ca01-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1ca01-217">DATE_CREATED</span></span>|<span data-ttu-id="1ca01-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ca01-218">DateTime</span></span>|  
|<span data-ttu-id="1ca01-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1ca01-219">DATE_MODIFIED</span></span>|<span data-ttu-id="1ca01-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ca01-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="1ca01-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="1ca01-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="1ca01-222">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-222">ColumnName</span></span>|<span data-ttu-id="1ca01-223">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1ca01-225">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-225">String</span></span>|  
|<span data-ttu-id="1ca01-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1ca01-227">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-227">String</span></span>|  
|<span data-ttu-id="1ca01-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="1ca01-229">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-229">String</span></span>|  
|<span data-ttu-id="1ca01-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-230">PARAMETER_NAME</span></span>|<span data-ttu-id="1ca01-231">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-231">String</span></span>|  
|<span data-ttu-id="1ca01-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1ca01-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="1ca01-233">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-233">Int32</span></span>|  
|<span data-ttu-id="1ca01-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="1ca01-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="1ca01-235">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-235">Int32</span></span>|  
|<span data-ttu-id="1ca01-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1ca01-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="1ca01-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-237">Boolean</span></span>|  
|<span data-ttu-id="1ca01-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1ca01-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="1ca01-239">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-239">String</span></span>|  
|<span data-ttu-id="1ca01-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1ca01-240">IS_NULLABLE</span></span>|<span data-ttu-id="1ca01-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-241">Boolean</span></span>|  
|<span data-ttu-id="1ca01-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1ca01-242">DATA_TYPE</span></span>|<span data-ttu-id="1ca01-243">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-243">Int32</span></span>|  
|<span data-ttu-id="1ca01-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1ca01-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1ca01-245">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-245">Int64</span></span>|  
|<span data-ttu-id="1ca01-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1ca01-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1ca01-247">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-247">Int64</span></span>|  
|<span data-ttu-id="1ca01-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1ca01-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1ca01-249">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-249">Int32</span></span>|  
|<span data-ttu-id="1ca01-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1ca01-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="1ca01-251">Int16</span><span class="sxs-lookup"><span data-stu-id="1ca01-251">Int16</span></span>|  
|<span data-ttu-id="1ca01-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ca01-252">DESCRIPTION</span></span>|<span data-ttu-id="1ca01-253">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-253">String</span></span>|  
|<span data-ttu-id="1ca01-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-254">TYPE_NAME</span></span>|<span data-ttu-id="1ca01-255">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-255">String</span></span>|  
|<span data-ttu-id="1ca01-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="1ca01-257">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="1ca01-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="1ca01-258">Catalog</span></span>  
  
|<span data-ttu-id="1ca01-259">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-259">ColumnName</span></span>|<span data-ttu-id="1ca01-260">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-261">CATALOG_NAME</span></span>|<span data-ttu-id="1ca01-262">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-262">String</span></span>|  
|<span data-ttu-id="1ca01-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ca01-263">DESCRIPTION</span></span>|<span data-ttu-id="1ca01-264">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="1ca01-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="1ca01-265">Indexes</span></span>  
  
|<span data-ttu-id="1ca01-266">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-266">ColumnName</span></span>|<span data-ttu-id="1ca01-267">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-268">TABLE_CATALOG</span></span>|<span data-ttu-id="1ca01-269">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-269">String</span></span>|  
|<span data-ttu-id="1ca01-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="1ca01-271">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-271">String</span></span>|  
|<span data-ttu-id="1ca01-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-272">TABLE_NAME</span></span>|<span data-ttu-id="1ca01-273">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-273">String</span></span>|  
|<span data-ttu-id="1ca01-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-274">INDEX_CATALOG</span></span>|<span data-ttu-id="1ca01-275">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-275">String</span></span>|  
|<span data-ttu-id="1ca01-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="1ca01-277">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-277">String</span></span>|  
|<span data-ttu-id="1ca01-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-278">INDEX_NAME</span></span>|<span data-ttu-id="1ca01-279">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-279">String</span></span>|  
|<span data-ttu-id="1ca01-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="1ca01-280">PRIMARY_KEY</span></span>|<span data-ttu-id="1ca01-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-281">Boolean</span></span>|  
|<span data-ttu-id="1ca01-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="1ca01-282">UNIQUE</span></span>|<span data-ttu-id="1ca01-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-283">Boolean</span></span>|  
|<span data-ttu-id="1ca01-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="1ca01-284">CLUSTERED</span></span>|<span data-ttu-id="1ca01-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-285">Boolean</span></span>|  
|<span data-ttu-id="1ca01-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="1ca01-286">TYPE</span></span>|<span data-ttu-id="1ca01-287">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-287">Int32</span></span>|  
|<span data-ttu-id="1ca01-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="1ca01-288">FILL_FACTOR</span></span>|<span data-ttu-id="1ca01-289">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-289">Int32</span></span>|  
|<span data-ttu-id="1ca01-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="1ca01-290">INITIAL_SIZE</span></span>|<span data-ttu-id="1ca01-291">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-291">Int32</span></span>|  
|<span data-ttu-id="1ca01-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="1ca01-292">NULLS</span></span>|<span data-ttu-id="1ca01-293">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-293">Int32</span></span>|  
|<span data-ttu-id="1ca01-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="1ca01-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="1ca01-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-295">Boolean</span></span>|  
|<span data-ttu-id="1ca01-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="1ca01-296">AUTO_UPDATE</span></span>|<span data-ttu-id="1ca01-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-297">Boolean</span></span>|  
|<span data-ttu-id="1ca01-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="1ca01-298">NULL_COLLATION</span></span>|<span data-ttu-id="1ca01-299">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-299">Int32</span></span>|  
|<span data-ttu-id="1ca01-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1ca01-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="1ca01-301">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-301">Int64</span></span>|  
|<span data-ttu-id="1ca01-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-302">COLUMN_NAME</span></span>|<span data-ttu-id="1ca01-303">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-303">String</span></span>|  
|<span data-ttu-id="1ca01-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1ca01-304">COLUMN_GUID</span></span>|<span data-ttu-id="1ca01-305">Guid</span><span class="sxs-lookup"><span data-stu-id="1ca01-305">Guid</span></span>|  
|<span data-ttu-id="1ca01-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1ca01-306">COLUMN_PROPID</span></span>|<span data-ttu-id="1ca01-307">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-307">Int64</span></span>|  
|<span data-ttu-id="1ca01-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="1ca01-308">COLLATION</span></span>|<span data-ttu-id="1ca01-309">Int16</span><span class="sxs-lookup"><span data-stu-id="1ca01-309">Int16</span></span>|  
|<span data-ttu-id="1ca01-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="1ca01-310">CARDINALITY</span></span>|<span data-ttu-id="1ca01-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="1ca01-311">Decimal</span></span>|  
|<span data-ttu-id="1ca01-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="1ca01-312">PAGES</span></span>|<span data-ttu-id="1ca01-313">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-313">Int32</span></span>|  
|<span data-ttu-id="1ca01-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="1ca01-314">FILTER_CONDITION</span></span>|<span data-ttu-id="1ca01-315">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-315">String</span></span>|  
|<span data-ttu-id="1ca01-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="1ca01-316">INTEGRATED</span></span>|<span data-ttu-id="1ca01-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="1ca01-318">Microsoft Oracle OLE DB    </span><span class="sxs-lookup"><span data-stu-id="1ca01-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="1ca01-319">Microsoft Oracle OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="1ca01-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="1ca01-320">Tables</span><span class="sxs-lookup"><span data-stu-id="1ca01-320">Tables</span></span>  
  
-   <span data-ttu-id="1ca01-321">Columns</span><span class="sxs-lookup"><span data-stu-id="1ca01-321">Columns</span></span>  
  
-   <span data-ttu-id="1ca01-322">절차</span><span class="sxs-lookup"><span data-stu-id="1ca01-322">Procedures</span></span>  
  
-   <span data-ttu-id="1ca01-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="1ca01-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="1ca01-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="1ca01-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="1ca01-325">뷰</span><span class="sxs-lookup"><span data-stu-id="1ca01-325">Views</span></span>  
  
-   <span data-ttu-id="1ca01-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="1ca01-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="1ca01-327">Tables</span><span class="sxs-lookup"><span data-stu-id="1ca01-327">Tables</span></span>  
  
|<span data-ttu-id="1ca01-328">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-328">ColumnName</span></span>|<span data-ttu-id="1ca01-329">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-330">TABLE_CATALOG</span></span>|<span data-ttu-id="1ca01-331">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-331">String</span></span>|  
|<span data-ttu-id="1ca01-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="1ca01-333">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-333">String</span></span>|  
|<span data-ttu-id="1ca01-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-334">TABLE_NAME</span></span>|<span data-ttu-id="1ca01-335">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-335">String</span></span>|  
|<span data-ttu-id="1ca01-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1ca01-336">TABLE_TYPE</span></span>|<span data-ttu-id="1ca01-337">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-337">String</span></span>|  
|<span data-ttu-id="1ca01-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="1ca01-338">TABLE_GUID</span></span>|<span data-ttu-id="1ca01-339">Guid</span><span class="sxs-lookup"><span data-stu-id="1ca01-339">Guid</span></span>|  
|<span data-ttu-id="1ca01-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ca01-340">DESCRIPTION</span></span>|<span data-ttu-id="1ca01-341">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-341">String</span></span>|  
|<span data-ttu-id="1ca01-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="1ca01-342">TABLE_PROPID</span></span>|<span data-ttu-id="1ca01-343">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-343">Int64</span></span>|  
|<span data-ttu-id="1ca01-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1ca01-344">DATE_CREATED</span></span>|<span data-ttu-id="1ca01-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ca01-345">DateTime</span></span>|  
|<span data-ttu-id="1ca01-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1ca01-346">DATE_MODIFIED</span></span>|<span data-ttu-id="1ca01-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ca01-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="1ca01-348">Columns</span><span class="sxs-lookup"><span data-stu-id="1ca01-348">Columns</span></span>  
  
|<span data-ttu-id="1ca01-349">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-349">ColumnName</span></span>|<span data-ttu-id="1ca01-350">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-351">TABLE_CATALOG</span></span>|<span data-ttu-id="1ca01-352">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-352">String</span></span>|  
|<span data-ttu-id="1ca01-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="1ca01-354">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-354">String</span></span>|  
|<span data-ttu-id="1ca01-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-355">TABLE_NAME</span></span>|<span data-ttu-id="1ca01-356">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-356">String</span></span>|  
|<span data-ttu-id="1ca01-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-357">COLUMN_NAME</span></span>|<span data-ttu-id="1ca01-358">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-358">String</span></span>|  
|<span data-ttu-id="1ca01-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1ca01-359">COLUMN_GUID</span></span>|<span data-ttu-id="1ca01-360">Guid</span><span class="sxs-lookup"><span data-stu-id="1ca01-360">Guid</span></span>|  
|<span data-ttu-id="1ca01-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1ca01-361">COLUMN_PROPID</span></span>|<span data-ttu-id="1ca01-362">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-362">Int64</span></span>|  
|<span data-ttu-id="1ca01-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1ca01-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="1ca01-364">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-364">Int64</span></span>|  
|<span data-ttu-id="1ca01-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1ca01-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="1ca01-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-366">Boolean</span></span>|  
|<span data-ttu-id="1ca01-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1ca01-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="1ca01-368">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-368">String</span></span>|  
|<span data-ttu-id="1ca01-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1ca01-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="1ca01-370">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-370">Int64</span></span>|  
|<span data-ttu-id="1ca01-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1ca01-371">IS_NULLABLE</span></span>|<span data-ttu-id="1ca01-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-372">Boolean</span></span>|  
|<span data-ttu-id="1ca01-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1ca01-373">DATA_TYPE</span></span>|<span data-ttu-id="1ca01-374">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-374">Int32</span></span>|  
|<span data-ttu-id="1ca01-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="1ca01-375">TYPE_GUID</span></span>|<span data-ttu-id="1ca01-376">Guid</span><span class="sxs-lookup"><span data-stu-id="1ca01-376">Guid</span></span>|  
|<span data-ttu-id="1ca01-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1ca01-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1ca01-378">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-378">Int64</span></span>|  
|<span data-ttu-id="1ca01-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1ca01-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1ca01-380">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-380">Int64</span></span>|  
|<span data-ttu-id="1ca01-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1ca01-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1ca01-382">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-382">Int32</span></span>|  
|<span data-ttu-id="1ca01-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1ca01-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="1ca01-384">Int16</span><span class="sxs-lookup"><span data-stu-id="1ca01-384">Int16</span></span>|  
|<span data-ttu-id="1ca01-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1ca01-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="1ca01-386">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-386">Int64</span></span>|  
|<span data-ttu-id="1ca01-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="1ca01-388">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-388">String</span></span>|  
|<span data-ttu-id="1ca01-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="1ca01-390">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-390">String</span></span>|  
|<span data-ttu-id="1ca01-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="1ca01-392">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-392">String</span></span>|  
|<span data-ttu-id="1ca01-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="1ca01-394">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-394">String</span></span>|  
|<span data-ttu-id="1ca01-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="1ca01-396">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-396">String</span></span>|  
|<span data-ttu-id="1ca01-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-397">COLLATION_NAME</span></span>|<span data-ttu-id="1ca01-398">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-398">String</span></span>|  
|<span data-ttu-id="1ca01-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="1ca01-400">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-400">String</span></span>|  
|<span data-ttu-id="1ca01-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="1ca01-402">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-402">String</span></span>|  
|<span data-ttu-id="1ca01-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-403">DOMAIN_NAME</span></span>|<span data-ttu-id="1ca01-404">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-404">String</span></span>|  
|<span data-ttu-id="1ca01-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ca01-405">DESCRIPTION</span></span>|<span data-ttu-id="1ca01-406">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="1ca01-407">절차</span><span class="sxs-lookup"><span data-stu-id="1ca01-407">Procedures</span></span>  
  
|<span data-ttu-id="1ca01-408">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-408">ColumnName</span></span>|<span data-ttu-id="1ca01-409">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1ca01-411">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-411">String</span></span>|  
|<span data-ttu-id="1ca01-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1ca01-413">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-413">String</span></span>|  
|<span data-ttu-id="1ca01-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="1ca01-415">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-415">String</span></span>|  
|<span data-ttu-id="1ca01-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1ca01-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="1ca01-417">Int16</span><span class="sxs-lookup"><span data-stu-id="1ca01-417">Int16</span></span>|  
|<span data-ttu-id="1ca01-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1ca01-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="1ca01-419">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-419">String</span></span>|  
|<span data-ttu-id="1ca01-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ca01-420">DESCRIPTION</span></span>|<span data-ttu-id="1ca01-421">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-421">String</span></span>|  
|<span data-ttu-id="1ca01-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1ca01-422">DATE_CREATED</span></span>|<span data-ttu-id="1ca01-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ca01-423">DateTime</span></span>|  
|<span data-ttu-id="1ca01-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1ca01-424">DATE_MODIFIED</span></span>|<span data-ttu-id="1ca01-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ca01-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="1ca01-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="1ca01-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="1ca01-427">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-427">ColumnName</span></span>|<span data-ttu-id="1ca01-428">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1ca01-430">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-430">String</span></span>|  
|<span data-ttu-id="1ca01-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1ca01-432">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-432">String</span></span>|  
|<span data-ttu-id="1ca01-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="1ca01-434">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-434">String</span></span>|  
|<span data-ttu-id="1ca01-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-435">COLUMN_NAME</span></span>|<span data-ttu-id="1ca01-436">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-436">String</span></span>|  
|<span data-ttu-id="1ca01-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1ca01-437">COLUMN_GUID</span></span>|<span data-ttu-id="1ca01-438">Guid</span><span class="sxs-lookup"><span data-stu-id="1ca01-438">Guid</span></span>|  
|<span data-ttu-id="1ca01-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1ca01-439">COLUMN_PROPID</span></span>|<span data-ttu-id="1ca01-440">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-440">Int64</span></span>|  
|<span data-ttu-id="1ca01-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="1ca01-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="1ca01-442">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-442">Int64</span></span>|  
|<span data-ttu-id="1ca01-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1ca01-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="1ca01-444">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-444">Int64</span></span>|  
|<span data-ttu-id="1ca01-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1ca01-445">IS_NULLABLE</span></span>|<span data-ttu-id="1ca01-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-446">Boolean</span></span>|  
|<span data-ttu-id="1ca01-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1ca01-447">DATA_TYPE</span></span>|<span data-ttu-id="1ca01-448">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-448">Int32</span></span>|  
|<span data-ttu-id="1ca01-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="1ca01-449">TYPE_GUID</span></span>|<span data-ttu-id="1ca01-450">Guid</span><span class="sxs-lookup"><span data-stu-id="1ca01-450">Guid</span></span>|  
|<span data-ttu-id="1ca01-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1ca01-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1ca01-452">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-452">Int64</span></span>|  
|<span data-ttu-id="1ca01-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1ca01-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1ca01-454">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-454">Int64</span></span>|  
|<span data-ttu-id="1ca01-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1ca01-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1ca01-456">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-456">Int32</span></span>|  
|<span data-ttu-id="1ca01-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1ca01-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="1ca01-458">Int16</span><span class="sxs-lookup"><span data-stu-id="1ca01-458">Int16</span></span>|  
|<span data-ttu-id="1ca01-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ca01-459">DESCRIPTION</span></span>|<span data-ttu-id="1ca01-460">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-460">String</span></span>|  
|<span data-ttu-id="1ca01-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="1ca01-461">OVERLOAD</span></span>|<span data-ttu-id="1ca01-462">Int16</span><span class="sxs-lookup"><span data-stu-id="1ca01-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="1ca01-463">뷰</span><span class="sxs-lookup"><span data-stu-id="1ca01-463">Views</span></span>  
  
|<span data-ttu-id="1ca01-464">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-464">ColumnName</span></span>|<span data-ttu-id="1ca01-465">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-466">TABLE_CATALOG</span></span>|<span data-ttu-id="1ca01-467">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-467">String</span></span>|  
|<span data-ttu-id="1ca01-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="1ca01-469">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-469">String</span></span>|  
|<span data-ttu-id="1ca01-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-470">TABLE_NAME</span></span>|<span data-ttu-id="1ca01-471">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-471">String</span></span>|  
|<span data-ttu-id="1ca01-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1ca01-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="1ca01-473">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-473">String</span></span>|  
|<span data-ttu-id="1ca01-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="1ca01-474">CHECK_OPTION</span></span>|<span data-ttu-id="1ca01-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-475">Boolean</span></span>|  
|<span data-ttu-id="1ca01-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="1ca01-476">IS_UPDATABLE</span></span>|<span data-ttu-id="1ca01-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-477">Boolean</span></span>|  
|<span data-ttu-id="1ca01-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ca01-478">DESCRIPTION</span></span>|<span data-ttu-id="1ca01-479">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-479">String</span></span>|  
|<span data-ttu-id="1ca01-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1ca01-480">DATE_CREATED</span></span>|<span data-ttu-id="1ca01-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ca01-481">DateTime</span></span>|  
|<span data-ttu-id="1ca01-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1ca01-482">DATE_MODIFIED</span></span>|<span data-ttu-id="1ca01-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ca01-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="1ca01-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="1ca01-484">Indexes</span></span>  
  
|<span data-ttu-id="1ca01-485">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-485">ColumnName</span></span>|<span data-ttu-id="1ca01-486">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-487">TABLE_CATALOG</span></span>|<span data-ttu-id="1ca01-488">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-488">String</span></span>|  
|<span data-ttu-id="1ca01-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="1ca01-490">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-490">String</span></span>|  
|<span data-ttu-id="1ca01-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-491">TABLE_NAME</span></span>|<span data-ttu-id="1ca01-492">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-492">String</span></span>|  
|<span data-ttu-id="1ca01-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-493">INDEX_CATALOG</span></span>|<span data-ttu-id="1ca01-494">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-494">String</span></span>|  
|<span data-ttu-id="1ca01-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="1ca01-496">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-496">String</span></span>|  
|<span data-ttu-id="1ca01-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-497">INDEX_NAME</span></span>|<span data-ttu-id="1ca01-498">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-498">String</span></span>|  
|<span data-ttu-id="1ca01-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="1ca01-499">PRIMARY_KEY</span></span>|<span data-ttu-id="1ca01-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-500">Boolean</span></span>|  
|<span data-ttu-id="1ca01-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="1ca01-501">UNIQUE</span></span>|<span data-ttu-id="1ca01-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-502">Boolean</span></span>|  
|<span data-ttu-id="1ca01-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="1ca01-503">CLUSTERED</span></span>|<span data-ttu-id="1ca01-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-504">Boolean</span></span>|  
|<span data-ttu-id="1ca01-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="1ca01-505">TYPE</span></span>|<span data-ttu-id="1ca01-506">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-506">Int32</span></span>|  
|<span data-ttu-id="1ca01-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="1ca01-507">FILL_FACTOR</span></span>|<span data-ttu-id="1ca01-508">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-508">Int32</span></span>|  
|<span data-ttu-id="1ca01-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="1ca01-509">INITIAL_SIZE</span></span>|<span data-ttu-id="1ca01-510">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-510">Int32</span></span>|  
|<span data-ttu-id="1ca01-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="1ca01-511">NULLS</span></span>|<span data-ttu-id="1ca01-512">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-512">Int32</span></span>|  
|<span data-ttu-id="1ca01-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="1ca01-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="1ca01-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-514">Boolean</span></span>|  
|<span data-ttu-id="1ca01-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="1ca01-515">AUTO_UPDATE</span></span>|<span data-ttu-id="1ca01-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-516">Boolean</span></span>|  
|<span data-ttu-id="1ca01-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="1ca01-517">NULL_COLLATION</span></span>|<span data-ttu-id="1ca01-518">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-518">Int32</span></span>|  
|<span data-ttu-id="1ca01-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1ca01-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="1ca01-520">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-520">Int64</span></span>|  
|<span data-ttu-id="1ca01-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-521">COLUMN_NAME</span></span>|<span data-ttu-id="1ca01-522">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-522">String</span></span>|  
|<span data-ttu-id="1ca01-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1ca01-523">COLUMN_GUID</span></span>|<span data-ttu-id="1ca01-524">Guid</span><span class="sxs-lookup"><span data-stu-id="1ca01-524">Guid</span></span>|  
|<span data-ttu-id="1ca01-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1ca01-525">COLUMN_PROPID</span></span>|<span data-ttu-id="1ca01-526">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-526">Int64</span></span>|  
|<span data-ttu-id="1ca01-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="1ca01-527">COLLATION</span></span>|<span data-ttu-id="1ca01-528">Int16</span><span class="sxs-lookup"><span data-stu-id="1ca01-528">Int16</span></span>|  
|<span data-ttu-id="1ca01-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="1ca01-529">CARDINALITY</span></span>|<span data-ttu-id="1ca01-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="1ca01-530">Decimal</span></span>|  
|<span data-ttu-id="1ca01-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="1ca01-531">PAGES</span></span>|<span data-ttu-id="1ca01-532">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-532">Int32</span></span>|  
|<span data-ttu-id="1ca01-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="1ca01-533">FILTER_CONDITION</span></span>|<span data-ttu-id="1ca01-534">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-534">String</span></span>|  
|<span data-ttu-id="1ca01-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="1ca01-535">INTEGRATED</span></span>|<span data-ttu-id="1ca01-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="1ca01-537">Microsoft Jet OLE DB    </span><span class="sxs-lookup"><span data-stu-id="1ca01-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="1ca01-538">Microsoft Jet OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="1ca01-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="1ca01-539">Tables</span><span class="sxs-lookup"><span data-stu-id="1ca01-539">Tables</span></span>  
  
-   <span data-ttu-id="1ca01-540">Columns</span><span class="sxs-lookup"><span data-stu-id="1ca01-540">Columns</span></span>  
  
-   <span data-ttu-id="1ca01-541">절차</span><span class="sxs-lookup"><span data-stu-id="1ca01-541">Procedures</span></span>  
  
-   <span data-ttu-id="1ca01-542">뷰</span><span class="sxs-lookup"><span data-stu-id="1ca01-542">Views</span></span>  
  
-   <span data-ttu-id="1ca01-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="1ca01-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="1ca01-544">Tables</span><span class="sxs-lookup"><span data-stu-id="1ca01-544">Tables</span></span>  
  
|<span data-ttu-id="1ca01-545">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-545">ColumnName</span></span>|<span data-ttu-id="1ca01-546">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-547">TABLE_CATALOG</span></span>|<span data-ttu-id="1ca01-548">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-548">String</span></span>|  
|<span data-ttu-id="1ca01-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="1ca01-550">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-550">String</span></span>|  
|<span data-ttu-id="1ca01-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-551">TABLE_NAME</span></span>|<span data-ttu-id="1ca01-552">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-552">String</span></span>|  
|<span data-ttu-id="1ca01-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1ca01-553">TABLE_TYPE</span></span>|<span data-ttu-id="1ca01-554">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-554">String</span></span>|  
|<span data-ttu-id="1ca01-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="1ca01-555">TABLE_GUID</span></span>|<span data-ttu-id="1ca01-556">Guid</span><span class="sxs-lookup"><span data-stu-id="1ca01-556">Guid</span></span>|  
|<span data-ttu-id="1ca01-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ca01-557">DESCRIPTION</span></span>|<span data-ttu-id="1ca01-558">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-558">String</span></span>|  
|<span data-ttu-id="1ca01-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="1ca01-559">TABLE_PROPID</span></span>|<span data-ttu-id="1ca01-560">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-560">Int64</span></span>|  
|<span data-ttu-id="1ca01-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1ca01-561">DATE_CREATED</span></span>|<span data-ttu-id="1ca01-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ca01-562">DateTime</span></span>|  
|<span data-ttu-id="1ca01-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1ca01-563">DATE_MODIFIED</span></span>|<span data-ttu-id="1ca01-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ca01-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="1ca01-565">Columns</span><span class="sxs-lookup"><span data-stu-id="1ca01-565">Columns</span></span>  
  
|<span data-ttu-id="1ca01-566">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-566">ColumnName</span></span>|<span data-ttu-id="1ca01-567">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-568">TABLE_CATALOG</span></span>|<span data-ttu-id="1ca01-569">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-569">String</span></span>|  
|<span data-ttu-id="1ca01-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="1ca01-571">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-571">String</span></span>|  
|<span data-ttu-id="1ca01-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-572">TABLE_NAME</span></span>|<span data-ttu-id="1ca01-573">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-573">String</span></span>|  
|<span data-ttu-id="1ca01-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-574">COLUMN_NAME</span></span>|<span data-ttu-id="1ca01-575">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-575">String</span></span>|  
|<span data-ttu-id="1ca01-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1ca01-576">COLUMN_GUID</span></span>|<span data-ttu-id="1ca01-577">Guid</span><span class="sxs-lookup"><span data-stu-id="1ca01-577">Guid</span></span>|  
|<span data-ttu-id="1ca01-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1ca01-578">COLUMN_PROPID</span></span>|<span data-ttu-id="1ca01-579">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-579">Int64</span></span>|  
|<span data-ttu-id="1ca01-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1ca01-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="1ca01-581">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-581">Int64</span></span>|  
|<span data-ttu-id="1ca01-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1ca01-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="1ca01-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-583">Boolean</span></span>|  
|<span data-ttu-id="1ca01-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1ca01-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="1ca01-585">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-585">String</span></span>|  
|<span data-ttu-id="1ca01-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1ca01-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="1ca01-587">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-587">Int64</span></span>|  
|<span data-ttu-id="1ca01-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1ca01-588">IS_NULLABLE</span></span>|<span data-ttu-id="1ca01-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-589">Boolean</span></span>|  
|<span data-ttu-id="1ca01-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1ca01-590">DATA_TYPE</span></span>|<span data-ttu-id="1ca01-591">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-591">Int32</span></span>|  
|<span data-ttu-id="1ca01-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="1ca01-592">TYPE_GUID</span></span>|<span data-ttu-id="1ca01-593">Guid</span><span class="sxs-lookup"><span data-stu-id="1ca01-593">Guid</span></span>|  
|<span data-ttu-id="1ca01-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1ca01-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1ca01-595">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-595">Int64</span></span>|  
|<span data-ttu-id="1ca01-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1ca01-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1ca01-597">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-597">Int64</span></span>|  
|<span data-ttu-id="1ca01-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1ca01-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1ca01-599">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-599">Int32</span></span>|  
|<span data-ttu-id="1ca01-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1ca01-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="1ca01-601">Int16</span><span class="sxs-lookup"><span data-stu-id="1ca01-601">Int16</span></span>|  
|<span data-ttu-id="1ca01-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1ca01-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="1ca01-603">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-603">Int64</span></span>|  
|<span data-ttu-id="1ca01-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="1ca01-605">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-605">String</span></span>|  
|<span data-ttu-id="1ca01-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="1ca01-607">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-607">String</span></span>|  
|<span data-ttu-id="1ca01-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="1ca01-609">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-609">String</span></span>|  
|<span data-ttu-id="1ca01-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="1ca01-611">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-611">String</span></span>|  
|<span data-ttu-id="1ca01-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="1ca01-613">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-613">String</span></span>|  
|<span data-ttu-id="1ca01-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-614">COLLATION_NAME</span></span>|<span data-ttu-id="1ca01-615">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-615">String</span></span>|  
|<span data-ttu-id="1ca01-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="1ca01-617">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-617">String</span></span>|  
|<span data-ttu-id="1ca01-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="1ca01-619">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-619">String</span></span>|  
|<span data-ttu-id="1ca01-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-620">DOMAIN_NAME</span></span>|<span data-ttu-id="1ca01-621">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-621">String</span></span>|  
|<span data-ttu-id="1ca01-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ca01-622">DESCRIPTION</span></span>|<span data-ttu-id="1ca01-623">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="1ca01-624">절차</span><span class="sxs-lookup"><span data-stu-id="1ca01-624">Procedures</span></span>  
  
|<span data-ttu-id="1ca01-625">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-625">ColumnName</span></span>|<span data-ttu-id="1ca01-626">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1ca01-628">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-628">String</span></span>|  
|<span data-ttu-id="1ca01-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1ca01-630">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-630">String</span></span>|  
|<span data-ttu-id="1ca01-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="1ca01-632">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-632">String</span></span>|  
|<span data-ttu-id="1ca01-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1ca01-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="1ca01-634">Int16</span><span class="sxs-lookup"><span data-stu-id="1ca01-634">Int16</span></span>|  
|<span data-ttu-id="1ca01-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1ca01-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="1ca01-636">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-636">String</span></span>|  
|<span data-ttu-id="1ca01-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ca01-637">DESCRIPTION</span></span>|<span data-ttu-id="1ca01-638">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-638">String</span></span>|  
|<span data-ttu-id="1ca01-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1ca01-639">DATE_CREATED</span></span>|<span data-ttu-id="1ca01-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ca01-640">DateTime</span></span>|  
|<span data-ttu-id="1ca01-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1ca01-641">DATE_MODIFIED</span></span>|<span data-ttu-id="1ca01-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ca01-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="1ca01-643">뷰</span><span class="sxs-lookup"><span data-stu-id="1ca01-643">Views</span></span>  
  
|<span data-ttu-id="1ca01-644">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-644">ColumnName</span></span>|<span data-ttu-id="1ca01-645">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-646">TABLE_CATALOG</span></span>|<span data-ttu-id="1ca01-647">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-647">String</span></span>|  
|<span data-ttu-id="1ca01-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="1ca01-649">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-649">String</span></span>|  
|<span data-ttu-id="1ca01-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-650">TABLE_NAME</span></span>|<span data-ttu-id="1ca01-651">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-651">String</span></span>|  
|<span data-ttu-id="1ca01-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1ca01-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="1ca01-653">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-653">String</span></span>|  
|<span data-ttu-id="1ca01-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="1ca01-654">CHECK_OPTION</span></span>|<span data-ttu-id="1ca01-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-655">Boolean</span></span>|  
|<span data-ttu-id="1ca01-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="1ca01-656">IS_UPDATABLE</span></span>|<span data-ttu-id="1ca01-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-657">Boolean</span></span>|  
|<span data-ttu-id="1ca01-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ca01-658">DESCRIPTION</span></span>|<span data-ttu-id="1ca01-659">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-659">String</span></span>|  
|<span data-ttu-id="1ca01-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1ca01-660">DATE_CREATED</span></span>|<span data-ttu-id="1ca01-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ca01-661">DateTime</span></span>|  
|<span data-ttu-id="1ca01-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1ca01-662">DATE_MODIFIED</span></span>|<span data-ttu-id="1ca01-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ca01-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="1ca01-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="1ca01-664">Indexes</span></span>  
  
|<span data-ttu-id="1ca01-665">열 이름</span><span class="sxs-lookup"><span data-stu-id="1ca01-665">ColumnName</span></span>|<span data-ttu-id="1ca01-666">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ca01-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1ca01-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-667">TABLE_CATALOG</span></span>|<span data-ttu-id="1ca01-668">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-668">String</span></span>|  
|<span data-ttu-id="1ca01-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="1ca01-670">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-670">String</span></span>|  
|<span data-ttu-id="1ca01-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-671">TABLE_NAME</span></span>|<span data-ttu-id="1ca01-672">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-672">String</span></span>|  
|<span data-ttu-id="1ca01-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1ca01-673">INDEX_CATALOG</span></span>|<span data-ttu-id="1ca01-674">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-674">String</span></span>|  
|<span data-ttu-id="1ca01-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1ca01-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="1ca01-676">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-676">String</span></span>|  
|<span data-ttu-id="1ca01-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-677">INDEX_NAME</span></span>|<span data-ttu-id="1ca01-678">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-678">String</span></span>|  
|<span data-ttu-id="1ca01-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="1ca01-679">PRIMARY_KEY</span></span>|<span data-ttu-id="1ca01-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-680">Boolean</span></span>|  
|<span data-ttu-id="1ca01-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="1ca01-681">UNIQUE</span></span>|<span data-ttu-id="1ca01-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-682">Boolean</span></span>|  
|<span data-ttu-id="1ca01-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="1ca01-683">CLUSTERED</span></span>|<span data-ttu-id="1ca01-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-684">Boolean</span></span>|  
|<span data-ttu-id="1ca01-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="1ca01-685">TYPE</span></span>|<span data-ttu-id="1ca01-686">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-686">Int32</span></span>|  
|<span data-ttu-id="1ca01-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="1ca01-687">FILL_FACTOR</span></span>|<span data-ttu-id="1ca01-688">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-688">Int32</span></span>|  
|<span data-ttu-id="1ca01-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="1ca01-689">INITIAL_SIZE</span></span>|<span data-ttu-id="1ca01-690">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-690">Int32</span></span>|  
|<span data-ttu-id="1ca01-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="1ca01-691">NULLS</span></span>|<span data-ttu-id="1ca01-692">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-692">Int32</span></span>|  
|<span data-ttu-id="1ca01-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="1ca01-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="1ca01-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-694">Boolean</span></span>|  
|<span data-ttu-id="1ca01-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="1ca01-695">AUTO_UPDATE</span></span>|<span data-ttu-id="1ca01-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ca01-696">Boolean</span></span>|  
|<span data-ttu-id="1ca01-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="1ca01-697">NULL_COLLATION</span></span>|<span data-ttu-id="1ca01-698">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-698">Int32</span></span>|  
|<span data-ttu-id="1ca01-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1ca01-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="1ca01-700">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-700">Int64</span></span>|  
|<span data-ttu-id="1ca01-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca01-701">COLUMN_NAME</span></span>|<span data-ttu-id="1ca01-702">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-702">String</span></span>|  
|<span data-ttu-id="1ca01-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1ca01-703">COLUMN_GUID</span></span>|<span data-ttu-id="1ca01-704">Guid</span><span class="sxs-lookup"><span data-stu-id="1ca01-704">Guid</span></span>|  
|<span data-ttu-id="1ca01-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1ca01-705">COLUMN_PROPID</span></span>|<span data-ttu-id="1ca01-706">Int64</span><span class="sxs-lookup"><span data-stu-id="1ca01-706">Int64</span></span>|  
|<span data-ttu-id="1ca01-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="1ca01-707">COLLATION</span></span>|<span data-ttu-id="1ca01-708">Int16</span><span class="sxs-lookup"><span data-stu-id="1ca01-708">Int16</span></span>|  
|<span data-ttu-id="1ca01-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="1ca01-709">CARDINALITY</span></span>|<span data-ttu-id="1ca01-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="1ca01-710">Decimal</span></span>|  
|<span data-ttu-id="1ca01-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="1ca01-711">PAGES</span></span>|<span data-ttu-id="1ca01-712">Int32</span><span class="sxs-lookup"><span data-stu-id="1ca01-712">Int32</span></span>|  
|<span data-ttu-id="1ca01-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="1ca01-713">FILTER_CONDITION</span></span>|<span data-ttu-id="1ca01-714">문자열</span><span class="sxs-lookup"><span data-stu-id="1ca01-714">String</span></span>|  
|<span data-ttu-id="1ca01-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="1ca01-715">INTEGRATED</span></span>|<span data-ttu-id="1ca01-716">부울</span><span class="sxs-lookup"><span data-stu-id="1ca01-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ca01-717">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ca01-717">See Also</span></span>  
 [<span data-ttu-id="1ca01-718">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="1ca01-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
