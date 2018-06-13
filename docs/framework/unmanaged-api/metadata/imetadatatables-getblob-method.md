---
title: IMetaDataTables::GetBlob 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 743fb1c77e2dd74487a7498be25ea23b4919032a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447301"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="0cff6-102">IMetaDataTables::GetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="0cff6-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="0cff6-103">이진 대형 개체 (BLOB)에 지정 된 열 인덱스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0cff6-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cff6-104">구문</span><span class="sxs-lookup"><span data-stu-id="0cff6-104">Syntax</span></span>  
  
```  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0cff6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0cff6-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="0cff6-106">[in] 메모리 주소를 가져올 `ppData`합니다.</span><span class="sxs-lookup"><span data-stu-id="0cff6-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="0cff6-107">[out] 를 바이트 단위로 크기에 대 한 포인터의 `ppData`합니다.</span><span class="sxs-lookup"><span data-stu-id="0cff6-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="0cff6-108">[out] 이진 데이터에 대 한 포인터에 대 한 포인터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cff6-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cff6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0cff6-109">Requirements</span></span>  
 <span data-ttu-id="0cff6-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0cff6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cff6-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0cff6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0cff6-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0cff6-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0cff6-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cff6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cff6-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0cff6-114">See Also</span></span>  
 [<span data-ttu-id="0cff6-115">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cff6-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="0cff6-116">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cff6-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
