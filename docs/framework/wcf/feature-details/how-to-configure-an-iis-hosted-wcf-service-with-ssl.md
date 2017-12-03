---
title: "방법: SSL을 사용하여 IIS에서 호스트되는 WCF 서비스 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e43aca439ee354557cac42ba88599b6ea105b097
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a>방법: SSL을 사용하여 IIS에서 호스트되는 WCF 서비스 구성
이 항목에서는 HTTP 전송 보안을 사용하도록 IIS에서 호스트되는 WCF 서비스를 설정하는 방법에 대해 설명합니다. HTTP 전송 보안에는 IIS에 등록할 SSL 인증서가 필요합니다. SSL 인증서가 없는 경우에는 IIS를 사용하여 테스트 인증서를 생성할 수 있습니다. 그런 다음 SSL 바인딩을 웹 사이트에 추가하고 웹 사이트의 인증 속성을 구성해야 합니다. 마지막으로, HTTPS를 사용하도록 WCF 서비스를 구성해야 합니다.  
  
### <a name="creating-a-self-signed-certificate"></a>자체 서명된 인증서 만들기  
  
1.  인터넷 정보 서비스 관리자(inetmgr.exe)를 열고 왼쪽 트리 뷰에서 컴퓨터 이름을 선택합니다. 화면 오른쪽에서 서버 인증서를 선택합니다.  
  
     ![IIS Manager 홈 화면](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "mg_INetMgrHome")  
  
2.  서버 인증서 창에서 클릭 된 **자체 서명 된 인증서 만들기...** 링크를 클릭합니다.  
  
     ![IIS와 인증서를 서명 자체 &#45; 만들기](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")  
  
3.  자체 서명 된 인증서에 사용할 이름을 입력 하 고 클릭 **확인**합니다.  
  
     ![만들기 자체 &#45; 서명 인증서 대화 상자](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "mg_MyCert")  
  
     새로 만든된 자체 서명 된 인증서 세부 정보에 표시 됩니다는 **서버 인증서** 창.  
  
     ![서버 인증서 창](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")  
  
     생성된 인증서는 신뢰할 수 있는 루트 인증 기관 저장소에 설치됩니다.  
  
### <a name="add-ssl-binding"></a>SSL 바인딩 추가  
  
1.  인터넷 정보 서비스 관리자에서 확장 하 고는 **사이트** 폴더 차례로 **기본 웹 사이트** 화면 왼쪽의 트리 보기에서 폴더입니다.  
  
2.  클릭는 **바인딩...** 연결에 **동작** 창의 오른쪽 상단 부분에는 섹션입니다.  
  
     ![SSL 바인딩 추가](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "mg_AddSSLBinding")  
  
3.  사이트 바인딩 창에서 클릭 된 **추가** 단추입니다.  
  
     ![사이트 바인딩 대화 상자](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")  
  
4.  에 **사이트 바인딩 추가** 대화 상자에서 만든 https를 선택 형식과 방금 자체 서명 된 인증서의 이름에 대 한 합니다.  
  
     ![사이트 바인딩 예제](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "mg_MyCertBinding")  
  
### <a name="configure-virtual-directory-for-ssl"></a>SSL용 가상 디렉터리 구성  
  
1.  인터넷 정보 서비스 관리자에서 WCF 보안 서비스를 포함하는 가상 디렉터리를 선택합니다.  
  
2.  창의 가운데 창에서 선택 **SSL 설정** IIS 섹션에 있습니다.  
  
     ![가상 디렉터리에 대 한 SSL 설정을](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")  
  
3.  SSL 설정 창에서 선택는 **SSL 필요** 확인란을 클릭 하 고는 **적용** 연결에 **작업** 화면 오른쪽에 섹션 합니다.  
  
     ![가상 디렉터리 SSL 설정](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")  
  
### <a name="configure-wcf-service-for-http-transport-security"></a>HTTP 전송 보안을 위한 WCF 서비스 구성  
  
1.  WCF 서비스의 web.config에서 다음 XML에 표시된 것처럼 전송 보안을 사용하도록 HTTP 바인딩을 구성합니다.  
  
    ```xml  
    <bindings>  
          <basicHttpBinding>  
            <binding name="secureHttpBinding">  
              <security mode="Transport">  
                <transport clientCredentialType="None"/>  
              </security>  
            </binding>  
          </basicHttpBinding>  
    </bindings>  
    ```  
  
2.  다음 XML에 표시된 것처럼 서비스 및 서비스 끝점을 지정합니다.  
  
    ```xml  
    <services>  
          <service name="MySecureWCFService.Service1">  
            <endpoint address=""  
                      binding="basicHttpBinding"  
                      bindingConfiguration="secureHttpBinding"  
                      contract="MySecureWCFService.IService1"/>  
  
            <endpoint address="mex"  
                      binding="mexHttpsBinding"  
                      contract="IMetadataExchange" />  
          </service>  
    </services>  
    ```  
  
## <a name="example"></a>예제  
 다음은 HTTP 전송 보안을 사용하는 WCF 서비스에 대한 web.config 파일의 전체 예제입니다.  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <services>  
      <service name="MySecureWCFService.Service1">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  bindingConfiguration="secureHttpBinding"  
                  contract="MySecureWCFService.IService1"/>  
  
        <endpoint address="mex"  
                  binding="mexHttpsBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="secureHttpBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <!-- To avoid disclosing metadata information, set the value below to false and remove the metadata endpoint above before deployment -->  
          <serviceMetadata httpsGetEnabled="true"/>  
          <!-- To receive exception details in faults for debugging purposes, set the value below to true.  Set to false before deployment to avoid disclosing exception information -->  
          <serviceDebug includeExceptionDetailInFaults="false"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
  </system.serviceModel>  
  <system.webServer>  
    <modules runAllManagedModulesForAllRequests="true"/>  
  </system.webServer>  
  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [인터넷 정보 서비스에서 호스팅](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [인터넷 정보 서비스 호스팅 지침](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)  
 [인터넷 정보 서비스 호스팅을 위한 최선의 방법](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [인라인 코드를 사용한 IIS 호스팅](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)
