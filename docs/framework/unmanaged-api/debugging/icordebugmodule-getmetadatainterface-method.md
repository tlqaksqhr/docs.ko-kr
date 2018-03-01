---
title: "ICorDebugModule::GetMetaDataInterface 메서드"
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
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d374b83155ccc8511c6e3217a8a49819d81a7d48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="afc42-102">ICorDebugModule::GetMetaDataInterface 메서드</span><span class="sxs-lookup"><span data-stu-id="afc42-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="afc42-103">모듈에 대 한 메타 데이터를 검사 하는 데 사용할 수 있는 메타 데이터 인터페이스 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="afc42-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afc42-104">구문</span><span class="sxs-lookup"><span data-stu-id="afc42-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="afc42-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="afc42-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="afc42-106">[in] 메타 데이터 인터페이스를 지정 하는 참조 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="afc42-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="afc42-107">[out] 주소에 대 한 포인터는 `T:IUnknown` 개체 중 하나를 [메타 데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="afc42-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afc42-108">설명</span><span class="sxs-lookup"><span data-stu-id="afc42-108">Remarks</span></span>  
 <span data-ttu-id="afc42-109">디버거에서 사용할 수는 `GetMetaDataInterface` 메서드를 해당 모듈을 편집 하기 위해 수행 해야 하는 모듈에 대 한 원래 메타 데이터의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="afc42-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="afc42-110">디버거 호출 `GetMetaDataInterface` 가져오려는 [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) 인터페이스 개체는 모듈에 대 한 호출 [imetadataemit:: Savetomemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) 메모리에 모듈의 메타 데이터의 복사본을 저장 하려면.</span><span class="sxs-lookup"><span data-stu-id="afc42-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afc42-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="afc42-111">Requirements</span></span>  
 <span data-ttu-id="afc42-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="afc42-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afc42-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="afc42-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afc42-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afc42-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afc42-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afc42-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afc42-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="afc42-116">See Also</span></span>  
 [<span data-ttu-id="afc42-117">메타데이터</span><span class="sxs-lookup"><span data-stu-id="afc42-117">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
