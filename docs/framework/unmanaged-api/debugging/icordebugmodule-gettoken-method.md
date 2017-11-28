---
title: "ICorDebugModule::GetToken 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetToken
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c06c4c8ac937864748cbac8872de9b3994db2464
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="55a9b-102">ICorDebugModule::GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="55a9b-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="55a9b-103">이 모듈에 대 한 테이블 항목에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="55a9b-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55a9b-104">구문</span><span class="sxs-lookup"><span data-stu-id="55a9b-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="55a9b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="55a9b-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="55a9b-106">[out] 에 대 한 포인터는 `mdModule` 모듈의 메타 데이터를 참조 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="55a9b-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55a9b-107">설명</span><span class="sxs-lookup"><span data-stu-id="55a9b-107">Remarks</span></span>  
 <span data-ttu-id="55a9b-108">토큰에 전달 될 수는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), 및 [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 메타 데이터 가져오기 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="55a9b-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55a9b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55a9b-109">Requirements</span></span>  
 <span data-ttu-id="55a9b-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="55a9b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55a9b-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55a9b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55a9b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55a9b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55a9b-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55a9b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55a9b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55a9b-114">See Also</span></span>  
 [<span data-ttu-id="55a9b-115">메타 데이터</span><span class="sxs-lookup"><span data-stu-id="55a9b-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
