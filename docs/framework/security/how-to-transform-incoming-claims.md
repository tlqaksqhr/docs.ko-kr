---
title: "방법: 들어오는 클레임 변환 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2831d514-d9d8-4200-9192-954bb6da1126
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# 방법: 들어오는 클레임 변환
## 적용 대상  
  
-   Microsoft ® Windows ® Identity Foundation \(소리치 더\)  
  
-   ASP.NET® Web Forms  
  
## 요약  
 이 방법 간단한 Web Forms ASP.NET 클레임 인식 응용 프로그램을 만들고 들어오는 클레임 변환에 대 한 상세한 단계별 절차를 제공 합니다.  또한 응용 프로그램을 실행 하면 변환 된 클레임 나와 확인 하려면 응용 프로그램을 테스트 하는 방법에 대 한 지침을 제공 합니다.  
  
## 내용  
  
-   목표  
  
-   개요  
  
-   단계 요약  
  
-   1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 만들기  
  
-   단계 2 – 사용자 정의 Claimsauthenticationmanager를 사용 하 여 구현 클레임 변환  
  
-   3 단계 – 솔루션 테스트  
  
## 목표  
  
-   ASP.NET Web Forms 응용 프로그램에 클레임 기반 인증 구성  
  
-   관리자 역할 클레임을 추가 하 여 들어오는 클레임 변환  
  
-   ASP.NET Web Forms 응용 프로그램에서 제대로 작동 하는지 테스트 합니다.  
  
## 개요  
 소리치 더 라는 클래스를 제공 합니다. <xref:System.Security.Claims.ClaimsAuthenticationManager> 사용자가 신뢰 당사자 \(RP\) 응용 프로그램을 제시 하기 전에 클레임을 수정할 수는 있습니다.  <xref:System.Security.Claims.ClaimsAuthenticationManager> 인증 및 기본 응용 프로그램 코드 간에 중요 한 부분의 분리에 유용 합니다.  다음 예제에서는 역할에 들어오는 클레임을 추가 하는 방법을 보여 줍니다. <xref:System.Security.Claims.ClaimsPrincipal> RP에 필요한 수 있습니다.  
  
## 단계 요약  
  
-   1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 만들기  
  
-   단계 2 – 사용자 정의 Claimsauthenticationmanager를 사용 하 여 구현 클레임 변환  
  
-   3 단계 – 솔루션 테스트  
  
## 1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 만들기  
 이 단계에서는 새 ASP.NET Web Forms 응용 프로그램을 만듭니다.  
  
#### 간단한 ASP.NET 응용 프로그램을 만들려면  
  
1.  관리자 권한으로 상승 된 모드에서 시작 하는 Visual Studio.  
  
2.  클릭 Visual Studio  **파일**, 클릭  **새**를 누른 다음  **프로젝트**.  
  
3.  에  **새 프로젝트** 창에서 클릭  **ASP.NET 웹 폼 응용 프로그램**.  
  
4.  In **Name**, enter `TestApp` and press **OK**.  
  
5.  마우스의  **TestApp** 프로젝트에서  **솔루션 탐색기**, 선택  **Id 및 액세스**.  
  
6.  **Id 및 액세스** 창이 나타납니다.  아래  **공급자**,  **테스트 응용 프로그램에 로컬 개발 STS**, 누른 다음  **적용**.  
  
7.  에  *Default.aspx* 파일, 기존 태그를 다음 중 교체 후 파일을 저장 합니다.  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
          <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
  
    ```  
  
8.  코드 숨김 파일을 열고  *Default.aspx.cs*.  파일 저장 후 다음과 같은 기존 코드를 바꿉니다.  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        public partial class _Default : Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Page.User as ClaimsPrincipal;  
                this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                this.ClaimsGridView.DataBind();  
            }  
        }  
    }  
    ```  
  
## 단계 2 – 사용자 정의 Claimsauthenticationmanager를 사용 하 여 구현 클레임 변환  
 이 단계에서는 기본 기능을 무시 합니다의 <xref:System.Security.Claims.ClaimsAuthenticationManager> 관리자 역할 들어오는 주 서버에 추가 합니다.  
  
