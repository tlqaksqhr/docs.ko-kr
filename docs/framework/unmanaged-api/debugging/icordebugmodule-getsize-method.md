---
title: ICorDebugModule::GetSize 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0d741bda5426dee1292df0e6fd9107cc2f44c8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413321"
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="ad18c-102">ICorDebugModule::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="ad18c-102">ICorDebugModule::GetSize Method</span></span>
<span data-ttu-id="ad18c-103">모듈의 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ad18c-103">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad18c-104">구문</span><span class="sxs-lookup"><span data-stu-id="ad18c-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad18c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad18c-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="ad18c-106">[out] 크기 (바이트)에서 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="ad18c-106">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="ad18c-107">모듈 네이티브 이미지 생성기 (NGen.exe)에서 생성 된, 경우 모듈의 크기는 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad18c-107">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad18c-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad18c-108">Requirements</span></span>  
 <span data-ttu-id="ad18c-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ad18c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad18c-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad18c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad18c-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad18c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad18c-112">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad18c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
