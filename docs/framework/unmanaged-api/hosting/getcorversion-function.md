---
title: GetCORVersion 함수
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0e922273a7d4e5b98c1321992e5e89e01adb437
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431495"
---
# <a name="getcorversion-function"></a><span data-ttu-id="b0401-102">GetCORVersion 함수</span><span class="sxs-lookup"><span data-stu-id="b0401-102">GetCORVersion Function</span></span>
<span data-ttu-id="b0401-103">현재 프로세스에서 실행 중인 공용 언어 런타임 (CLR)의 버전 번호를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0401-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="b0401-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="b0401-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0401-105">구문</span><span class="sxs-lookup"><span data-stu-id="b0401-105">Syntax</span></span>  
  
```  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0401-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b0401-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="b0401-107">CLR에서 현재 프로세스에 로드 된 런타임 버전을 지정 하는 문자열을 반환 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b0401-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="b0401-108">반환 된 문자열은 동일한 형식 문자열에 전달 된 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), 예를 들어 "v1.0.1216"입니다.</span><span class="sxs-lookup"><span data-stu-id="b0401-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="b0401-109">런타임 프로세스에 아직 로드 되지 않았습니다 고 함수는 컴퓨터에 설치 된 런타임의 최신 버전에 대 한 적절 한 디렉터리 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0401-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="b0401-110">문자 수 (`WCHAR`s)에 저장할 수 있는 `pbuffer`합니다.</span><span class="sxs-lookup"><span data-stu-id="b0401-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="b0401-111">에 실제로 반환 된 문자 수에 대 한 포인터 `pbuffer`합니다.</span><span class="sxs-lookup"><span data-stu-id="b0401-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="b0401-112">경우 `pbuffer` 가 null 포인터 이면 런타임은 E_POINTER를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0401-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="b0401-113">문자 수가 큰 경우의 길이 `pbuffer` , 런타임은 ERROR_INSUFFICIENT_BUFFER를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0401-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0401-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b0401-114">Requirements</span></span>  
 <span data-ttu-id="b0401-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0401-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0401-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b0401-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b0401-117">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b0401-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0401-118">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0401-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0401-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0401-119">See Also</span></span>  
 [<span data-ttu-id="b0401-120">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="b0401-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
