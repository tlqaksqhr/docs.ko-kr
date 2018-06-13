---
title: ICorPublishProcessEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19a10a527c37d93d00bec799fdaa12bb0ad3fdbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423873"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="70b6a-102">ICorPublishProcessEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="70b6a-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="70b6a-103">현재 커서 위치부터 시작 하 고 컬렉션에서 지정 된 프로세스 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="70b6a-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70b6a-104">구문</span><span class="sxs-lookup"><span data-stu-id="70b6a-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="70b6a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="70b6a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="70b6a-106">[in] 검색 프로세스의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70b6a-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="70b6a-107">[out] 검색에 대 한 포인터의 배열에 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) 각각 프로세스를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="70b6a-107">[out] A pointer to the array of retrieved [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="70b6a-108">[out] 실제로 반환 된 프로세스의 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="70b6a-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="70b6a-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="70b6a-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70b6a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70b6a-110">Requirements</span></span>  
 <span data-ttu-id="70b6a-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70b6a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70b6a-112">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="70b6a-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="70b6a-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70b6a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70b6a-114">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70b6a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70b6a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70b6a-115">See Also</span></span>  
 [<span data-ttu-id="70b6a-116">ICorPublishProcessEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70b6a-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)
