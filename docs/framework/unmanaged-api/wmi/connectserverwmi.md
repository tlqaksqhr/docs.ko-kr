---
title: "ConnectServerWmi 함수 (관리 되지 않는 API 참조)"
description: "ConnectServerWmi 함수 DCOM를 사용 하 여 WMI 네임 스페이스에 대 한 연결을 만듭니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dc821bddf1d33ea1144fef0821b81cf027d8f92f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="c06f7-103">ConnectServerWmi 함수</span><span class="sxs-lookup"><span data-stu-id="c06f7-103">ConnectServerWmi function</span></span>
<span data-ttu-id="c06f7-104">지정된 된 컴퓨터에서 DCOM 통해 WMI 네임 스페이스에 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c06f7-105">구문</span><span class="sxs-lookup"><span data-stu-id="c06f7-105">Syntax</span></span>  
  
```  
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel, 
   [in] DWORD              authLevel
);
```  
## <a name="parameters"></a><span data-ttu-id="c06f7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c06f7-106">Parameters</span></span>

<span data-ttu-id="c06f7-107">`strNetworkResource`[in] 포인터를 올바른 `BSTR` 올바른 WMI 네임 스페이스의 개체 경로 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-107">`strNetworkResource` [in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="c06f7-108">참조는 [주의](#remarks) 한 자세 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-108">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="c06f7-109">`strUser`[in] 에 대 한 포인터를 올바른 `BSTR` 사용자 이름이 들어 있는입니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-109">`strUser` [in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="c06f7-110">A `null` 값 현재 보안 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="c06f7-111">사용자가을 현재 보다 다른 도메인의 경우 `strUser` 백슬래시로 구분 된 도메인과 사용자 이름을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="c06f7-112">`strUser`수 사용자에서 계정 이름 (UPN)의 형식을 지정할 수도,으로 suhc  *userName@domainName* 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-112">`strUser` can also be in user principal name (UPN) format, suhc as *userName@domainName*.</span></span> <span data-ttu-id="c06f7-113">참조는 [주의](#remarks) 한 자세 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-113">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="c06f7-114">`strPassword`[in] 에 대 한 포인터를 올바른 `BSTR` 암호가 포함 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-114">`strPassword` [in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="c06f7-115">A `null` 현재 보안 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="c06f7-116">빈 문자열 ("") 유효한 빈 암호를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-116">An empty string ("") indicates a valid zero-length password.</span></span>

<span data-ttu-id="c06f7-117">`strLocale`[in] 에 대 한 포인터를 올바른 `BSTR` 정보 검색에 대 한 올바른 로캘을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-117">`strLocale` [in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="c06f7-118">Microsoft 로캘 식별자에 대 한 문자열의 형식은 "MS\_*xxx*" 여기서 *xxx* 로캘 식별자 (LCID)를 나타내는 16 진수 형식 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="c06f7-119">잘못 된 로캘 지정 되 면 메서드가 반환 `WBEM_E_INVALID_PARAMETER` 제외 Windows 7, 서버에서 기본 로캘을 대신 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="c06f7-120">경우 ' null1, 현재 로캘을 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-120">If \`null1, the current locale is used.</span></span> 
 
<span data-ttu-id="c06f7-121">`lSecurityFlags`[in] 플래그를 전달 하는 `ConnectServerWmi` 메서드.</span><span class="sxs-lookup"><span data-stu-id="c06f7-121">`lSecurityFlags` [in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="c06f7-122">에 대 한 호출에서 값이이 매개 변수에 대해 영 (0) 이면 `ConnectServerWmi` 서버에 연결 된 후에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="c06f7-123">이 인해 응답 하지 않는 무기한 끊어진 경우는 응용 프로그램 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="c06f7-124">다른 유효한 값은:</span><span class="sxs-lookup"><span data-stu-id="c06f7-124">The other valid values are:</span></span>

| <span data-ttu-id="c06f7-125">상수</span><span class="sxs-lookup"><span data-stu-id="c06f7-125">Constant</span></span>  | <span data-ttu-id="c06f7-126">값</span><span class="sxs-lookup"><span data-stu-id="c06f7-126">Value</span></span>  | <span data-ttu-id="c06f7-127">설명</span><span class="sxs-lookup"><span data-stu-id="c06f7-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="c06f7-128">0x40</span><span class="sxs-lookup"><span data-stu-id="c06f7-128">0x40</span></span> | <span data-ttu-id="c06f7-129">내부용으로 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-129">Reserved for internal use.</span></span> <span data-ttu-id="c06f7-130">사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="c06f7-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="c06f7-131">0x80</span><span class="sxs-lookup"><span data-stu-id="c06f7-131">0x80</span></span> | <span data-ttu-id="c06f7-132">`ConnectServerWmi`2 분 이내에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

<span data-ttu-id="c06f7-133">`strAuthority`[in] 사용자의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-133">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="c06f7-134">다음 값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-134">It can have the following values:</span></span>

| <span data-ttu-id="c06f7-135">값</span><span class="sxs-lookup"><span data-stu-id="c06f7-135">Value</span></span> | <span data-ttu-id="c06f7-136">설명</span><span class="sxs-lookup"><span data-stu-id="c06f7-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="c06f7-137">비어 있음</span><span class="sxs-lookup"><span data-stu-id="c06f7-137">blank</span></span> | <span data-ttu-id="c06f7-138">NTLM 인증을 사용 하 고 현재 사용자의 NTLM 도메인 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="c06f7-139">경우 `strUser` 도메인 (권장된 위치)를 지정 합니다. 여기 지정 되지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="c06f7-140">함수 반환 `WBEM_E_INVALID_PARAMETER` 매개 변수가 모두에서 도메인을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="c06f7-141">Kerberos:*사용자 이름*</span><span class="sxs-lookup"><span data-stu-id="c06f7-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="c06f7-142">Kerberos 인증을 사용 하 고이 매개 변수에 Kerberos 사용자 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="c06f7-143">NTLMDOMAIN:*도메인 이름*</span><span class="sxs-lookup"><span data-stu-id="c06f7-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="c06f7-144">NT LAN Manager 인증을 사용 하 고이 매개 변수에 NTLM 도메인 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`   
<span data-ttu-id="c06f7-145">[in] 일반적으로이 매개 변수는 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-145">[in] Typically, this parameter is is `null`.</span></span> <span data-ttu-id="c06f7-146">그렇지 않은 경우에 대 한 포인터는 [IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx) 개체가 하나 이상의 동적 클래스 공급자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-146">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx) object required by one or more dynamic class providers.</span></span> 

