---
title: "방법: CLR 활성화 문제 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "CLR 활성화, 디버깅 문제"
ms.assetid: 4fe17546-d56e-4344-a930-6d8e4a545914
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: CLR 활성화 문제 디버깅
CLR\(공용 언어 런타임\)의 올바른 버전으로 실행하여 응용 프로그램을 구하는 동안 문제가 발생하는 경우 CLR 활성화 로그를 보고 디버깅할 수 있습니다.  이러한 로그는 응용 프로그램이 예상과 다른 CLR 버전을 로드하거나 CLR을 전혀 로드하지 않을 때 활성화 문제의 근원을 확인하는 데 매우 유용할 수 있습니다.  [.NET Framework 초기화 오류: 사용자 환경 관리](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md)에서는 응용 프로그램에 대해 검색된 CLR이 없는 경우에 대해 설명합니다.  
  
 CLR 활성화 로깅은 HKEY\_LOCAL\_MACHINE 레지스트리 키 또는 시스템 환경 변수를 사용하여 시스템 차원에서 활성화할 수 있습니다.  로그는 레지스트리 항목 또는 환경 변수가 제거될 때까지 생성됩니다.  또는 사용자나 프로세스가 로컬 환경 변수를 사용하여 다른 범위와 기간의 로깅을 사용할 수 있습니다.  
  
 CLR 활성화 로그는 완전히 다른 [어셈블리 바인딩 로그](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md)와 혼동하면 안 됩니다.  
  
## CLR 활성화 로깅을 사용하는 방법  
  
#### 레지스트리 사용  
  
1.  레지스트리 편집기에서 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework\(32비트 컴퓨터\) 또는 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\.NETFramework 폴더\(64비트 컴퓨터\)를 탐색합니다.  
  
2.  `CLRLoadLogDir`라는 문자열 값을 추가하고 CLR 활성화 로그를 저장하고자 하는 기존 디렉터리의 전체 경로에 설정합니다.  
  
 문자열 값을 제거할 때까지 로깅 활성화를 설정된 상태로 유지합니다.  
  
#### 환경 변수 사용  
  
-   `COMPLUS_CLRLoadLogDir` 환경 변수를 CLR 활성화 로그를 저장하려는 기존 디렉터리의 전체 경로를 나타내는 문자열로 설정합니다.  
  
     환경 변수를 설정하여 범위를 확인하는 방법:  
  
    -   시스템 수준에서 설치하는 경우 환경 변수가 제거될 때까지 해당 컴퓨터에서 모든 .NET Framework 응용 프로그램에 대해 활성화 로깅이 활성화됩니다.  
  
    -   사용자 수준에서 설치하는 경우 현재 사용자 계정에 대해서만 활성화 로깅이 사용됩니다.  환경 변수를 제거할 때까지 로깅을 계속합니다.  
  
    -   프로세스 내에서 CLR를 로드하기 전에 이를 설정하였다면 프로세스가 종료될 때까지 로깅 활성화를 사용할 수 있습니다.  
  
    -   응용 프로그램을 실행하기 전에 명령 프롬프트에서 이를 설정하였다면, 해당 명령 프롬프트에서 실행되는 모든 응용 프로그램에 로깅 활성화가 가능합니다.  
  
     예를 들어, 응용 프로그램을 실행하기 전에 프로세스 수준에서 c:\\clrloadlogs 디렉터리에 활성화 로그를 저장하려면 명령 프롬프트 창을 열고 다음을 입력합니다.  
  
    ```  
    set COMPLUS_CLRLoadLogDir=c:\clrloadlogs  
    ```  
  
