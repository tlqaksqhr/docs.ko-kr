---
title: "방법: 개발 중 사용할 임시 인증서 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a1b386906c1d493a23d8a58f3540758d3ae0d26e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a>방법: 개발 중 사용할 임시 인증서 만들기
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하여 보안 서비스 또는 클라이언트를 개발하는 경우 자격 증명으로 사용할 X.509 인증서를 제공해야 할 수도 있습니다. 일반적으로 인증서는 루트 인증 기관이 컴퓨터의 신뢰할 수 있는 루트 인증 기관 저장소에 있는 인증서 체인의 일부입니다. 인증서 체인을 사용하면 일반적으로 루트 인증 기관이 조직 또는 비즈니스 사업부에 있는 인증서 집합의 범위를 지정할 수 있습니다. 개발 시 이를 에뮬레이트하려면 보안 요구 사항에 맞는 두 개의 인증서를 만듭니다. 첫 번째 인증서는 신뢰할 수 있는 루트 인증 기관 저장소에 있는 자체 서명된 인증서이고, 두 번째 인증서는 첫 번째 인증서에서 만들어지고 로컬 컴퓨터 위치의 개인 저장소나 현재 사용자 위치의 개인 저장소에 있습니다. 이 항목에서는 [SDK에서 제공하는](http://go.microsoft.com/fwlink/?LinkId=248185)인증서 작성 도구(MakeCert.exe) [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 를 사용하여 이러한 두 인증서를 만드는 단계를 안내합니다.  
  
> [!IMPORTANT]
>  인증서 작성 도구가 생성하는 인증서는 테스트 용도로만 제공됩니다. 서비스 또는 클라이언트를 배포할 때는 인증 기관에서 제공하는 적절한 인증서를 사용해야 합니다. 조직의 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 인증서 서버나 타사 인증서일 수 있습니다.  
>   
>  기본적으로는 [Makecert.exe (인증서 작성 도구)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) 해당 루트 기관 라고 하는 인증서를 만들며 "루트 에이전시**."** 라고 하는 인증서를 만듭니다. "루트 에이전시"는 신뢰할 수 있는 루트 인증 기관 저장소에 없으므로 해당 인증서를 신뢰할 수 없습니다. 신뢰할 수 있는 루트 인증 기관 저장소에 배치되는 자체 서명된 인증서를 만들면 배포 환경을 보다 근접하게 시뮬레이션하는 개발 환경을 만들 수 있습니다.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] 는 [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)을 참조하세요. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] 는 [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)을 참조하세요. Microsoft Authenticode 기술을 사용하는 방법에 대한 자습서는 [Authenticode Overviews and Tutorials](http://go.microsoft.com/fwlink/?LinkId=88919)를 참조하십시오.  
  
### <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a>자체 서명된 루트 인증 기관 인증서를 만들고 개인 키를 내보내려면  
  
1.  MakeCert.exe 도구에 다음 스위치를 사용합니다.  
  
    1.  `-n` `subjectName`. 주체 이름을 지정합니다. 규칙에 따라 주체 이름 앞에 "일반 이름"을 나타내는 "CN = "을 붙입니다.  
  
    2.  `-r`. 인증서가 자체 서명되도록 지정합니다.  
  
    3.  `-sv` `privateKeyFile`. 개인 키 컨테이너를 포함하는 파일을 지정합니다.  
  
     예를 들어 다음 명령은 주체 이름 "CN=TempCA"를 사용하여 자체 서명된 인증서를 만듭니다.  
  
    ```  
    makecert -n "CN=TempCA" -r -sv TempCA.pvk TempCA.cer  
    ```  
  
     암호를 제공하여 개인 키를 보호하라는 메시지가 표시됩니다. 이 암호는 이 루트 인증서로 서명된 인증서를 만들 때 필요합니다.  
  
### <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a>루트 인증 기관 인증서로 서명된 새 인증서를 만들려면  
  
1.  MakeCert.exe 도구에 다음 스위치를 사용합니다.  
  
    1.  `-sk` `subjectKey`. 개인 키가 들어 있는 주체의 키 컨테이너 위치입니다. 키 컨테이너가 없으면 키 컨테이너가 새로 만들어집니다. -sk 또는 -sv 옵션을 사용하지 않으면 기본적으로 JoeSoft라는 키 컨테이너가 만들어집니다.  
  
    2.  `-n` `subjectName`. 주체 이름을 지정합니다. 규칙에 따라 주체 이름 앞에 "일반 이름"을 나타내는 "CN = "을 붙입니다.  
  
    3.  `-iv` `issuerKeyFile`. 발급자의 개인 키 파일을 지정합니다.  
  
    4.  `-ic` `issuerCertFile`. 발급자의 인증서 위치를 지정합니다.  
  
     예를 들어 다음 명령은 발급자의 개인 키를 사용하여 주체 이름이 `TempCA` 이고 `"CN=SignedByCA"` 루트 인증 기관 인증서로 서명된 인증서를 만듭니다.  
  
    ```  
    makecert -sk SignedByCA -iv TempCA.pvk -n "CN=SignedByCA" -ic TempCA.cer SignedByCA.cer -sr currentuser -ss My  
    ```  
  
## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a>신뢰할 수 있는 루트 인증 기관 저장소에 인증서 설치  
 자체 서명된 인증서를 만들면 신뢰할 수 있는 루트 인증 기관 저장소에 설치할 수 있습니다. 이때 인증서로 서명된 모든 인증서는 컴퓨터에 의해 신뢰됩니다. 따라서 인증서가 더 이상 필요하지 않으면 즉시 저장소에서 삭제합니다. 이 루트 인증 기관 인증서를 삭제하면 해당 인증서로 서명된 다른 모든 인증서의 권한이 해제됩니다. 루트 인증 기관 인증서는 단순히 필요에 따라 인증서 그룹의 범위를 지정할 수 있는 메커니즘입니다. 예를 들어 피어 투 피어 응용 프로그램에서는 일반적으로 제공된 인증서로 개인의 ID를 신뢰하므로 루트 인증 기관이 필요하지 않습니다.  
  
#### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a>신뢰할 수 있는 루트 인증 기관에 자체 서명된 인증서를 설치하려면  
  
1.  인증서 스냅인을 엽니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][하는 방법: MMC 스냅인을 사용 하 여 인증서 보기](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)합니다.  
  
