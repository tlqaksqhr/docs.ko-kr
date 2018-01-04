---
title: "IMetaDataTables 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables
helpviewer_keywords: IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ff70e99a963c929792a73cefd6e8feaefa8b252e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatables-interface"></a><span data-ttu-id="b4472-102">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4472-102">IMetaDataTables Interface</span></span>
<span data-ttu-id="b4472-103">테이블에서 메타데이터 정보를 저장 및 검색하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-103">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b4472-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-104">Methods</span></span>  
  
|<span data-ttu-id="b4472-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-105">Method</span></span>|<span data-ttu-id="b4472-106">설명</span><span class="sxs-lookup"><span data-stu-id="b4472-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b4472-107">GetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-107">GetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|<span data-ttu-id="b4472-108">이진 대형 개체 (BLOB)에 지정 된 열 인덱스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-108">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="b4472-109">GetBlobHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-109">GetBlobHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="b4472-110">BLOB 힙을 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-110">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="b4472-111">GetCodedTokenInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-111">GetCodedTokenInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="b4472-112">지정된 된 행 인덱스와 연결 된 토큰의 배열에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-112">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="b4472-113">GetColumn 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-113">GetColumn Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|<span data-ttu-id="b4472-114">지정된 된 테이블 인덱스에 있는 테이블에 지정 된 열 인덱스의 열에 포함 된 값에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-114">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="b4472-115">GetColumnInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-115">GetColumnInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="b4472-116">지정된 된 테이블의 지정된 된 열에 대 한 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-116">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="b4472-117">GetGuid 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-117">GetGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|<span data-ttu-id="b4472-118">지정된 된 인덱스에서 행의 GUID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-118">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="b4472-119">GetGuidHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-119">GetGuidHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="b4472-120">GUID 힙을 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-120">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="b4472-121">GetNextBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-121">GetNextBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|<span data-ttu-id="b4472-122">테이블의 다음 BLOB의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-122">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="b4472-123">GetNextGuid 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-123">GetNextGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|<span data-ttu-id="b4472-124">현재 테이블 열에 다음 GUID 값의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-124">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="b4472-125">GetNextString 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-125">GetNextString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|<span data-ttu-id="b4472-126">현재 테이블 열에 다음 문자열의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-126">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="b4472-127">GetNextUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-127">GetNextUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="b4472-128">현재 테이블 열에 있는 다음 하드 코드 된 문자열이 포함 된 행의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-128">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="b4472-129">GetNumTables 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-129">GetNumTables Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|<span data-ttu-id="b4472-130">현재 범위에 테이블의 수를 가져옵니다 `IMetaDataTables` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="b4472-130">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="b4472-131">GetRow 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-131">GetRow Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|<span data-ttu-id="b4472-132">지정 된 행 인덱스에 지정된 된 테이블 인덱스에 있는 테이블에 행을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-132">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="b4472-133">GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-133">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|<span data-ttu-id="b4472-134">현재 참조 범위에서 테이블 열에서 지정된 된 인덱스에 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-134">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="b4472-135">GetStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-135">GetStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="b4472-136">문자열 힙을 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-136">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="b4472-137">GetTableIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-137">GetTableIndex Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|<span data-ttu-id="b4472-138">지정한 토큰이 참조 하는 테이블에 대 한 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-138">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="b4472-139">GetTableInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-139">GetTableInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|<span data-ttu-id="b4472-140">지정한 테이블 인덱스에는 이름, 행 크기, 행의 수, 열 개수 및 테이블의 키 열 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-140">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="b4472-141">GetUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-141">GetUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|<span data-ttu-id="b4472-142">현재 범위에서 문자열 열에서 지정된 된 인덱스에 하드 코드 된 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-142">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="b4472-143">GetUserStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="b4472-143">GetUserStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="b4472-144">사용자 문자열 힙을 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-144">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b4472-145">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4472-145">Requirements</span></span>  
 <span data-ttu-id="b4472-146">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b4472-146">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4472-147">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b4472-147">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4472-148">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b4472-148">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b4472-149">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4472-149">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4472-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4472-150">See Also</span></span>  
 [<span data-ttu-id="b4472-151">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4472-151">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="b4472-152">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4472-152">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
