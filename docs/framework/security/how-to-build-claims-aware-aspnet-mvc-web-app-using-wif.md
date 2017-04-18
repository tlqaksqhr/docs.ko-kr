---
title: "방법: WIF를 사용하여 클레임 인식 ASP.NET MVC 웹 응용 프로그램 빌드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0efb76bc-9f7b-4afe-be1c-2a57c917010b
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# 방법: WIF를 사용하여 클레임 인식 ASP.NET MVC 웹 응용 프로그램 빌드
## 적용 대상  
  
-   Microsoft ® Windows ® Identity Foundation \(소리치 더\)  
  
-   ASP.NET® MVC  
  
## 요약  
 이 방법 간단한 클레임 인식 ASP.NET MVC 웹 응용 프로그램을 만들기 위한 자세한 단계별 절차를 제공 합니다.  또한 테스트는 간단한 클레임 인식 ASP.NET MVC 웹 응용 프로그램에 클레임 기반 인증을 성공적으로 구현 하는 방법을 설명 합니다.  이 보안 토큰 서비스 \(STS\)을 만드는 방법을 자세하게 설명 하지 않은 방법과 STS를 이미 구성한 것으로 가정 합니다.  
  
## 내용  
  
-   목표  
  
-   단계 요약  
  
-   1 단계 – 간단한 ASP.NET MVC 응용 프로그램 만들기  
  
-   2 단계 – ASP.NET MVC 응용 프로그램에 클레임 기반 인증 구성  
  
-   3 단계 – 솔루션 테스트  
  
-   관련 항목  
  
## 목표  
  
-   ASP.NET MVC 웹 응용 프로그램에 클레임 기반 인증 구성  
  
-   성공적인 클레임 인식 ASP.NET MVC 웹 응용 프로그램 테스트  
  
## 단계 요약  
  
-   1 단계 – 간단한 ASP.NET MVC 응용 프로그램 만들기  
  
-   2 단계 – ASP.NET MVC 응용 프로그램에 클레임 기반 인증 구성  
  
-   3 단계 – 솔루션 테스트  
  
## 1 단계 – 간단한 ASP.NET MVC 응용 프로그램 만들기  
 이 단계에서는 새 ASP.NET MVC 응용 프로그램을 만듭니다.  
  
#### 간단한 ASP.NET MVC 응용 프로그램을 만들려면  
  
1.  Visual Studio 시작 하 고 클릭  **파일**,  **New**, 다음  **프로젝트**.  
  
2.  에  **새 프로젝트** 창에서 클릭  **ASP.NET MVC 3 웹 응용 프로그램**.  
  
3.  In **Name**, enter `TestApp` and press **OK**.  
  
4.  에  **새 ASP.NET MVC 3 프로젝트** 선택 대화  **인터넷 응용 프로그램** 사용 가능한 서식 파일에서 확인  **뷰 엔진** 설정 되어  **면도날**를 누른 다음  **확인**.  
  
5.  새 프로젝트를 열 때 마우스는  **TestApp** 프로젝트에  **솔루션 탐색기** 선택 하 고는  **속성** 옵션.  
  
6.  프로젝트의 속성 페이지를 클릭의  **웹** 왼쪽에 탭 및 확인은  **로컬 IIS 웹 서버 사용** 옵션을 선택한.  
  
## 2 단계 – ASP.NET MVC 응용 프로그램에 클레임 기반 인증 구성  
 이 단계에서는 구성 항목을 추가 합니다에  *Web.config* 클레임 인식 하도록 ASP.NET MVC 웹 응용 프로그램의 구성 파일입니다.  
  
#### ASP.NET MVC 응용 프로그램에 클레임 기반 인증을 구성 하려면  
  