2.  인증서를 저장할 폴더( **로컬 컴퓨터** 또는 **현재 사용자**)를 엽니다.  
  
3.  **신뢰할 수 있는 루트 인증 기관** 폴더를 엽니다.  
  
4.  **인증서** 폴더를 마우스 오른쪽 단추로 클릭하고 **모든 작업**을 클릭한 다음 **가져오기**를 클릭합니다.  
  
5.  화면에 표시되는 마법사 지침에 따라 TempCa.cer를 저장소로 가져옵니다.  
  
## <a name="using-certificates-with-wcf"></a>WCF에서 인증서 사용  
 임시 인증서를 설정했으면 클라이언트 자격 증명 형식으로 인증서를 지정하는 WCF 솔루션을 이 인증서를 사용하여 개발할 수 있습니다. 예를 들어 다음 XML 구성에서는 메시지 보안과 인증서를 클라이언트 자격 증명 형식으로 지정합니다.  
  
#### <a name="to-specify-a-certificate-as-the-client-credential-type"></a>인증서를 클라이언트 자격 증명 형식으로 지정하려면  
  
-   서비스의 구성 파일에서 다음 XML을 사용하여 보안 모드를 메시지로 설정하고 클라이언트 자격 증명 형식을 인증서로 설정합니다.  
  
    ```xml  
    <bindings>       
      <wsHttpBinding>  
        <binding name="CertificateForClient">  
          <security>  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
 인증서는 사용자의 저장소에서 찾을 수 이며 SubjectName 필드에서 "CohoWinery" 값을 검색 하 여 찾을 수를 지정 하는 클라이언트에 대 한 구성 파일에 다음 XML을 사용  
  
```xml  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="CertForClient">  
      <clientCredentials>  
        <clientCertificate findValue="CohoWinery" x509FindType="FindBySubjectName" />  
       </clientCredentials>  
     </behavior>  
   </endpointBehaviors>  
</behaviors>  
```  
  
 WCF에서의 인증서 사용에 대한 자세한 내용은 [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)을 참조하세요.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 인증서를 마우스 오른쪽 단추로 클릭한 다음 **삭제** 를 클릭하여 **신뢰할 수 있는 루트 인증 기관** 및 **개인**폴더에서 임시 루트 인증 기관 인증서를 모두 삭제합니다.  
  
## <a name="see-also"></a>참고 항목  
 [인증서 작업](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [방법: MMC 스냅인을 사용 하 여 인증서 보기](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [서비스 및 클라이언트 보안 설정](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
