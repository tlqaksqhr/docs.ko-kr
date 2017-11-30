---
title: "StrongNameKeyInstall 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameKeyInstall
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameKeyInstall
helpviewer_keywords: StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 60044e12a884a28cb7485118a95d2bf7650723fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="cbacf-102">StrongNameKeyInstall 함수</span><span class="sxs-lookup"><span data-stu-id="cbacf-102">StrongNameKeyInstall Function</span></span>
<span data-ttu-id="cbacf-103">컨테이너에 공개/개인 키 쌍을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cbacf-103">Imports a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="cbacf-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cbacf-104">This function has been deprecated.</span></span> <span data-ttu-id="cbacf-105">사용 하 여 [iclrstrongname:: Strongnamekeyinstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbacf-105">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbacf-106">구문</span><span class="sxs-lookup"><span data-stu-id="cbacf-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cbacf-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cbacf-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="cbacf-108">[in] 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cbacf-108">[in] The name of the key container.</span></span> <span data-ttu-id="cbacf-109">`wszKeyContainer`비어 있지 않은 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbacf-109">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="cbacf-110">[in] 이진 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="cbacf-110">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="cbacf-111">[in] 를 바이트 단위로 크기의 `pbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="cbacf-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cbacf-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="cbacf-112">Return Value</span></span>  
 <span data-ttu-id="cbacf-113">`true`성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="cbacf-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbacf-114">설명</span><span class="sxs-lookup"><span data-stu-id="cbacf-114">Remarks</span></span>  
 <span data-ttu-id="cbacf-115">사용 하 여는 [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) 키 컨테이너를 삭제 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="cbacf-115">Use the [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) function to delete the key container.</span></span>  
  
 <span data-ttu-id="cbacf-116">경우는 `StrongNameKeyInstall` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbacf-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbacf-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cbacf-117">Requirements</span></span>  
 <span data-ttu-id="cbacf-118">**플랫폼:** WindSee [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cbacf-118">**Platforms:** WindSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbacf-119">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="cbacf-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="cbacf-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="cbacf-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cbacf-121">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbacf-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbacf-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbacf-122">See Also</span></span>  
 [<span data-ttu-id="cbacf-123">StrongNameKeyInstall 메서드</span><span class="sxs-lookup"><span data-stu-id="cbacf-123">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="cbacf-124">StrongNameKeyDelete 메서드</span><span class="sxs-lookup"><span data-stu-id="cbacf-124">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="cbacf-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cbacf-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
