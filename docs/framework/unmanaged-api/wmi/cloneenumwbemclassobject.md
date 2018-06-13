---
title: CloneEnumWbemClassObject 함수 (관리 되지 않는 API 참조)
description: CloneEnumWbemClassObject 함수 열거자의 논리적 복사본을 만듭니다.
ms.date: 11/06/2017
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71e881eca541d6a987fa7d27e1d73903f843e26a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460608"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="26afa-103">CloneEnumWbemClassObject 함수</span><span class="sxs-lookup"><span data-stu-id="26afa-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="26afa-104">열거형의 현재 위치를 유지 하는 열거자의 논리적 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="26afa-105">구문</span><span class="sxs-lookup"><span data-stu-id="26afa-105">Syntax</span></span>  
  
```  
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum, 
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject, 
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority 
); 
```  

## <a name="parameters"></a><span data-ttu-id="26afa-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="26afa-106">Parameters</span></span>

`ppEnum`  
<span data-ttu-id="26afa-107">[out] 새에 대 한 포인터를 받는 [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-107">[out] Receives a pointer to a new [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).</span></span>

`authLevel`  
<span data-ttu-id="26afa-108">[in] 권한 부여 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-108">[in] The authorization level.</span></span>

<span data-ttu-id="26afa-109">`impLevel` [in] 가장 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-109">`impLevel` [in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`  
<span data-ttu-id="26afa-110">[out] 에 대 한 포인터는 [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) 인스턴스를 복제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-110">[out] A pointer to the [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) instance to be cloned.</span></span>

`strUser`   
<span data-ttu-id="26afa-111">[in] 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-111">[in] The user name.</span></span> <span data-ttu-id="26afa-112">참조는 [ConnectServerWmi](connectserverwmi.md) 자세한 정보에 대 한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="26afa-113">[in] 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-113">[in] The password.</span></span> <span data-ttu-id="26afa-114">참조는 [ConnectServerWmi](connectserverwmi.md) 자세한 정보에 대 한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="26afa-115">[in] 사용자의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-115">[in] The domain name of the user.</span></span> <span data-ttu-id="26afa-116">참조는 [ConnectServerWmi](connectserverwmi.md) 자세한 정보에 대 한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="26afa-117">반환 값</span><span class="sxs-lookup"><span data-stu-id="26afa-117">Return value</span></span>

<span data-ttu-id="26afa-118">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="26afa-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="26afa-119">상수</span><span class="sxs-lookup"><span data-stu-id="26afa-119">Constant</span></span>  |<span data-ttu-id="26afa-120">값</span><span class="sxs-lookup"><span data-stu-id="26afa-120">Value</span></span>  |<span data-ttu-id="26afa-121">설명</span><span class="sxs-lookup"><span data-stu-id="26afa-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="26afa-122">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="26afa-122">0x80041001</span></span> | <span data-ttu-id="26afa-123">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="26afa-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="26afa-124">0x80041008</span></span> | <span data-ttu-id="26afa-125">매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="26afa-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="26afa-126">0x80041006</span></span> | <span data-ttu-id="26afa-127">사용 가능한 메모리가 부족 합니다. 작업을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="26afa-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="26afa-128">0x80041015</span></span> | <span data-ttu-id="26afa-129">현재 프로세스 사이의 WMI 원격 프로시저 호출 (RPC) 연결 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="26afa-130">0</span><span class="sxs-lookup"><span data-stu-id="26afa-130">0</span></span> | <span data-ttu-id="26afa-131">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="26afa-132">설명</span><span class="sxs-lookup"><span data-stu-id="26afa-132">Remarks</span></span>

<span data-ttu-id="26afa-133">이 함수에 대 한 호출을 래핑하는 [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="26afa-133">This function wraps a call to the [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="26afa-134">이 메서드는 "최상의" 복사본만을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="26afa-135">인해 많은 CIM 개체의 동적 특성과 새 열거자 원본 열거자로 동일한 개체 집합을 열거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>  

<span data-ttu-id="26afa-136">함수 호출에 실패 하는 경우 호출 하 여 추가 오류 정보를 얻을 수 있습니다는 [GetErrorInfo](geterrorinfo.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="26afa-137">예제</span><span class="sxs-lookup"><span data-stu-id="26afa-137">Example</span></span>

<span data-ttu-id="26afa-138">예를 들어 참조는 [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="26afa-138">For an example, see the [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="26afa-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="26afa-139">Requirements</span></span>  
 <span data-ttu-id="26afa-140">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26afa-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26afa-141">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="26afa-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="26afa-142">**.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="26afa-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26afa-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="26afa-143">See also</span></span>  
[<span data-ttu-id="26afa-144">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="26afa-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
