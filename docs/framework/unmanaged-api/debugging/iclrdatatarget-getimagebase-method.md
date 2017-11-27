---
title: "ICLRDataTarget::GetImageBase 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetImageBase
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1d397995266d6063164510a4b563ba94f7f54950
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="8ced4-102">ICLRDataTarget::GetImageBase 메서드</span><span class="sxs-lookup"><span data-stu-id="8ced4-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="8ced4-103">지정된 된 이미지의 기본 메모리 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8ced4-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ced4-104">구문</span><span class="sxs-lookup"><span data-stu-id="8ced4-104">Syntax</span></span>  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8ced4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ced4-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="8ced4-106">[in] 해당 경로 포함 하는 이미지의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8ced4-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="8ced4-107">[out] 이미지의 기준 주소를 저장 하는 CLRDATA_ADDRESS에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8ced4-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ced4-108">설명</span><span class="sxs-lookup"><span data-stu-id="8ced4-108">Remarks</span></span>  
 <span data-ttu-id="8ced4-109">이미지 파일 이름 수도 있습니다는 경로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ced4-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="8ced4-110">경로 지정 하는 경우 일치 하는 대해서는 전체 경로입니다. 그렇지 않으면 일치 하는 파일 이름에 대해서만 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ced4-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ced4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ced4-111">Requirements</span></span>  
 <span data-ttu-id="8ced4-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ced4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ced4-113">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="8ced4-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8ced4-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ced4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ced4-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ced4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ced4-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ced4-116">See Also</span></span>  
 [<span data-ttu-id="8ced4-117">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ced4-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