## 예제  
 CLR 활성화 로그는 CLR 활성화 및 CLR 호스팅 API의 사용에 대한 다량의 데이터를 제공합니다.  이 글에서 설명한 것처럼 이 데이터의 대부분은 Microsoft 내부에서 사용되지만 일부 데이터는 개발자도 사용할 수 있습니다.  
  
 로그는 CLR 호스팅 API가 호출되는 순서를 반영합니다.  또한 컴퓨터에서 검색하여 설치된 런타임 집합에 대한 유용한 데이터를 포함합니다.  CLR 활성화 로그 형식은 자체적으로 문서화되지 않지만 CLR 활성화 문제를 해결해야 하는 개발자를 지원하는 데 사용할 수 있습니다.  
  
> [!NOTE]
>  CLR을 사용하는 프로세스가 종료될 때까지 활성화 로그를 열 수 없습니다.  
  
> [!NOTE]
>  CLR 활성화 로그는 지역화되지 않습니다. 이 로그는 항상 영어로 생성됩니다.  
  
 활성화 로그의 다음 예에서 가장 유용한 정보가 강조 표시되고 로그 다음에 설명됩니다.  
  
```  
532,205950.367,CLR Loading log for C:\Tests\myapp.exe   
532,205950.367,Log started at 4:26:12 PM on 10/6/2011   
532,205950.367,-----------------------------------   
532,205950.382,FunctionCall: _CorExeMain   
532,205950.382,FunctionCall: ClrCreateInstance, Clsid: {2EBCD49A-1B47-4A61-B13A-4A03701E594B}, Iid: {E2190695-77B2-492E-8E14-C4B3A7FDD593}   
532,205950.382,MethodCall: ICLRMetaHostPolicy::GetRequestedRuntime. Version: (null), Metahost Policy Flags: 0x168, Binary: (null), Iid: {BD39D1D2-BA2F-486A-89B0-B4B0CB466891}   
532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0   
532,205950.382,Input values for ComputeVersionString follow this line   
532,205950.382,-----------------------------------   
532,205950.382,Default Application Name: C:\Tests\myapp.exe   
532,205950.382,IsLegacyBind is: 0   
532,205950.382,IsCapped is 0   
532,205950.382,SkuCheckFlags are 0   
532,205950.382,ShouldEmulateExeLaunch is 0   
532,205950.382,LegacyBindRequired is 0   
532,205950.382,-----------------------------------   
532,205950.382,Parsing config file: C:\Tests\myapp.exe   
532,205950.382,UseLegacyV2RuntimeActivationPolicy is set to 0   
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe   
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe   
532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727   
532,205950.382,ERROR: Version v2.0.50727 is not present on the machine.   
532,205950.398,SEM_FAILCRITICALERRORS is set to 0   
532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3   
532,205950.398,FunctionCall: RealDllMain. Reason: 0   
532,205950.398,FunctionCall: OnShimDllMainCalled. Reason: 0  
  
```  
  
-   **CLR 로드 로그**는 관리되는 코드를 로드한 프로세스를 시작했던 실행 파일의 경로를 제공합니다.  네이티브 호스트가 될 수 있습니다.  
  
    ```  
    532,205950.367,CLR Loading log for C:\Tests\myapp.exe  
  
    ```  
  
-   **설치된 런타임**은 활성화 요청을 위한 후보인 컴퓨터에 설치된 CLR 버전 집합입니다.  
  
    ```  
    532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0  
  
    ```  
  
-   **built with version**은 [ICLRMetaHostPolicy::GetRequestedRuntime](../Topic/ICLRMetaHostPolicy::GetRequestedRuntime%20Method.md) 같은 메서드에 제공된 이진을 빌드하는 데 사용된 CLR의 버전입니다.  
  
    ```  
    532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727  
  
    ```  
  
-   **요청 시 기능 설치**는 Windows 8에서 .NET Framework 3.5를 활성화함을 의미합니다.  이 시나리오에 대한 자세한 내용은 [.NET Framework 초기화 오류: 사용자 환경 관리](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md)를 참조하십시오.  
  
    ```  
    532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3  
  
    ```  
  
## 참고 항목  
 [배포](../../../docs/framework/deployment/net-framework-and-applications.md)   
 [방법: .NET Framework 4 또는 4.5를 지원하도록 응용 프로그램 구성](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)