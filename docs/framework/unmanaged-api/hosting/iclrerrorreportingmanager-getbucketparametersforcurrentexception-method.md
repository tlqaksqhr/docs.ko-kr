---
title: ICLRErrorReportingManager::GetBucketParametersForCurrentException 메서드
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f37bbe7d9e76d76bfe4c0f80b6f2343a5598bbfb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431752"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="9063d-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="9063d-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="9063d-103">호출 스레드에서 현재 예외에 대 한 Watson 버킷이 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9063d-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="9063d-104">A *버킷* 는 동일한 코드 결함과 관련 된 오류 데이터의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="9063d-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="9063d-105">*Watson* 예외와 연결 된 데이터 수집 및 분석 하기 위한 기술 집합인을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="9063d-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9063d-106">구문</span><span class="sxs-lookup"><span data-stu-id="9063d-106">Syntax</span></span>  
  
```  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9063d-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9063d-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="9063d-108">[out] 에 대 한 포인터는 [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) 예외에 대 한 오류 데이터를 포함 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="9063d-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9063d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9063d-109">Requirements</span></span>  
 <span data-ttu-id="9063d-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9063d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9063d-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9063d-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9063d-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9063d-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9063d-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9063d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9063d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9063d-114">See Also</span></span>  
 [<span data-ttu-id="9063d-115">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9063d-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
