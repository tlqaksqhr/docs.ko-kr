---
title: GetCurrentApartmentType 함수 (관리 되지 않는 API 참조)
description: GetCurrentApartmentType 함수 아파트 호출자에 게 실행 되는 형식을 검색 합니다.
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca7b5fa5bf6d845d542d3e80c0571e59f3d4c1e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461726"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="c0689-103">GetCurrentApartmentType 함수</span><span class="sxs-lookup"><span data-stu-id="c0689-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="c0689-104">아파트 호출자에 게 실행 되는 형식을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0689-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c0689-105">구문</span><span class="sxs-lookup"><span data-stu-id="c0689-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="c0689-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c0689-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c0689-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0689-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c0689-108">[in] 에 대 한 포인터는 [IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="c0689-108">[in] A pointer to an [IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx) instance.</span></span>

`aptType`  
<span data-ttu-id="c0689-109">[out] 에 대 한 포인터는 [APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx) 호출자의 아파트를 나타내는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c0689-109">[out] A pointer to an [APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="c0689-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="c0689-110">Return value</span></span>


|<span data-ttu-id="c0689-111">상수</span><span class="sxs-lookup"><span data-stu-id="c0689-111">Constant</span></span>  |<span data-ttu-id="c0689-112">값</span><span class="sxs-lookup"><span data-stu-id="c0689-112">Value</span></span>  |<span data-ttu-id="c0689-113">설명</span><span class="sxs-lookup"><span data-stu-id="c0689-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="c0689-114">0</span><span class="sxs-lookup"><span data-stu-id="c0689-114">0</span></span> | <span data-ttu-id="c0689-115">함수는 성공적으로 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c0689-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="c0689-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="c0689-116">0x80000008</span></span> | <span data-ttu-id="c0689-117">호출자에 게는 아파트에서 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0689-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="c0689-118">설명</span><span class="sxs-lookup"><span data-stu-id="c0689-118">Remarks</span></span>

<span data-ttu-id="c0689-119">이 함수에 대 한 호출을 래핑하는 [IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c0689-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c0689-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c0689-120">Requirements</span></span>  
 <span data-ttu-id="c0689-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0689-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0689-122">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c0689-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c0689-123">**.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c0689-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0689-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="c0689-124">See also</span></span>  
[<span data-ttu-id="c0689-125">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="c0689-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
