---
title: "방법: ASP.NET 웹 서비스 코드를 Windows Communication Foundation으로 마이그레이션 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e528c64f-c027-4f2e-ada6-d8f3994cf8d6
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 방법: ASP.NET 웹 서비스 코드를 Windows Communication Foundation으로 마이그레이션
다음 절차에서는 ASP.NET 웹 서비스를 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]로 마이그레이션하는 방법에 대해 설명합니다.  
  
## 절차  
  
#### ASP.NET 웹 서비스 코드를 WCF로 마이그레이션하려면  
  
1.  서비스에 대한 포괄적인 테스트 집합이 있는지 확인합니다.  
  
2.  서비스에 대한 WSDL을 생성하고 서비스의 .asmx 파일과 동일한 폴더에 복사본을 저장합니다.  
  
3.  .NET 2.0을 사용하도록 ASP.NET 웹 서비스를 업그레이드합니다.  먼저 [Visual Studio .NET 2002\/2003에서 Visual Studio 2005로 웹 프로젝트를 변환하는 방법에 대한 단계별 지침](http://go.microsoft.com/fwlink/?LinkId=96492)\(영문\)에 문서화된 대로 .NET Framework 2.0을 IIS의 응용 프로그램에 배포한 다음 Visual Studio 2005를 사용하여 코드 변환 프로세스를 자동화합니다.  테스트 집합을 실행합니다.  
  
4.  아직 제공하지 않은 경우 <xref:System.Web.Services.WebService> 특성의 `Namespace` 및 `Name` 매개 변수에 명시적 값을 제공합니다.  <xref:System.Web.Services.WebMethodAttribute>의 `MessageName` 매개 변수에 대해 동일한 작업을 수행합니다.  요청이 메서드로 라우트되는 SOAPAction HTTP 헤더에 대해 아직 명시적 값을 제공하지 않은 경우 <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>를 사용하여 명시적으로 `Action` 매개 변수의 기본값을 지정합니다.  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              double sum = 0.00;  
              foreach (double inputValue in input.Input)  
              {  
                  sum += inputValue;  
              }  
          return sum;  
         }  
    }  
    ```  
  
5.  변경 내용을 테스트합니다.  
  
6.  클래스의 메서드 본문에 있는 중요한 코드를 원래 클래스가 사용하도록 설정된 별도의 클래스로 이동합니다.  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
    }  
  
    internal class ActualAdder  
    {  
         internal double Add(SumInput input)  
         {  
              double sum = 0.00;  
              foreach (double inputValue in input.Input)  
              {  
                  sum += inputValue;  
              }  
          return sum;  
         }  
    }  
    ```  
  
7.  변경 내용을 테스트합니다.  
  
8.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 어셈블리 System.ServiceModel 및 System.Runtime.Serialization에 대한 참조를 ASP.NET 웹 서비스 프로젝트에 추가합니다.  
  
9. [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 실행하여 WSDL에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 클래스를 생성합니다.  생성된 클래스 모듈을 솔루션에 추가합니다.  
  
10. 이전 단계에서 생성된 클래스 모듈에는 인터페이스 정의가 들어 있습니다.  
  
    ```  
    [System.ServiceModel.ServiceContractAttribute()]  
    public interface AdderSoap  
    {  
         [System.ServiceModel.OperationContractAttribute(  
          Action="http://tempuri.org/Add",   
          ReplyAction="http://tempuri.org/Add")]  
         AddResponse Add(AddRequest request);  
    }  
    ```  
  
     다음 샘플 코드와 같이 클래스가 인터페이스 구현으로 정의되도록 ASP.NET 웹 서비스 클래스의 정의를 수정합니다.  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder: AdderSoap  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
  
         public AddResponse Add(AddRequest request)  
         {  
            return new AddResponse(  
            new AddResponseBody(  
            this.Add(request.Body.input)));  
         }  
    }  
    ```  
  
11. 프로젝트를 컴파일합니다.  일부 형식 정의를 복제한 9단계에서 생성된 코드로 인해 오류가 발생할 수 있습니다.  일반적으로 형식의 기존 정의를 삭제하여 이러한 오류를 복구합니다.  변경 내용을 테스트합니다.  
  
12. <xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> 및 <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> 같은 ASP.NET 관련 특성을 제거합니다.  
  
    ```  
    public class Adder: AdderSoap  
    {  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
  
         public AddResponse Add(AddRequest request)  
         {  
              return new AddResponse(  
             new AddResponseBody(  
            this.Add(request.Body.input)));  
         }  
    }  
    ```  
  
13. ASP.NET 웹 서비스가 다음 중 하나를 사용하는 경우 현재 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 형식인 클래스를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET 호환 모드가 필요하도록 구성합니다.  
  
    -   <xref:System.Web.HttpContext> 클래스  
  
    -   ASP.NET 프로필  
  
    -   .asmx 파일의 ACL  
  
    -   IIS 인증 옵션  
  
    -   ASP.NET 가장 옵션  
  
    -   ASP.NET 전역화  
  
    ```  
    [System.ServiceModel.AspNetCompatibilityRequirements(  
      RequirementsMode=AspNetCompatbilityRequirementsMode.Required)]  
    public class Adder: AdderSoap  
    ```  
  
14. 원래 .asmx 파일의 이름을 .asmx.old로 바꿉니다.  
  
15. 서비스의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 파일을 만들고 확장명 .asmx를 지정하여 IIS의 응용 프로그램 루트에 저장합니다.  
  
    ```  
    <%@Service Class="MyOrganization.Adder" %>  
    <%@Assembly Name="MyServiceAssembly" %>   
    ```  
  
16. 서비스의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구성을 해당 Web.config 파일에 추가합니다.  [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)를 사용하고, 이전 단계에서 만든 .asmx 확장명을 가진 서비스 파일을 사용하고, 자체 WSDL을 생성하지 않고 2단계의 WSDL을 사용하도록 서비스를 구성합니다.  또한 필요한 경우 ASP.NET 호환 모드를 사용하도록 구성합니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
     <system.web>  
      <compilation>  
      <buildProviders>  
       <remove extension=".asmx" />  
       <add extension=".asmx"   
        type=  
        "System.ServiceModel.Activation.ServiceBuildProvider,  
        T:System.ServiceModel, Version=2.0.0.0,   
       Culture=neutral,   
       PublicKeyToken=b77a5c561934e089" />  
      </buildProviders>  
      </compilation>  
     </system.web>  
     <system.serviceModel>  
      <services>  
      <service name="MyOrganization.Adder "  
        behaviorConfiguration="AdderBehavior">  
       <endpoint   
        address="”  
        binding="basicHttpBinding"  
        contract="AdderSoap "/>  
       </service>  
      </services>  
      <behaviors>  
      <behavior name="AdderBehavior">  
       <metadataPublishing   
        enableMetadataExchange="true"   
        enableGetWsdl="true"   
        enableHelpPage="true"   
        metadataLocation=  
        "http://MyHost.com/AdderService/Service.WSDL"/>  
      </behavior>  
      </behaviors>  
      <serviceHostingEnvironment   
       aspNetCompatibilityEnabled ="true"/>  
     </system.serviceModel>  
    </configuration>  
  
    ```  
  
17. 구성을 저장합니다.  
  
18. 프로젝트를 컴파일합니다.  
  
19. 테스트 집합을 실행하여 모든 변경 내용이 작동하는지 확인합니다.  
  
## 참고 항목  
 [방법: ASP.NET 웹 서비스 클라이언트 코드를 Windows Communication Foundation으로 마이그레이션](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)