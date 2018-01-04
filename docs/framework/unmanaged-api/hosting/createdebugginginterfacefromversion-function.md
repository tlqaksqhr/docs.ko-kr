---
title: "CreateDebuggingInterfaceFromVersion 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CreateDebuggingInterfaceFromVersion
helpviewer_keywords: CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b3f269f5b1758481995d6064e7137e62bff4a868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="c18db-102">CreateDebuggingInterfaceFromVersion 함수</span><span class="sxs-lookup"><span data-stu-id="c18db-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="c18db-103">만듭니다는 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 지정된 된 버전 정보에 따라 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c18db-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="c18db-104">이 함수에서 사용 되지 않는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="c18db-104">This function is obsolete in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="c18db-105">대신, 사용 공용 언어 런타임 (CLR) 2.0에 대 한 인터페이스를 가져올 수는 [iclrruntimeinfo:: Getinterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) 메서드 CLSID_CLRDebuggingLegacy 클래스 식별자 및 IID_ICorDebug 인터페이스 식별자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c18db-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="c18db-106">CLR 4에 대 한 인터페이스를 가져오거나 이상 버전에서는 호출 하 여 [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) 함수 및 클래스 식별자 CLSID_CLRDebugging IID_ICLRDebugging 인터페이스 식별자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c18db-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c18db-107">구문</span><span class="sxs-lookup"><span data-stu-id="c18db-107">Syntax</span></span>  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c18db-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c18db-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="c18db-109">[in] 버전의 `ICorDebug` 디버거를 통해 사용할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="c18db-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="c18db-110">참조는 [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) 유효한 값에 대 한 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="c18db-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="c18db-111">[in] 응용 프로그램이 나 프로세스를 디버깅할와 연결 된 공용 언어 런타임 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="c18db-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="c18db-112">참조는 [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) 또는 [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) 이 값을 검색에 대 한 내용은 메서드.</span><span class="sxs-lookup"><span data-stu-id="c18db-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="c18db-113">[out] 에 대 한 포인터를 받는 위치는 `ICorDebug` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c18db-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c18db-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="c18db-114">Return Value</span></span>  
 <span data-ttu-id="c18db-115">이 메서드는 다음 값 외에도 WinError.h 파일에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c18db-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="c18db-116">반환 코드</span><span class="sxs-lookup"><span data-stu-id="c18db-116">Return code</span></span>|<span data-ttu-id="c18db-117">설명</span><span class="sxs-lookup"><span data-stu-id="c18db-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c18db-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="c18db-118">S_OK</span></span>|<span data-ttu-id="c18db-119">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c18db-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="c18db-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c18db-120">E_INVALIDARG</span></span>|<span data-ttu-id="c18db-121">`szDebuggeeVersion`또는 `ppCordb` null 또는 버전 문자열이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c18db-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c18db-122">설명</span><span class="sxs-lookup"><span data-stu-id="c18db-122">Remarks</span></span>  
 <span data-ttu-id="c18db-123">`szDebuggeeVersion` 매개 변수 MSCorDbi.dll의 해당 버전에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="c18db-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c18db-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c18db-124">Requirements</span></span>  
 <span data-ttu-id="c18db-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c18db-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c18db-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c18db-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c18db-127">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c18db-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c18db-128">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c18db-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c18db-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c18db-129">See Also</span></span>  
 [<span data-ttu-id="c18db-130">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="c18db-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