`ppNamespace`  
<span data-ttu-id="c06f7-147">[out] 함수가 반환할 때 수신에 대 한 포인터는 [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) 개체가 지정된 된 네임 스페이스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-147">[out] When the function returns, receives a pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object bound to the specified namespace.</span></span> <span data-ttu-id="c06f7-148">가리키도록 설정 되어 `null` 때 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`  
<span data-ttu-id="c06f7-149">[in] 가장 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-149">[in] The impersonation level.</span></span>

`authLevel`  
<span data-ttu-id="c06f7-150">[in] 권한 부여 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="c06f7-151">반환 값</span><span class="sxs-lookup"><span data-stu-id="c06f7-151">Return value</span></span>

<span data-ttu-id="c06f7-152">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="c06f7-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c06f7-153">상수</span><span class="sxs-lookup"><span data-stu-id="c06f7-153">Constant</span></span>  |<span data-ttu-id="c06f7-154">값</span><span class="sxs-lookup"><span data-stu-id="c06f7-154">Value</span></span>  |<span data-ttu-id="c06f7-155">설명</span><span class="sxs-lookup"><span data-stu-id="c06f7-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="c06f7-156">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="c06f7-156">0x80041001</span></span> | <span data-ttu-id="c06f7-157">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c06f7-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c06f7-158">0x80041008</span></span> | <span data-ttu-id="c06f7-159">매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c06f7-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c06f7-160">0x80041006</span></span> | <span data-ttu-id="c06f7-161">작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="c06f7-162">0</span><span class="sxs-lookup"><span data-stu-id="c06f7-162">0</span></span> | <span data-ttu-id="c06f7-163">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="c06f7-164">설명</span><span class="sxs-lookup"><span data-stu-id="c06f7-164">Remarks</span></span>

<span data-ttu-id="c06f7-165">이 함수에 대 한 호출을 래핑하는 [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c06f7-165">This function wraps a call to the [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) method.</span></span>

 <span data-ttu-id="c06f7-166">기본 네임 스페이스에 대 한 로컬 액세스에 대 한 `strNetworkResource` 단순 개체 경로일 수 있습니다: "root\default" 또는 "\\.\root\default"입니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="c06f7-167">COM 또는 Microsoft 호환 네트워킹을 사용 하 여 원격 컴퓨터에서 기본 네임 스페이스에 대 한 액세스에 대 한 컴퓨터 이름을 포함할: "\\myserver\root\default"입니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="c06f7-168">또한 컴퓨터 이름을 DNS 이름 또는 IP 주소 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="c06f7-169">`ConnectServerWmi` 함수 i p v 6을 실행 하는 컴퓨터와 연결할 수도 IPv6 주소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="c06f7-170">`strUser`빈 문자열일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="c06f7-171">에 도메인을 지정 하는 경우 `strAuthority`, 것도 포함 해서도 안에 `strUser`, 함수 반환 또는 `WBEM_E_INVALID_PARAMETER`합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>


## <a name="requirements"></a><span data-ttu-id="c06f7-172">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c06f7-172">Requirements</span></span>  
 <span data-ttu-id="c06f7-173">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c06f7-173">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c06f7-174">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c06f7-174">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c06f7-175">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c06f7-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c06f7-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c06f7-176">See also</span></span>  
[<span data-ttu-id="c06f7-177">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="c06f7-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
