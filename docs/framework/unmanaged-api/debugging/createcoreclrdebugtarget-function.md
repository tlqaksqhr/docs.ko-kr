---
title: CreateCoreClrDebugTarget 함수
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a957eb6907b55fe948d696a6a25076c3950f7381
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402977"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="9da13-102">CreateCoreClrDebugTarget 함수</span><span class="sxs-lookup"><span data-stu-id="9da13-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="9da13-103">원격 컴퓨터에서 실행 되 고 반환 하는 디버거 프록시에 대 한 연결을 만듭니다는 [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) 실행 중인 프로세스 및 원격 컴퓨터에 로드 된 런타임을 쿼리 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da13-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9da13-104">구문</span><span class="sxs-lookup"><span data-stu-id="9da13-104">Syntax</span></span>  
  
```  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9da13-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9da13-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="9da13-106">[in] 원격 대상 컴퓨터의 IPv4 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="9da13-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="9da13-107">[out] 에 대 한 포인터에 대 한 포인터는 [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) 생성 되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9da13-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9da13-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="9da13-108">Return Value</span></span>  
 <span data-ttu-id="9da13-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="9da13-109">S_OK</span></span>  
 <span data-ttu-id="9da13-110">프로세스의 CLR 수가 성공적으로 확인되었으며 해당 핸들 및 경로 배열이 제대로 채워졌습니다.</span><span class="sxs-lookup"><span data-stu-id="9da13-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="9da13-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9da13-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="9da13-112">`ppTarget`에 대해 충분한 메모리를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9da13-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="9da13-113">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="9da13-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9da13-114">기타 실패</span><span class="sxs-lookup"><span data-stu-id="9da13-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9da13-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9da13-115">Requirements</span></span>  
 <span data-ttu-id="9da13-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9da13-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9da13-117">**헤더:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="9da13-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="9da13-118">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="9da13-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="9da13-119">**.NET framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="9da13-119">**.NET Framework Versions:** 3.5 SP1</span></span>
