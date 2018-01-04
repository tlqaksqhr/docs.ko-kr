---
title: "ICLRStrongName::StrongNameKeyInstall 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameKeyInstall
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df1bdb5d6d6018855cb76b48d58e557a61288a51
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="0f6df-102">ICLRStrongName::StrongNameKeyInstall 메서드</span><span class="sxs-lookup"><span data-stu-id="0f6df-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="0f6df-103">컨테이너에 공개/개인 키 쌍을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f6df-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f6df-104">구문</span><span class="sxs-lookup"><span data-stu-id="0f6df-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f6df-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f6df-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="0f6df-106">[in] 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0f6df-106">[in] The name of the key container.</span></span> <span data-ttu-id="0f6df-107">`wszKeyContainer`비어 있지 않은 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f6df-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="0f6df-108">[in] 이진 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="0f6df-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="0f6df-109">[in] 를 바이트 단위로 크기의 `pbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="0f6df-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f6df-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="0f6df-110">Return Value</span></span>  
 <span data-ttu-id="0f6df-111">`S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="0f6df-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f6df-112">설명</span><span class="sxs-lookup"><span data-stu-id="0f6df-112">Remarks</span></span>  
 <span data-ttu-id="0f6df-113">사용 하 여는 [iclrstrongname:: Strongnamekeydelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) 메서드 키 컨테이너를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f6df-113">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f6df-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f6df-114">Requirements</span></span>  
 <span data-ttu-id="0f6df-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f6df-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f6df-116">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="0f6df-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0f6df-117">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0f6df-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f6df-118">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f6df-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f6df-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f6df-119">See Also</span></span>  
 [<span data-ttu-id="0f6df-120">StrongNameKeyDelete 메서드</span><span class="sxs-lookup"><span data-stu-id="0f6df-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="0f6df-121">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f6df-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
