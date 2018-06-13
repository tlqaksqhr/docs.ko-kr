---
title: ICorRuntimeHost::MapFile 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.MapFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45b88758c339cd77bc7e17e0c29969f8783555f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436626"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="8a225-102">ICorRuntimeHost::MapFile 메서드</span><span class="sxs-lookup"><span data-stu-id="8a225-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="8a225-103">지정된 된 파일을 메모리에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="8a225-103">Maps the specified file into memory.</span></span> <span data-ttu-id="8a225-104">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a225-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a225-105">구문</span><span class="sxs-lookup"><span data-stu-id="8a225-105">Syntax</span></span>  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a225-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8a225-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="8a225-107">[in] 매핑할 파일의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="8a225-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="8a225-108">[out] 매핑 파일을 시작 하는 시작 메모리 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a225-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a225-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a225-109">Requirements</span></span>  
 <span data-ttu-id="8a225-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8a225-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a225-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8a225-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a225-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8a225-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a225-113">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="8a225-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a225-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a225-114">See Also</span></span>  
 [<span data-ttu-id="8a225-115">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a225-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
