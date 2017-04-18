---
title: ".NET Core 및 오픈 소스 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e6bd4655-ce37-4003-8462-468a6fe2c40f
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 6
---
# .NET Core 및 오픈 소스
.NET Core는 코드 재사용 및 코드 공유를 최대화하기 위해 플랫폼 간에 이식 가능 하도록 설계된.NET Framework의 모듈식 버전입니다. 또한 .NET Core는 오픈 소스이며 커뮤니티에서 기여한 내용을 수락합니다. 이 항목에서는 .NET Core 및 오픈 소스 패키지에 액세스하고 기여하는 방법과 관련된 일반적인 질문에 대한 답변을 제공합니다.  
  
<a name="BKMK_WhatisNETCore"></a>   
## .NET Core란?  
 앞에서 언급했듯이 .NET Core는 플랫폼 간에 이식 가능 하도록 설계된.NET Framework의 모듈식 버전입니다.  
  
 .NET Core는 전체 .NET Framework의 하위 집합이지만 필요한 앱 기능을 구현하고 플랫폼 대상에 관계없이 이 코드를 재사용하기 위한 주요 기능을 제공하기 때문에 플랫폼 간에 이식 가능합니다. 과거의 다양한 플랫폼용 .NET 버전에는 로컬 파일 읽기와 같은 주요 작업을 위한 공유 기능이 없었습니다. .NET Core에서 대상으로 지정할 수 있는 Microsoft 플랫폼에는 기존의 데스크톱 Windows, Windows 장치 및 휴대폰이 포함됩니다. Xamarin과 같은 타사 도구를 사용하면 .NET Core를 IOS 및 Android 장치로 이식할 수 있습니다. 또한 Mac 및 Linux 운영 체제에서 웹앱을 실행할 수 있도록 해당 운영 체제용 .NET Core도 곧 제공될 예정입니다.  
  
 .NET Core는 NuGet을 통해 작은 어셈블리 패키지로 릴리스되므로 모듈식입니다. 대부분의 핵심 기능을 포함하는 하나의 큰 어셈블리 대신, .NET Core는 작은 기능 중심 패키지로 제공됩니다. 따라서 보다 민첩한 개발 모델이 가능하며 앱과 라이브러리에 필요한 기능 조각을 선택할 수 있습니다. NuGet에 릴리스되는 .NET 패키지에 대한 자세한 내용은 [.NET Framework 및 번외 릴리스](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)를 참조하세요.  
  
 다음은 .NET Core와 관련된 몇 가지 질문과 대답입니다.  
  
### .NET Core를 최대한 활용하려면 어떻게 해야 하나요?  
 기존 앱의 경우 PCL\(이식 가능한 클래스 라이브러리\) 및 범용 앱 프로젝트를 사용하고 플랫폼 특정 코드에서 비즈니스 논리를 분리하는 것이 .NET Core를 활용하고 코드 재사용을 최대화하는 가장 좋은 방법입니다. 앱에 대해 MVC\(Model\-View\-Controller\) 또는 MVVM\(Model View\-ViewModel\) 패턴을 선택하여 앱을 .NET Core로 쉽게 마이그레이션할 수 있게 하는 것이 좋습니다.  
  
### .NET Core는 호환성 및 배포에 어떤 영향을 주나요?  
 몇 가지 배포 시나리오가 있지만 배포 작업은 여전히 용이합니다. .NET Framework는 현재와 마찬가지로 Windows와 함께 배포되고 Microsoft 업데이트를 통해 업데이트 됩니다. 앱이 디스크에 있는 이 .NET Framework 배포를 사용하는 경우도 있고 앱 패키지와 함께 배포되는 .NET 어셈블리를 사용하는 경우도 있습니다. 또한 버전 간 호환성은 여전히 .NET Framework에서 우선 순위가 높으므로 앱이 컴파일 시의 대상 어셈블리보다 최신 버전에서 실행되는 경우에도 해당 동작이 동일하게 유지되어야 합니다.  
  
