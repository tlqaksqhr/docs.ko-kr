---
title: 개체 식별자를 암호화 알고리즘에 매핑
ms.date: 03/30/2017
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7801c55cf6b3334347788013d9052038d5d2f3ec
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756620"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a>개체 식별자를 암호화 알고리즘에 매핑
디지털 서명 프로그램에서 간에 전송 될 때 데이터를 손상 되지 않은 것을 확인 합니다. 일반적으로 서명할 데이터의 해시에는 수치 연산 함수를 적용 하 여 디지털 서명을 계산 됩니다. 서명할 해시 값의 서식을 지정할 때 일부 디지털 서명 알고리즘 서식 지정 작업의 일부로 ASN.1 개체 식별자 (OID)을 추가 합니다. OID는 해시를 계산 하는 데 사용 된 알고리즘을 식별 합니다. 알고리즘 사용자 지정 알고리즘을 사용 하는 암호화 메커니즘을 확장 하는 개체 식별자를 매핑할 수 있습니다. 다음 예제에서는 새 해시 알고리즘에 대 한 개체 식별자를 매핑하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MyNewHash="MyNewHashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="NewHash" class="MyNewHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.14.33.42.46"  name="NewHash"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 [ \<r y > 요소](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) 두 특성을 포함 합니다. **OID** 특성 개체 식별자입니다. **이름** 특성의 값은는 **이름** 에서 특성의 [ \<r y > 요소](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)합니다. 개체 식별자는 단순한 이름에 매핑될 수 전에 클래스에 알고리즘 이름을 매핑이 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [암호화 클래스 구성](../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