#### 사용자 지정 Claimsauthenticationmanager을 사용 하 여 클레임 변환 구현 하기  
  
1.  Visual Studio 마우스 오른쪽 단추로 클릭은 솔루션을 클릭  **추가**를 누른 다음  **새 프로젝트**.  
  
2.  에  **새 프로젝트 추가** 창에서  **클래스 라이브러리** 에서  **C\#** 템플릿 목록에서 입력 `ClaimsTransformation`, 다음 키를 누릅니다  **확인**.  새 프로젝트를 솔루션 폴더에 만들어집니다.  
  
3.  마우스 오른쪽 단추로 클릭  **참조** 아래는  **ClaimsTransformation** 프로젝트를 누른 다음  **참조 추가**.  
  
4.  에  **관리자 참조** 창에서  **System.IdentityModel**를 누른 다음  **확인**.  
  
5.  열기  **Class1.cs**, 또는 없는 경우 마우스 오른쪽 단추로 클릭  **ClaimsTransformation**, 클릭  **추가**를 누른 다음  **클래스가 있습니다.**  
  
6.  다음 추가 코드 파일에 지시문을 사용 합니다.  
  
    ```csharp  
    using System.Security.Claims;  
    using System.Security.Principal;  
    ```  
  
7.  코드 파일에 다음 클래스 및 메서드를 추가 합니다.  
  
    > [!WARNING]
    >  다음 코드는 데모용입니다. 프로덕션 코드에 의도 된 사용 권한을 확인 하는 것이 있는지 확인 합니다.  
  
    ```csharp  
    public class ClaimsTransformationModule : ClaimsAuthenticationManager  
    {  
        public override ClaimsPrincipal Authenticate(string resourceName, ClaimsPrincipal incomingPrincipal)  
        {  
            if (incomingPrincipal != null && incomingPrincipal.Identity.IsAuthenticated == true)  
            {  
               ((ClaimsIdentity)incomingPrincipal.Identity).AddClaim(new Claim(ClaimTypes.Role, "Admin"));  
            }  
  
            return incomingPrincipal;  
        }  
    }  
    ```  
  
8.  파일을 저장 하 고 빌드는  **ClaimsTransformation** 프로젝트.  
  
9. 에  **TestApp** ASP.NET 프로젝트에서 참조를 마우스 오른쪽 단추로 누르고  **참조 추가**.  
  
10. 에  **관리자 참조** 창에서  **솔루션** 왼쪽된 메뉴에서 선택  **ClaimsTransformation** 에서 채워진 옵션과 클릭  **확인**.  
  
11. 루트에  **Web.config** 파일을 이동 하는  **\<system.identityModel\>** 항목.  내는  **\<identityConfiguration\>** 요소를 추가 하는 다음 줄 및 파일을 저장 합니다.  
  
    ```  
    <claimsAuthenticationManager type="ClaimsTransformation.ClaimsTransformationModule, ClaimsTransformation" />  
    ```  
  
## 3 단계 – 솔루션 테스트  
 이 단계에서 사용자는 폼 인증을 사용 하 여 서명 하면 클레임 나와 확인 하 고 ASP.NET Web Forms 응용 프로그램을 테스트 합니다.  
  
#### 폼 인증을 사용 하는 클레임에 대 한 ASP.NET Web Forms 응용 프로그램을 테스트 하려면  
  
1.  **F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  제공 될 해야  *Default.aspx*.  
  
2.  에  *Default.aspx* 페이지, 테이블 아래에 표시 합니다의  **를 클레임** 머리글 포함의  **발급자**,  **OriginalIssuer**,  **형식**,  **값**, 및  **ValueType** 클레임 정보를 계정에 대 한.  다음과 같은 방법으로 마지막 행 제공 해야 합니다.  
  
    ||||||  
    |-|-|-|-|-|  
    |로컬 권한|로컬 권한|http:\/\/schemas.microsoft.com\/ws\/2008\/06\/identity\/claims\/role|Admin|http:\/\/www.w3.org\/2001\/XMLSchema\#string|