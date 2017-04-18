---
title: "WIF 구성 스키마 규칙 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f7864356-f72f-4cae-995c-18e0431f8a58
caps.latest.revision: 3
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 3
---
# WIF 구성 스키마 규칙
이 여기서 소리치 \(Windows Identity Foundation 더\) 구성 항목 전체에서 사용 되는 규칙에 설명 하 고 몇 가지 일반적인 기능에 설명 하 고 특성 사용에 [\<system.identityModel\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) , [\<system.identityModel.services\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) 섹션.  
  
<a name="BKMK_Modes"></a>   
## 모드  
 소리치 더 구성 요소의 대부분은 `mode` 특성.  이 특성은 일반적으로 클래스는 특정 부분의 처리에 사용 되며 수 있는 구성 요소는 현재 요소의 자식 요소로 제어 합니다.  모드 설정 때문에 구성 파일에 포함 된 요소를 무시 하려면 구성 오류가 발생 합니다.  
  
<a name="BKMK_TimespanValues"></a>   
## Timespan 값입니다.  
 위치 <xref:System.TimeSpan> 됩니다 특성 형식으로 사용을 참조 하십시오의 <xref:System.TimeSpan.Parse%28System.String%29> 메서드 허용 되는 형식을 참조 하십시오.  이 형식은 다음과 같은 사양에 따릅니다.  
  
```  
[ws][-]{ d | [d.]hh:mm[:ss[.ff]] }[ws]  
```  
  
 예를 들어, "30" "30.00:00", "30.00:00:00" 모든 30 일을 의미 합니다. "00: 05" 하 고 "00: 05: 00", "0.00:05:00.00" 모든 5 분을 의미 합니다.  
  
<a name="BKMK_CertificateReferences"></a>   
## 인증서 참조  
 여러 요소를 사용 하 여 인증서에 대 한 참조 걸릴를 `<certificateReference>` 요소.  인증서를 참조 하는 경우 다음과 같은 특성을 사용할 수 있습니다.  
  
|||  
|-|-|  
|`storeLocation`|값은 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 열거형: `CurrentUser` 또는 `CurrentMachine`.|  
|`storeName`|값은 <xref:System.Security.Cryptography.X509Certificates.StoreName> 열거형입니다. 이 컨텍스트에 대 한 가장 유용한 `My` 및 `TrustedPeople`.|  
|`x509FindType`|값은 <xref:System.Security.Cryptography.X509Certificates.X509FindType> 열거형입니다. 이 컨텍스트에 대 한 가장 유용한 `FindBySubjectName` 및 `FindByThumbprint`.  오류 발생 가능성을 제거 하는 것입니다는 `FindByThumbprint` 종류는 프로덕션 환경에서 사용할 수 있습니다.|  
|`findValue`|기준으로 인증서를 찾는 데 사용 되는 값은 `x509FindType` 특성.  오류 발생 가능성을 제거 하는 것입니다는 `FindByThumbprint` 종류는 프로덕션 환경에서 사용할 수 있습니다.  때 `FindByThumbPrint` ,이 특성 사용 인증서 손도장. 16 진수 문자열 형태의 값 지정 예를 들어, "97249e1a5fa6bee5e515b82111ef524a4c91583f"가 됩니다.|  
  
<a name="BKMK_CustomTypeReferences"></a>   
## 사용자 정의 형식 참조  
 여러 요소를 사용 하 여 사용자 지정 형식을 참조는 `type` 특성.  이 특성은 사용자 정의 형식의 이름을 지정 해야 합니다.  전역 어셈블리 캐시 \(GAC\)에서 형식을 참조 하려면 강력한 이름을 사용 합니다.  저장소에서 어셈블리에서 형식을 참조 합니다 \/ 디렉터리에 간단한 정규화 된 어셈블리 참조를 사용할 수 있습니다.  App\_code에 정의 된 형식\/없음 한정 어셈블리와 형식 이름을 단순히 지정 디렉터리도 참조할 수 있습니다.  
  
 가 제공 하는 사용자 정의 형식을 지정 된 형식에서 파생 된 해야는 `public` \(0 인수\) 기본 생성자입니다.  
  
## 참고 항목  
 [\<system.identityModel\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)   
 [\<system.identityModel.services\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)