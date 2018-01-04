---
title: "IMetaDataEmit2::SaveDelta 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.SaveDelta
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 31b06f014a4638fd7f947e8188730c583183f176
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="33013-102">IMetaDataEmit2::SaveDelta 메서드</span><span class="sxs-lookup"><span data-stu-id="33013-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="33013-103">편집 하며 계속 하기는 현재 세션에서 지정된 된 파일 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="33013-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33013-104">구문</span><span class="sxs-lookup"><span data-stu-id="33013-104">Syntax</span></span>  
  
```  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33013-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="33013-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="33013-106">[in] 변경 내용을 저장 하는 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="33013-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="33013-107">[in] 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33013-107">[in] Reserved.</span></span> <span data-ttu-id="33013-108">0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33013-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33013-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="33013-109">Requirements</span></span>  
 <span data-ttu-id="33013-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="33013-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33013-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="33013-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="33013-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="33013-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="33013-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33013-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33013-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33013-114">See Also</span></span>  
 [<span data-ttu-id="33013-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="33013-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="33013-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="33013-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
