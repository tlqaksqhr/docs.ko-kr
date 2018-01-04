---
title: "IMetaDataImport::FindMemberRef 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindMemberRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a94fb09e1ff62abac9dd716257ba75542453707e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindmemberref-method"></a>IMetaDataImport::FindMemberRef 메서드
지정 된로 묶인 멤버에 대 한 MemberRef 토큰에 대 한 포인터 참조 즉 가져옵니다 <xref:System.Type> 올려진 지정 된 이름 및 메타 데이터 서명을 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `td`  
 [in] 해당 클래스 또는 인터페이스에 대 한 검색에 대 한 멤버 참조를 포함 하는 TypeRef 토큰입니다. 이 값이 `mdTokenNil`, 전역 변수 또는 전역 함수 참조에 대 한 조회가 수행 됩니다.  
  
 `szName`  
 [in] 검색할 멤버 참조의 이름입니다.  
  
 `pvSigBlob`  
 [in] 멤버 참조가의 이진 메타 데이터 서명에 대 한 포인터입니다.  
  
 `cbSigBlob`  
 [in] 바이트 크기 `pvSigBlob`합니다.  
  
 `pmr`  
 [out] 일치 하는 MemberRef 토큰에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 바깥쪽 클래스 또는 인터페이스를 사용 하 여 멤버를 지정 (`td`), 해당 이름 (`szName`), 및 선택적 요소인 시그니처 (`pvSigBlob`).  
  
 에 전달 된 서명을 `FindMemberRef` 서명에 특정 범위에 바인딩되어 있기 때문에 현재 범위에서 생성 해야 합니다. 서명을 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰을 포함할 수 있습니다. 토큰은 로컬 TypeDef 테이블에 대 한 인덱스. 현재 범위의 컨텍스트 외부에서 런타임에 서명을 한에 대 한 입력으로 사용할 수는 없습니다 `FindMemberRef`합니다.  
  
 `FindMemberRef`클래스 또는 인터페이스에 직접 정의 된 멤버 참조를 찾습니다. 상속 된 멤버 참조는 찾지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
