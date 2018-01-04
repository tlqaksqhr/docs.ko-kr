---
title: "IMetaDataImport2::GetVersionString 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetVersionString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ccf168473c1182e4b7d57d52930d90084eaa2dd8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2getversionstring-method"></a>IMetaDataImport2::GetVersionString 메서드
어셈블리를 빌드하는 데 사용 된 런타임 버전 번호를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pwzBuf`  
 [out] 버전을 지정 하 여 문자열을 저장할 배열입니다.  
  
 `ccBufSize`  
 [in] 와이드 문자에서 크기의는 `pwzBuf` 배열입니다.  
  
 `pccBufSize`  
 [out] 반환 되는 null 종결자를 포함 하 여 와이드 문자 수는 `pwzBuf` 배열입니다.  
  
## <a name="remarks"></a>설명  
 `GetVersionString` 메서드는 현재 메타 데이터 범위의 빌드 버전을 가져옵니다. 범위를 저장 한 적 빌드 대상 버전이 갖지 않습니다 및 빈 문자열이 반환 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
