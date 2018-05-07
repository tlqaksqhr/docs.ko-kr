---
title: Custom Secure Metadata Endpoint
ms.date: 03/30/2017
ms.assetid: 9e369e99-ea4a-49ff-aed2-9fdf61091a48
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2baa99ddaf5de60407b233b5a6ea013ad87401f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="custom-secure-metadata-endpoint"></a>Custom Secure Metadata Endpoint
이 샘플을 구성 하는 방법과 비 메타 데이터 교환 바인딩을 중 하나를 사용 하 여 보안 메타 데이터 끝점을 사용 하 여 서비스를 구현 하는 방법을 보여 줍니다. [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 또는 인출 하는 클라이언트는 이러한 메타 데이터 끝점에서 메타 데이터입니다. 메타데이터 끝점을 노출하는 데 시스템에서 제공한 두 가지 바인딩, mexHttpBinding 및 mexHttpsBinding을 사용할 수 있습니다. mexHttpBinding은 HTTP를 통해 비보안 방식으로 메타데이터 끝점을 노출하는 데 사용되고, mexHttpsBinding은 HTTPS를 통해 보안 방식으로 메타데이터 끝점을 노출하는 데 사용됩니다. 이 샘플에서는 <xref:System.ServiceModel.WSHttpBinding>을 사용하여 보안 메타데이터 끝점을 노출하는 방법을 보여 줍니다. 바인딩의 보안 설정을 변경하려고 하지만 HTTPS를 사용하지 않으려는 경우 이 방법을 사용할 수 있습니다. mexHttpsBinding을 사용하면 메타데이터 끝점이 보안되지만 바인딩 설정은 수정할 수 없습니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
## <a name="service"></a>서비스  
 이 샘플의 서비스에는 두 개의 끝점이 있습니다. 응용 프로그램 끝점에서는 인증서를 통한 `ICalculator` 보안 및 `WSHttpBinding`이 설정된 `ReliableSession`에서 `Message` 계약을 처리합니다. 메타데이터 끝점에서는 보안 설정은 동일하지만 `WSHttpBinding`이 없는 `ReliableSession`을 사용합니다. 관련 구성은 다음과 같습니다.  
  
```xml  
<services>   
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
     <!-- use base address provided by host -->  
     <endpoint address=""  
       binding="wsHttpBinding"  
       bindingConfiguration="Binding2"  
       contract="Microsoft.ServiceModel.Samples.ICalculator" />  
     <endpoint address="mex"  
       binding="wsHttpBinding"  
       bindingConfiguration="Binding1"  
       contract="IMetadataExchange" />  
     </service>  
 </services>  
 <bindings>  
   <wsHttpBinding>  
     <binding name="Binding1">  
       <security mode="Message">  
         <message clientCredentialType="Certificate" />  
       </security>  
     </binding>  
     <binding name="Binding2">  
       <reliableSession inactivityTimeout="00:01:00" enabled="true" />  
       <security mode="Message">  
         <message clientCredentialType="Certificate" />  
       </security>  
     </binding>  
   </wsHttpBinding>  
 </bindings>  
```  
  
 대부분의 다른 샘플에서는 메타데이터 끝점에 보안되지 않은 기본 `mexHttpBinding`을 사용하지만 여기서는 `WSHttpBinding` 보안이 설정된 `Message`을 사용하여 메타데이터를 보호합니다. 메타데이터 클라이언트가 이 메타데이터를 검색하려면 일치하는 바인딩으로 구성되어야 합니다. 이 샘플에서는 이러한 두 개의 클라이언트를 보여 줍니다.  
  
 첫 번째 클라이언트는 디자인 타임에 Svcutil.exe를 사용하여 메타데이터를 페치하고 클라이언트 코드 및 구성을 생성합니다. 서비스에서 기본 바인딩이 아닌 바인딩을 메타데이터에 사용하므로 Svcutil.exe 도구는 해당 바인딩을 사용하는 서비스에서 메타데이터를 가져올 수 있도록 특수하게 구성되어야 합니다.  
  
 두 번째 클라이언트는 `MetadataResolver`를 사용하여 알려진 계약에 대한 메타데이터를 동적으로 페치한 다음 동적으로 생성된 클라이언트에서 작업을 호출합니다.  
  
## <a name="svcutil-client"></a>Svcutil 클라이언트  
 `IMetadataExchange` 끝점을 호스팅하기 위해 기본 바인딩을 사용할 경우 해당 끝점의 주소와 함께 Svcutil.exe를 실행할 수 있습니다.  
  
```  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 그러나 이 샘플에서 서버는 기본값이 아닌 끝점을 사용하여 메타데이터를 호스팅합니다. 따라서 올바른 바인딩을 사용하도록 Svcutil.exe에 지시해야 합니다. 이렇게 하려면 Svcutil.exe.config 파일을 사용합니다.  
  
 Svcutil.exe.config 파일은 클라이언트 끝점 이름과 계약이 추가된다는 것을 제외하면 일반적인 클라이언트 구성 파일과 비슷합니다.  
  
```xml  
<endpoint name="http"  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"  
          behaviorConfiguration="ClientCertificateBehavior"  
          contract="IMetadataExchange" />  
```  
  
 끝점 이름은 메타데이터가 호스팅된 주소 체계의 이름이어야 하고 끝점 계약은 `IMetadataExchange`여야 합니다. 따라서 Svcutil.exe를 다음과 같은 명령줄로 실행하면  
  
```  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 Svcutil.exe는 "http"라는 끝점과 `IMetadataExchange` 계약을 찾아 메타데이터 끝점과의 통신 교환에 사용할 바인딩 및 동작을 구성합니다. 샘플에서 Svcutil.exe.config 파일의 나머지 부분은 서버의 메타데이터 끝점 구성과 일치하도록 바인딩 구성 및 동작 자격 증명을 지정합니다.  
  
 Svcutil.exe가 Svcutil.exe.config에서 구성을 선택하려면 이 구성 파일과 동일한 디렉터리에 Svcutil.exe가 있어야 합니다. 결과적으로 Svcutil.exe를 해당 설치 위치에서 Svcutil.exe.config 파일이 있는 디렉터리에 복사해야 합니다. 그런 다음 해당 디렉터리에서 다음 명령을 실행합니다.  
  
```  
.\svcutil.exe http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 앞에 오는 "입니다. \\"(의 하나는 해당 Svcutil.exe.config가 있는)이이 디렉터리의 Svcutil.exe 복사본이 실행 되도록 합니다.  
  
## <a name="metadataresolver-client"></a>MetadataResolver 클라이언트  
 클라이언트는 계약을 알고 있고 디자인 타임에 메타데이터에 통신하는 방법을 알고 있는 경우 `MetadataResolver`를 사용하여 응용 프로그램 끝점의 바인딩과 주소를 동적으로 찾을 수 있습니다. 이 작업을 보여 주기 위해 이 샘플 클라이언트에서는 `MetadataResolver`를 만들고 구성하여 `MetadataExchangeClient`에 사용되는 바인딩과 자격 증명을 구성하는 방법을 제공합니다.  
  
 Svcutil.exe.config에 표시된 것과 동일한 바인딩 및 인증서 정보를 `MetadataExchangeClient`에서 명령 형식으로 지정할 수 있습니다.  
  
```  
// Specify the Metadata Exchange binding and its security mode  
WSHttpBinding mexBinding = new WSHttpBinding(SecurityMode.Message);  
mexBinding.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
// Create a MetadataExchangeClient for retrieving metadata, and set the // certificate details  
MetadataExchangeClient mexClient = new MetadataExchangeClient(mexBinding);  
mexClient.SoapCredentials.ClientCertificate.SetCertificate(    StoreLocation.CurrentUser, StoreName.My,  
    X509FindType.FindBySubjectName, "client.com");  
mexClient.SoapCredentials.ServiceCertificate.Authentication.    CertificateValidationMode =    X509CertificateValidationMode.PeerOrChainTrust;  
mexClient.SoapCredentials.ServiceCertificate.SetDefaultCertificate(    StoreLocation.CurrentUser, StoreName.TrustedPeople,  
    X509FindType.FindBySubjectName, "localhost");  
```  
  
 `mexClient`가 구성된 상태에서 원하는 계약을 열거하고 `MetadataResolver`를 사용하여 이러한 계약과 함께 끝점 목록을 페치할 수 있습니다.  
  
```  
// The contract we want to fetch metadata for  
Collection<ContractDescription> contracts =    new Collection<ContractDescription>();  
ContractDescription contract =    ContractDescription.GetContract(typeof(ICalculator));  
contracts.Add(contract);  
// Find endpoints for that contract  
EndpointAddress mexAddress = new    EndpointAddress(ConfigurationManager.AppSettings["mexAddress"]);  
ServiceEndpointCollection endpoints =    MetadataResolver.Resolve(contracts, mexAddress, mexClient);  
```  
  
 마지막으로 이러한 끝점의 정보를 사용하여 응용 프로그램 끝점과 통신하기 위한 채널을 만드는 데 사용되는 `ChannelFactory`의 바인딩과 주소를 초기화할 수 있습니다.  
  
```  
ChannelFactory<ICalculator> cf = new    ChannelFactory<ICalculator>(endpoint.Binding, endpoint.Address);  
```  
  
 이 샘플 클라이언트의 요점은 `MetadataResolver`를 사용하는 중이고 메타데이터 교환 통신을 위한 사용자 지정 바인딩이나 동작을 지정해야 할 경우 `MetadataExchangeClient`를 사용하여 이러한 사용자 지정 설정을 지정할 수 있다는 것입니다.  
  
#### <a name="to-set-up-and-build-the-sample"></a>샘플을 설치하고 빌드하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a>단일 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  샘플 설치 폴더에서 Setup.bat를 실행하여 이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다. Setup.bat에서 setupCertTool.bat를 실행 하 여 설치 하는 FindPrivateKey.exe 도구를 사용 하 여 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  \MetadataResolverClient\bin 또는 \SvcutilClient\bin에서 클라이언트 응용 프로그램을 실행합니다. 클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.  
  
3.  클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.  
  
4.  샘플 사용을 마치면 Cleanup.bat를 실행하여 인증서를 제거합니다. 다른 보안 샘플에도 동일한 인증서가 사용됩니다.  
  
#### <a name="to-run-the-sample-across-machines"></a>다중 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  서버에서 `setup.bat service`를 실행합니다. 실행 `setup.bat` 와 `service` 인수가 컴퓨터의 정규화 된 도메인 이름을 사용 하 여 서비스 인증서를 만들고 되어 Service.cer 이라는 파일로 서비스 인증서를 내보냅니다.  
  
2.  서버에서 Web.config를 편집하여 새 인증서 이름을 반영합니다. 즉, 변경 된 `findValue` 특성에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) 요소는 컴퓨터의 정규화 된 도메인 이름입니다.  
  
3.  서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.  
  
4.  클라이언트에서 `setup.bat client`를 실행합니다. 실행 `setup.bat` 와 `client` 인수 Client.com 이라는 클라이언트 인증서를 만들고 클라이언트 인증서 Client.cer 이라는 파일로 내보냅니다.  
  
5.  클라이언트 컴퓨터에 있는 `MetadataResolverClient`의 App.config 파일에서 mex 끝점의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다. 이 작업을 수행하려면 localhost를 서버의 정규화된 도메인 이름으로 바꿉니다. 또한 metadataResolverClient.cs 파일의 "localhost" 항목을 새 서비스 인증서 이름(서버의 정규화된 도메인 이름)으로 변경합니다. SvcutilClient 프로젝트의 App.config에도 동일한 작업을 수행합니다.  
  
6.  클라이언트 디렉터리에서 서버의 서비스 디렉터리로 Client.cer 파일을 복사합니다.  
  
7.  클라이언트에서 `ImportServiceCert.bat`를 실행합니다. 이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.  
  
8.  서버에서 `ImportClientCert.bat`를 실행하여 Client.cer 파일에서 LocalMachine - TrustedPeople 저장소로 클라이언트 인증서를 가져옵니다.  
  
9. 서비스 컴퓨터의 Visual Studio에서 서비스 프로젝트를 빌드하고 웹 브라우저에서 도움말 페이지를 선택하여 해당 서비스 프로젝트가 실행 중인지 확인합니다.  
  
10. 클라이언트 컴퓨터의 VS에서 MetadataResolverClient 또는 SvcutilClient를 실행합니다.  
  
    1.  클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.  
  
#### <a name="to-clean-up-after-the-sample"></a>샘플 실행 후 정리를 수행하려면  
  
-   샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다.  
  
    > [!NOTE]
    >  다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 서비스 인증서를 제거할 수 없습니다. 여러 시스템에서 인증서를 사용 하는 Windows Communication Foundation (WCF) 샘플을 실행 한 경우 CurrentUser-TrustedPeople 저장소에에서 설치 된 서비스 인증서의 선택을 취소 해야 합니다. 이렇게 하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다. 예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Metadata\CustomMexEndpoint`  
  
## <a name="see-also"></a>참고 항목
