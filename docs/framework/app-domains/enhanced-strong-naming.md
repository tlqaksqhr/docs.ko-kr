---
title: "향상된 강력한 이름 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "강력한 이름[.NET Framework], 개선됨"
  - "강력한 이름의 어셈블리"
ms.assetid: 6cf17a82-62a1-4f6d-8d5a-d7d06dec2bb5
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 향상된 강력한 이름 지정
강력한 이름 서명은 어셈블리를 식별하기 위한 .NET Framework의 ID 메커니즘입니다.  일반적으로 작성자\(서명자\)에서 수신자\(검증 도구\)로 전달되는 데이터의 무결성을 확인하는 데 일반적으로 사용되는 공개 키 디지털 서명입니다.  이 서명은 어셈블리의 고유 ID로 사용되며 어셈블리에 대한 참조가 모호하지 않은지 확인합니다.  어셈블리는 빌드 프로세스의 일부로 서명되고 로드될 때 확인됩니다.  
  
 강력한 이름 서명은 악의적인 당사자가 어셈블리를 조작한 다음 원래 서명자의 키를 사용하여 어셈블리에 다시 서명하지 않도록 합니다.  그러나 강력한 이름 키는 게시자에 대한 안정적인 정보를 포함하지도, 인증 계층 구조를 포함하지도 않습니다.  강력한 이름 서명은 어셈블리에 서명한 사람의 신뢰성을 보증하거나 해당 사람이 키의 합법적인 소유자인지 여부를 나타내지 못합니다. 이는 키의 소유자가 어셈블리에 서명했다는 것만 나타냅니다.  따라서 강력한 이름 서명을 타사 코드를 신뢰하는 데 대한 보안 유효성 검사기로 사용하지 않는 것이 좋습니다.  코드 인증을 위해 Microsoft Authenticode를 사용하기를 권장합니다.  
  
## 기존의 강력한 이름의 제한점  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 이전 버전에서 사용되는 강력한 명명 기술에는 다음과 같은 단점이 있습니다.  
  
-   키는 지속적으로 공격을 받으며 개선된 기술과 하드웨어가 개인기가 공개 키로부터 유추되기 쉽도록 합니다.  공격으로부터 보호하기 위해서는 더 큰 키가 필요합니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 이전의 .NET Framework 버전은 모든 크기 키\(기본 크기는 1024비트\)로 로그인하는 기능을 제공하지만, 새로운 키로 어셈블리에 로그인하면 어셈블리의 오래된 ID를 참조하는 모든 바이너리를 차단합니다.  따라서 호환성을 유지하려는 경우 서명 키의 크기를 업그레이드하기가 매우 어렵습니다.  
  
-   강력한 이름 서명은 SHA\-1 알고리즘만 지원합니다.  SHA\-1은 해시 보안 응용 프로그램에 적합한 것으로 최근에 발견되었습니다.  따라서 강력한 알고리즘\(sha\-256 이상\)이 필요합니다.  SHA\-1이 FIPS 규격을 상실하여 FIPS 규격 소프트웨어 및 알고리즘만 사용하도록 선택하는 사용자에게 문제가 발생합니다.  
  
## 향상된 강력한 이름의 장점  
 향상된 강력한 이름의 주요 장점은 기존 강력한 이름과 호환되며 ID 하나를 다른 ID와 동일하게 클레임할 수 있다는 점입니다.  
  
-   기존에 서명된 어셈블리가 있는 개발자는 SHA\-2 알고리즘으로 ID를 마이그레이션하면서 기존 ID를 참조하는 어셈블리와의 호환성을 유지할 수 있습니다.  
  
-   새로운 어셈블리를 만들고 기존의 강력한 이름 서명과 관련이 없는 개발자는 더 안전한 SHA\-2 알고리즘을 사용하고 평소와 마찬가지로 어셈블리에 서명할 수 있습니다.  
  
## 향상된 강력한 이름 사용  
 강력한 이름 키는 id 키 및 서명 키를 구성합니다.  어셈블리는 서명 키로 서명되고 ID키로 식별됩니다.  [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]이전에는, 두 개의 키가 동일했습니다.  [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]부터 시작하여 ID 키는 이전 .NET Framework 버전과 동일하게 유지되지만 서명 키는 보다 강력한 해시 알고리즘으로 향상됩니다.  또한 서명 키는 카운터 서명을 만드는 ID 키를 사용하여 서명합니다.  
  
 <xref:System.Reflection.AssemblySignatureKeyAttribute> 특성은 어셈블리 메타 데이터를 활성화하여 어셈블리 ID에 대한 기존 공개 키를 사용합니다. 이를 통해 기존 어셈블리 참조가 작업을 계속할 수 있습니다.  <xref:System.Reflection.AssemblySignatureKeyAttribute> 특성은 카운터 서명을 사용하여 새 서명 키의 소유자가 기존 ID 키의 소유자일 수 있도록 합니다.  
  
### 마이그레이션 키를 사용하지 않고 SHA\-2로 서명합니다.  
 명령 프롬프트 창에서 다음 명령을 실행하여 강력한 이름 서명을 마이그레이션하지 않고 어셈블리에 서명합니다.  
  
1.  필요한 경우 새 ID 키를 생성합니다.  
  
    ```  
    sn -k IdentityKey.snk  
    ```  
  
2.  ID 공개 키를 추출하고 이 키로 서명할 때 SHA\-2 알고리즘을 사용해야 함을 지정합니다.  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk sha256  
    ```  
  
3.  ID 공개 키 파일을 사용하여 어셈블리 서명을 연기합니다.  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
4.  전체 ID 키 쌍을 사용하여 어셈블리에 다시 서명합니다.  
  
    ```  
    sn -Ra MyAssembly.exe IdentityKey.snk  
    ```  
  
### SHA\-2와 마이그레이션 키를 사용하여 서명합니다.  
 명령 프롬프트 창에서 다음 명령을 실행하여 마이그레이션된 강력한 이름 서명을 사용하여 어셈블리에 서명합니다.  
  
1.  필요한 경우 ID 및 서명 키 쌍을 생성합니다.  
  
    ```  
    sn -k IdentityKey.snk  
    sn -k SignatureKey.snk  
    ```  
  
2.  서명 공개 키를 추출하고 이 키로 서명할 때 SHA\-2 알고리즘을 사용해야 함을 지정합니다.  
  
    ```  
    sn -p SignatureKey.snk SignaturePubKey.snk sha256  
    ```  
  
3.  카운터 서명을 생성하는 해시 알고리즘을 결정하는 ID 공개 키를 추출합니다.  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk  
    ```  
  
4.  <xref:System.Reflection.AssemblySignatureKeyAttribute> 특성에 대한 매개 변수를 생성하고 어셈블리에 특성을 연결합니다.  
  
    ```  
    sn -ac IdentityPubKey.snk IdentityKey.snk SignaturePubKey.snk  
    ```  
  
5.  ID 공개 키를 사용하여 어셈블리 서명을 연기합니다.  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
  
    ```  
  
6.  서명 키 쌍을 사용하여 어셈블리에 완전히 서명합니다.  
  
    ```  
    sn -Ra MyAssembly.exe SignatureKey.snk  
    ```  
  
## 참고 항목  
 [강력한 이름의 어셈블리 만들기 및 사용](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)