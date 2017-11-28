---
title: "개체 식별자를 암호화 알고리즘에 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: dbfe394193925e38dad774d39d79ac813abef22a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="cac40-102">개체 식별자를 암호화 알고리즘에 매핑</span><span class="sxs-lookup"><span data-stu-id="cac40-102">Mapping Object Identifiers to Cryptography Algorithms</span></span>
<span data-ttu-id="cac40-103">디지털 서명 프로그램에서 간에 전송 될 때 데이터를 손상 되지 않은 것을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cac40-103">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="cac40-104">일반적으로 서명할 데이터의 해시에는 수치 연산 함수를 적용 하 여 디지털 서명을 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cac40-104">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="cac40-105">서명할 해시 값의 서식을 지정할 때 일부 디지털 서명 알고리즘 서식 지정 작업의 일부로 ASN.1 개체 식별자 (OID)을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cac40-105">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="cac40-106">OID는 해시를 계산 하는 데 사용 된 알고리즘을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="cac40-106">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="cac40-107">알고리즘 사용자 지정 알고리즘을 사용 하는 암호화 메커니즘을 확장 하는 개체 식별자를 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cac40-107">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="cac40-108">다음 예제에서는 새 해시 알고리즘에 대 한 개체 식별자를 매핑하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cac40-108">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
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
  
 <span data-ttu-id="cac40-109">[ \<r y > 요소](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) 두 특성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cac40-109">The [\<oidEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="cac40-110">**OID** 특성 개체 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="cac40-110">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="cac40-111">**이름** 특성의 값은는 **이름** 에서 특성의 [ \<r y > 요소](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cac40-111">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="cac40-112">개체 식별자는 단순한 이름에 매핑될 수 전에 클래스에 알고리즘 이름을 매핑이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cac40-112">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac40-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cac40-113">See Also</span></span>  
 [<span data-ttu-id="cac40-114">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="cac40-114">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [<span data-ttu-id="cac40-115">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="cac40-115">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
