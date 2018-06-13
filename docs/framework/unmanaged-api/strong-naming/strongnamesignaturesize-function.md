---
title: StrongNameSignatureSize 함수
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c11de99359701bb6c3198a0b1dc18ba4318c8bc1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461203"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="e5e1a-102">StrongNameSignatureSize 함수</span><span class="sxs-lookup"><span data-stu-id="e5e1a-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="e5e1a-103">강력한 이름 서명의 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e1a-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="e5e1a-104">`StrongNameSignatureSize` 대개 사용 컴파일러에서 서명이 연기 된 어셈블리를 만들 때 파일에 예약할 공간 크기를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e1a-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="e5e1a-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5e1a-105">This function has been deprecated.</span></span> <span data-ttu-id="e5e1a-106">사용 하 여 [iclrstrongname:: Strongnamesignaturesize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e1a-106">Use the [ICLRStrongName::StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5e1a-107">구문</span><span class="sxs-lookup"><span data-stu-id="e5e1a-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5e1a-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5e1a-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="e5e1a-109">[in] 형식의 구조 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 강력한 이름 서명을 생성 하는 데 사용 되는 키 쌍의 공개 부분을 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e1a-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="e5e1a-110">[in] 를 바이트 단위로 크기의 `pbPublicKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e1a-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="e5e1a-111">[in] 강력한 이름 서명을 저장 하는 데 필요한 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e5e1a-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5e1a-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="e5e1a-112">Return Value</span></span>  
 <span data-ttu-id="e5e1a-113">`true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e1a-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5e1a-114">설명</span><span class="sxs-lookup"><span data-stu-id="e5e1a-114">Remarks</span></span>  
 <span data-ttu-id="e5e1a-115">경우는 `StrongNameSignatureSize` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e1a-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5e1a-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5e1a-116">Requirements</span></span>  
 <span data-ttu-id="e5e1a-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e1a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5e1a-118">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="e5e1a-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e5e1a-119">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e5e1a-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e5e1a-120">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5e1a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5e1a-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5e1a-121">See Also</span></span>  
 [<span data-ttu-id="e5e1a-122">StrongNameSignatureSize 메서드</span><span class="sxs-lookup"><span data-stu-id="e5e1a-122">StrongNameSignatureSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)  
 [<span data-ttu-id="e5e1a-123">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5e1a-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
