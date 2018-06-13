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
# <a name="how-to-migrate-aspnet-web-service-code-to-the-windows-communication-foundation"></a><span data-ttu-id="07f8f-102">방법: ASP.NET 웹 서비스 코드를 Windows Communication Foundation으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="07f8f-102">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="07f8f-103">다음 절차는 Windows Communication Foundation (WCF)에 ASP.NET 웹 서비스를 마이그레이션하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-103">The following procedure describes how to migrate an ASP.NET Web Service to Windows Communication Foundation (WCF).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="07f8f-104">프로시저</span><span class="sxs-lookup"><span data-stu-id="07f8f-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-code-to-wcf"></a><span data-ttu-id="07f8f-105">ASP.NET 웹 서비스 코드를 WCF로 마이그레이션하려면</span><span class="sxs-lookup"><span data-stu-id="07f8f-105">To migrate ASP.NET Web service code to WCF</span></span>  
  
1.  <span data-ttu-id="07f8f-106">서비스에 대한 포괄적인 테스트 집합이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-106">Ensure that a comprehensive set of tests exist for the service.</span></span>  
  
2.  <span data-ttu-id="07f8f-107">서비스에 대한 WSDL을 생성하고 서비스의 .asmx 파일과 동일한 폴더에 복사본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-107">Generate the WSDL for the service and save a copy in the same folder as the service’s .asmx file.</span></span>  
  
3.  <span data-ttu-id="07f8f-108">.NET 2.0을 사용하도록 ASP.NET 웹 서비스를 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-108">Upgrade the ASP.NET Web service to use .NET 2.0.</span></span> <span data-ttu-id="07f8f-109">먼저 IIS에서 응용 프로그램에.NET Framework 2.0을 배포 하 고 다음에 설명 된 대로 Visual Studio 2005 코드 변환 프로세스를 자동화 사용 [에서 Visual Studio.NET 2002/2003 Visual studio 웹 프로젝트를 변환 하기 위한 단계별 지침 2005](http://go.microsoft.com/fwlink/?LinkId=96492)합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-109">First deploy the .NET Framework 2.0 to the application in IIS, and then use Visual Studio 2005 to automate the code conversion process, as documented in [Step-By-Step Guide to Converting Web Projects from Visual Studio .NET 2002/2003 to Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=96492).</span></span> <span data-ttu-id="07f8f-110">테스트 집합을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-110">Run the set of tests.</span></span>  
  
4.  <span data-ttu-id="07f8f-111">아직 제공하지 않은 경우 `Namespace` 특성의 `Name` 및 <xref:System.Web.Services.WebService> 매개 변수에 명시적 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-111">Provide explicit values for the `Namespace` and `Name` parameters of the <xref:System.Web.Services.WebService> attributes if they are not provided already.</span></span> <span data-ttu-id="07f8f-112">`MessageName`의 <xref:System.Web.Services.WebMethodAttribute> 매개 변수에 대해 동일한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-112">Do the same for the `MessageName` parameter of the <xref:System.Web.Services.WebMethodAttribute>.</span></span> <span data-ttu-id="07f8f-113">요청이 메서드로 라우트되는 SOAPAction HTTP 헤더에 대해 아직 명시적 값을 제공하지 않은 경우 `Action`를 사용하여 명시적으로 <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> 매개 변수의 기본값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-113">If explicit values are not already provided for the SOAPAction HTTP headers by which requests are routed to methods, then explicitly specify the default value of the `Action` parameter with a <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span></span>  
  
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
  
5.  <span data-ttu-id="07f8f-114">변경 내용을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-114">Test the change.</span></span>  
  
6.  <span data-ttu-id="07f8f-115">클래스의 메서드 본문에 있는 중요한 코드를 원래 클래스가 사용하도록 설정된 별도의 클래스로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-115">Move any substantive code in the bodies of the methods of the class to a separate class that the original class is made to use.</span></span>  
  
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
  
7.  <span data-ttu-id="07f8f-116">변경 내용을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-116">Test the change.</span></span>  
  
8.  <span data-ttu-id="07f8f-117">ASP.NET 웹 서비스 프로젝트에 WCF 어셈블리 System.ServiceModel 및 System.Runtime.Serialization에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-117">Add references to WCF assemblies System.ServiceModel and System.Runtime.Serialization to the ASP.NET Web service project.</span></span>  
  
9. <span data-ttu-id="07f8f-118">실행 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 를 WSDL에서 WCF 클라이언트 클래스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-118">Run [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate a WCF client class from the WSDL.</span></span> <span data-ttu-id="07f8f-119">생성된 클래스 모듈을 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-119">Add the generated class module to the solution.</span></span>  
  
10. <span data-ttu-id="07f8f-120">이전 단계에서 생성된 클래스 모듈에는 인터페이스 정의가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-120">The class module generated in the preceding step contains the definition of an interface.</span></span>  
  
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
  
     <span data-ttu-id="07f8f-121">다음 샘플 코드와 같이 클래스가 인터페이스 구현으로 정의되도록 ASP.NET 웹 서비스 클래스의 정의를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-121">Modify the definition of the ASP.NET Web service class so that the class is defined as implementing that interface, as shown in the following sample code.</span></span>  
  
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
  
