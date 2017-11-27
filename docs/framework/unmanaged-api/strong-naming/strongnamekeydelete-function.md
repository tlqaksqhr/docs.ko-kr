---
title: "StrongNameKeyDelete 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameKeyDelete
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameKeyDelete
helpviewer_keywords: StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c7b3ccc9ec1b8cbc81de115f734e1d11e0e0ae0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="5de69-102">StrongNameKeyDelete 함수</span><span class="sxs-lookup"><span data-stu-id="5de69-102">StrongNameKeyDelete Function</span></span>
<span data-ttu-id="5de69-103">지정된 된 키 컨테이너를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="5de69-103">Deletes the specified key container.</span></span>  
  
 <span data-ttu-id="5de69-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5de69-104">This function has been deprecated.</span></span> <span data-ttu-id="5de69-105">사용 하 여 [iclrstrongname:: Strongnamekeydelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="5de69-105">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5de69-106">구문</span><span class="sxs-lookup"><span data-stu-id="5de69-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5de69-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5de69-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="5de69-108">[in] 삭제할 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5de69-108">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5de69-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="5de69-109">Return Value</span></span>  
 <span data-ttu-id="5de69-110">`true`성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="5de69-110">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5de69-111">설명</span><span class="sxs-lookup"><span data-stu-id="5de69-111">Remarks</span></span>  
 <span data-ttu-id="5de69-112">사용 하 여는 [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) 컨테이너에 공개/개인 키 쌍을 importa에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5de69-112">Use the [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) function to importa a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="5de69-113">경우는 `StrongNameKeyDelete` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="5de69-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5de69-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5de69-114">Requirements</span></span>  
 <span data-ttu-id="5de69-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5de69-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5de69-116">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="5de69-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5de69-117">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5de69-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5de69-118">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5de69-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de69-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5de69-119">See Also</span></span>  
 [<span data-ttu-id="5de69-120">StrongNameKeyDelete 메서드</span><span class="sxs-lookup"><span data-stu-id="5de69-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="5de69-121">StrongNameKeyInstall 메서드</span><span class="sxs-lookup"><span data-stu-id="5de69-121">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="5de69-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5de69-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
