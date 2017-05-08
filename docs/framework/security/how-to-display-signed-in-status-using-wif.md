---
title: "방법: WIF를 사용하여 로그인 상태 표시 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4d1174e4-5397-4962-9a5f-3b1ad7b3fc14
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# 방법: WIF를 사용하여 로그인 상태 표시
## 적용 대상  
  
-   Microsoft ® Windows ® Identity 기초 \(WIF\) 4.5  
  
-   ASP.NET® 웹 양식  
  
## 요약  
 이 항목의 기호 WIF를 사용 하는 ASP.NET 응용 프로그램의 상태를 표시 하는 방법을 설명 합니다.  WIF에 클레임 인식 응용 프로그램 및 관리 인증 및 권한 부여 응용 프로그램 리소스를 만들기 위한 메커니즘을 제공 합니다.  
  
## 내용  
  
-   개요  
  
-   단계 요약  
  
-   1 단계\-Id 설치 확장 액세스  
  
-   2 단계 – 신뢰 파티 ASP.NET 응용 프로그램 만들기  
  
-   사용자 인증에 사용 로컬 개발 STS – 3 단계  
  
-   4 단계\-상태에서 기호를 표시 하려면 ASP.NET 응용 프로그램을 수정 합니다.  
  
-   5 단계 – WIF 및 ASP.NET 응용 프로그램 간 통합을 테스트 합니다.  
  
## 개요  
 이 항목에는 WIF를 사용 하 여 간단한 클레임 인식 응용 프로그램을 만드는 방법 및 사용자의 로그인 여부를 쉽게 표시 하는 방법을 보여 줍니다.  다음 단계는 Id 및 액세스 Visual Studio 확장에 포함 된 로컬 개발 STS를 사용 합니다.  지역 개발 STS는 클레임 응용 프로그램에 통합 하는 간단한 방법을 제공 하는 개발 및 테스트 환경을 위한 것입니다.  절대로 사용 해야 프로덕션 환경에서 실제 인증을 수행 하지 않습니다 및 자격 증명이 필요 합니다.  그러나 다음 단계에서 명령 코드 실제 인증을 사용 하는 즉시 응용 프로그램에 대 한 같습니다.  
  
## 단계 요약  
  
-   1 단계\-Id 설치 확장 액세스  
  
-   2 단계 – 신뢰 파티 ASP.NET 응용 프로그램 만들기  
  
-   사용자 인증에 사용 로컬 개발 STS – 3 단계  
  
-   4 단계\-상태에서 기호를 표시 하려면 ASP.NET 응용 프로그램을 수정 합니다.  
  
-   5 단계 – WIF 및 ASP.NET 응용 프로그램 간 통합을 테스트 합니다.  
  
## 1 단계\-Id 설치 확장 액세스  
 이 단계에서는 Visual Studio 2012 Id 및 액세스 확장을 구성 하는 방법을 설명 합니다.  이 확장 STS 끝점과 통신 하는 응용 프로그램을 구성 하는 과정을 자동화 합니다.  
  
#### Id 및 액세스 확장을 설치 하려면  
  
1.  관리자 모드에서 관리자로 Visual Studio 시작 합니다.  
  
2.  Visual Studio 클릭  **도구** 를 클릭 하 고  **확장 관리자**.  **확장 관리자** 창이 나타납니다.  
  
3.  **확장 관리자**을 클릭  **온라인 확장** 왼쪽된 메뉴에서 선택  **Visual Studio 갤러리**.  
  
4.  오른쪽 위 모서리에서  **확장 관리자**를 검색  *Id 및 액세스*.  
  
5.  **Id 및 액세스** 항목이 검색 결과에 표시 됩니다.  클릭 한 다음 클릭  **다운로드**.  
  
6.  **다운로드 및 설치** 대화 상자가 나타납니다.  사용 조건에 동의 하면 클릭  **설치**.  
  
7.  경우는  **Id 및 액세스** 확장을 설치 했습니다, 관리자 모드에서 Visual Studio 다시 시작 합니다.  
  
