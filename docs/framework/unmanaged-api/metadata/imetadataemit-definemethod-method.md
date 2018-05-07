---
title: IMetaDataEmit::DefineMethod 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53fd830cdefda58d40f96f8662a80d1888d963dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitdefinemethod-method"></a>IMetaDataEmit::DefineMethod 메서드
지정 된 시그니처를 가진 메서드 또는 전역 함수에 대 한 정의 만들고 해당 메서드 정의에 토큰을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 `td`  
 [in] `mdTypedef` 부모 클래스 또는 부모 인터페이스 메서드의 토큰입니다. 설정 `td` 를 `mdTokenNil`, 전역 함수를 정의 하는 경우.  
  
 `szName`  
 [in] 유니코드에 사용 되는 멤버 이름입니다.  
  
 `dwMethodFlags`  
 [in] 값은 [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) 메서드 또는 전역 함수의 특성을 지정 하는 열거형입니다.  
  
 `pvSigBlob`  
 [in] 메서드 서명입니다. 서명은 제공 될 때 유지 됩니다. 모든 매개 변수에 대 한 추가 정보를 지정 해야 할 경우 사용 된 [imetadataemit:: Setparamprops](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) 메서드.  
  
 `cbSigBlob`  
 [in] 바이트 수 `pvSigBlob`합니다.  
  
 `ulCodeRVA`  
 [in] 코드의 주소입니다.  
  
 `dwImplFlags`  
 [in] 값은 [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) 메서드 구현 함수를 지정 하는 열거형입니다.  
  
 `pmd`  
 [out] 멤버 토큰입니다.  
  
## <a name="remarks"></a>설명  
 메타 데이터 API 사용 하면 호출자가 내보낸 지정 된 바깥쪽 클래스 또는 인터페이스에 지정 된 대로 동일한 순서로 메서드를 유지할 수는 `td` 매개 변수입니다.  
  
 사용과 관련 된 추가 정보 `DefineMethod` 아래 특정 매개 변수 설정을 지정 합니다.  
  
## <a name="slots-in-the-v-table"></a>슬롯, v-table에서  
 메서드 정의 사용 하 여 v-table 슬롯을 설정 하는 런타임입니다. 하나 이상의 슬롯 건너뛴, 해야 하는 경우에는 COM 인터페이스 레이아웃으로 패리티를 유지에 대 한 더미 메서드를 정의 슬롯 또는 슬롯 v-table;에서 공간을 차지 하도록 설정의 `dwMethodFlags` 에 `mdRTSpecialName` 값은 [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) 열거형으로 이름을 지정:  
  
 _VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*>  
  
 여기서 *SequenceNumber* 메서드의 시퀀스 번호 및 *CountOfSlots* 슬롯, v-table에서 생략할 수입니다. 경우 *CountOfSlots* 은 생략 하면 1이 사용 됩니다. 이러한 더미 메서드 또는 비관리 코드에서 호출할 수 되지 않으며 하려고 전화할 또는 비관리 코드에서 예외를 생성 합니다. 유일한 목적은 런타임에서 COM 통합에 대 한 생성 하는 v 테이블에서 공간을 차지 하는 것입니다.  
  
## <a name="duplicate-methods"></a>중복 메서드  
 중복 된 메서드를 정의 하면 안 됩니다. 즉, 호출 하면 안 `DefineMethod` 에 있는 값의 중복 집합으로는 `td`, `wzName`, 및 `pvSig` 매개 변수입니다. (이러한 세 가지 매개 변수를 함께 고유 하 게 메서드를 정의 합니다.). 그러나 메서드 정의 중 하나에 대해 설정 된 중복 세 번 사용할 수 있습니다는 `mdPrivateScope` 비트는 `dwMethodFlags` 매개 변수입니다. (의 `mdPrivateScope` 비트 의미 컴파일러가 메서드 정의에 대 한 참조를 생성 하지 것입니다.)  
  
## <a name="method-implementation-information"></a>메서드 구현 정보  
 메서드 구현에 대 한 정보는 메서드가 선언 된 시간에 알 수 없습니다 경우가 많습니다. 따라서 불필요 값을 전달 하는 `ulCodeRVA` 및 `dwImplFlags` 매개 변수를 호출할 때 `DefineMethod`합니다. 값을 통해 나중에 제공 될 수 있습니다. [imetadataemit:: Setmethodimplflags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) 또는 [imetadataemit:: Setrva](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)를 적절 하 게 합니다.  
  
 플랫폼 호출 (PInvoke) 또는 COM interop 시나리오 같은 일부 상황에서는 메서드 본문이 제공 되지 것입니다, 그리고 및 `ulCodeRVA` 0으로 설정 합니다. 이러한 상황에서는 메서드 하지 태그를 지정 해야 추상으로 런타임은 찾는 데 구현 하기 때문에 있습니다.  
  
## <a name="defining-a-method-for-pinvoke"></a>PInvoke에 대 한 메서드를 정의합니다.  
 PInvoke를 통해 호출할 수를 각 관리 되지 않는 함수에 대 한 대상 관리 되지 않는 기능을 나타내는 관리 되는 메서드를 정의 해야 합니다. 사용 하 여 관리 되는 메서드를 정의 하려면 `DefineMethod` PInvoke 사용 되는 방식에 따라 특정 값으로 설정 된 매개 변수 중 일부:  
  
-   PInvoke-관리 되지 않는 DLL에 상주 하는 외부 관리 되지 않는 메서드의 호출이 포함 됩니다.  
  
-   -로컬 PInvoke에는 현재 관리 되는 모듈에 포함 된 관리 되지 않는 네이티브 메서드의 호출이 포함 됩니다.  
  
 매개 변수 설정은 다음 표에 제공 됩니다.  
  
|매개 변수|True PInvoke에 대 한 값|로컬 PInvoke에 대 한 값|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||설정 `mdStatic`지우기; `mdSynchronized` 및 `mdAbstract`합니다.|  
|`pvSigBlob`|관리 되는 형식 유효한 공용 언어 런타임 (CLR) 메서드 서명을 사용할 수 있는 매개 변수를 사용 합니다.|유효한 매개 변수에 유효한 CLR 메서드 시그니처 관리 되는 형식입니다.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|설정 `miCil` 및 `miManaged`합니다.|설정 `miNative` 및 `miUnmanaged`합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
