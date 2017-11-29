---
title: "IMetaDataTables::GetTableInfo 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetTableInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0f4ccd9bbd1c7caa9bbeb548176d834dc8844213
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="9c6c3-102">IMetaDataTables::GetTableInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="9c6c3-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="9c6c3-103">이름, 행 크기, 행의 수, 열 개수 및 지정된 된 테이블의 키 열 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c6c3-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c6c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="9c6c3-104">Syntax</span></span>  
  
```  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c6c3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9c6c3-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="9c6c3-106">[in] 테이블의 식별자 해당 속성을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c6c3-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="9c6c3-107">[out] 테이블 행의 바이트 단위로 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9c6c3-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="9c6c3-108">[out] 테이블의 행 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9c6c3-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="9c6c3-109">[out] 테이블의 열 개수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9c6c3-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="9c6c3-110">[out] 키 열 또는 테이블에 키 열이 없는 경우-1의 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9c6c3-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="9c6c3-111">[out] 테이블 이름에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9c6c3-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c6c3-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9c6c3-112">Requirements</span></span>  
 <span data-ttu-id="9c6c3-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9c6c3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c6c3-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9c6c3-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9c6c3-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="9c6c3-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9c6c3-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c6c3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c6c3-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c6c3-117">See Also</span></span>  
 [<span data-ttu-id="9c6c3-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c6c3-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="9c6c3-119">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c6c3-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
