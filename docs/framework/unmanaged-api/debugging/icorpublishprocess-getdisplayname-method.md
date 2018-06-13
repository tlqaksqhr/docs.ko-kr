---
title: ICorPublishProcess::GetDisplayName 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetDisplayName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 815f2e2f695837c973210a21ab3631ef307c23d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423639"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="92ed6-102">ICorPublishProcess::GetDisplayName 메서드</span><span class="sxs-lookup"><span data-stu-id="92ed6-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="92ed6-103">이 참조 하는 프로세스에 대 한 실행 파일의 전체 경로 가져옵니다 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92ed6-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92ed6-104">구문</span><span class="sxs-lookup"><span data-stu-id="92ed6-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92ed6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="92ed6-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="92ed6-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="92ed6-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="92ed6-107">[out] 반환 하는 와이드 문자 수는 `szName` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="92ed6-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="92ed6-108">[out] 실행 파일의 전체 경로 포함 하 여 이름을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="92ed6-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="92ed6-109">이름은은 null로 끝나는입니다.</span><span class="sxs-lookup"><span data-stu-id="92ed6-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92ed6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="92ed6-110">Requirements</span></span>  
 <span data-ttu-id="92ed6-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92ed6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92ed6-112">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="92ed6-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="92ed6-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92ed6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92ed6-114">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92ed6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ed6-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92ed6-115">See Also</span></span>  
 [<span data-ttu-id="92ed6-116">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92ed6-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
