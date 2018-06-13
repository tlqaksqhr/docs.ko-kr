---
title: ICLRStrongName::StrongNameSignatureSize 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6641490908b1f384bf8192fd46b7dadb4ff5e23
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431944"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="2371d-102">ICLRStrongName::StrongNameSignatureSize 메서드</span><span class="sxs-lookup"><span data-stu-id="2371d-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="2371d-103">강력한 이름 서명의 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2371d-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="2371d-104">서명이 연기 된 어셈블리를 만들 때 파일에 예약할 공간을 확인 하려면이 메서드는 일반적으로 컴파일러에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2371d-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2371d-105">구문</span><span class="sxs-lookup"><span data-stu-id="2371d-105">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="2371d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2371d-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="2371d-107">[in] 형식의 구조 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 강력한 이름 서명을 생성 하는 데 사용 되는 키 쌍의 공개 부분을 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="2371d-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="2371d-108">[in] 를 바이트 단위로 크기의 `pbPublicKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="2371d-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="2371d-109">[in] 강력한 이름 서명을 저장 하는 데 필요한 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2371d-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2371d-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="2371d-110">Return Value</span></span>  
 <span data-ttu-id="2371d-111">`S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="2371d-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2371d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2371d-112">Requirements</span></span>  
 <span data-ttu-id="2371d-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2371d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2371d-114">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="2371d-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2371d-115">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2371d-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2371d-116">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2371d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2371d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2371d-117">See Also</span></span>  
 [<span data-ttu-id="2371d-118">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2371d-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
