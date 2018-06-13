---
title: IMetaDataImport::FindMember 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 79c9a54a44ae1751cb8b1b57379ccfd6485f6e6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448193"
---
# <a name="imetadataimportfindmember-method"></a>IMetaDataImport::FindMember 메서드
토큰을 가져옵니다 memberdef 필드 또는 메서드가 포함 된에 대 한 지정 된 <xref:System.Type> 올려진 지정 된 이름 및 메타 데이터 서명을 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `td`  
 [in] 클래스 또는 검색할 멤버를 포함 하는 인터페이스에 대 한 TypeDef 토큰입니다. 이 값이 `mdTokenNil`, 전역 변수 또는 전역 함수에 대 한 조회가 수행 됩니다.  
  
 `szName`  
 [in] 검색할 멤버의 이름입니다.  
  
 `pvSigBlob`  
 [in] 멤버의 이진 메타 데이터 서명에 대 한 포인터입니다.  
  
 `cbSigBlob`  
 [in] 바이트 크기 `pvSigBlob`합니다.  
  
 `pmb`  
 [out] 일치 하는 MemberDef 토큰에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 바깥쪽 클래스 또는 인터페이스를 사용 하 여 멤버를 지정 (`td`), 해당 이름 (`szName`), 및 선택적 요소인 시그니처 (`pvSigBlob`). 클래스 또는 인터페이스에 이름이 같은 여러 멤버가 있을 수 있습니다. 이 경우 전달 해당 멤버의 시그니처에 고유 일치 항목을 찾습니다.  
  
 에 전달 된 서명을 `FindMember` 서명에 특정 범위에 바인딩되어 있기 때문에 현재 범위에서 생성 해야 합니다. 서명을 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰을 포함할 수 있습니다. 토큰은 로컬 TypeDef 테이블에 대 한 인덱스. 현재 범위의 컨텍스트 외부에서 런타임에 서명을 한에 입력으로 사용할 수는 없습니다 `FindMember`합니다.  
  
 `FindMember` 클래스 또는 인터페이스에 직접 정의 된 구성원을 찾습니다. 상속 된 멤버는 찾지 않습니다.  
  
> [!NOTE]
>  `FindMember` 도우미 메서드입니다. 호출 [imetadataimport:: Findmethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md)호출 하는 일치 하는 항목을 찾을 수 없는 경우; `FindMember` 다음 호출 [imetadataimport:: Findfield](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
