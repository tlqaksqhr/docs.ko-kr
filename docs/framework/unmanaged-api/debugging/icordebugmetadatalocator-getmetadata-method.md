---
title: "ICorDebugMetaDataLocator::GetMetaData 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMetaDataLocator.GetMetaData
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMetaDataLocator::GetMetaData
helpviewer_keywords:
- ICorDebugMetaDataLocator::GetMetaData method [.NET Framework debugging]
- GetMetaData method, ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: f9b0ff22-54db-45eb-9cc3-508000a3141d
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42c0548a626d43592184efa92619e74446058d58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmetadatalocatorgetmetadata-method"></a><span data-ttu-id="d27f4-102">ICorDebugMetaDataLocator::GetMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="d27f4-102">ICorDebugMetaDataLocator::GetMetaData Method</span></span>
<span data-ttu-id="d27f4-103">디버거가 요청한 작업을 완료하는 데 필요한 메타데이터가 포함된 모듈의 전체 경로를 반환하도록 디버거에 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-103">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d27f4-104">구문</span><span class="sxs-lookup"><span data-stu-id="d27f4-104">Syntax</span></span>  
  
```  
HRESULT GetMetaData(  
      [in] LPCWSTR wszImagePath,  
      [in] DWORD   dwImageTimeStamp,  
      [in] DWORD   dwImageSize,  
      [in] ULONG32 cchPathBuffer,  
      [out] ULONG32 * pcchPathBuffer,  
      [out, size_is(cchPathBuffer), length_is(*pcchPathBuffer)]  
               WCHAR wszPathBuffer[]  
      );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d27f4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d27f4-105">Parameters</span></span>  
 `wszImagePath`  
 <span data-ttu-id="d27f4-106">[in] 파일의 전체 경로를 나타내는 null로 종료된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-106">[in] A null-terminated string that represents the full path to the file.</span></span> <span data-ttu-id="d27f4-107">전체 경로 사용할 수 없는 경우 이름 및 파일의 확장명 (*filename*. *확장*).</span><span class="sxs-lookup"><span data-stu-id="d27f4-107">If the full path is not available, the name and extension of the file (*filename*.*extension*).</span></span>  
  
 `dwImageTimeStamp`  
 <span data-ttu-id="d27f4-108">[in] 이미지 PE 파일 헤더의 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-108">[in] The time stamp from the image's PE file headers.</span></span> <span data-ttu-id="d27f4-109">이 매개 변수 기호 서버에 사용 될 수 있습니다 ([SymSrv](http://msdn.microsoft.com/library/cc266470.aspx)) 조회 합니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-109">This parameter can potentially be used for a symbol server ([SymSrv](http://msdn.microsoft.com/library/cc266470.aspx)) lookup.</span></span>  
  
 `dwImageSize`  
 <span data-ttu-id="d27f4-110">[in] PE 파일 헤더의 이미지 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-110">[in] The image size from PE file headers.</span></span> <span data-ttu-id="d27f4-111">이 매개 변수는 SymSrv 조회에 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-111">This parameter can potentially be used for a SymSrv lookup.</span></span>  
  
 `cchPathBuffer`  
 <span data-ttu-id="d27f4-112">[in] `wszPathBuffer`의 문자 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-112">[in] The character count in `wszPathBuffer`.</span></span>  
  
 `pcchPathBuffer`  
 <span data-ttu-id="d27f4-113">[out] `wszPathBuffer`에 기록된 `WCHAR` 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-113">[out] The count of `WCHAR`s written to `wszPathBuffer`.</span></span>  
  
 <span data-ttu-id="d27f4-114">메서드가 E_NOT_SUFFICIENT_BUFFER를 반환할 경우 경로를 저장하는 데 필요한 `WCHAR` 개수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-114">If the method returns E_NOT_SUFFICIENT_BUFFER, contains the count of `WCHAR`s needed to store the path.</span></span>  
  
 `wszPathBuffer`  
 <span data-ttu-id="d27f4-115">[out] 디버거가 요청된 메타데이터를 포함한 파일의 전체 경로를 복사할 대상 버퍼에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-115">[out] Pointer to a buffer into which the debugger will copy the full path of the file that contains the requested metadata.</span></span>  
  
 <span data-ttu-id="d27f4-116">`ofReadOnly` 에서 플래그는 [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) 열거형이이 파일의 메타 데이터에 대 한 읽기 전용 액세스를 요청 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-116">The `ofReadOnly` flag from the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration is used to request read-only access to the metadata in this file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d27f4-117">반환 값</span><span class="sxs-lookup"><span data-stu-id="d27f4-117">Return Value</span></span>  
 <span data-ttu-id="d27f4-118">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-118">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span> <span data-ttu-id="d27f4-119">모든 기타 오류 HRESULT는 파일을 검색할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-119">All other failure HRESULTs indicate that the file is not retrievable.</span></span>  
  
|<span data-ttu-id="d27f4-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d27f4-120">HRESULT</span></span>|<span data-ttu-id="d27f4-121">설명</span><span class="sxs-lookup"><span data-stu-id="d27f4-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d27f4-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="d27f4-122">S_OK</span></span>|<span data-ttu-id="d27f4-123">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-123">The method completed successfully.</span></span> <span data-ttu-id="d27f4-124">`wszPathBuffer`는 파일의 전체 경로를 포함하고 null로 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-124">`wszPathBuffer` contains the full path to the file and is null-terminated.</span></span>|  
|<span data-ttu-id="d27f4-125">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="d27f4-125">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="d27f4-126">`wszPathBuffer`의 현재 크기는 전체 경로를 포함하기에 충분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-126">The current size of `wszPathBuffer` is not sufficient to hold the full path.</span></span> <span data-ttu-id="d27f4-127">이 경우 `pcchPathBuffer`는 종료 null 문자를 비롯하여 필요한 `WCHAR` 개수를 포함하고, `GetMetaData`는 요청된 버퍼 크기와 함께 두 번째로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-127">In this case, `pcchPathBuffer` contains the needed count of `WCHAR`s, including the terminating null character, and `GetMetaData` is called a second time with the requested buffer size.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d27f4-128">설명</span><span class="sxs-lookup"><span data-stu-id="d27f4-128">Remarks</span></span>  
 <span data-ttu-id="d27f4-129">`wszImagePath`에 덤프부터 모듈의 전체 경로가 포함되면 이 매개 변수는 덤프가 수집된 컴퓨터의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-129">If `wszImagePath` contains a full path for a module from a dump, it specifies the path from the computer where the dump was collected.</span></span> <span data-ttu-id="d27f4-130">이 위치에 파일이 있을 수 없거나 같은 이름을 가진 잘못된 파일이 경로에 저장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-130">The file may not exist at this location, or an incorrect file with the same name may be stored on the path.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d27f4-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d27f4-131">Requirements</span></span>  
 <span data-ttu-id="d27f4-132">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d27f4-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d27f4-133">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d27f4-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d27f4-134">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d27f4-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d27f4-135">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d27f4-135">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d27f4-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d27f4-136">See Also</span></span>  
 [<span data-ttu-id="d27f4-137">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d27f4-137">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="d27f4-138">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d27f4-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="d27f4-139">디버깅</span><span class="sxs-lookup"><span data-stu-id="d27f4-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
