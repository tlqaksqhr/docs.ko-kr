---
title: "IMetaDataEmit::DefineMethod 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineMethod
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fa136f5e6669e58ef709db5b53f538804cfcac2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="1daa7-102">IMetaDataEmit::DefineMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="1daa7-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="1daa7-103">지정 된 시그니처를 가진 메서드 또는 전역 함수에 대 한 정의 만들고 해당 메서드 정의에 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1daa7-104">구문</span><span class="sxs-lookup"><span data-stu-id="1daa7-104">Syntax</span></span>  
  
```  
HRESULT DefineMethod (      
    [in]  mdTypeDef         td,   
    [in]  LPCWSTR           szName,   
    [in]  DWORD             dwMethodFlags,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [in]  ULONG             ulCodeRVA,   
    [in]  DWORD             dwImplFlags,   
    [out] mdMethodDef      *pmd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1daa7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1daa7-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="1daa7-106">[in] `mdTypedef` 부모 클래스 또는 부모 인터페이스 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="1daa7-107">설정 `td` 를 `mdTokenNil`, 전역 함수를 정의 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="1daa7-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="1daa7-108">[in] 유니코드에 사용 되는 멤버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="1daa7-109">[in] 값은 [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) 메서드 또는 전역 함수의 특성을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="1daa7-110">[in] 메서드 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-110">[in] The method signature.</span></span> <span data-ttu-id="1daa7-111">서명은 제공 될 때 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="1daa7-112">모든 매개 변수에 대 한 추가 정보를 지정 해야 할 경우 사용 된 [imetadataemit:: Setparamprops](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="1daa7-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="1daa7-113">[in] 바이트 수 `pvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="1daa7-114">[in] 코드의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="1daa7-115">[in] 값은 [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) 메서드 구현 함수를 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="1daa7-116">[out] 멤버 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1daa7-117">설명</span><span class="sxs-lookup"><span data-stu-id="1daa7-117">Remarks</span></span>  
 <span data-ttu-id="1daa7-118">메타 데이터 API 사용 하면 호출자가 내보낸 지정 된 바깥쪽 클래스 또는 인터페이스에 지정 된 대로 동일한 순서로 메서드를 유지할 수는 `td` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="1daa7-119">사용과 관련 된 추가 정보 `DefineMethod` 아래 특정 매개 변수 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="1daa7-120">슬롯, v-table에서</span><span class="sxs-lookup"><span data-stu-id="1daa7-120">Slots in the V-table</span></span>  
 <span data-ttu-id="1daa7-121">메서드 정의 사용 하 여 v-table 슬롯을 설정 하는 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="1daa7-122">하나 이상의 슬롯 건너뛴, 해야 하는 경우에는 COM 인터페이스 레이아웃으로 패리티를 유지에 대 한 더미 메서드를 정의 슬롯 또는 슬롯 v-table;에서 공간을 차지 하도록 설정의 `dwMethodFlags` 에 `mdRTSpecialName` 값은 [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) 열거형으로 이름을 지정:</span><span class="sxs-lookup"><span data-stu-id="1daa7-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="1daa7-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span><span class="sxs-lookup"><span data-stu-id="1daa7-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>  
  
 <span data-ttu-id="1daa7-124">여기서 *SequenceNumber* 메서드의 시퀀스 번호 및 *CountOfSlots* 슬롯, v-table에서 생략할 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="1daa7-125">경우 *CountOfSlots* 은 생략 하면 1이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="1daa7-126">이러한 더미 메서드 또는 비관리 코드에서 호출할 수 되지 않으며 하려고 전화할 또는 비관리 코드에서 예외를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="1daa7-127">유일한 목적은 런타임에서 COM 통합에 대 한 생성 하는 v 테이블에서 공간을 차지 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="1daa7-128">중복 메서드</span><span class="sxs-lookup"><span data-stu-id="1daa7-128">Duplicate Methods</span></span>  
 <span data-ttu-id="1daa7-129">중복 된 메서드를 정의 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-129">You should not define duplicate methods.</span></span> <span data-ttu-id="1daa7-130">즉, 호출 하면 안 `DefineMethod` 에 있는 값의 중복 집합으로는 `td`, `wzName`, 및 `pvSig` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="1daa7-131">(이러한 세 가지 매개 변수를 함께 고유 하 게 메서드를 정의 합니다.).</span><span class="sxs-lookup"><span data-stu-id="1daa7-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="1daa7-132">그러나 메서드 정의 중 하나에 대해 설정 된 중복 세 번 사용할 수 있습니다는 `mdPrivateScope` 비트는 `dwMethodFlags` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="1daa7-133">(의 `mdPrivateScope` 비트 의미 컴파일러가 메서드 정의에 대 한 참조를 생성 하지 것입니다.)</span><span class="sxs-lookup"><span data-stu-id="1daa7-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="1daa7-134">메서드 구현 정보</span><span class="sxs-lookup"><span data-stu-id="1daa7-134">Method Implementation Information</span></span>  
 <span data-ttu-id="1daa7-135">메서드 구현에 대 한 정보는 메서드가 선언 된 시간에 알 수 없습니다 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="1daa7-136">따라서 불필요 값을 전달 하는 `ulCodeRVA` 및 `dwImplFlags` 매개 변수를 호출할 때 `DefineMethod`합니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="1daa7-137">값을 통해 나중에 제공 될 수 있습니다. [imetadataemit:: Setmethodimplflags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) 또는 [imetadataemit:: Setrva](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)를 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="1daa7-138">플랫폼 호출 (PInvoke) 또는 COM interop 시나리오 같은 일부 상황에서는 메서드 본문이 제공 되지 것입니다, 그리고 및 `ulCodeRVA` 0으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="1daa7-139">이러한 상황에서는 메서드 하지 태그를 지정 해야 추상으로 런타임은 찾는 데 구현 하기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="1daa7-140">PInvoke에 대 한 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="1daa7-141">PInvoke를 통해 호출할 수를 각 관리 되지 않는 함수에 대 한 대상 관리 되지 않는 기능을 나타내는 관리 되는 메서드를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="1daa7-142">사용 하 여 관리 되는 메서드를 정의 하려면 `DefineMethod` PInvoke 사용 되는 방식에 따라 특정 값으로 설정 된 매개 변수 중 일부:</span><span class="sxs-lookup"><span data-stu-id="1daa7-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
