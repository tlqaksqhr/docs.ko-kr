---
title: "ICorProfilerInfo::GetModuleMetaData 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetModuleMetaData
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ad52460bcd6eb320e970cd0ce2078f2e93df353
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a><span data-ttu-id="38952-102">ICorProfilerInfo::GetModuleMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="38952-102">ICorProfilerInfo::GetModuleMetaData Method</span></span>
<span data-ttu-id="38952-103">지정된 된 모듈에 매핑되는 메타 데이터 인터페이스 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38952-103">Gets a metadata interface instance that maps to the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38952-104">구문</span><span class="sxs-lookup"><span data-stu-id="38952-104">Syntax</span></span>  
  
```  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38952-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="38952-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="38952-106">[in] 인터페이스 인스턴스가 매핑할 수는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="38952-106">[in] The ID of the module to which the interface instance will be mapped.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="38952-107">[in] 값은 [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) 매니페스트 파일을 열에 대 한 모드를 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="38952-107">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration that specifies the mode for opening manifest files.</span></span> <span data-ttu-id="38952-108">만 `ofRead`, `ofWrite` 및 `ofNoTransform` 비트는 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="38952-108">Only the `ofRead`, `ofWrite` and `ofNoTransform` bits are valid.</span></span>  
  
 `riid`  
 <span data-ttu-id="38952-109">[in] 인스턴스가 검색 되는 메타 데이터 인터페이스의 ID (GUID)를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="38952-109">[in] The reference ID (GUID) of the metadata interface whose instance will be retrieved.</span></span> <span data-ttu-id="38952-110">참조 [메타 데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) 인터페이스 목록에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="38952-110">See [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) for a list of the interfaces.</span></span>  
  
 `ppOut`  
 <span data-ttu-id="38952-111">[out] 메타 데이터 인터페이스 인스턴스 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="38952-111">[out] A pointer to the address of the metadata interface instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38952-112">설명</span><span class="sxs-lookup"><span data-stu-id="38952-112">Remarks</span></span>  
 <span data-ttu-id="38952-113">메타 데이터 읽기/쓰기 모드에서 열 수를 요청할 수 있습니다 하지만 프로그램의 메타 데이터 실행 속도가 느려지게 이렇게 하면, 컴파일러에서 했을 때 메타 데이터 변경 때문에 최적화 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38952-113">You may ask for the metadata to be opened in read/write mode, but this will result in slower metadata execution of the program, because changes made to the metadata cannot be optimized as they were from the compiler.</span></span>  
  
 <span data-ttu-id="38952-114">일부 모듈 (예: 리소스 모듈)에 메타 데이터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38952-114">Some modules (such as resource modules) have no metadata.</span></span> <span data-ttu-id="38952-115">이 경우 `GetModuleMetaData` HRESULT 값에 null을 및 S_FALSE를 반환 합니다 *`ppOut`합니다.</span><span class="sxs-lookup"><span data-stu-id="38952-115">In those cases, `GetModuleMetaData` will return an HRESULT value of S_FALSE, and a null in *`ppOut`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38952-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38952-116">Requirements</span></span>  
 <span data-ttu-id="38952-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="38952-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38952-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="38952-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="38952-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38952-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38952-120">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38952-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38952-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38952-121">See Also</span></span>  
 [<span data-ttu-id="38952-122">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38952-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
