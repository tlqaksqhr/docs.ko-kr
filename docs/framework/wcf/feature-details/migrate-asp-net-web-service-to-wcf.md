---
title: '방법: ASP.NET 웹 서비스 코드를 Windows Communication Foundation으로 마이그레이션'
ms.date: 03/30/2017
ms.assetid: e528c64f-c027-4f2e-ada6-d8f3994cf8d6
ms.openlocfilehash: 90a6109a56299ec1bcaff4a35141abc194484772
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496701"
---
# <a name="how-to-migrate-aspnet-web-service-code-to-the-windows-communication-foundation"></a>방법: ASP.NET 웹 서비스 코드를 Windows Communication Foundation으로 마이그레이션
다음 절차는 Windows Communication Foundation (WCF)에 ASP.NET 웹 서비스를 마이그레이션하는 방법을 설명 합니다.  
  
## <a name="procedure"></a>프로시저  
  
#### <a name="to-migrate-aspnet-web-service-code-to-wcf"></a>ASP.NET 웹 서비스 코드를 WCF로 마이그레이션하려면  
  
1.  서비스에 대한 포괄적인 테스트 집합이 있는지 확인합니다.  
  
2.  서비스에 대한 WSDL을 생성하고 서비스의 .asmx 파일과 동일한 폴더에 복사본을 저장합니다.  
  
3.  .NET 2.0을 사용하도록 ASP.NET 웹 서비스를 업그레이드합니다. 먼저 IIS에서 응용 프로그램에.NET Framework 2.0을 배포 하 고 다음에 설명 된 대로 Visual Studio 2005 코드 변환 프로세스를 자동화 사용 [에서 Visual Studio.NET 2002/2003 Visual studio 웹 프로젝트를 변환 하기 위한 단계별 지침 2005](http://go.microsoft.com/fwlink/?LinkId=96492)합니다. 테스트 집합을 실행합니다.  
  
4.  아직 제공하지 않은 경우 `Namespace` 특성의 `Name` 및 <xref:System.Web.Services.WebService> 매개 변수에 명시적 값을 제공합니다. `MessageName`의 <xref:System.Web.Services.WebMethodAttribute> 매개 변수에 대해 동일한 작업을 수행합니다. 요청이 메서드로 라우트되는 SOAPAction HTTP 헤더에 대해 아직 명시적 값을 제공하지 않은 경우 `Action`를 사용하여 명시적으로 <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> 매개 변수의 기본값을 지정합니다.  
  
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
  
8.  ASP.NET 웹 서비스 프로젝트에 WCF 어셈블리 System.ServiceModel 및 System.Runtime.Serialization에 대 한 참조를 추가 합니다.  
  
9. 실행 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 를 WSDL에서 WCF 클라이언트 클래스를 생성 합니다. 생성된 클래스 모듈을 솔루션에 추가합니다.  
  
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
  
11. 프로젝트를 컴파일합니다. 일부 형식 정의를 복제한 9단계에서 생성된 코드로 인해 오류가 발생할 수 있습니다. 일반적으로 형식의 기존 정의를 삭제하여 이러한 오류를 복구합니다. 변경 내용을 테스트합니다.  
  
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
  
13. ASP.NET 웹 서비스는 다음 중 하나를 사용 하는 경우 WCF ASP.NET 호환 모드를 요구 하는 WCF 서비스 유형은 이제 되는 클래스를 구성 합니다.  
  
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
  
15. 서비스에 대 한 WCF 서비스 파일 만들기, 확장명,.asmx 및 IIS에서 응용 프로그램 루트에 저장 합니다.  
  
    ```xml  
    <%@Service Class="MyOrganization.Adder" %>  
    <%@Assembly Name="MyServiceAssembly" %>   
    ```  
  
16. 서비스에 대 한 WCF 구성을 해당 Web.config 파일에 추가 합니다. 사용 하도록 서비스 구성의 [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), 위의 단계에서 만든.asmx 확장명이 서비스 파일을 사용 하 고 자체에 대 한 WSDL을 생성 하지 않도록 있지만 2 단계에서 WSDL을 사용 하도록 합니다. 또한 필요한 경우 ASP.NET 호환 모드를 사용하도록 구성합니다.  
  
    ```xml  
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
        address=""  
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
  
## <a name="see-also"></a>참고 항목  
 [방법: ASP.NET 웹 서비스 클라이언트 코드를 Windows Communication Foundation으로 마이그레이션](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
