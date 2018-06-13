---
title: ICorDebugClass::GetToken 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetToken
helpviewer_keywords:
- GetToken method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetToken method [.NET Framework debugging]
ms.assetid: ee5c848a-eac4-4462-b07a-07ccd76a75df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f67bd427c83385b2433b9f2e97f0b54e3b29a76f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401065"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="74848-102">ICorDebugClass::GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="74848-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="74848-103">가져옵니다는 `TypeDef` 이 클래스의 정의 참조 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="74848-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74848-104">구문</span><span class="sxs-lookup"><span data-stu-id="74848-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74848-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="74848-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="74848-106">[out] 에 대 한 포인터는 `mdTypeDef` 이 클래스의 정의 참조 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="74848-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74848-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="74848-107">Requirements</span></span>  
 <span data-ttu-id="74848-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="74848-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74848-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74848-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74848-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74848-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74848-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74848-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74848-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74848-112">See Also</span></span>  
 [<span data-ttu-id="74848-113">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="74848-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
