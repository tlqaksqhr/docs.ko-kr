---
title: "ExecQueryWmi 함수 (관리 되지 않는 API 참조)"
description: "ExecQueryWmi 함수 개체를 검색 하는 쿼리를 실행 합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: ExecQueryWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: ExecQueryWmi
helpviewer_keywords: ExecQueryWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ebd5463fd3b4109203e829da8e3683bbb79cf59
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="execquerywmi-function"></a><span data-ttu-id="cb600-103">ExecQueryWmi 함수</span><span class="sxs-lookup"><span data-stu-id="cb600-103">ExecQueryWmi function</span></span>
<span data-ttu-id="cb600-104">개체를 검색 하는 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-104">Executes a query to retrieve objects.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="cb600-105">구문</span><span class="sxs-lookup"><span data-stu-id="cb600-105">Syntax</span></span>  
  
```  
HRESULT ExecQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
); 
```  

## <a name="parameters"></a><span data-ttu-id="cb600-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb600-106">Parameters</span></span>

`strQueryLanguage`    
<span data-ttu-id="cb600-107">[in] Windows 관리에서 지원 되는 유효한 쿼리 언어에 사용 되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-107">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="cb600-108">WMI 쿼리 언어에 대 한 약어 "WQL" 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-108">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`  
<span data-ttu-id="cb600-109">[in] 쿼리 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-109">[in] The text of the query.</span></span> <span data-ttu-id="cb600-110">이 매개 변수 여야 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-110">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="cb600-111">[in] 이 함수의 동작에 영향을 주는 플래그의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-111">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="cb600-112">에 정의 된 다음 값은 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="cb600-112">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

| <span data-ttu-id="cb600-113">상수</span><span class="sxs-lookup"><span data-stu-id="cb600-113">Constant</span></span> | <span data-ttu-id="cb600-114">값</span><span class="sxs-lookup"><span data-stu-id="cb600-114">Value</span></span>  | <span data-ttu-id="cb600-115">설명</span><span class="sxs-lookup"><span data-stu-id="cb600-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="cb600-116">0 x 20000</span><span class="sxs-lookup"><span data-stu-id="cb600-116">0x20000</span></span> | <span data-ttu-id="cb600-117">경우 집합 함수는 현재 연결의 로캘의 지역화 된 네임 스페이스에 저장 된 수정 된 한정자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-117">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="cb600-118">그렇지 않은 경우 집합 함수 즉시 네임 스페이스에 저장 된 한정자만 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-118">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="cb600-119">0x10</span><span class="sxs-lookup"><span data-stu-id="cb600-119">0x10</span></span> | <span data-ttu-id="cb600-120">플래그를 사용 하면 일부 동기 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-120">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="cb600-121">0x20</span><span class="sxs-lookup"><span data-stu-id="cb600-121">0x20</span></span> | <span data-ttu-id="cb600-122">함수는 앞 으로만 이동 가능한 열거자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-122">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="cb600-123">에 대 한 호출을 허용 하지 않습니다 앞 으로만 이동 가능한 열거자 빠르고 기본 열거자 보다 메모리를 적게 사용 되지만 일반적으로 [복제](clone.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-123">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="cb600-124">0</span><span class="sxs-lookup"><span data-stu-id="cb600-124">0</span></span> | <span data-ttu-id="cb600-125">WMI 회수 될 때까지 enumration의 개체에 대 한 포인터를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-125">WMI retains pointers to objects in the enumration until they are released.</span></span> | 
| `WBEM_FLAG_ENSURE_LOCATABLE` | <span data-ttu-id="cb600-126">0x100</span><span class="sxs-lookup"><span data-stu-id="cb600-126">0x100</span></span> | <span data-ttu-id="cb600-127">반환 된 개체에 대 한 충분 한 정보가 있으므로 사용 하면 해당 시스템 속성 같은 **__PATH**, **__RELPATH**, 및 **__SERVER**, 없는 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-127">Ensures that any returned objects have enough information in them so that system properties, such as **__PATH**, **__RELPATH**, and **__SERVER**, are not `null`.</span></span> |
| `WBEM_FLAG_PROTOTYPE` | <span data-ttu-id="cb600-128">2</span><span class="sxs-lookup"><span data-stu-id="cb600-128">2</span></span> | <span data-ttu-id="cb600-129">이 플래그는 프로토타입 생성에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-129">This flag is used for prototyping.</span></span> <span data-ttu-id="cb600-130">쿼리를 실행 하지 않는 하 고 대신 다음과 같은 일반적인 결과 개체는 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-130">It does not execute the query and instead returns an object that looks like a typical result object.</span></span> |
| `WBEM_FLAG_DIRECT_READ` | <span data-ttu-id="cb600-131">0x200</span><span class="sxs-lookup"><span data-stu-id="cb600-131">0x200</span></span> | <span data-ttu-id="cb600-132">원인을 직접 부모 클래스 또는 서브 클래스에 관계 없이 지정 된 클래스에 대 한 공급자에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-132">Causes direct access to the provider for the class specified without regard to its parent class or any subclasses.</span></span> |

<span data-ttu-id="cb600-133">권장 되는 플래그를 `WBEM_FLAG_RETURN_IMMEDIATELY` 및 `WBEM_FLAG_FORWARD_ONLY` 최상의 성능을 위해.</span><span class="sxs-lookup"><span data-stu-id="cb600-133">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="cb600-134">[in] 이 값은 일반적으로 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-134">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="cb600-135">그렇지 않은 경우에 대 한 포인터는 [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) 요청 된 클래스를 제공 하는 공급자가 사용할 수 있는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="cb600-135">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppEnum`  
<span data-ttu-id="cb600-136">[out] 오류가 발생 하는 경우 호출자는 쿼리 결과 집합의 인스턴스를 검색 하는 열거자에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-136">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="cb600-137">쿼리 결과 집합을 제로 인스턴스를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-137">The query can have a result set with zero instances.</span></span> <span data-ttu-id="cb600-138">참조는 [주의](#remarks) 한 자세 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-138">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`  
<span data-ttu-id="cb600-139">[in] 권한 부여 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-139">[in] The authorization level.</span></span>

<span data-ttu-id="cb600-140">`impLevel`[in] 가장 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-140">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="cb600-141">[in] 에 대 한 포인터는 [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) 현재 네임 스페이스를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-141">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="cb600-142">[in] 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-142">[in] The user name.</span></span> <span data-ttu-id="cb600-143">참조는 [ConnectServerWmi](connectserverwmi.md) 자세한 정보에 대 한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-143">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="cb600-144">[in] 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-144">[in] The password.</span></span> <span data-ttu-id="cb600-145">참조는 [ConnectServerWmi](connectserverwmi.md) 자세한 정보에 대 한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-145">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="cb600-146">[in] 사용자의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-146">[in] The domain name of the user.</span></span> <span data-ttu-id="cb600-147">참조는 [ConnectServerWmi](connectserverwmi.md) 자세한 정보에 대 한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-147">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="cb600-148">반환 값</span><span class="sxs-lookup"><span data-stu-id="cb600-148">Return value</span></span>

<span data-ttu-id="cb600-149">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="cb600-149">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="cb600-150">상수</span><span class="sxs-lookup"><span data-stu-id="cb600-150">Constant</span></span>  |<span data-ttu-id="cb600-151">값</span><span class="sxs-lookup"><span data-stu-id="cb600-151">Value</span></span>  |<span data-ttu-id="cb600-152">설명</span><span class="sxs-lookup"><span data-stu-id="cb600-152">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="cb600-153">0x80041003</span><span class="sxs-lookup"><span data-stu-id="cb600-153">0x80041003</span></span> | <span data-ttu-id="cb600-154">사용자에가 함수에서 반환할 수 있는 클래스를 하나 이상 볼 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-154">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="cb600-155">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="cb600-155">0x80041001</span></span> | <span data-ttu-id="cb600-156">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-156">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="cb600-157">0x80041008</span><span class="sxs-lookup"><span data-stu-id="cb600-157">0x80041008</span></span> | <span data-ttu-id="cb600-158">매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-158">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="cb600-159">0x80041017</span><span class="sxs-lookup"><span data-stu-id="cb600-159">0x80041017</span></span> | <span data-ttu-id="cb600-160">쿼리 구문 오류가 발생을 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-160">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="cb600-161">0x80041018</span><span class="sxs-lookup"><span data-stu-id="cb600-161">0x80041018</span></span> | <span data-ttu-id="cb600-162">요청한 쿼리 언어는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-162">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="cb600-163">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="cb600-163">0x8004106c</span></span> | <span data-ttu-id="cb600-164">쿼리는 너무 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-164">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="cb600-165">0x80041006</span><span class="sxs-lookup"><span data-stu-id="cb600-165">0x80041006</span></span> | <span data-ttu-id="cb600-166">작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-166">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="cb600-167">0x80041033</span><span class="sxs-lookup"><span data-stu-id="cb600-167">0x80041033</span></span> | <span data-ttu-id="cb600-168">WMI 아마도 중지 및 다시 시작 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-168">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="cb600-169">호출 [ConnectServerWmi](connectserverwmi.md) 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-169">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="cb600-170">0x80041015</span><span class="sxs-lookup"><span data-stu-id="cb600-170">0x80041015</span></span> | <span data-ttu-id="cb600-171">현재 프로세스 사이의 WMI 원격 프로시저 호출 (RPC) 연결 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-171">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="cb600-172">0x80041002</span><span class="sxs-lookup"><span data-stu-id="cb600-172">0x80041002</span></span> | <span data-ttu-id="cb600-173">쿼리에서 존재 하지 않는 클래스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-173">The query specifies a class that does not exist.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="cb600-174">0</span><span class="sxs-lookup"><span data-stu-id="cb600-174">0</span></span> | <span data-ttu-id="cb600-175">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-175">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="cb600-176">설명</span><span class="sxs-lookup"><span data-stu-id="cb600-176">Remarks</span></span>

<span data-ttu-id="cb600-177">이 함수에 대 한 호출을 래핑하는 [IWbemServices::ExecQuery](https://msdn.microsoft.com/library/aa392107(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="cb600-177">This function wraps a call to the [IWbemServices::ExecQuery](https://msdn.microsoft.com/library/aa392107(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="cb600-178">이 함수에 지정 된 쿼리 처리는 `strQuery` 매개 변수는 호출자에 게 쿼리 결과 액세스할 수 있는 열거자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-178">This function processes the query specified in the `strQuery` parameter and creates an enumerator through which the caller can access the query results.</span></span> <span data-ttu-id="cb600-179">열거자가에 대 한 포인터는 [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) 인터페이스; 쿼리 결과 통해 사용할 수 있는 클래스 개체의 인스턴스는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433(v=vs.85).aspx) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-179">The enumerator is a pointer to an [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) interface; the query results are instances of class objects made available through the [IWbemClassObject](https://msdn.microsoft.com/library/aa391433(v=vs.85).aspx) interface.</span></span>

<span data-ttu-id="cb600-180">수에 제한이 `AND` 및 `OR` WQL 쿼리에서 사용할 수 있는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-180">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="cb600-181">많은 수의 복잡 한 쿼리에서 사용 하는 WQL 키워드 반환 하기 위해 WMI를 발생할 수 있습니다는 `WBEM_E_QUOTA_VIOLATION` (또는 0x8004106c)으로 오류 코드는 `HRESULT` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-181">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="cb600-182">WQL 키워드 제한인 쿼리가 복잡 한 정도에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-182">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="cb600-183">함수 호출에 실패 하는 경우 호출 하 여 추가 오류 정보를 얻을 수 있습니다는 [GetErrorInfo](geterrorinfo.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-183">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="cb600-184">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb600-184">Requirements</span></span>  
 <span data-ttu-id="cb600-185">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb600-185">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb600-186">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="cb600-186">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="cb600-187">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cb600-187">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb600-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb600-188">See also</span></span>  
[<span data-ttu-id="cb600-189">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="cb600-189">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