1.  다음 구성 섹션 정의에 추가 된  *Web.config* 구성 파일.  이러한 Windows Identity 파운데이션으로 필요한 구성 섹션을 정의 합니다.  추가 정의 바로 뒤에  **\<configuration\>** 시작 요소:  
  
    ```xml  
    <configSections>  
        <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
        <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  추가 된  **\<location\>** 요소는 응용 프로그램의 페더레이션 메타 데이터에 액세스할 수 있습니다.  
  
    ```xml  
    <location path="FederationMetadata">  
        <system.web>  
            <authorization>  
                <allow users="*" />  
            </authorization>  
        </system.web>  
    </location>  
    ```  
  
3.  다음 구성 항목에 추가 된  **\<system.web\>** 기본 인증을 사용 하지 않도록 설정 하 고 소리치 더 인증을 관리할 수 있도록 사용자를 거부 하는 요소.  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  다음 Windows Identity 토대 관련 구성 항목 및 ASP.NET 응용 프로그램의 URL 및 포트 번호의 값과 일치 하는지 확인 하십시오 추가  **\<audienceUris\>** 항목을  **영역** 특성의는  **\<wsFederation\>** 요소와  **회신** 특성의의  **\<wsFederation\>** 요소.  또한 확인을  **발급자** 값에 맞는 보안 토큰 서비스 \(STS\) URL을.  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <audienceUris>  
                <add value="http://localhost:28503/" />  
            </audienceUris>  
            <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
                <trustedIssuers>  
                    <add thumbprint="1234567890ABCDEFGHIJKLMNOPQRSTUVWXYZ1234" name="YourSTSName" />  
                </trustedIssuers>   
            </issuerNameRegistry>  
            <certificateValidation certificateValidationMode="None" />  
        </identityConfiguration>  
    </system.identityModel>  
    <system.identityModel.services>  
        <federationConfiguration>  
            <cookieHandler requireSsl="false" />  
            <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:13922/wsFederationSTS/Issue" realm="http://localhost:28503/" reply="http://localhost:28503/" requireHttps="false" />  
        </federationConfiguration>  
    </system.identityModel.services>  
    ```  
  
5.  추가 참조 하는 [System.IdentityModel](assetId:///System.IdentityModel?qualifyHint=False&amp;autoUpgrade=True) 어셈블리.  
  
6.  오류가 있는지 확인 하는 솔루션을 컴파일하십시오.  
  
## 3 단계 – 솔루션 테스트  
 이 단계에서 클레임 기반 인증을 위해 구성 ASP.NET MVC 웹 응용 프로그램을 테스트 합니다.  기본 테스트를 수행 하려면 클레임 토큰이 발급 된 보안 토큰 서비스 \(STS에서\)를 표시 하는 간단한 코드를 추가 합니다.  
  
#### 클레임 기반 인증을 위한 ASP.NET MVC 응용 프로그램을 테스트 하려면  
  
1.  에  **솔루션 탐색기**, 확장은  **컨트롤러** 폴더 및 열기  *HomeController.cs* 파일 편집기에서.  다음 코드를 추가 된  **인덱스** 메서드:  
  
    ```csharp  
    public ActionResult Index()  
    {  
        ViewBag.ClaimsIdentity = Thread.CurrentPrincipal.Identity;  
  
        return View();  
    }  
  
    ```  
  
2.  에  **솔루션 탐색기** 확장  **보기** 다음  **홈** 폴더와 열기  *Index.cshtml* 파일 편집기에서.  해당 내용을 삭제 하 고 다음 태그를 추가 합니다.  
  
    ```html  
  
    @{  
        ViewBag.Title = "Home Page";  
    }  
  
    <h2>Welcome: @ViewBag.ClaimsIdentity.Name</h2>  
    <h3>Values from Identity</h3>  
    <table>  
        <tr>  
            <th>  
                IsAuthenticated   
            </th>  
            <td>  
                @ViewBag.ClaimsIdentity.IsAuthenticated   
            </td>  
        </tr>  
        <tr>  
            <th>  
                Name   
            </th>          
            <td>  
                @ViewBag.ClaimsIdentity.Name  
            </td>          
        </tr>  
    </table>  
    <h3>Claims from ClaimsIdentity</h3>  
    <table>  
        <tr>  
            <th>  
                Claim Type  
            </th>  
            <th>  
                Claim Value  
            </th>  
            <th>  
                Value Type  
            </th>  
            <th>  
                Subject Name  
            </th>          
            <th>  
                Issuer Name  
            </th>          
        </tr>  
            @foreach (System.Security.Claims.Claim claim in ViewBag.ClaimsIdentity.Claims ) {  
        <tr>  
            <td>  
                @claim.Type  
            </td>  
            <td>  
                @claim.Value  
            </td>  
            <td>  
                @claim.ValueType  
            </td>  
            <td>  
                @claim.Subject.Name  
            </td>  
            <td>  
                @claim.Issuer  
            </td>  
        </tr>  
    }  
    </table>  
  
    ```  
  
3.  키를 눌러 솔루션을 실행할의  **F5** 키.  
  
4.  클레임을 보안 토큰 서비스에서 발급 된 토큰에 표시 된 페이지에 표시 됩니다.  
  
## 관련 항목  
  
-   [방법: WIF를 사용하여 클레임 인식 ASP.NET Web Forms 응용 프로그램 빌드](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)