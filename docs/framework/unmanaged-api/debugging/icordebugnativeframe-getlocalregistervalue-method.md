---
title: ICorDebugNativeFrame::GetLocalRegisterValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b408654f367bc846dc878fb8412eb3e896dd192a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417088"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="adfc8-102">ICorDebugNativeFrame::GetLocalRegisterValue 메서드</span><span class="sxs-lookup"><span data-stu-id="adfc8-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>
<span data-ttu-id="adfc8-103">네이티브 프레임에 대 한 지정된 된 레지스터에 저장 된 지역 변수 또는 인수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="adfc8-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adfc8-104">구문</span><span class="sxs-lookup"><span data-stu-id="adfc8-104">Syntax</span></span>  
  
```  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="adfc8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="adfc8-105">Parameters</span></span>  
 `reg`  
 <span data-ttu-id="adfc8-106">[in] 값을 포함 하는 레지스터를 지정 하는 "CorDebugRegister" 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="adfc8-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="adfc8-107">[in] 참조 하는 이진 메타 데이터 서명의 크기를 지정 하는 정수는 `pvSigBlob` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="adfc8-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="adfc8-108">[in] A `PCCOR_SIGNATURE` 값의 형식의 이진 메타 데이터 서명을를 가리키는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="adfc8-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="adfc8-109">[out] 지정된 된 레지스터에 저장 된 검색 된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="adfc8-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adfc8-110">설명</span><span class="sxs-lookup"><span data-stu-id="adfc8-110">Remarks</span></span>  
 <span data-ttu-id="adfc8-111">`GetLocalRegisterValue` 네이티브 프레임이 또는-just-in-time (JIT) 메서드를 사용할 수 있으며-컴파일된 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="adfc8-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adfc8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="adfc8-112">Requirements</span></span>  
 <span data-ttu-id="adfc8-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="adfc8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adfc8-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="adfc8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="adfc8-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="adfc8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="adfc8-116">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adfc8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adfc8-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="adfc8-117">See Also</span></span>  
 
