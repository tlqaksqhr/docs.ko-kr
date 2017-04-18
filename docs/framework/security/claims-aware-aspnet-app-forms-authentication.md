---
title: "방법: 양식 기반 인증을 사용하여 클레임 인식 ASP.NET 응용 프로그램 빌드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98a3e029-1a9b-4e0c-b5d0-29d3f23f5b15
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# 방법: 양식 기반 인증을 사용하여 클레임 인식 ASP.NET 응용 프로그램 빌드
## 적용 대상  
  
-   Microsoft ® Windows ® Identity Foundation \(소리치 더\)  
  
-   ASP.NET® Web Forms  
  
## 요약  
 이 방법 폼 인증을 사용 하는 간단한 클레임 인식 ASP.NET Web Forms 응용 프로그램을 만들기 위한 자세한 단계별 절차를 제공 합니다.  또한 사용자는 폼 인증을 사용 하 여 서명 하면 클레임 나와 확인 하려면 응용 프로그램을 테스트 하는 방법에 대 한 지침을 제공 합니다.  
  
## 내용  
  
-   목표  
  
-   개요  
  
-   단계 요약  
  
-   1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 만들기  
  
-   2 단계 – ASP.NET 웹 폼 응용 프로그램에 대 한 폼 인증을 사용 하 여 클레임 구성  
  
-   3 단계 – 솔루션 테스트  
  
## 목표  
  
-   ASP.NET Web Forms 응용 프로그램의 폼 인증을 사용 하 여 클레임 구성  
  
-   ASP.NET Web Forms 응용 프로그램에서 제대로 작동 하는지 테스트 합니다.  
  
## 개요  
 .NET 4.5에서 소리치 더 및 해당 클레임 기반 권한 부여 프레임 워크의 필수적인 부분으로 포함 되었습니다.  이전에 ASP.NET 사용자는 클레임을 원한다 면 소리치 더를 설치할 필요는, 다음 캐스트 보안 주체를 개체 같은 인터페이스 `Thread.CurrentPrincipal` 또는 `HttpContext.Current.User`.  이제 클레임 자동으로 이러한 사용자가 개체 처리 됩니다.  
  
 클레임 관련 양식에서 자동으로 인증 된 모든 사용자가 있기 때문에 폼 인증에.net 4.5 소리치 더의 포함에서 높아졌습니다.  이 방법에서 볼 수 있듯이 이러한 클레임 ASP.NET 응용 프로그램에서 폼 인증을 사용 하 여 바로 사용을 시작할 수 있습니다.  
  
## 단계 요약  
  
-   1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 만들기  
  
-   2 단계 – ASP.NET 웹 폼 응용 프로그램에 대 한 폼 인증을 사용 하 여 클레임 구성  
  
-   3 단계 – 솔루션 테스트  
  
## 1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 만들기  
 이 단계에서는 새 ASP.NET Web Forms 응용 프로그램을 만듭니다.  
  
#### 간단한 ASP.NET 응용 프로그램을 만들려면  
  
1.  Visual Studio 시작 하 고 클릭  **파일**,  **New**, 다음  **프로젝트**.  
  
2.  에  **새 프로젝트** 창에서 클릭  **ASP.NET 웹 폼 응용 프로그램**.  
  
3.  In **Name**, enter `TestApp` and press **OK**.  
  
## 2 단계 – ASP.NET 웹 폼 응용 프로그램에 대 한 폼 인증을 사용 하 여 클레임 구성  
 이 단계에서 구성 항목을 추가 합니다의  *Web.config* 구성 파일 및 편집의  *Default.aspx* 파일을 계정에 대 한 정보를 주장 합니다.  
  
#### Forms 인증을 사용 하는 클레임에 대 한 ASP.NET 응용 프로그램을 구성 하려면  
  
1.  에  *Default.aspx* 파일, 기존 태그를 다음 코드로 바꿉니다:  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
        <p>  
            This page displays the claims associated with a Forms authenticated user.          
        </p>  
        <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
  
    ```  
  
     이 단계는 GridView 컨트롤을  *Default.aspx* 클레임을 채워야 하는 페이지 검색 폼 인증에서.  
  
2.  저장 된  *Default.aspx* 파일을 다음 코드 숨김 파일을 열고  *Default.aspx.cs*.  기존 코드를 다음 코드로 바꿉니다.  
  
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
  
                if (claimsPrincipal != null)  
                {  
                    this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                    this.ClaimsGridView.DataBind();  
                }  
            }  
        }  
    }  
    ```  
  
     위의 코드 식별 폼 인증으로 사용자를 포함 하 여 인증 된 사용자에 대 한 클레임을 표시 합니다.  
  
## 3 단계 – 솔루션 테스트  
 이 단계에서 사용자는 폼 인증을 사용 하 여 서명 하면 클레임 나와 확인 하 고 ASP.NET Web Forms 응용 프로그램을 테스트 합니다.  
  
#### 폼 인증을 사용 하는 클레임에 대 한 ASP.NET Web Forms 응용 프로그램을 테스트 하려면  
  
1.  **F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  제공 될 해야  *Default.aspx*,이  **등록** 및  **로그인** 맨 위에서 링크 페이지의 오른쪽.  **등록**을 클릭합니다.  
  
2.  에  **등록** 페이지에서 사용자 계정을 만들어야 하 고 누른 다음  **등록**.  폼 인증을 사용 하 여 계정을 만들 수 있습니다 및 자동으로 로그인 해야 합니다.  
  
3.  홈 페이지로 리디렉션된 후 테이블 아래에 표시 됩니다의  **를 클레임** 머리글 포함의  **발급자**,  **OriginalIssuer**,  **형식**,  **값**, 및  **ValueType** 사용자 계정에 대 한 정보를 주장.