|시나리오|배포|  
|----------|--------|  
|Windows 컴퓨터에서 실행되는 Windows 데스크톱 및 ASP.NET 앱|배포는 현재와 동일합니다. 앱이 서버나 사용자 컴퓨터의 .NET Framework 설치를 사용합니다. .NET Framework가 설치되어 있지 않으면 설치하라는 메시지가 표시됩니다. 또는 .NET 설치를 앱에 연결할 수 있습니다. .NET Framework에 포함되지 않은 .NET Core 어셈블리를 사용하는 경우 해당 어셈블리는 앱 패키지에 포함됩니다. 또한 동일한 어셈블리의 두 버전이 동일한 앱에서 참조되는 경우 앱이 최신 어셈블리로 리디렉션됩니다. 자세한 내용은 [앱 수준에서 어셈블리 버전 리디렉션](../../../docs/framework/configure-apps/redirect-assembly-versions.md#BKMK_Redirectingassemblyversionsattheapplevel) 및 [방법: 자동 바인딩 리디렉션 사용 설정 및 해제](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)를 참조하세요.<br /><br /> .NET 배포에 대한 자세한 내용은 [개발자를 위한 배포 가이드](../../../docs/framework/deployment/deployment-guide-for-developers.md)를 참조하세요.|  
|Windows 및 Windows Phone 스토어를 통해 제공되는 Windows 및 Windows Phone 앱|배포는 현재와 동일하며, 앱이 운영 체제에 포함된 .NET Framework 어셈블리를 사용합니다. 앱이 .NET Framework에 없는 .NET Core 어셈블리에 릴리스된 기능을 사용하는 경우 해당 어셈블리는 앱 패키지에 포함됩니다. 동일한 어셈블리의 여러 버전이 앱에서 참조되는 경우 앱이 자동으로 최신 버전의 어셈블리를 사용합니다.|  
|ASP.NET Core 5.0 앱|.NET Core 어셈블리는 app\-local이므로 필수 어셈블리가 앱 패키지와 함께 배포됩니다. ASP.NET Core 5.0에 대한 자세한 내용은 [ASP.NET 5 개요](http://www.asp.net/vnext/overview/aspnet-vnext/aspnet-5-overview)를 참조하세요.|  
|다른 플랫폼에서 실행되는 Xamarin 도구로 빌드된 앱|현재 이러한 앱은 앱 패키지에 들어 있는 간소화된 모노 어셈블리 집합과 함께 배포됩니다. 이는 오픈 소스되는 .NET Core 어셈블리가 많아짐에 따라 변경될 수 있습니다.|  
  
<a name="BKMK_NETCoreOpenSourcePackages"></a>   
## .NET Core 오픈 소스 패키지  
 .NET Framework의 모듈화 외에도 Microsoft는 [MIT](https://github.com/dotnet/corefx/blob/master/LICENSE) 라이선스로, [GitHub](https://github.com/)에서 .NET Core 패키지를 오픈 소싱합니다. 즉, GitHub에 있는 다른 오픈 소스 패키지와 마찬가지로 Git 리포지토리를 복제하고, 코드를 읽고 컴파일한 다음 끌어오기 요청을 제출할 수 있습니다. 품질과 호환성을 위해 각 끌어오기 요청은 신중하게 평가된 후 수락됩니다. 다음은 몇 가지 질문과 대답입니다.  
  
### 코드를 가져와서 빌드하려면 어떻게 해야 하나요?  
 .NET Core 소스 패키지는 `Git`를 소스 제어 시스템으로 사용하는 `GitHub`에 저장되어 있습니다. 코드에 액세스하고 빌드하려면 [Git](http://git-scm.com/), [GitHub](https://github.com/dotnet/corefx) 및 [Visual Studio](http://msdn.microsoft.com/vstudio/aa718325.aspx)에 대한 기본 지식이 있어야 하지만 다음 단계에서 제공하는 일부 정보 및 링크를 통해 시작할 수 있습니다.  
  
 Git 및 GitHub를 설정하려면 GitHub 사이트에서 [Git 설정](https://help.github.com/articles/set-up-git/)을 참조하세요.  
  
 .NET Framework 코드에 액세스하려면 해당 코드가 포함된 Git 리포지토리를 분기하고 개발 컴퓨터에 복제해야 합니다. 리포지토리로 이동한 다음 브라우저의 오른쪽 위에서 **분기**를 클릭하면 코드를 분기할 수 있습니다. GitHub 앱을 사용하거나 GitHub 셸의 명령줄에서 분기를 복제할 수 있습니다. GitHub 셸에서 리포지토리를 복제하려면 다음 명령을 실행합니다.  
  
```  
git clone https://github.com/dotnet/corefx  
```  
  
 코드를 빌드하려면 Visual Studio 2013이 설치되어 있어야 합니다. Visual Studio 2013에서 F5 키를 눌러 솔루션을 열고 빌드하거나 개발자 명령 프롬프트를 사용하여 명령줄에서 빌드할 수 있습니다. 명령 프롬프트로 빌드하려면 개발자 명령 프롬프트를 열고 소스 코드를 복제한 폴더로 이동합니다. 그런 후에 다음을 입력합니다.  
  
```  
build.cmd  
  
```  
  
 개발자 명령 프롬프트에 액세스하는 방법에 대한 자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.  
  
### 코드 제출 지침은 무엇인가요?  
 먼저 [CLA\(Contributor License Agreement\)](https://cla.dotnetfoundation.org/)에 서명해야 작업 내용을 마스터 분기에 통합할 수 있습니다.  
  
 분기 및 끌어오기 모델을 사용하여 커뮤니티에서 기여한 내용을 수락합니다. 코드를 분기 및 복제하고 끌어오기 요청을 .NET Framework 마스터 분기로 제출해야 합니다. 끌어오기 요청에 대한 자세한 내용은 [끌어오기 요청 사용](https://help.github.com/articles/using-pull-requests/)을 참조하세요. 끌어오기 요청 제출에 대한 자세한 지침은 [.NET Core 기여 가이드](https://github.com/dotnet/corefx/wiki/Contributing)를 참조하세요.  
  
### 내 끌어오기 요청을 수락하지 않은 이유는 무엇인가요?  
 요청을 거부하는 경우 거부 이유를 제공하지만, 일반적으로 Microsoft는 코드 품질과 호환성을 유지 관리합니다. 끌어오기 요청이 수락되지 않은 경우 코딩 지침을 준수하지 않았거나, 코드 제출을 위한 적절한 테스트를 수행하지 않았거나, API 호환성을 위반한 것입니다. 또한 코드 변경 내용이 .NET Framework를 위한 로드맵과 일치해야 합니다. 코딩 지침 및 자세한 내용은 [.NET Core 기여 가이드](https://github.com/dotnet/corefx/wiki/Contributing)를 참조하세요.  
  
## 참고 항목  
 [오픈 소스인 .NET](http://blogs.msdn.com/b/dotnet/archive/2014/11/12/net-core-is-open-source.aspx)   
 [.NET 오픈 소스 Curah](https://curah.microsoft.com/254870/net-core-open-source)   
 [ASP.NET 5 개요](http://www.asp.net/vnext/overview/aspnet-vnext/aspnet-5-overview)