11. <span data-ttu-id="07f8f-122">프로젝트를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-122">Compile the project.</span></span> <span data-ttu-id="07f8f-123">일부 형식 정의를 복제한 9단계에서 생성된 코드로 인해 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-123">There may be some errors due to the code generated in step nine that duplicated some type definitions.</span></span> <span data-ttu-id="07f8f-124">일반적으로 형식의 기존 정의를 삭제하여 이러한 오류를 복구합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-124">Repair those errors, usually by deleting the pre-existing definitions of the types.</span></span> <span data-ttu-id="07f8f-125">변경 내용을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-125">Test the change.</span></span>  
  
12. <span data-ttu-id="07f8f-126"><xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> 및 <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> 같은 ASP.NET 관련 특성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-126">Remove the ASP.NET-specific attributes, such as the <xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> and <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span></span>  
  
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
  
13. <span data-ttu-id="07f8f-127">ASP.NET 웹 서비스는 다음 중 하나를 사용 하는 경우 WCF ASP.NET 호환 모드를 요구 하는 WCF 서비스 유형은 이제 되는 클래스를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-127">Configure the class, which is now a WCF service type, to require WCF ASP.NET compatibility mode if the ASP.NET Web service relied on any of the following:</span></span>  
  
    -   <span data-ttu-id="07f8f-128"><xref:System.Web.HttpContext> 클래스</span><span class="sxs-lookup"><span data-stu-id="07f8f-128">The <xref:System.Web.HttpContext> class.</span></span>  
  
    -   <span data-ttu-id="07f8f-129">ASP.NET 프로필</span><span class="sxs-lookup"><span data-stu-id="07f8f-129">The ASP.NET Profiles.</span></span>  
  
    -   <span data-ttu-id="07f8f-130">.asmx 파일의 ACL</span><span class="sxs-lookup"><span data-stu-id="07f8f-130">ACLs on .asmx files.</span></span>  
  
    -   <span data-ttu-id="07f8f-131">IIS 인증 옵션</span><span class="sxs-lookup"><span data-stu-id="07f8f-131">IIS authentication options.</span></span>  
  
    -   <span data-ttu-id="07f8f-132">ASP.NET 가장 옵션</span><span class="sxs-lookup"><span data-stu-id="07f8f-132">ASP.NET impersonation options.</span></span>  
  
    -   <span data-ttu-id="07f8f-133">ASP.NET 전역화</span><span class="sxs-lookup"><span data-stu-id="07f8f-133">ASP.NET globalization.</span></span>  
  
    ```  
    [System.ServiceModel.AspNetCompatibilityRequirements(  
      RequirementsMode=AspNetCompatbilityRequirementsMode.Required)]  
    public class Adder: AdderSoap  
    ```  
  
14. <span data-ttu-id="07f8f-134">원래 .asmx 파일의 이름을 .asmx.old로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-134">Rename the original .asmx file to .asmx.old.</span></span>  
  
15. <span data-ttu-id="07f8f-135">서비스에 대 한 WCF 서비스 파일 만들기, 확장명,.asmx 및 IIS에서 응용 프로그램 루트에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-135">Create a WCF service file for the service, give it the extension, .asmx, and save it into the application root in IIS.</span></span>  
  
    ```xml  
    <%@Service Class="MyOrganization.Adder" %>  
    <%@Assembly Name="MyServiceAssembly" %>   
    ```  
  
16. <span data-ttu-id="07f8f-136">서비스에 대 한 WCF 구성을 해당 Web.config 파일에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-136">Add a WCF configuration for the service to its Web.config file.</span></span> <span data-ttu-id="07f8f-137">사용 하도록 서비스 구성의 [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), 위의 단계에서 만든.asmx 확장명이 서비스 파일을 사용 하 고 자체에 대 한 WSDL을 생성 하지 않도록 있지만 2 단계에서 WSDL을 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-137">Configure the service to use the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), to use the service file with the .asmx extension created in the preceding steps, and to not generate WSDL for itself, but to use the WSDL from step two.</span></span> <span data-ttu-id="07f8f-138">또한 필요한 경우 ASP.NET 호환 모드를 사용하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-138">Also configure it to use ASP.NET compatibility mode if necessary.</span></span>  
  
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
  
17. <span data-ttu-id="07f8f-139">구성을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-139">Save the configuration.</span></span>  
  
18. <span data-ttu-id="07f8f-140">프로젝트를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-140">Compile the project.</span></span>  
  
19. <span data-ttu-id="07f8f-141">테스트 집합을 실행하여 모든 변경 내용이 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="07f8f-141">Run the set of tests to make sure all the changes work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07f8f-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07f8f-142">See Also</span></span>  
 [<span data-ttu-id="07f8f-143">방법: ASP.NET 웹 서비스 클라이언트 코드를 Windows Communication Foundation으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="07f8f-143">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
