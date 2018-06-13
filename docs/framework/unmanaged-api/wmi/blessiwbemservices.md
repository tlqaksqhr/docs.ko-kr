---
title: BlessIWbemServices 함수 (관리 되지 않는 API 참조)
description: BlessIWbemServices 함수는 사용자 자격 증명 IWbemServices 클래스에 대 한 액세스를 허용 하는지 여부를 나타냅니다.
ms.date: 11/06/2017
api_name:
- BlessIWbemServices
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServices
helpviewer_keywords:
- BlessIWbemServices function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59cb20f7ccfbd0b8f9d6026c9805468613818130
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458164"
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="b2c9b-103">BlessIWbemServices 함수</span><span class="sxs-lookup"><span data-stu-id="b2c9b-103">BlessIWbemServices function</span></span>
<span data-ttu-id="b2c9b-104">사용자 자격 증명을 지정 된 액세스를 허용 하는지 여부를 나타냅니다. [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b2c9b-104">Indicates whether the user credentials permit access to the specified [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) class.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="b2c9b-105">구문</span><span class="sxs-lookup"><span data-stu-id="b2c9b-105">Syntax</span></span>  
  
```  
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="b2c9b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2c9b-106">Parameters</span></span>

`pIWbemServices`  
<span data-ttu-id="b2c9b-107">[in] 에 대 한 포인터는 [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) 개체 사용 권한을 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2c9b-107">[in] A pointer to the [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object for which permissions are required.</span></span>

`strUser`  
<span data-ttu-id="b2c9b-108">[in] 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b2c9b-108">[in] The user name.</span></span>

`strPassword`  
<span data-ttu-id="b2c9b-109">[in] 연결 된 암호 `strUser`합니다.</span><span class="sxs-lookup"><span data-stu-id="b2c9b-109">[in] The password associated with `strUser`.</span></span>

<span data-ttu-id="b2c9b-110">`strAuthority` [in] 사용자의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b2c9b-110">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="b2c9b-111">참조는 [ConnectServerWmi](connectserverwmi.md) 자세한 정보에 대 한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b2c9b-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="b2c9b-112">`impLevel` [in] 가장 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="b2c9b-112">`impLevel` [in] The impersonation level.</span></span>

<span data-ttu-id="b2c9b-113">`authnLevel` [in] 권한 부여 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="b2c9b-113">`authnLevel` [in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="b2c9b-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="b2c9b-114">Return value</span></span>

<span data-ttu-id="b2c9b-115">이 함수에서 반환 되는 다음 값에 정의 된는 *WinError.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="b2c9b-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b2c9b-116">상수</span><span class="sxs-lookup"><span data-stu-id="b2c9b-116">Constant</span></span>  |<span data-ttu-id="b2c9b-117">값</span><span class="sxs-lookup"><span data-stu-id="b2c9b-117">Value</span></span>  |<span data-ttu-id="b2c9b-118">설명</span><span class="sxs-lookup"><span data-stu-id="b2c9b-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="b2c9b-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="b2c9b-119">0x80070057</span></span> | <span data-ttu-id="b2c9b-120">하나 이상의 인수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b2c9b-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="b2c9b-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="b2c9b-121">0x80004003</span></span> | <span data-ttu-id="b2c9b-122">`pIWbemServices`가 `null`인 경우</span><span class="sxs-lookup"><span data-stu-id="b2c9b-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="b2c9b-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="b2c9b-123">0x80000008</span></span> | <span data-ttu-id="b2c9b-124">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b2c9b-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="b2c9b-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="b2c9b-125">0x80000002</span></span> | <span data-ttu-id="b2c9b-126">메모리가 부족 하 여 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2c9b-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="b2c9b-127">0</span><span class="sxs-lookup"><span data-stu-id="b2c9b-127">0</span></span> | <span data-ttu-id="b2c9b-128">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b2c9b-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="b2c9b-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2c9b-129">Requirements</span></span>  
 <span data-ttu-id="b2c9b-130">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2c9b-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2c9b-131">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b2c9b-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b2c9b-132">**.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b2c9b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2c9b-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="b2c9b-133">See also</span></span>  
[<span data-ttu-id="b2c9b-134">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="b2c9b-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
