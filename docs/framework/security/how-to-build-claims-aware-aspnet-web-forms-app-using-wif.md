---
title: "방법: WIF를 사용하여 클레임 인식 ASP.NET Web Forms 응용 프로그램 빌드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: efb264dd-f47b-49a9-85ee-9f45d4425765
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# 방법: WIF를 사용하여 클레임 인식 ASP.NET Web Forms 응용 프로그램 빌드
## 적용 대상  
  
-   Microsoft ® Windows ® Identity Foundation \(소리치 더\)  
  
-   ASP.NET® Web Forms  
  
## 요약  
 이 방법 간단한 클레임 인식 ASP.NET Web Forms 응용 프로그램을 만들기 위한 자세한 단계별 절차를 제공 합니다.  또한 클레임 인식 간단한 ASP.NET Web Forms 응용 프로그램을 페더레이션된 인증의 성공적인 구현 테스트 하는 방법에 대 한 지침을 제공 합니다.  이 보안 토큰 서비스 \(STS\)을 만드는 방법을 자세하게 설명 하지 않은 방법과 STS를 이미 구성한 것으로 가정 합니다.  
  
## 내용  
  
-   목표  
  
-   단계 요약  
  
-   1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 만들기  
  
-   2 단계 – ASP.NET 웹 폼 응용 프로그램에 클레임 기반 인증 구성  
  
-   3 단계 – 솔루션 테스트  
  
## 목표  
  
-   ASP.NET Web Forms 응용 프로그램에 클레임 기반 인증 구성  
  
-   클레임 인식 ASP.NET Web Forms 응용 프로그램을 테스트 합니다.  
  
## 단계 요약  
  
-   1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 만들기  
  
-   2 단계 – ASP.NET 웹 폼 응용 프로그램을 페더레이션 인증 구성  
  
-   3 단계 – 솔루션 테스트  
  
## 1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 만들기  
 이 단계에서는 새 ASP.NET Web Forms 응용 프로그램을 만듭니다.  
  
#### 간단한 ASP.NET 응용 프로그램을 만들려면  
  
1.  Visual Studio 시작 하 고 클릭  **파일**,  **New**, 다음  **프로젝트**.  
  
2.  에  **새 프로젝트** 창에서 클릭  **ASP.NET 웹 폼 응용 프로그램**.  
  
3.  In **Name**, enter `TestApp` and press **OK**.  
  
## 2 단계 – ASP.NET 웹 폼 응용 프로그램에 클레임 기반 인증 구성  
 이 단계에서는 구성 항목을 추가 합니다에  *Web.config* 클레임 인식 하도록 ASP.NET Web Forms 응용 프로그램의 구성 파일입니다.  
  
#### ASP.NET 응용 프로그램에 클레임 기반 인증을 구성 하려면  
  
1.  구성 섹션 항목 추가  *Web.config* 구성 파일 바로 뒤에 있는  **\<configuration\>** 시작 요소:  
  
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
  
4.  추가 된  **\<system.webServer\>** 페더레이션 인증 모듈을 정의 하는 요소입니다.  참고는   은  특성으로 동일 해야는   은  특성에 대 한의  **\<configSections\>** 항목 앞에 추가:  
  
    ```  
    <system.webServer>  
      <modules>  
        <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
        <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      </modules>  
    </system.webServer>  
    ```  
  
5.  다음 Windows Identity 토대 관련 구성 항목 및 ASP.NET 응용 프로그램의 URL 및 포트 번호의 값과 일치 하는지 확인 하십시오 추가  **\<audienceUris\>** 항목을  **영역** 특성의는  **\<wsFederation\>** 요소와  **회신** 특성의의  **\<wsFederation\>** 요소.  또한 확인을  **발급자** 값에 맞는 보안 토큰 서비스 \(STS\) URL을.  
  
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
  
6.  추가 참조 하는 [System.IdentityModel](assetId:///System.IdentityModel?qualifyHint=False&amp;autoUpgrade=True) 어셈블리.  
  
7.  오류가 있는지 확인 하는 솔루션을 컴파일하십시오.  
  
## 3 단계 – 솔루션 테스트  
 이 단계에서 클레임 기반 인증을 위해 구성 ASP.NET Web Forms 응용 프로그램을 테스트 합니다.  기본 테스트를 수행 하려면 클레임 토큰이 발급 된 보안 토큰 서비스 \(STS에서\)를 표시 하는 코드를 추가 합니다.  
  
#### 클레임 기반 인증을 위한 ASP.NET Web Form 응용 프로그램을 테스트 하려면  
  
1.  열기는  **Default.aspx** 파일에서  **TestApp** 프로젝트와 해당 기존 태그를 다음 태그로 바꿉니다.  
  
    ```  
    %@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head id="Head1" runat="server">  
        <title></title>  
    </head>  
    <body>  
        <h1><asp:label ID="signedIn" runat="server" /></h1>  
        <asp:label ID="claimType" runat="server" />  
        <asp:label ID="claimValue" runat="server" />  
        <asp:label ID="claimValueType" runat="server" />  
        <asp:label ID="claimSubjectName" runat="server" />  
        <asp:label ID="claimIssuer" runat="server" />  
    </body>  
    </html>  
    ```  
  
2.  저장  **Default.aspx**를 클릭 한 다음 해당 코드 숨김 파일을 열고  **Default.aspx.cs**.  
  
    > [!NOTE]
    >  **Default.aspx.cs** 아래에 숨겨져 있을 수 있습니다  **Default.aspx** 솔루션 탐색기에서입니다.  경우  **Default.aspx.cs** 표시 되지 확장  **Default.aspx** 옆에 있는 삼각형을 클릭 합니다.  
  
3.  기존 코드를 대체는  **Page\_Load** 메서드의  **Default.aspx.cs** 다음 코드를:  
  
    ```csharp  
    using System;  
    using System.IdentityModel;  
    using System.Security.Claims;  
    using System.Threading;  
    using System.Web.UI;  
  
    namespace TestApp  
    {  
        public partial class _Default : System.Web.UI.Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
                if (claimsPrincipal != null)  
                {  
                    signedIn.Text = "You are signed in.";  
  
                    foreach (Claim claim in claimsPrincipal.Claims)  
                    {  
                        claimType.Text = claim.Type;  
                        claimValue.Text = claim.Value;  
                        claimValueType.Text = claim.ValueType;  
                        claimSubjectName.Text = claim.Subject.Name;  
                        claimIssuer.Text = claim.Issuer;  
                    }  
                }  
                else  
                {  
                    signedIn.Text = "You are not signed in.";  
                }  
            }  
        }  
    }  
    ```  
  
4.  저장  **Default.aspx.cs**, 및 솔루션을 빌드합니다.  
  
5.  키를 눌러 솔루션을 실행할의  **F5** 키.  
  
6.  클레임을 보안 토큰 서비스에서 발급 된 토큰에 표시 된 페이지에 표시 됩니다.