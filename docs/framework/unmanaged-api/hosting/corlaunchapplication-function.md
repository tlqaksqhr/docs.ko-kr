---
title: "CorLaunchApplication 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type: COM
f1_keywords: CorLaunchApplication
helpviewer_keywords: CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d6246ab600438e2237dcbe531d9d7641c0897d81
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="6f916-102">CorLaunchApplication 함수</span><span class="sxs-lookup"><span data-stu-id="6f916-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="6f916-103">지정 된 매니페스트 및 기타 응용 프로그램 데이터를 사용 하 여 지정 된 네트워크 경로에 있는 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f916-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="6f916-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="6f916-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f916-105">구문</span><span class="sxs-lookup"><span data-stu-id="6f916-105">Syntax</span></span>  
  
```  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6f916-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6f916-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="6f916-107">[in] 값은 [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) 응용 프로그램을 시작 하는 호스트의 형식을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="6f916-107">[in] A value of the [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="6f916-108">[in] 실행 하는 응용 프로그램의 전체 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6f916-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="6f916-109">[in] 응용 프로그램에 대 한 매니페스트 경로 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f916-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="6f916-110">[in] 경로 실행 하는 응용 프로그램에 대 한 매니페스트를 지정 하며 각 문자열의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6f916-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="6f916-111">[in] 실행 하는 응용 프로그램에 대 한 정품 인증 데이터 항목의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6f916-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="6f916-112">[in] 각각이 실행 하는 응용 프로그램에 대 한 정품 인증 데이터 항목이 문자열의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6f916-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="6f916-113">[out] 응용 프로그램을 로드 하는 프로세스에 대 한 정보에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f916-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f916-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f916-114">Requirements</span></span>  
 <span data-ttu-id="6f916-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6f916-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f916-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6f916-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f916-117">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6f916-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f916-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f916-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f916-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f916-119">See Also</span></span>  
 [<span data-ttu-id="6f916-120">사용 되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="6f916-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
