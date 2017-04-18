---
title: "방법: Windows 인증을 사용하여 클레임 인식 ASP.NET 응용 프로그램 빌드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 11c53d9d-d34a-44b4-8b5e-22e3eaeaee93
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# 방법: Windows 인증을 사용하여 클레임 인식 ASP.NET 응용 프로그램 빌드
## 적용 대상  
  
-   Microsoft ® Windows ® Identity Foundation \(소리치 더\)  
  
-   ASP.NET® Web Forms  
  
## 요약  
 이 방법 Windows 인증을 사용 하는 간단한 클레임 인식 ASP.NET Web Forms 응용 프로그램을 만들기 위한 자세한 단계별 절차를 제공 합니다.  또한 사용자는 Windows 인증을 사용 하 여 서명 하면 클레임 나와 확인 하려면 응용 프로그램을 테스트 하는 방법에 대 한 지침을 제공 합니다.  
  
## 내용  
  
-   목표  
  
-   개요  
  
-   단계 요약  
  
-   1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 만들기  
  
-   2 단계 – ASP.NET 웹 폼 응용 프로그램에 대 한 Windows 인증을 사용 하 여 클레임 구성  
  
-   3 단계 – 솔루션 테스트  
  
## 목표  
  
-   ASP.NET Web Forms 응용 프로그램이 Windows 인증을 사용 하는 클레임에 대 한 구성  
  
-   ASP.NET Web Forms 응용 프로그램에서 제대로 작동 하는지 테스트 합니다.  
  
## 개요  
 .NET 4.5에서 소리치 더 및 해당 클레임 기반 권한 부여 프레임 워크의 필수적인 부분으로 포함 되었습니다.  이전에 ASP.NET 사용자는 클레임을 원한다 면 소리치 더를 설치할 필요는, 다음 캐스트 보안 주체를 개체 같은 인터페이스 `Thread.CurrentPrincipal` 또는 `HttpContext.Current.User`.  이제 클레임 자동으로 이러한 사용자가 개체 처리 됩니다.  
  
 자동으로 Windows 자격 증명으로 인증 된 모든 사용자가 해당 클레임 없으므로.net 4.5에 소리치 더의 포함에서 Windows 인증이 높아졌습니다.  이 방법에서 볼 수 있듯이 이러한 클레임 ASP.NET 응용 프로그램에서 Windows 인증을 사용 하 여 바로 사용을 시작할 수 있습니다.  
  
## 단계 요약  
  
-   1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 만들기  
  
-   2 단계 – ASP.NET 웹 폼 응용 프로그램에 대 한 Windows 인증을 사용 하 여 클레임 구성  
  
-   3 단계 – 솔루션 테스트  
  
## 1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 만들기  
 이 단계에서는 새 ASP.NET Web Forms 응용 프로그램을 만듭니다.  
  
#### 간단한 ASP.NET 응용 프로그램을 만들려면  
  
1.  Visual Studio 시작 하 고 클릭  **파일**,  **New**, 다음  **프로젝트**.  
  
2.  에  **새 프로젝트** 창에서 클릭  **ASP.NET 웹 폼 응용 프로그램**.  
  
3.  In **Name**, enter `TestApp` and press **OK**.  
  
4.  다음은  **TestApp** 프로젝트 작성 되었습니다를 클릭  **솔루션 탐색기**.  프로젝트의 속성에는  **속성** 창 아래  **솔루션 탐색기**.  설정 된  **Windows 인증** 속성을  **사용**.  
  
    > [!WARNING]
    >  수동으로 설정 해야 하므로 Windows 인증 새 ASP.NET 응용 프로그램에서 기본적으로 사용할 수 없습니다.  
  
## 2 단계 – ASP.NET 웹 폼 응용 프로그램에 대 한 Windows 인증을 사용 하 여 클레임 구성  
 이 단계에서는 구성 항목을 추가 합니다의  *Web.config* 구성 파일을 수정 하 고는  *Default.aspx* 파일을 계정에 대 한 정보를 주장.  
  
#### Windows 인증을 사용 하는 클레임에 대 한 ASP.NET 응용 프로그램을 구성 하려면  
  
1.  에  **TestApp** 프로젝트의  *Default.aspx* 파일, 기존 태그를 다음 코드로 바꿉니다:  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
        <p>  
            This page displays the claims associated with a Windows authenticated user.          
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
  
     이 단계는 GridView 컨트롤을  *Default.aspx* 클레임을 채워야 하는 페이지에서 Windows 인증 검색.  
  
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
                this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                this.ClaimsGridView.DataBind();  
            }  
        }  
    }  
    ```  
  
     위의 코드는 인증 된 사용자에 대 한 클레임을 표시 합니다.  
  
3.  응용 프로그램의 인증 형식을 변경 하려면 수정의  **\<authentication\>** 차단  **\<system.web\>** 섹션의 루트 프로젝트의  *Web.config* 단지 다음 구성 항목이 포함 되도록 파일:  
  
    ```  
    <authentication mode="Windows" />  
    ```  
  
4.  마지막으로 수정의  **\<authorization\>** 차단  **\<system.web\>** 동일한 섹션  *Web.config* 인증 할 파일:  
  
    ```  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    ```  
  
## 3 단계 – 솔루션 테스트  
 이 단계에서 사용자는 Windows 인증을 사용 하 여 서명 하면 클레임 나와 확인 하 고 ASP.NET Web Forms 응용 프로그램을 테스트 합니다.  
  
#### Windows 인증을 사용 하는 클레임에 대 한 ASP.NET Web Forms 응용 프로그램을 테스트 하려면  
  
1.  **F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  제공 될 해야  *Default.aspx*, 및 Windows 계정 이름 \(도메인 이름 포함\) 이미 인증 된 사용자는 위쪽에 표시 됩니다 오른쪽.  콘텐츠 페이지의 Windows 계정에서 검색할 클레임으로 채워진 테이블을 포함 해야 합니다.