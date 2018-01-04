---
title: "LoadTypeLibWithResolver 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoadTypeLibWithResolver
api_location: TlbRef.dll
api_type: DLLExport
f1_keywords: LoadTypeLibWithResolver
helpviewer_keywords: LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f069d09f25575c39db097024384ad1bf14eaaf02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="88dca-102">LoadTypeLibWithResolver 함수</span><span class="sxs-lookup"><span data-stu-id="88dca-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="88dca-103">형식 라이브러리를 로드 하 고 사용 하 여 제공 된 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) 내부적으로 참조 된 형식 라이브러리를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-103">Loads a type library and uses the supplied [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88dca-104">구문</span><span class="sxs-lookup"><span data-stu-id="88dca-104">Syntax</span></span>  
  
```  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="88dca-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="88dca-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="88dca-106">[in] 형식 라이브러리의 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="88dca-107">[in] A [REGKIND 열거형](https://msdn.microsoft.com/library/windows/desktop/ms221159.aspx) 형식 라이브러리를 등록 하는 방법을 제어 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-107">[in] A [REGKIND enumeration](https://msdn.microsoft.com/library/windows/desktop/ms221159.aspx) flag that controls how the type library is registered.</span></span> <span data-ttu-id="88dca-108">가능한 값은 같습니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-108">Its possible values are:</span></span>  
  
-   <span data-ttu-id="88dca-109">`REGKIND_DEFAULT`: 기본 등록 동작을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
-   <span data-ttu-id="88dca-110">`REGKIND_REGISTER`:이 형식 라이브러리를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
-   <span data-ttu-id="88dca-111">`REGKIND_NONE`:이 형식 라이브러리를 등록 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="88dca-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="88dca-112">[in] 구현에 대 한 포인터는 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="88dca-113">[out] 로드 되는 형식 라이브러리에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88dca-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="88dca-114">Return Value</span></span>  
 <span data-ttu-id="88dca-115">다음 표에 나열 된 HRESULT 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="88dca-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="88dca-116">Return value</span></span>|<span data-ttu-id="88dca-117">의미</span><span class="sxs-lookup"><span data-stu-id="88dca-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="88dca-118">명령 실행 성공</span><span class="sxs-lookup"><span data-stu-id="88dca-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="88dca-119">메모리가 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="88dca-120">포인터 중 하나 이상이 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="88dca-121">인수 중 하나 이상이 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="88dca-122">함수는 파일에 쓸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="88dca-123">시스템 등록 데이터베이스를 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="88dca-124">형식 라이브러리를 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="88dca-125">형식 라이브러리 또는 DLL을 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88dca-126">설명</span><span class="sxs-lookup"><span data-stu-id="88dca-126">Remarks</span></span>  
 <span data-ttu-id="88dca-127">[Tlbexp.exe (형식 라이브러리 내보내기)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) 호출은 `LoadTypeLibWithResolver` 어셈블리를 형식 라이브러리로 변환 하는 동안 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-127">The [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="88dca-128">이 함수는 레지스트리에 최소한의 권한이 있는 지정 된 형식 라이브러리를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="88dca-129">함수는 해당 로드 고 부모 형식 라이브러리에 추가 해야 하며 각 내부적으로 참조 된 형식 라이브러리에 대 한 형식 라이브러리를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="88dca-130">참조 된 형식 라이브러리를 로드할 수 있는 전에 해당 참조 파일 경로가 전체 파일 경로 확인 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="88dca-131">통해 이렇게는 [ResolveTypeLib 메서드](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) 에서 제공 하는 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)에 전달 되는 `pTlbResolver` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-131">This is accomplished through the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="88dca-132">참조 된 형식 라이브러리의 전체 파일 경로 알고 있을 때의 `LoadTypeLibWithResolver` 함수 로드 하 고 결합 된 마스터 형식 라이브러리를 만들 부모 형식 라이브러리에 참조 된 형식 라이브러리를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="88dca-133">마스터 확인 된 형식 라이브러리에 대 한 참조를 반환 함수를 확인 하 고 모든 내부적으로 참조 된 형식 라이브러리를 로드 한 후의 `pptlib` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="88dca-134">`LoadTypeLibWithResolver` 함수 일반적으로 호출 됩니다는 [Tlbexp.exe (형식 라이브러리 내보내기)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)를 제공 하는 자체 내부 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) 구현에는 `pTlbResolver` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="88dca-135">호출 하는 경우 `LoadTypeLibWithResolver` 를 직접 입력 해야 자신의 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88dca-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="88dca-136">Requirements</span></span>  
 <span data-ttu-id="88dca-137">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88dca-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88dca-138">**헤더:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="88dca-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="88dca-139">**라이브러리:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="88dca-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="88dca-140">**.NET framework 버전:** 3.5, 3.0, 2.0</span><span class="sxs-lookup"><span data-stu-id="88dca-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88dca-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88dca-141">See Also</span></span>  
 [<span data-ttu-id="88dca-142">Tlbexp 도우미 함수</span><span class="sxs-lookup"><span data-stu-id="88dca-142">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 <span data-ttu-id="88dca-143">[LoadTypeLibEx 함수](https://msdn.microsoft.com/library/windows/desktop/ms221249\(v=vs.85\).aspx)</span><span class="sxs-lookup"><span data-stu-id="88dca-143">[LoadTypeLibEx Function](https://msdn.microsoft.com/library/windows/desktop/ms221249\(v=vs.85\).aspx)</span></span>
