---
title: IMetaDataImport::GetPropertyProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7312cbd31a04365801b0380d5914966f36679560
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportgetpropertyprops-method"></a>IMetaDataImport::GetPropertyProps 메서드
지정한 토큰이 나타내는 속성에 대 한 메타 데이터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,   
   [out] LPCWSTR           szProperty,   
   [in]  ULONG             cchProperty,   
   [out] ULONG             *pchProperty,   
   [out] DWORD             *pdwPropFlags,   
   [out] PCCOR_SIGNATURE   *ppvSig,   
   [out] ULONG             *pbSig,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,   
   [out] mdMethodDef       *pmdGetter,   
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,   
   [out] ULONG             *pcOtherMethod   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `prop`  
 [in] 에 대 한 메타 데이터를 반환할 속성을 나타내는 토큰입니다.  
  
 `pClass`  
 [out] 속성을 구현 하는 형식을 나타내는 TypeDef 토큰에 대 한 포인터입니다.  
  
 `szProperty`  
 [out] 속성 이름을 저장할 버퍼입니다.  
  
 `cchProperty`  
 [in] 와이드 문자에서 크기 `szProperty`합니다.  
  
 `pchProperty`  
 [out] 반환 된 와이드 문자의 수가 `szProperty`합니다.  
  
 `pdwPropFlags`  
 [out] 이 속성에 적용 하는 모든 특성 플래그에 대 한 포인터입니다. 이 값은의 비트 마스크는 [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) 열거 합니다.  
  
 `ppvSig`  
 [out] 속성의 메타 데이터 서명에 대 한 포인터입니다.  
  
 `pbSig`  
 [out] 반환 된 바이트 수가 `ppvSig`합니다.  
  
 `pdwCPlusTypeFlag`  
 [out] 속성의 기본값은 상수 종류를 지정 하는 플래그입니다. CorElementType 열거형에서이 값은입니다.  
  
 `ppDefaultValue`  
 [out] 이 속성에 대 한 기본값을 저장 하는 바이트에 대 한 포인터입니다.  
  
 `pcchDefaultValue`  
 [out] 와이드 문자에서 크기 `ppDefaultValue`경우 `pdwCPlusTypeFlag` ELEMENT_TYPE_STRING;는 그렇지 않은 경우이 값은와 관련이 없습니다. 길이 경우 `ppDefaultValue` 변수로 지정 된 형식에서 유추 `pdwCPlusTypeFlag`합니다.  
  
 `pmdSetter`  
 [out] 속성에 대 한 set 접근자 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.  
  
 `pmdGetter`  
 [out] 속성 get 접근자 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.  
  
 `rmdOtherMethod`  
 [out] 배열 속성에 연결 된 다른 메서드를 나타내는 MethodDef 토큰입니다.  
  
 `cMax`  
 [in] `rmdOtherMethod` 배열의 최대 크기입니다. 배열을 모든 메서드를 포함할 수 있는 크기를 제공 하지 않는 경우 경고 없이 건너뜁니다.  
  
 `pcOtherMethod`  
 [out] 반환 된 MethodDef 토큰 수 `rmdOtherMethod`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
