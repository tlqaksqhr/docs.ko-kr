---
title: ICLRDataTarget::GetImageBase 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a79133b117f3a718dd84af6c2144a6098bc79f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407242"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="60a6c-102">ICLRDataTarget::GetImageBase 메서드</span><span class="sxs-lookup"><span data-stu-id="60a6c-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="60a6c-103">지정된 된 이미지의 기본 메모리 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="60a6c-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60a6c-104">구문</span><span class="sxs-lookup"><span data-stu-id="60a6c-104">Syntax</span></span>  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="60a6c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="60a6c-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="60a6c-106">[in] 해당 경로 포함 하는 이미지의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="60a6c-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="60a6c-107">[out] 이미지의 기준 주소를 저장 하는 CLRDATA_ADDRESS에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="60a6c-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60a6c-108">설명</span><span class="sxs-lookup"><span data-stu-id="60a6c-108">Remarks</span></span>  
 <span data-ttu-id="60a6c-109">이미지 파일 이름 수도 있습니다는 경로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="60a6c-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="60a6c-110">경로 지정 하는 경우 일치 하는 대해서는 전체 경로입니다. 그렇지 않으면 일치 하는 파일 이름에 대해서만 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60a6c-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60a6c-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60a6c-111">Requirements</span></span>  
 <span data-ttu-id="60a6c-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="60a6c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60a6c-113">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="60a6c-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="60a6c-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60a6c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60a6c-115">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60a6c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60a6c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60a6c-116">See Also</span></span>  
 [<span data-ttu-id="60a6c-117">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60a6c-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
