---
title: "ICLRDataTarget::GetMachineType 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetMachineType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetMachineType
helpviewer_keywords:
- ICLRDataTarget::GetMachineType method [.NET Framework debugging]
- GetMachineType method [.NET Framework debugging]
ms.assetid: 5f1f9c61-3e3b-48b2-b111-a4395f7623a7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8cd3a71d150011a1a5b9ad84c4687aac6346eb6f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="b35be-102">ICLRDataTarget::GetMachineType 메서드</span><span class="sxs-lookup"><span data-stu-id="b35be-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="b35be-103">대상 프로세스를 사용 하는 명령 집합의 종류에 대 한 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b35be-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b35be-104">구문</span><span class="sxs-lookup"><span data-stu-id="b35be-104">Syntax</span></span>  
  
```  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b35be-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b35be-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="b35be-106">[out] 대상 프로세스는 명령 집합을 표시 하는 값에 대 한 포인터 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="b35be-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="b35be-107">반환 된 `machineType` WinNT.h 헤더 파일에 정의 된 IMAGE_FILE_MACHINE 상수 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="b35be-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b35be-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b35be-108">Requirements</span></span>  
 <span data-ttu-id="b35be-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b35be-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b35be-110">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="b35be-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b35be-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b35be-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b35be-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b35be-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b35be-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b35be-113">See Also</span></span>  
 [<span data-ttu-id="b35be-114">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b35be-114">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
