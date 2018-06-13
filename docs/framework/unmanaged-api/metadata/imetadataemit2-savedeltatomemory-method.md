---
title: IMetaDataEmit2::SaveDeltaToMemory 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 38d0d794cdedfd058b93785f4f444b4dd3196195
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444772"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="6530c-102">IMetaDataEmit2::SaveDeltaToMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="6530c-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="6530c-103">편집 하며 계속 하기는 현재 세션에서 변경 내용을 메모리에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6530c-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6530c-104">구문</span><span class="sxs-lookup"><span data-stu-id="6530c-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,   
    [in]  ULONG       cbData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6530c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6530c-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="6530c-106">[out] 메타 데이터 델타를 작성을 시작 하는 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6530c-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="6530c-107">[in] 변경 내용의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6530c-107">[in] The size of the changes.</span></span> <span data-ttu-id="6530c-108">사용 하 여 [imetadataemit2:: Getdeltasavesize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) 크기를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6530c-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6530c-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6530c-109">Requirements</span></span>  
 <span data-ttu-id="6530c-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6530c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6530c-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6530c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6530c-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="6530c-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6530c-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6530c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6530c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6530c-114">See Also</span></span>  
 [<span data-ttu-id="6530c-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6530c-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="6530c-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6530c-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