-   <span data-ttu-id="1daa7-143">PInvoke-관리 되지 않는 DLL에 상주 하는 외부 관리 되지 않는 메서드의 호출이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
-   <span data-ttu-id="1daa7-144">-로컬 PInvoke에는 현재 관리 되는 모듈에 포함 된 관리 되지 않는 네이티브 메서드의 호출이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="1daa7-145">매개 변수 설정은 다음 표에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="1daa7-146">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1daa7-146">Parameter</span></span>|<span data-ttu-id="1daa7-147">True PInvoke에 대 한 값</span><span class="sxs-lookup"><span data-stu-id="1daa7-147">Values for true PInvoke</span></span>|<span data-ttu-id="1daa7-148">로컬 PInvoke에 대 한 값</span><span class="sxs-lookup"><span data-stu-id="1daa7-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="1daa7-149">설정 `mdStatic`지우기; `mdSynchronized` 및 `mdAbstract`합니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="1daa7-150">관리 되는 형식 유효한 공용 언어 런타임 (CLR) 메서드 서명을 사용할 수 있는 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="1daa7-151">유효한 매개 변수에 유효한 CLR 메서드 시그니처 관리 되는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="1daa7-152">0</span><span class="sxs-lookup"><span data-stu-id="1daa7-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="1daa7-153">설정 `miCil` 및 `miManaged`합니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="1daa7-154">설정 `miNative` 및 `miUnmanaged`합니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1daa7-155">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1daa7-155">Requirements</span></span>  
 <span data-ttu-id="1daa7-156">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1daa7-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1daa7-157">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1daa7-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1daa7-158">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="1daa7-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1daa7-159">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1daa7-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1daa7-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1daa7-160">See Also</span></span>  
 [<span data-ttu-id="1daa7-161">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1daa7-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="1daa7-162">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1daa7-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
