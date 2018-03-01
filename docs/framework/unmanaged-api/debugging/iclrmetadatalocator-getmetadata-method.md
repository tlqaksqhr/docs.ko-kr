---
title: "ICLRMetadataLocator::GetMetadata 메서드"
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
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8758a96464d1465d92fb17314f1e36ab8d9169c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a><span data-ttu-id="19206-102">ICLRMetadataLocator::GetMetadata 메서드</span><span class="sxs-lookup"><span data-stu-id="19206-102">ICLRMetadataLocator::GetMetadata Method</span></span>
<span data-ttu-id="19206-103">이미지의 메타 데이터를 검색 하는 공용 언어 런타임 (CLR) 데이터 액세스 서비스에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19206-103">Called by the common language runtime (CLR) data access services to retrieve the metadata of an image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19206-104">구문</span><span class="sxs-lookup"><span data-stu-id="19206-104">Syntax</span></span>  
  
```  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19206-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="19206-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="19206-106">[in] 이미지 파일의 경로 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="19206-106">[in] A string that specifies the path of the image file.</span></span>  
  
 `imageTimestamp`  
 <span data-ttu-id="19206-107">[in] 이미지 파일의 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="19206-107">[in] The time stamp of the image file.</span></span>  
  
 `imageSize`  
 <span data-ttu-id="19206-108">[in] 이미지 파일의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="19206-108">[in] The size of the image file.</span></span>  
  
 `mvid`  
 <span data-ttu-id="19206-109">[in] 이미지의 전역 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="19206-109">[in] The globally unique identifier of the image.</span></span>  
  
 `mdRva`  
 <span data-ttu-id="19206-110">[in] 상대 가상 주소 (RVA) 메타 데이터의 합니다.</span><span class="sxs-lookup"><span data-stu-id="19206-110">[in] The relative virtual address (RVA) of the metadata.</span></span> <span data-ttu-id="19206-111">주소는 이미지 기준 주소에 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="19206-111">The address is relative to the image base address.</span></span>  
  
 `flags`  
 <span data-ttu-id="19206-112">[in] 나중에 사용할 수는 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19206-112">[in] Reserved for future use.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="19206-113">[in] 메타 데이터를 배치할 수 있는 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="19206-113">[in] The size of the buffer in which to place the metadata.</span></span>  
  
 `buffer`  
 <span data-ttu-id="19206-114">[out] 메타 데이터를 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="19206-114">[out] The buffer in which to place the metadata.</span></span>  
  
 `dataSize`  
 <span data-ttu-id="19206-115">[out] 반환 되는 메타 데이터의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="19206-115">[out] The size of the metadata that is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19206-116">설명</span><span class="sxs-lookup"><span data-stu-id="19206-116">Remarks</span></span>  
 <span data-ttu-id="19206-117">이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="19206-117">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19206-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19206-118">Requirements</span></span>  
 <span data-ttu-id="19206-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="19206-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19206-120">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="19206-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="19206-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19206-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19206-122">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19206-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19206-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19206-123">See Also</span></span>  
 [<span data-ttu-id="19206-124">ICLRMetadataLocator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19206-124">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)
