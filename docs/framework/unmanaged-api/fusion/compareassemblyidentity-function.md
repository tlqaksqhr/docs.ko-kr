---
title: "CompareAssemblyIdentity 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type: COM
f1_keywords: CompareAssemblyIdentity
helpviewer_keywords: CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d9d7b4934d4295ee799fb13d3d749e6b977e644
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="compareassemblyidentity-function"></a>CompareAssemblyIdentity 함수
동일한 지 여부를 확인 하려면 두 개의 어셈블리 id를 비교 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pwzAssemblyIdentity1`  
 [in] 텍스트 비교에 사용 된 첫 번째 어셈블리의 id입니다.  
  
 `fUnified1`  
 [in] 에 대 한 사용자 지정 통합을 나타내는 부울 플래그 `pwzAssemblyIdentity1`합니다.  
  
 `pwzAssemblyIdentity2`  
 [in] 텍스트 비교에 사용 된 두 번째 어셈블리의 id입니다.  
  
 `fUnified2`  
 [in] 에 대 한 사용자 지정 통합을 나타내는 부울 플래그 `pwzAssemblyIdentity2`합니다.  
  
 `pfEquivalent`  
 [out] 두 명의 어셈블리가 동일한 지 여부를 나타내는 부울 플래그입니다.  
  
 `pResult`  
 [out] [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) 비교에 대 한 자세한 정보를 포함 하는 열거형입니다.  
  
## <a name="return-value"></a>반환 값  
 `pfEquivalent`두 명의 어셈블리가 동일한 지 여부를 나타내는 부울 값을 반환 합니다. `pResult`중 하나를 반환 된 `AssemblyComparisonResult` 값의 값에 대 한 보다 자세한 이유와 함께을 `pfEquivalent`합니다.  
  
## <a name="remarks"></a>설명  
 `CompareAssemblyIdentity`확인 여부 `pwzAssemblyIdentity1` 및 `pwzAssemblyIdentity2` 동일 합니다. `pfEquivalent`로 설정 되어 `true` 다음 조건 중 하나 이상:  
  
-   두 어셈블리 id는 동일 합니다. 강력한 이름의 어셈블리 어셈블리일 어셈블리 이름, 버전, 공개 키 토큰 및 culture 동일 하 게 됩니다. 간단한 이름의 어셈블리일 어셈블리 이름 및 문화권의 일치 내용이 해당 됩니다.  
  
-   두 어셈블리 id는.NET Framework에서 실행 되는 어셈블리를 참조 하십시오. 이 반환 `true` 경우 어셈블리 버전 번호가 일치 하지 않습니다.  
  
-   두 어셈블리는 관리 되는 어셈블리 하지만 `fUnified1` 또는 `fUnified2` 로 설정 된 `true`합니다.  
  
 `fUnified` 플래그가 모든 버전 번호는 강력한 이름의 어셈블리의 버전 번호는 강력한 이름의 어셈블리에 해당 간주 됩니다. 예를 들어 경우의 값 `pwzAssemblyIndentity1` 은 "MyAssembly, 버전 3.0.0.0, culture = neutral, publicKeyToken = =...", 및의 값 `fUnified1` 은 `true`, 모든 버전의 버전 3.0.0.0를 0.0.0.0 MyAssembly 되어야 함을 나타냅니다 동등한 것으로 처리 합니다. 이 경우 경우 `pwzAssemblyIndentity2` 동일한 어셈블리를 참조 `pwzAssemblyIndentity1`낮은 버전 번호를 가진 것 이라는 점을 제외 하면 `pfEquivalent` 로 설정 된 `true`합니다. 경우 `pwzAssemblyIdentity2` 더 높은 버전 번호를 참조 `pfEquivalent` 로 설정 된 `true` 경우에만 값을 `fUnified2` 은 `true`합니다.  
  
 `pResult` 매개 변수 같은 두 명의 어셈블리가으로 간주 하는 이유는 방법에 대 한 특정 정보를 포함 합니다. 자세한 내용은 참조 [AssemblyComparisonResult 열거형](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Fusion.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Fusion 전역 정적 함수](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [AssemblyComparisonResult 열거형](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)
