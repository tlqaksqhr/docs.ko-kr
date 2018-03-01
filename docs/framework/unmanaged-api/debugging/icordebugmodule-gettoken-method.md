---
title: "ICorDebugModule::GetToken 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugModule.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 651612b07a69f0cbcc9c818fe7627bf496f6d68e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="2c5a2-102">ICorDebugModule::GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="2c5a2-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="2c5a2-103">이 모듈에 대 한 테이블 항목에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2c5a2-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c5a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="2c5a2-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c5a2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c5a2-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="2c5a2-106">[out] 에 대 한 포인터는 `mdModule` 모듈의 메타 데이터를 참조 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2c5a2-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c5a2-107">설명</span><span class="sxs-lookup"><span data-stu-id="2c5a2-107">Remarks</span></span>  
 <span data-ttu-id="2c5a2-108">토큰에 전달 될 수는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), 및 [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 메타 데이터 가져오기 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2c5a2-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c5a2-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c5a2-109">Requirements</span></span>  
 <span data-ttu-id="2c5a2-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c5a2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c5a2-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c5a2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c5a2-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c5a2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c5a2-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c5a2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c5a2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c5a2-114">See Also</span></span>  
 [<span data-ttu-id="2c5a2-115">메타데이터</span><span class="sxs-lookup"><span data-stu-id="2c5a2-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
