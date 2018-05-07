---
title: IMetaDataImport::GetParamProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 95850448504fd863f2726a7fb7574436476a6dc5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportgetparamprops-method"></a>IMetaDataImport::GetParamProps 메서드
지정한 ParamDef 토큰이 참조하는 매개 변수에 대한 메타데이터 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `tk`  
 [in] 에 대 한 메타 데이터를 반환 매개 변수를 나타내는 ParamDef 토큰입니다.  
  
 `pmd`  
 [out] 매개 변수를 사용 하는 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.  
  
 `pulSequence`  
 [out] 메서드 인수 목록에서 매개 변수의 서 수 위치입니다.  
  
 `szName`  
 [out] 매개 변수의 이름을 저장할 버퍼입니다.  
  
 `cchName`  
 [in] 요청된 된 크기의 와이드 문자에서 `szName`합니다.  
  
 `pchName`  
 [out] 반환 되는 크기의 와이드 문자에서 `szName`합니다.  
  
 `pdwAttr`  
 [out] 매개 변수와 연관 된 특성 플래그에 대 한 포인터입니다.  
  
 `pdwCPlusTypeFlag`  
 [out] 매개 변수가 지정 하는 플래그에 대 한 포인터는 <xref:System.ValueType>합니다.  
  
 `ppValue`  
 [out] 매개 변수에서 반환 된 상수 문자열에 대 한 포인터입니다.  
  
 `pcchValue`  
 [out] 크기 `ppValue` 와이드 문자 또는 경우에는 0에서 `ppValue` 문자열로 저장 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
