---
title: "방법: 기본 Windows Communication Foundation 클라이언트 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "WCF 클라이언트 [WCF], 구성"
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
caps.latest.revision: 47
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 47
---
# 방법: 기본 Windows Communication Foundation 클라이언트 구성
이 작업은 기본 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 응용 프로그램을 만드는 데 필요한 6가지 작업 중 다섯 번째 작업입니다.  6가지 작업의 개요를 모두 보려면 [초보자를 위한 자습서](../../../docs/framework/wcf/getting-started-tutorial.md) 항목을 참조하세요.  
  
 이 항목은 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 또는 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)의 서비스 참조 추가 기능을 사용하여 생성된 클라이언트 구성 파일에 대해 설명합니다.  클라이언트를 구성하려면 클라이언트에서 서비스에 액세스하는 데 사용하는 끝점을 지정해야 합니다.  끝점에는 주소, 바인딩 및 계약이 포함되어 있으며 이러한 각 항목은 클라이언트 구성 프로세스에서 지정되어야 합니다.  
  
### Windows Communication Foundation 클라이언트를 구성하려면  
  
1.  GettingStartedClient 프로젝트에서 생성된 구성 파일\(App.config\)을 엽니다.  다음 예제에서는 생성된 구성 파일을 보여 줍니다.  [\<system.serviceModel\>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)[\<endpoint\> 섹션 아래에서](http://msdn.microsoft.com/ko-kr/13aa23b7-2f08-4add-8dbf-a99f8127c017) 요소를 찾습니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
        <startup>   
          <!-- specifies the version of WCF to use-->  
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />  
        </startup>  
        <system.serviceModel>  
            <bindings>  
                <!-- Uses wsHttpBinding-->  
                <wsHttpBinding>  
                    <binding name="WSHttpBinding_ICalculator" />  
                </wsHttpBinding>  
            </bindings>  
            <client>  
                <!-- specifies the endpoint to use when calling the service -->  
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"  
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"  
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">  
                    <identity>  
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />  
                    </identity>  
                </endpoint>  
            </client>  
        </system.serviceModel>  
    </configuration><?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
        <startup>   
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />  
        </startup>  
        <system.serviceModel>  
            <bindings>  
                <wsHttpBinding>  
                    <binding name="WSHttpBinding_ICalculator" />  
                </wsHttpBinding>  
            </bindings>  
            <client>  
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"  
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"  
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">  
                    <identity>  
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />  
                    </identity>  
                </endpoint>  
            </client>  
        </system.serviceModel>  
    </configuration>   
    ```  
  
     이 예제에서는 다음 주소에 위치한 서비스에 액세스하도록 클라이언트가 사용하는 끝점을 구성합니다. http:\/\/localhost:8000\/ServiceModelSamples\/Service\/CalculatorService  
  
     끝점 요소는 WCF 클라이언트와 서비스 사이의 통신에 `ServiceReference1.ICalculator` 서비스 계약을 사용하도록 지정합니다.  WCF 채널은 시스템에서 제공한 <xref:System.ServiceModel.WsHttpBinding>을 사용하여 구성합니다.  이 계약은 Visual Studio의 서비스 참조 추가를 사용하여 생성한 것입니다.  실질적으로 GettingStartedLib 프로젝트에 정의된 계약의 사본입니다.  <xref:System.ServiceModel.WsHttpBinding> 바인딩은 HTTP를 전송, 상호 운용 가능한 보안 및 기타 구성 세부 사항으로 지정합니다.  
  
2.  이 구성을 통해 생성한 클라이언트를 사용하는 방법[!INCLUDE[crabout](../../../includes/crabout-md.md)] [방법: 클라이언트 사용](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)을 참조하세요.  
  
## 참고 항목  
 [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [방법: 클라이언트 만들기](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)   
 [시작](../../../docs/framework/wcf/samples/getting-started-sample.md)   
 [자체 호스팅](../../../docs/framework/wcf/samples/self-host.md)