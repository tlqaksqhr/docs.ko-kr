---
title: "ICorDebugNativeFrame::GetLocalDoubleRegisterValue 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75b8c4d5551c9624852f1e0f730d1215236608de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a><span data-ttu-id="559d7-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue 메서드</span><span class="sxs-lookup"><span data-stu-id="559d7-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue Method</span></span>
<span data-ttu-id="559d7-103">네이티브 프레임에 대 한 지정 된 두 레지스터에 저장 된 지역 변수 또는 인수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="559d7-103">Gets the value of an argument or local variable that is stored in the two specified registers for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="559d7-104">구문</span><span class="sxs-lookup"><span data-stu-id="559d7-104">Syntax</span></span>  
  
```  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="559d7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="559d7-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="559d7-106">[in] 값의 많은 단어를 포함 하는 레지스터를 지정 하는 "CorDebugRegister" 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="559d7-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordReg`  
 <span data-ttu-id="559d7-107">[in] 값은 `CorDebugRegister` 값의 낮은 단어를 포함 하는 레지스터를 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="559d7-107">[in] A value of the `CorDebugRegister` enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="559d7-108">[in] 참조 하는 이진 메타 데이터 서명의 크기를 지정 하는 정수는 `pvSigBlob` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="559d7-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="559d7-109">[in] A `PCCOR_SIGNATURE` 값의 형식의 이진 메타 데이터 서명을를 가리키는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="559d7-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="559d7-110">[out] 지정 된 레지스터에 저장 된 검색 된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="559d7-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified registers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="559d7-111">설명</span><span class="sxs-lookup"><span data-stu-id="559d7-111">Remarks</span></span>  
 <span data-ttu-id="559d7-112">`GetLocalDoubleRegisterValue` 네이티브 프레임이 또는-just-in-time (JIT) 메서드를 사용할 수 있으며-컴파일된 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="559d7-112">The `GetLocalDoubleRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="559d7-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="559d7-113">Requirements</span></span>  
 <span data-ttu-id="559d7-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="559d7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="559d7-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="559d7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="559d7-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="559d7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="559d7-117">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="559d7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="559d7-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="559d7-118">See Also</span></span>  
 
