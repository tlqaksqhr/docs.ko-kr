---
title: IMetaDataImport::GetMemberRefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d62b9be1bef16014e2870c15a232bb46d4daf10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportgetmemberrefprops-method"></a>IMetaDataImport::GetMemberRefProps 메서드
지정한 토큰이 참조하는 멤버와 연결된 메타데이터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,   
   [out] mdToken           *ptk,   
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pbSig   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mr`  
 [in] 반환할 연결 된 메타 데이터에 대 한 MemberRef 토큰입니다.  
  
 `ptk`  
 [out] TypeDef 또는 TypeRef, 또는 TypeSpec 토큰은 멤버 또는 멤버 또는 멤버를 나타내는 MethodDef 선언 하는 모듈 클래스를 나타내는 ModuleRef 토큰을 선언 하는 클래스를 나타내는입니다.  
  
 `szMember`  
 [out] 멤버의 이름에 대 한 문자열 버퍼입니다.  
  
 `cchMember`  
 [in] 요청된 된 크기의 와이드 문자에서 `szMember`합니다.  
  
 `pchMember`  
 [out] 반환 되는 크기의 와이드 문자에서 `szMember`합니다.  
  
 `ppvSibBlob`  
 [out] 멤버에 대 한 이진 메타 데이터 서명에 대 한 포인터입니다.  
  
 `pbSig`  
 [out] 바이트 크기 `ppvSigBlob`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
