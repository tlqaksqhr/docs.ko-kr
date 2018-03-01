---
title: "IMetaDataEmit::DefinePinvokeMap 메서드"
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
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bd42c54990fd8aad1b9e6325d59ac7ccc5d6a3fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="f2b06-102">IMetaDataEmit::DefinePinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="f2b06-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="f2b06-103">지정한 토큰이 참조 하는 메서드에 PInvoke 시그니처의 기능을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b06-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2b06-104">구문</span><span class="sxs-lookup"><span data-stu-id="f2b06-104">Syntax</span></span>  
  
```  
HRESULT DefinePinvokeMap (   
    [in]  mdToken            tk,   
    [in]  DWORD              dwMappingFlags,   
    [in]  LPCWSTR            szImportName,   
    [in]  mdModuleRef        mrImportDLL   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2b06-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f2b06-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f2b06-106">[in] 대상 방법에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f2b06-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="f2b06-107">[in] PInvoke 하는 매핑을 수행 하는 데 사용 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="f2b06-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="f2b06-108">[in] 대상의 이름 관리 되지 않는 DLL에서 메서드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2b06-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="f2b06-109">[in] 대상에 대 한 토큰 네이티브 DLL입니다.</span><span class="sxs-lookup"><span data-stu-id="f2b06-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2b06-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2b06-110">Requirements</span></span>  
 <span data-ttu-id="f2b06-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b06-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2b06-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f2b06-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2b06-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="f2b06-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2b06-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2b06-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2b06-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2b06-115">See Also</span></span>  
 [<span data-ttu-id="f2b06-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2b06-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="f2b06-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2b06-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
