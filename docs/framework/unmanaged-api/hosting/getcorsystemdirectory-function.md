---
title: "GetCORSystemDirectory 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetCORSystemDirectory
helpviewer_keywords: GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02b695ac7f75dd38da8cd06e1444af4ae425ebd2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="a0f6e-102">GetCORSystemDirectory 함수</span><span class="sxs-lookup"><span data-stu-id="a0f6e-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="a0f6e-103">프로세스에 로드 하는 공용 언어 런타임 (CLR)의 설치 디렉터리를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0f6e-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="a0f6e-104">설치 디렉터리는 정규화 된 예를 들어 "c:\windows\microsoft.net\framework\v1.0.3705"입니다.</span><span class="sxs-lookup"><span data-stu-id="a0f6e-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="a0f6e-105">이 함수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0f6e-105">This function is deprecated.</span></span> <span data-ttu-id="a0f6e-106">으로 인해 교체 되는 [iclrruntimeinfo:: Getruntimedirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) 에 제공 된 메서드는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="a0f6e-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0f6e-107">구문</span><span class="sxs-lookup"><span data-stu-id="a0f6e-107">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0f6e-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a0f6e-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="a0f6e-109">[out] 런타임 프로세스에 로드 하는 런타임 설치 디렉터리의 정규화 된 이름이 포함 된 문자열을 반환 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="a0f6e-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="a0f6e-110">런타임 프로세스에 아직 로드 되지 않았습니다 고 함수는 컴퓨터에 설치 된 런타임의 최신 버전에 대 한 적절 한 디렉터리 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0f6e-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="a0f6e-111">[in] 를 바이트 단위로 크기의 `pbuffer`합니다.</span><span class="sxs-lookup"><span data-stu-id="a0f6e-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="a0f6e-112">[out] 반환 된 문자 수가 `pbuffer`합니다.</span><span class="sxs-lookup"><span data-stu-id="a0f6e-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0f6e-113">설명</span><span class="sxs-lookup"><span data-stu-id="a0f6e-113">Remarks</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a0f6e-114">Clr 버전 4를 실행 중인 프로세스에서이 함수를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="a0f6e-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="a0f6e-115">이전 버전의 CLR은 컴퓨터에 설치,이 함수는 해당 버전에 대 한 설치 디렉터리를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0f6e-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0f6e-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0f6e-116">Requirements</span></span>  
 <span data-ttu-id="a0f6e-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a0f6e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0f6e-118">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a0f6e-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0f6e-119">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0f6e-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0f6e-120">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0f6e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0f6e-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0f6e-121">See Also</span></span>  
 [<span data-ttu-id="a0f6e-122">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="a0f6e-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
