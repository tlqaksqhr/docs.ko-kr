---
title: .NET Framework로 여러 플랫폼 개발
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b153baaa-130c-4169-860b-e580591de91e
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 92ed36d632aefbb566bedd87ddf6a2100807aac6
ms.sourcegitcommit: 68b60d38043e50104ccc90c76f8599b1ffe18346
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="developing-for-multiple-platforms-with-the-net-framework"></a>.NET Framework로 여러 플랫폼 개발
.NET Framework 및 Visual Studio를 사용하여 Microsoft 플랫폼과 Microsoft 이외의 플랫폼 둘 모두에서 사용할 수 있는 앱을 개발할 수 있습니다.  
  
## <a name="options-for-cross-platform-development"></a>플랫폼 간 개발 옵션  
 여러 플랫폼용으로 개발하기 위해 소스 코드 또는 바이너리를 공유하고 .NET Framework 코드와 Windows 런타임 API 간에 호출할 수 있습니다.  
  
|다음을 원하는 경우...|다음을 사용...|  
|-----------------------|------------|  
|Windows Phone 8.1과 Windows 8.1 앱 간에 소스 코드 공유|**공유 프로젝트** (Visual Studio 2013 업데이트 2의에서 유니버설 응용 프로그램 템플릿).<br /><br /> -현재 없는 Visual Basic은 지원 합니다.<br />-#을 사용 하 여 플랫폼별 코드를 구분할 수 있습니다`if` 문.<br /><br /> 자세한 내용은 다음 문서를 참조하세요.<br /><br /> -   [Visual Studio를 사용 하 여 Windows 및 Windows Phone 대상으로 하는 앱을 빌드할](https://msdn.microsoft.com/library/windows/apps/dn609832.aspx) (MSDN 문서)<br />-   [Visual Studio를 사용 하 여 유니버설 XAML 앱을 빌드 하려는](https://blogs.msdn.microsoft.com/visualstudio/2014/04/14/using-visual-studio-to-build-universal-xaml-apps/) (블로그 게시물)<br />-   [Visual Studio XAML 수렴 형 앱 빌드를 사용 하 여](https://channel9.msdn.com/Events/Build/2014/3-591) (비디오)|  
|여러 플랫폼을 대상으로 하는 앱 간에 바이너리 공유|**이식 가능한 클래스 라이브러리 프로젝트** 플랫폼 제약이 없는 코드에 대 한 합니다.<br /><br /> -이 방법은 비즈니스 논리를 구현 하는 코드에 대 한 일반적으로 사용 됩니다.<br />-Visual Basic 또는 C#을 사용할 수 있습니다.<br />-API 지원은 플랫폼별으로 다릅니다.<br />-Windows 8.1 및 Windows Phone 8.1을 대상으로 하는 이식 가능한 클래스 라이브러리 프로젝트는 Windows 런타임 Api 및 XAML을 지원 합니다. 이러한 기능은 이식 가능한 클래스 라이브러리의 이전 버전에서는 사용할 수 없습니다.<br />-필요한 경우 인터페이스 또는 추상 클래스를 사용 하 여 플랫폼별 코드를 추출할 수 있습니다.<br /><br /> 자세한 내용은 다음 문서를 참조하세요.<br /><br /> -   [이식 가능한 클래스 라이브러리](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)<br />-   [방법 휴대용 클래스 라이브러리를](https://blogs.msdn.microsoft.com/dsplaisted/2012/08/27/how-to-make-portable-class-libraries-work-for-you/) (블로그 게시물)<br />-   [MVVM과 함께 이식 가능한 클래스 라이브러리 사용](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md) <br />-   [여러 플랫폼을 대상으로 하는 라이브러리에 대 한 응용 프로그램 리소스](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md) <br />-   [.NET 이식성 분석기](http://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b) (Visual Studio 확장명)|  
|Windows 8.1 및 Windows Phone 8.1 이외 플랫폼용 앱 간에 소스 코드 공유|**링크로 추가** 기능입니다.<br /><br /> -이 방법은 몇 가지 이유로 두 앱 모두에 공통 되지만 식은 가능 하지 않은 앱 논리에 적합 합니다. 이 기능은 C# 또는 Visual Basic 코드에 사용할 수 있습니다.<br />     예를 들어, Windows Phone 8 및 Windows 8은 Windows 런타임 API를 공유하지만 이식 가능한 클래스 라이브러리는 이러한 플랫폼에 Windows 런타임을 지원하지 않습니다. `Add as link`를 사용하여 Windows Phone 8 앱과 Windows 8이 대상인 Windows 스토어 앱 간에 공통 Windows 런타임 코드를 공유할 수 있습니다.<br /><br /> 자세한 내용은 다음 문서를 참조하세요.<br /><br /> -   [링크로 추가 코드를 공유할](http://msdn.microsoft.com/library/windowsphone/develop/jj714082\(v=vs.105\).aspx) (MSDN 문서)<br />-   [방법: 프로젝트에 기존 항목 추가](http://msdn.microsoft.com/library/vstudio/9f4t9t92\(v=vs.100\).aspx) (MSDN 문서)|  
|.NET Framework를 사용하여 Windows 스토어 앱 쓰기 또는 .NET Framework 코드에서 Windows 런타임 API 호출|**Windows 런타임 Api** NET Framework C# 또는 Visual Basic 코드를 사용 하 여.NET Framework Windows 스토어 앱을 만들 수 있습니다. 두 플랫폼 간의 API 차이점을 알고 있어야 합니다. 그러나 이러한 차이점을 처리하는 데 도움이 되는 클래스가 있습니다.<br /><br /> 자세한 내용은 다음 문서를 참조하세요.<br /><br /> -   [Windows 스토어 앱 및 Windows 런타임용.NET framework 지원](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) <br />-   [Windows 런타임에 URI 전달](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md) <br />-   <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> [`System.IO.WindowsRuntimeStreamExtensions`](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions(v=vs.110).aspx) (MSDN API 참조 페이지)<br />-   <!--zz <xref:System.WindowsRuntimeSystemExtensions>--> [`System.WindowsRuntimeSystemExtensions`](https://msdn.microsoft.com/library/system.windowsruntimesystemextensions(v=vs.110).aspx) (MSDN API 참조 페이지)|  
|Microsoft 이외의 플랫폼용 .NET Framework 앱 빌드|**이식 가능한 클래스 라이브러리 참조 어셈블리** .NET Framework Xamarin과 같은 Visual Studio 확장 프로그램이 나 타사 도구에서 합니다.<br /><br /> 자세한 내용은 다음 문서를 참조하세요.<br /><br /> -   [이식 가능한 클래스 라이브러리를 모든 플랫폼에서 현재 사용할 수 있는 합니다.](http://blogs.msdn.com/b/dotnet/archive/2013/10/14/portable-class-library-pcl-now-available-on-all-platforms.aspx) (블로그 게시물)<br />-   [Xamarin 설명서](/xamarin)|  
|플랫폼 간 개발에 JavaScript 및 HTML 사용|**유니버설 응용 프로그램 템플릿** Visual Studio 2013에서 Windows 8.1 및 Windows Phone 8.1 용 Windows 런타임 Api에 대해 개발 하는 2를 업데이트 합니다. 현재 플랫폼 간 앱을 개발하기 위해 .NET Framework API를 JavaScript 및 HTML과 함께 사용할 수 없습니다.<br /><br /> 자세한 내용은 다음 문서를 참조하세요.<br /><br /> -   [JavaScript 프로젝트 템플릿](http://msdn.microsoft.com/library/windows/apps/hh758331.aspx)<br />-   [Windows Phone JavaScript를 사용 하 여 Windows 런타임 앱 포팅](http://msdn.microsoft.com/library/windows/apps/dn636144.aspx)|
