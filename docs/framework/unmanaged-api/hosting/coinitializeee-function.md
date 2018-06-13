---
title: CoInitializeEE 함수
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bbd25909e70826f8cd29076c1eb62a4da6779cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435403"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="5245f-102">CoInitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="5245f-102">CoInitializeEE Function</span></span>
<span data-ttu-id="5245f-103">공용 언어 런타임 실행 엔진 프로세스에 로드 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5245f-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="5245f-104">이 함수는 사용 되지 않습니다는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="5245f-104">This function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="5245f-105">사용 하 여 [iclrruntimehost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="5245f-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5245f-106">구문</span><span class="sxs-lookup"><span data-stu-id="5245f-106">Syntax</span></span>  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5245f-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5245f-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="5245f-108">[in] 중 하나는 [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) 열거형 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="5245f-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5245f-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="5245f-109">Return Value</span></span>  
 <span data-ttu-id="5245f-110">이 메서드는 다음 표에서 값과 Winerror.h에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5245f-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="5245f-111">반환 코드</span><span class="sxs-lookup"><span data-stu-id="5245f-111">Return code</span></span>|<span data-ttu-id="5245f-112">설명</span><span class="sxs-lookup"><span data-stu-id="5245f-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="5245f-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="5245f-113">S_OK</span></span>|<span data-ttu-id="5245f-114">실행 엔진을 로드 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5245f-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="5245f-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5245f-115">S_FALSE</span></span>|<span data-ttu-id="5245f-116">실행 엔진 이미 로드 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5245f-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="5245f-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5245f-117">E_FAIL</span></span>|<span data-ttu-id="5245f-118">실행 엔진을 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5245f-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5245f-119">설명</span><span class="sxs-lookup"><span data-stu-id="5245f-119">Remarks</span></span>  
 <span data-ttu-id="5245f-120">이 메서드는 이전에 로드 되지 않았으면 하는 경우 실행 엔진을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="5245f-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5245f-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5245f-121">Requirements</span></span>  
 <span data-ttu-id="5245f-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5245f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5245f-123">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5245f-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5245f-124">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5245f-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5245f-125">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5245f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5245f-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5245f-126">See Also</span></span>  
 [<span data-ttu-id="5245f-127">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="5245f-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
