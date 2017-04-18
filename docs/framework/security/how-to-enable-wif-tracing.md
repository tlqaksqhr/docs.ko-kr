---
title: "방법: WIF 추적 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 271b6889-3454-46ff-96ab-9feb15e742ee
caps.latest.revision: 3
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 3
---
# 방법: WIF 추적 사용
## 적용 대상  
  
-   Microsoft ® Windows ® Identity 기초 \(WIF\)  
  
-   ASP.NET® 웹 양식  
  
## 요약  
 이 방법 ASP.NET 응용 프로그램에 WIF 추적 설정에 대 한 상세한 단계별 절차를 제공 합니다.  또한 제공 되었는지 확인 하려면 응용 프로그램을 테스트 하는 지침 추적 수신기 및 로그는 제대로 작동 합니다.  이 방법에는 서비스가 STS \(보안 토큰\)를 만들기 위한 자세한 지침은 없고 대신 Id 및 액세스 도구로 개발 STS를 사용 하 여.  STS 개발 실제 인증을 수행 하지 않습니다 및 테스트 목적 으로만 위한 것입니다.  Id 및 액세스이 방법이를 수행 하려면 도구를 설치 해야 합니다.  다음 위치에서 다운로드할 수 있습니다: [Id 및 액세스 도구](http://go.microsoft.com/fwlink/?LinkID=245849)  
  
> [!IMPORTANT]
>  수동 응용 프로그램에 WIF 추적, WS\-페더레이션 프로토콜을 사용 하는 응용 프로그램을 발생할 수 악의적인 사용자를 응용 프로그램 \(DoS\) 서비스 거부 공격 또는 정보 유출.  수동 RPs와 수동 STSes이 포함 되어 있습니다.  이러한 이유로 하지 사용 하는 WIF 추적 수동 RPs 또는 STSes에 대 한 프로덕션 환경에서 하는 것이 좋습니다.  
  
## 내용  
  
-   목표  
  
-   개요  
  
-   단계 요약  
  
-   1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 만들기 및 추적 사용  
  
-   2 단계\-솔루션 테스트  
  
## 목표  
  
-   WIF 및 개발 STS에서 Id 및 액세스 도구를 사용 하는 간단한 ASP.NET 응용 프로그램 만들기  
  
-   추적 기능을 사용 하 고 작동 하는지 확인 하십시오.  
  
## 개요  
 추적을 사용 하면 디버깅 하 고 여러 유형의 WIF에서 토큰 등, 쿠키, 클레임, 프로토콜 메시지를 사용 하 여 문제를 해결 합니다.  WCF 추적; WIF 추적이 비슷합니다. 예를 들어, 중요 한 메시지에 이르기까지 모든 메시지를 표시 하는 추적의 자세한 정도 선택할 수 있습니다.  WIF 추적에서 생성 될 수 있습니다  **.xml** 파일이 나  **.svclog** 서비스 추적 뷰어 도구를 사용 하 여 볼 수 있는 파일입니다.  이 도구에는  **bin** 디렉터리의 Windows SDK 설치 경로 컴퓨터의 예:  **C:\\Program 서식 SDKs\\Windows\\v7.1\\Bin\\SvcTraceViewer.exe**.  
  
## 단계 요약  
  
-   1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 만들기 및 추적 사용  
  
-   2 단계\-솔루션 테스트  
  
## 1 단계 – 간단한 ASP.NET 웹 폼 응용 프로그램 만들기 및 추적 사용  
 이 단계에서는 새 ASP.NET Web Forms 응용 프로그램 만들기 및 수정 됩니다는  *Web.config* 추적을 설정 하는 파일입니다.  
  
#### 간단한 ASP.NET 응용 프로그램을 만들려면  
  
1.  Visual Studio 시작 하 고 클릭  **파일**,  **New**, 및  **프로젝트**.  
  
2.  에  **새 프로젝트** 창 클릭  **ASP.NET Web Forms 응용**.  
  
3.  In **Name**, enter `TestApp` and press **OK**.  
  
4.  마우스 오른쪽 단추로 클릭 하면  **TestApp** 프로젝트에서  **솔루션 탐색기**선택 후,  **Id 및 액세스**.  
  
5.  **Id 및 액세스** 창이 나타납니다.  **공급자**선택 합니다  **로컬 STS 개발을 사용 하 여 응용 프로그램 테스트**를 누른 다음  **적용**.  
  
6.  새 폴더 만들기에 명명 된  **로그** 의 루트에는  **c:** 드라이브 처럼 표시:  **C:\\logs**  
  
7.  다음 추가 **\<system.diagnostics\>** 요소는  *Web.config* 구성 파일 바로 뒤에 닫는 **\<\/configSections\>** 요소를 같은 표시:  
  
    ```  
    <configuration>  
        <configSections>  
        …  
        </configSections>  
        <system.diagnostics>  
            <sources>  
                <source name="System.IdentityModel" switchValue="Verbose">  
                    <listeners>  
                        <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="C:\logs\WIF.xml" />  
                    </listeners>  
                </source>  
            </sources>  
            <trace autoflush="true" />  
        </system.diagnostics>  
    ```  
  
    > [!NOTE]
    >  지정 된 디렉터리 위치는  **initializeData** 특성 로깅을 시작 하기 전에 존재 해야 합니다.  위치가 존재 하지 않는 경우 없음 로그가 생성 됩니다.  
  
     위의 구성을 설정 하면  **Verbose** 군에 대 한 추적 결과 로그를 저장 하 고는  **C:\\logs\\WIF.xml** 파일입니다.  
  
## 2 단계\-솔루션 테스트  
 이 단계에서 로그가 기록 되 고 있는지 확인 하기 위해 WIF를 사용 하는 ASP.NET 응용 프로그램을 테스트 합니다.  
  
#### 성공 추적 WIF를 사용 하는 ASP.NET 응용 프로그램을 테스트 하려면  
  
1.  키를 눌러 솔루션을 실행 하면  **F5** 키.  기본 ASP.NET 홈 페이지에 표시 되 고 자동으로 사용자를 인증 해야  *관리할 수 없*는를 개발 STS에서 반환 되는 기본 사용자입니다.  
  
2.  브라우저 창을 닫은 다음으로 이동은  **C:\\logs** 폴더입니다.  열려 있는  **C:\\logs\\WIF.xml** 파일을 텍스트 편집기를 사용 하 여.  
  
3.  검사는  **WIF.xml** 로 시작 하는 항목이 포함 되어 있는지 확인 하 고 파일을 **\<E2ETraceEvent\>**.  이러한 추적 포함 됩니다 **\<TraceRecord\>** 추적 된 작업에 대 한 설명 사용 하 여 요소와 같은  **SecurityToken 유효성 검사**.