## 2 단계 – 신뢰 파티 ASP.NET 응용 프로그램 만들기  
 이 단계에서는 당사자는 WIF를 사용 하 여 통합 된 ASP.NET Web Forms 응용 프로그램을 만드는 방법을 설명 합니다.  
  
#### 간단한 ASP.NET 응용 프로그램을 만들려면  
  
1.  Visual Studio 시작 하 고 클릭  **파일**,  **New**, 및  **프로젝트**.  
  
2.  에  **새 프로젝트** 창 클릭  **ASP.NET Web Forms 응용**.  
  
3.  In **Name**, enter `TestApp` and press **OK**.  
  
## 사용자 인증에 사용 로컬 개발 STS – 3 단계  
 이 단계는 응용 프로그램에서 로컬 개발 STS를 사용 하도록 설정 하는 방법을 설명 합니다.  Visual Studio 대 한 Id 및 액세스 확장을 사용 하 여 로컬 개발 STS 사용 됩니다.  
  
#### ASP.NET 응용 프로그램에서 로컬 개발 STS를 사용 하도록 설정 하려면  
  
1.  Visual Studio의  **TestApp** 프로젝트에서  **솔루션 탐색기**선택 후,  **Id 및 액세스**.  
  
2.  **Id 및 액세스** 창이 나타납니다.  **공급자**선택 합니다  **로컬 STS 개발을 사용 하 여 응용 프로그램 테스트**를 누른 다음  **적용**.  
  
## 4 단계\-상태에서 기호를 표시 하려면 ASP.NET 응용 프로그램을 수정 합니다.  
 이 단계에서는 현재 사용자가 로그인 되어 있는지 여부를 동적으로 표시 하도록 ASP.NET 응용 프로그램을 수정 하는 방법을 설명 합니다.  STS 공급자를 구성 하 고 나면 WIF 들어오는 클레임을 처리 합니다.  이제 인증의 결과 표시 하는 코드를 응용 프로그램을 구성 해야 합니다.  
  
#### 상태에서 기호를 표시 하려면  
  
1.  Visual Studio 엽니다의  **Default.aspx** 파일은  **TestApp** 프로젝트.  
  
2.  기존 태그를 바꿉니다 있는  **Default.aspx** 파일에 다음 태그를 사용 하 여:  
  
    ```  
    <%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head runat="server">  
        <title>Logged In Status</title>  
    </head>  
    <body>  
        <asp:label ID="myLabel" runat="server" />  
    </body>  
    </html>  
    ```  
  
3.  저장  **Default.aspx**를 연 다음 해당 코드 숨김 파일 이라는  **Default.aspx.cs**.  
  
    > [!NOTE]
    >  **Default.aspx.cs** 아래에 숨겨져 있을 수 있습니다  **Default.aspx** 솔루션 탐색기에서.  경우  **Default.aspx.cs** 보이지 않으면 확장  **Default.aspx** 옆에 있는 삼각형을 클릭 하 여 합니다.  
  
4.  기존 코드를 대체  **Default.aspx.cs** 다음 코드를 사용 합니다.  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        protected void Page_Load(object sender, EventArgs e)  
        {  
            ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
            if (claimsPrincipal != null)  
            {  
                myLabel.Text = "You are signed in.";  
            }  
            else  
            {  
                myLabel.Text = "You are not signed in.";  
            }  
        }  
    }  
    ```  
  
5.  저장  **Default.aspx.cs**를 하 고 있습니다.  
  
## 5 단계 – WIF 및 ASP.NET 응용 프로그램 간 통합을 테스트 합니다.  
 이 단계는 WIF 및 ASP.NET 응용 프로그램 간 통합을 테스트 하는 방법을 설명 합니다.  
  
#### WIF와 ASP.NET 통합 테스트  
  
1.  Visual Studio  **F5** 응용 프로그램 디버깅을 시작 합니다.  오류가 발견 되 면 새 브라우저 창이 열립니다.  
  
2.  브라우저 요청 STS를 자동으로 리디렉션합니다 하 고 Default.aspx 페이지를 열고 다음을 볼 수 있습니다.  WIF 제대로 구성 되어 있으면 다음과 같은 텍스트를 표시 하는 사이트 나타납니다:  **"서명 된"**.