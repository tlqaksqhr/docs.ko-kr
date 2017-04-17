---
title: ".NET Framework로 여러 플랫폼 개발 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: b153baaa-130c-4169-860b-e580591de91e
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# .NET Framework로 여러 플랫폼 개발
.NET Framework 및 Visual Studio를 사용하여 Microsoft 플랫폼과 Microsoft 이외의 플랫폼 둘 모두에서 사용할 수 있는 앱을 개발할 수 있습니다.  
  
## 플랫폼 간 개발 옵션  
 여러 플랫폼용으로 개발하기 위해 소스 코드 또는 바이너리를 공유하고 .NET Framework 코드와 Windows 런타임 API 간에 호출할 수 있습니다.  
  
|다음을 원하는 경우...|다음을 사용...|  
|-------------------|---------------|  
|Windows Phone 8.1과 Windows 8.1 앱 간에 소스 코드 공유|**공유된 프로젝트**\(Visual Studio 2013 업데이트 2의 유니버설 응용 프로그램 템플릿\).<br /><br /> -   현재 Visual Basic은 지원되지 않습니다.<br />-   \#`if` 문을 사용하여 플랫폼별 코드를 구분할 수 있습니다.<br /><br /> 자세한 내용은 다음 문서를 참조하세요.<br /><br /> -   [Visual Studio를 사용하여 Windows 및 Windows Phone을 대상으로 하는 앱 빌드](http://msdn.microsoft.com/library/windows/apps/dn609832.aspx)\(MSDN 문서\)<br />-   [Visual Studio를 사용한 유니버설 XAML 앱 빌드](http://blogs.msdn.com/b/visualstudio/archive/2014/04/14/using-visual-studio-to-build-universal-xaml-apps.aspx)\(블로그 게시물\)<br />-   [Visual Studio를 사용한 XAML 컨버지드 앱 빌드](http://channel9.msdn.com/Events/Build/2014/3-591)\(비디오\)|  
|여러 플랫폼을 대상으로 하는 앱 간에 바이너리 공유|플랫폼 제약이 없는 코드를 위한 **이식 가능한 클래스 라이브러리 프로젝트**.<br /><br /> -   이 접근 방식은 일반적으로 비즈니스 논리를 구현하는 코드에 사용됩니다.<br />-   Visual Basic 또는 C\#을 사용할 수 있습니다.<br />-   API 지원은 플랫폼별로 다릅니다.<br />-   Windows 8.1 및 Windows Phone 8.1을 대상으로 하는 이식 가능한 클래스 라이브러리 프로젝트는 Windows 런타임 API 및 XAML을 지원합니다.  이러한 기능은 이식 가능한 클래스 라이브러리의 이전 버전에서는 사용할 수 없습니다.<br />-   필요한 경우 인터페이스 또는 추상 클래스를 사용하여 플랫폼별 코드를 추출할 수 있습니다.<br /><br /> 자세한 내용은 다음 문서를 참조하세요.<br /><br /> -   [이식 가능한 클래스 라이브러리](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)\(MSDN 문서\)<br />-   [이식 가능한 클래스 라이브러리의 알맞은 사용 방법](http://blogs.msdn.com/b/dsplaisted/archive/2012/08/27/how-to-make-portable-class-libraries-work-for-you.aspx)\(블로그 게시물\)<br />-   [MVVM과 함께 이식 가능한 클래스 라이브러리 사용](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md)\(MSDN 문서\)<br />-   [여러 플랫폼을 대상으로 하는 라이브러리의 앱 리소스](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md)\(MSDN 문서\)<br />-   [.NET 이식성 분석기](http://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)\(Visual Studio 확장\)|  
|Windows 8.1 및 Windows Phone 8.1 이외 플랫폼용 앱 간에 소스 코드 공유|**링크로 추가** 기능<br /><br /> -   이 접근 방식은 몇 가지 이유로 두 앱에 공통으로 적용되지만 이식은 가능하지 않은 앱 논리에 적합합니다.  이 기능은 C\# 또는 Visual Basic 코드에 사용할 수 있습니다.<br />     예를 들어, Windows Phone 8 및 Windows 8은 Windows 런타임 API를 공유하지만 이식 가능한 클래스 라이브러리는 이러한 플랫폼에 Windows 런타임을 지원하지 않습니다.  `Add as link`를 사용하여 Windows Phone 8 앱과 Windows 8이 대상인 Windows 스토어 앱 간에 공통 Windows 런타임 코드를 공유할 수 있습니다.<br /><br /> 자세한 내용은 다음 문서를 참조하세요.<br /><br /> -   [링크로 추가를 사용하여 코드 공유](http://msdn.microsoft.com/library/windowsphone/develop/jj714082\(v=vs.105\).aspx)\(MSDN 문서\)<br />-   [방법: 프로젝트에 기존 항목 추가](http://msdn.microsoft.com/library/vstudio/9f4t9t92\(v=vs.100\).aspx)\(MSDN 문서\)|  
|.NET Framework를 사용하여 Windows 스토어 앱 쓰기 또는 .NET Framework 코드에서 Windows 런타임 API 호출|NET Framework C\# 또는 Visual Basic 코드의 **Windows 런타임 API**. .NET Framework를 사용하여 Windows 스토어 앱을 만듭니다.  두 플랫폼 간의 API 차이점을 알고 있어야 합니다.  그러나 이러한 차이점을 처리하는 데 도움이 되는 클래스가 있습니다.<br /><br /> 자세한 내용은 다음 문서를 참조하세요.<br /><br /> -   [Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)\(MSDN 문서\)<br />-   [Windows 런타임에 URI 전달](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md)\(MSDN 문서\)<br />-   <xref:System.IO.WindowsRuntimeStreamExtensions>\(MSDN API 참조 페이지\)<br />-   <xref:System.WindowsRuntimeSystemExtensions>\(MSDN API 참조 페이지\)|  
|Microsoft 이외의 플랫폼용 .NET Framework 앱 빌드|.NET Framework의 **이식 가능한 클래스 라이브러리 참조 어셈블리** 및 Visual Studio 확장 또는 Xamarin과 같은 타사 도구<br /><br /> 자세한 내용은 다음 문서를 참조하세요.<br /><br /> -   [이제 모든 플랫폼에서 사용할 수 있는 이식 가능한 클래스 라이브러리](http://blogs.msdn.com/b/dotnet/archive/2013/10/14/portable-class-library-pcl-now-available-on-all-platforms.aspx)\(블로그 게시물\)<br />-   [Xamarin](http://xamarin.com/visual-studio)\(Xamarin 웹 사이트\)|  
|플랫폼 간 개발에 JavaScript 및 HTML 사용|Windows 8.1 및 Windows Phone 8.1용 Windows 런타임 API에 대해 개발하기 위한 Visual Studio 2013 업데이트 2의 **유니버설 응용 프로그램 템플릿**.  현재 플랫폼 간 앱을 개발하기 위해 .NET Framework API를 JavaScript 및 HTML과 함께 사용할 수 없습니다.<br /><br /> 자세한 내용은 다음 문서를 참조하세요.<br /><br /> -   [JavaScript 프로젝트 템플릿](http://msdn.microsoft.com/library/windows/apps/hh758331.aspx)<br />-   [JavaScript를 사용하여 Windows Phone에 Windows 런타임 앱 포팅](http://msdn.microsoft.com/library/windows/apps/dn636144.aspx)|