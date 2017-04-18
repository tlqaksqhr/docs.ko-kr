---
title: "방법: 토큰 재생 검색 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a9f5771-f5f6-4100-8501-406aa20d731a
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# 방법: 토큰 재생 검색 사용
## 적용 대상  
  
-   Microsoft ® Windows ® Identity Foundation \(소리치 더\)  
  
-   ASP.NET® Web Forms  
  
## 요약  
 이 방법 소리치 더 사용 하는 ASP.NET 응용 프로그램에서 토큰 재생 검색 사용에 대 한 상세한 단계별 절차를 제공 합니다.  또한 토큰 재생 검색 설정 되어 있는지 확인 하려면 응용 프로그램을 테스트 하는 방법에 대 한 지침을 제공 합니다.  이 방법에는 보안 토큰 서비스 \(STS\)을 만들기에 대 한 자세한 없고 대신 Id 및 액세스 도구와 함께 제공 되는 개발 STS를 사용 하 여.  개발 STS 실제 인증을 수행 하지 않습니다 및 테스트 목적 으로만 사용 됩니다.  이 방법 완료 Id 및 액세스 도구를 설치 해야 합니다.  다음 위치에서 다운로드할 수 있습니다: [Id 및 액세스 도구](http://go.microsoft.com/fwlink/?LinkID=245849)  
  
## 내용  
  
-   목표  
  
-   개요  
  
-   단계 요약  
  
-   1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 및 사용 재생 검색 만들기  
  
-   2 단계 – 솔루션 테스트  
  
## 목표  
  
-   소리치 더 개발 STS에서 Id 및 액세스 도구를 사용 하는 간단한 ASP.NET 응용 프로그램 만들기  
  
-   토큰 재생 검색을 사용 하 고 작동 하는지 확인 합니다.  
  
## 개요  
 클라이언트는 상대가 이미 사용한 클라이언트는 STS 토큰을 인증 하려고 하면 재생 공격이 발생 합니다.  이 공격을 방지 하려면 소리치 더 재생 검색 캐시를 이전에 사용한 STS 토큰을 포함 합니다.  사용 하는 경우 재생 검색 토큰의 들어오는 요청을 검사 및 토큰 사용 이전에 있는지 확인 합니다.  토큰이 이미 사용 된 경우 요청을 거부 하는 <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> 예외가 throw 됩니다.  
  
 재생 검색을 사용 하려면 필요한 구성 변경 다음 단계를 보여 줍니다.  
  
## 단계 요약  
  
-   1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 및 사용 재생 검색 만들기  
  
-   2 단계 – 솔루션 테스트  
  
## 1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 및 사용 재생 검색 만들기  
 이 단계에서는 새 ASP.NET Web Forms 응용 프로그램 만들기 및 수정 되는  *Web.config* 재생 검색을 사용 하는 파일.  
  
#### 간단한 ASP.NET 응용 프로그램을 만들려면  
  
1.  Visual Studio 시작 하 고 클릭  **파일**,  **New**, 다음  **프로젝트**.  
  
2.  에  **새 프로젝트** 창에서 클릭  **ASP.NET 웹 폼 응용 프로그램**.  
  
3.  In **Name**, enter `TestApp` and press **OK**.  
  
4.  마우스의  **TestApp** 프로젝트에서  **솔루션 탐색기**, 선택  **Id 및 액세스**.  
  
5.  **Id 및 액세스** 창이 나타납니다.  아래  **공급자**,  **테스트 응용 프로그램에 로컬 개발 STS**, 누른 다음  **적용**.  
  
6.  다음 추가  **\<tokenReplayDetection\>** 요소에는  *Web.config* 바로 다음 구성 파일은  **\<system.identityModel\>** 및  **\<identityConfiguration\>** 요소를 다음과 같이 표시:  
  
    ```  
    <system.identityModel>  
        <identityConfiguration>  
            <tokenReplayDetection enabled=”true”/>  
    ```  
  
## 2 단계 – 솔루션 테스트  
 이 단계에서는 재생 검색 설정 되어 있는지 확인 하려면 ASP.NET 소리치 더 사용이 가능한 응용 프로그램을 테스트 합니다.  
  
#### 재생 검색에 대 한 ASP.NET 소리치 더 사용이 가능한 응용 프로그램을 테스트 하려면  
  
1.  키를 눌러 솔루션을 실행할의  **F5** 키.  기본 홈 페이지 ASP.NET 두고 자동으로 사용자를 인증 해야  *김동훈*을, 개발 STS에서 반환 되는 기본 사용자입니다.  
  
2.  브라우저의 키를  **다시** 단추.  제공 될 해야는  **서버 오류 '\/' 응용 프로그램** 페이지 다음 설명과 함께:  *ID1062: 재생에 대 한 검색 되었습니다: 토큰: 'System.IdentityModel.Tokens.SamlSecurityToken'*가 오고 그 뒤에  *AssertionId* 및  *발급자*.  
  
     때문에이 오류 페이지를 볼 수 있습니다 예외 형식의 <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> 토큰 재생 검색 되었을 때 발생 합니다.  토큰을 먼저 표시 하는 경우 초기 POST 요청을 다시 보내도록 시도 하기 때문에이 오류가 발생 합니다.  **다시** 단추 없습니다 하면이 문제가 후속 요청을 서버에.