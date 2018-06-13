---
title: GetDemultiplexedStub 함수 (관리 되지 않는 API 참조)
description: GetDemultiplexedStub 함수 Windows 관리에서 비동기 호출을 받는 클라이언트를 지원 하기 위해 개체 전달자 싱크를 만듭니다.
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b195d3a512c537ca409bd2039add9e69abaf4df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456364"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="bf014-103">GetDemultiplexedStub 함수</span><span class="sxs-lookup"><span data-stu-id="bf014-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="bf014-104">Windows 관리에서 비동기 호출을 받는 클라이언트를 지원 하기 위해 개체 전달자 싱크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf014-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="bf014-105">구문</span><span class="sxs-lookup"><span data-stu-id="bf014-105">Syntax</span></span>  
  
```  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="bf014-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bf014-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="bf014-107">[in] 클라이언트의 프로세스에 구현에 대 한 포인터 [IWbemObjectSink](https://msdn.microsoft.com/library/aa391787(v=vs.85).aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf014-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](https://msdn.microsoft.com/library/aa391787(v=vs.85).aspx).</span></span>

`isLocal`  
<span data-ttu-id="bf014-108">[in] 이벤트가 로컬 인지 여부를 나타내는 플래그 (`true`), 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf014-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="bf014-109">[out] Windows 관리에서 비동기 호출을 받는 클라이언트를 지원 하기 위해 개체 전달자 싱크.</span><span class="sxs-lookup"><span data-stu-id="bf014-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="bf014-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="bf014-110">Return value</span></span>

<span data-ttu-id="bf014-111">함수가 성공 하면 반환 값은 `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="bf014-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="bf014-112">함수가 실패 하면 반환 값은 0이 아닌 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="bf014-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="bf014-113">확장 정보를 가져오려면 오류를 호출 하는 [GetErrorInfo](geterrorinfo.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="bf014-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="bf014-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf014-114">Requirements</span></span>  
 <span data-ttu-id="bf014-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf014-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf014-116">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="bf014-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="bf014-117">**.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bf014-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf014-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="bf014-118">See also</span></span>  
[<span data-ttu-id="bf014-119">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="bf014-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
