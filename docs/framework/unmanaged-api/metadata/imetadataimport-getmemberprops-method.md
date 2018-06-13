---
title: IMetaDataImport::GetMemberProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d93763da2afbbdb1e738c802ba172e9f16e5f7af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448460"
---
# <a name="imetadataimportgetmemberprops-method"></a>IMetaDataImport::GetMemberProps 메서드
이름, 이진 서명 및 상대 가상 주소 등의 메타 데이터 정보를 가져옵니다는 <xref:System.Type> 지정한 메타 데이터 토큰에서 참조 하는 멤버입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] ULONG             *pulCodeRVA,   
   [out] DWORD             *pdwImplFlags,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mb`  
 [in] 에 대 한 연결 된 메타 데이터를 가져올 멤버를 참조 하는 토큰입니다.  
  
 `pClass`  
 [out] 멤버의 클래스를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.  
  
 `szMember`  
 [out] 멤버의 이름입니다.  
  
 `cchMember`  
 [in] 와이드 문자에서 크기는 `szMember` 버퍼입니다.  
  
 `pchMember`  
 [out] 반환된 된 이름의 와이드 문자에서 크기입니다.  
  
 `pdwAttr`  
 [out] 멤버에 적용 된 모든 플래그 값입니다.  
  
 `ppvSigBlob`  
 [out] 멤버의 이진 메타 데이터 서명에 대 한 포인터입니다.  
  
 `pcbSigBlob`  
 [out] 바이트 크기 `ppvSigBlob`합니다.  
  
 `pulCodeRVA`  
 [out] 멤버의 상대 가상 주소에 대 한 포인터입니다.  
  
 `pdwImplFlags`  
 [out] 멤버에 연결 된 모든 메서드 구현 플래그입니다.  
  
 `pdwCPlusTypeFlag`  
 [out] 표시 하는 플래그는 <xref:System.ValueType>합니다.  
  
 `ppValue`  
 [out] 이 멤버에서 반환 되는 상수 문자열 값입니다.  
  
 `pcchValue`  
 [out] 크기의 문자 `ppValue`, 경우에는 0 또는 `ppValue` 문자열로 저장 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
