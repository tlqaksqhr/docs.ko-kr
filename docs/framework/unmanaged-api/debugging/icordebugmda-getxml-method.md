---
title: "ICorDebugMDA::GetXML 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA.GetXML
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 387c9bf53dfbe146ccc1526404a1aed7386b2519
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="0be17-102">ICorDebugMDA::GetXML 메서드</span><span class="sxs-lookup"><span data-stu-id="0be17-102">ICorDebugMDA::GetXML Method</span></span>
<span data-ttu-id="0be17-103">연결 된 관리 디버깅 도우미 (MDA)으로 표시 된 전체 XML 스트림을 가져옵니다 [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0be17-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0be17-104">구문</span><span class="sxs-lookup"><span data-stu-id="0be17-104">Syntax</span></span>  
  
```  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0be17-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0be17-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="0be17-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0be17-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="0be17-107">[out] XML 스트림의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0be17-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="0be17-108">[out] XML 스트림을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0be17-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="0be17-109">배열이 비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0be17-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0be17-110">설명</span><span class="sxs-lookup"><span data-stu-id="0be17-110">Remarks</span></span>  
 <span data-ttu-id="0be17-111">`GetXML` 메서드는 연결 된 XML 스트림의 크기에 따라 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0be17-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0be17-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0be17-112">Requirements</span></span>  
 <span data-ttu-id="0be17-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0be17-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0be17-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0be17-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0be17-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0be17-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0be17-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0be17-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0be17-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0be17-117">See Also</span></span>  
 [<span data-ttu-id="0be17-118">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0be17-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="0be17-119">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="0be17-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
