---
title: "WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF application [WPF], files
- loose resources [WPF]
- content files [WPF]
- Site of Origin files [WPF]
- resource files [WPF]
- remote files [WPF]
- embedded resources [WPF]
- files [WPF]
- referencing application files [WPF]
- application development [WPF], files
- application management [WPF]
ms.assetid: 7ad2943b-3961-41d3-8fc6-1582d43f5d99
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 19fd82daabd5ed12776b2deee6bc850529a6ef23
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="wpf-application-resource-content-and-data-files"></a>WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]응용 프로그램은 종종 실행 파일이 아닌 데이터와 같은 포함 된 파일 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 이미지, 비디오 및 오디오 합니다. [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]에서는 응용 프로그램 데이터 파일이라고 하는 이러한 유형의 데이터 파일을 구성하고, 식별하고, 사용할 수 있도록 하는 특별한 지원을 제공합니다. 이러한 지원에는 다음을 포함한 특정 응용 프로그램 데이터 파일 형식 집합이 포함됩니다.  
  
-   **리소스 파일**: 실행 파일 또는 라이브러리에 컴파일되는 데이터 파일 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 어셈블리입니다.  
  
-   **콘텐츠 파일**: 명시적으로 연결 된 실행 파일에 있는 독립 실행형 데이터 파일 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 어셈블리입니다.  
  
-   **원본 사이트 파일**: 실행 개체와 연결 되지 않은 독립 실행형 데이터 파일 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 어셈블리입니다.  
  
 이 세 가지 파일 형식을 구분하는 한 가지 중요한 차이점은 리소스 파일과 콘텐츠 파일은 빌드할 때 인식된다는 점입니다. 어셈블리는 명시적으로 이 파일을 인식합니다. 그러나 원본 사이트에 대 한 어셈블리 있을 수 알지 전혀 또는 팩을 통해 암시적으로 인식 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 참조입니다; 두 번째의 경우 원본 파일의 참조 된 사이트 실제로 있는지는 보장 되지 않습니다.  
  
 응용 프로그램 데이터 파일을 참조 하려면 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 에서 팩을 사용 하 여 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 에서 자세히 설명 된 체계 [WPF의 Pack Uri](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)).  
  
 이 항목에서는 응용 프로그램 데이터 파일을 구성하고 사용하는 방법을 설명합니다.  
  
  
<a name="Resource_Files"></a>   
## <a name="resource-files"></a>리소스 파일  
 응용 프로그램에서 응용 프로그램 데이터 파일을 항상 사용할 수 있어야 하는 경우 가용성을 보장하는 유일한 방법은 데이터 파일을 응용 프로그램의 주 실행 어셈블리 또는 참조되는 어셈블리 중 하나로 컴파일하는 것입니다. 이러한 유형의 응용 프로그램 데이터 파일 이라고는 *리소스 파일*합니다.  
  
 다음과 같은 경우에 리소스 파일을 사용해야 합니다.  
  
-   어셈블리로 컴파일한 뒤에는 리소스 파일의 콘텐츠를 업데이트할 필요가 없는 경우.  
  
-   파일 종속성의 수를 줄여 응용 프로그램 배포의 복잡성을 줄이려는 경우.  
  
-   지역화할 수 있어야 응용 프로그램 데이터 파일 (참조 [WPF 전역화 및 지역화 개요](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)).  
  
> [!NOTE]
>  이 섹션에 설명 된 리소스 파일은 다른 리소스 파일에 설명 된 것 보다 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md) 포함 또는 연결 된 리소스에 설명 된 다른 [응용 프로그램 리소스 관리 (.NET) ](http://msdn.microsoft.com/library/f2582734-8ada-4baa-8a7c-e2ef943ddf7e).  
  
### <a name="configuring-resource-files"></a>리소스 파일 구성  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], 리소스 파일에 포함 된 파일은 프로그램 [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] 프로젝트로 `Resource` 항목입니다.  
  
```xml  
<Project "xmlns=http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], 파일을 프로젝트 설정에 추가 하 여 리소스 파일을 만들면 해당 `Build Action` 를 `Resource`합니다.  
  
 프로젝트를 빌드할 때 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] 리소스에서 어셈블리를 컴파일합니다.  
  
### <a name="using-resource-files"></a>리소스 파일 사용  
 리소스 파일을 로드 하려면 호출할 수 있습니다는 <xref:System.Windows.Application.GetResourceStream%2A> 의 메서드는 <xref:System.Windows.Application> 팩을 전달 하는 클래스, [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 원하는 리소스 파일을 나타내는입니다. <xref:System.Windows.Application.GetResourceStream%2A>반환는 <xref:System.Windows.Resources.StreamResourceInfo> 으로 리소스 파일을 노출 하는 개체는 <xref:System.IO.Stream> 고 해당 콘텐츠 형식을 설명 합니다.  
  
 예를 들어, 다음 코드를 사용 하는 방법을 보여 줍니다 <xref:System.Windows.Application.GetResourceStream%2A> 로드 하는 <xref:System.Windows.Controls.Page> 리소스 파일의 내용으로 설정 하 고는 <xref:System.Windows.Controls.Frame> (`pageFrame`):  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 호출 하는 동안 <xref:System.Windows.Application.GetResourceStream%2A> 에 액세스할 수 있습니다는 <xref:System.IO.Stream>, 있습니다 수 수를 설정 하는 속성의 형식에 변환 된 추가 작업을 수행 해야 합니다. 대신, 하도록 할 수 있습니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 열기와 변환을 처리는 <xref:System.IO.Stream> 코드를 사용 하는 형식의 속성에 직접 리소스 파일을 로드 하 여 합니다.  
  
 다음 예제에서는 로드 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.Page> 에 직접는 <xref:System.Windows.Controls.Frame> (`pageFrame`) 코드를 사용 하 여 합니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>리소스 파일로 사용되는 응용 프로그램 코드 파일  
 특별 한 설정의 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 팩을 사용 하 여 응용 프로그램 코드 파일을 참조할 수 있습니다 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], windows, 페이지, 유동 문서 및 리소스 사전을 포함 합니다. 예를 들어, 설정할 수는 <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> 팩 속성 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 창이 나 응용 프로그램이 시작 될 때 로드 하려면 페이지를 참조 하는 합니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 다음과 같은이 경우가 작업을 수행할 수는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에 포함 되어는 [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] 프로젝트로 `Page` 항목입니다.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Page Include="MainWindow.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], 새 추가 <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>, 또는 <xref:System.Windows.ResourceDictionary> 프로젝트에는 `Build Action` 태그에 대 한 파일은 기본적으로 `Page`합니다.  
  
 프로젝트와 `Page` 항목 컴파일되는 경우는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 항목 이진 형식으로 변환 되 고 연결 된 어셈블리로 컴파일됩니다. 결과적으로 이 파일을 일반적인 리소스 파일과 같은 방법으로 사용할 수 있습니다.  
  
> [!NOTE]
>  경우는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로 구성 된 파일을 `Resource` 항목을 선택한 원시 코드 숨김 파일이 없는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 의 원시 이진 버전 보다는 어셈블리에 컴파일됩니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다.  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a>콘텐츠 파일  
 A *콘텐츠 파일* 실행 가능한 어셈블리와 함께 느슨한 파일로 배포 됩니다. 어셈블리로 컴파일되지는 않지만 어셈블리는 각 콘텐츠 파일과 연결되는 메타데이터와 함께 컴파일됩니다.  
  
 데이터 파일을 사용하는 어셈블리를 재컴파일하지 않고 업데이트하고자 하는 응용 프로그램 데이터 파일을 응용 프로그램에서 필요로 할 때는 콘텐츠 파일을 사용해야 합니다.  
  
### <a name="configuring-content-files"></a>콘텐츠 파일 구성  
 콘텐츠 파일을 프로젝트에 추가 하려면 응용 프로그램 데이터 파일으로 포함 되어야 합니다는 `Content` 항목입니다. 또한 콘텐츠 파일을 어셈블리에 직접 컴파일되지 않았으므로로 설정 해야는 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory` 메타 데이터 요소를 지정 된 콘텐츠 파일에 빌드한 어셈블리 상대적인 위치에 복사 됩니다. 프로젝트가 빌드될 때마다 빌드 출력 폴더에 복사 되도록 리소스를 하려면 설정 합니다는 `CopyToOutputDirectory` 인 메타 데이터 요소는 `Always` 값입니다. 그렇지 않으면 확인할 수 있습니다를 사용 하 여 리소스의 최신 버전에만 빌드 출력 폴더에 복사 되는 `PreserveNewest` 값입니다.  
  
 다음 예제에서는 리소스의 새 버전이 프로젝트에 추가된 경우에만 콘텐츠 파일이 빌드 출력 폴더에 복사되는 방식으로 구성된 파일을 보여 줍니다.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Content Include="ContentFile.xaml">  
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
    </Content>  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], 파일을 프로젝트 설정에 추가 하 여 콘텐츠 파일을 만들면 해당 `Build Action` 를 `Content`, 설정 및 해당 `Copy to Output Directory` 를 `Copy always` (동일 `Always`) 및 `Copy if newer` (와 동일 `PreserveNewest`).  
  
 프로젝트를 빌드할 때는 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 특성 각 콘텐츠 파일에 대 한 어셈블리의 메타 데이터에 컴파일됩니다.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 값은 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 프로젝트 위치를 기준으로 콘텐츠 파일의 경로를 의미 합니다. 예를 들어 콘텐츠 파일, 프로젝트 하위 폴더에 있는 경우 추가 경로 정보에 통합 됩니다는 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 값입니다.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 값의 빌드 출력 폴더의 콘텐츠 파일에 대 한 경로의 값 이기도 합니다.  
  
### <a name="using-content-files"></a>콘텐츠 파일 사용  
 콘텐츠 파일을 로드 하려면 호출할 수 있습니다는 <xref:System.Windows.Application.GetContentStream%2A> 의 메서드는 <xref:System.Windows.Application> 팩을 전달 하는 클래스, [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 원하는 콘텐츠 파일을 식별 하는 합니다. <xref:System.Windows.Application.GetContentStream%2A>반환는 <xref:System.Windows.Resources.StreamResourceInfo> 으로 콘텐츠 파일을 노출 하는 개체는 <xref:System.IO.Stream> 고 해당 콘텐츠 형식을 설명 합니다.  
  
 예를 들어, 다음 코드를 사용 하는 방법을 보여 줍니다 <xref:System.Windows.Application.GetContentStream%2A> 로드 하는 <xref:System.Windows.Controls.Page> 콘텐츠 파일의 내용으로 설정 하 고는 <xref:System.Windows.Controls.Frame> (`pageFrame`).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 호출 하는 동안 <xref:System.Windows.Application.GetContentStream%2A> 에 액세스할 수 있습니다는 <xref:System.IO.Stream>, 있습니다 수 수를 설정 하는 속성의 형식에 변환 된 추가 작업을 수행 해야 합니다. 대신, 하도록 할 수 있습니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 열기와 변환을 처리는 <xref:System.IO.Stream> 코드를 사용 하는 형식의 속성에 직접 리소스 파일을 로드 하 여 합니다.  
  
 다음 예제에서는 로드 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.Page> 에 직접는 <xref:System.Windows.Controls.Frame> (`pageFrame`) 코드를 사용 하 여 합니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a>원본 사이트 파일  
 리소스 파일에 정의 된 대로, 함께 배포 되는 어셈블리와 명시적 관계 있어야는 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>합니다. 하지만 다음과 같이 어셈블리와 응용 프로그램 데이터 파일 사이에 암시적 관계 또는 존재하지 않는 관계를 설정해야 할 경우가 종종 있습니다.  
  
-   컴파일할 때 파일이 존재하지 않는 경우.  
  
-   런타임까지 어셈블리에 필요한 파일을 모르는 경우.  
  
-   연결된 어셈블리를 재컴파일하지 않고 파일을 업데이트할 수 있어야 하는 경우.  
  
-   응용 프로그램에서 오디오나 비디오와 같은 대용량 데이터 파일을 사용하며 사용자가 필요할 때에만 이를 다운로드하도록 하려는 경우.  
  
 이러한 종류의 일반적인 사용 하 여 파일을 로드할 수는 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] file:/// 및 http:// 스키마 같은 스키마에 있습니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 하지만 file:/// 및 http:// 스키마를 사용하려면 응용 프로그램이 완전히 신뢰되어야 합니다. 응용 프로그램이 [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] 허용 되는 해당 위치에서 시작 하는 응용 프로그램에 대 한 느슨한 파일 원점 (응용 프로그램의 사이트에서 로드할 수는 사용 권한 집합이 필요로 하는 인터넷 또는 인트라넷에서 시작 된 시작 위치). 이러한 파일을 이라고 *원본 사이트* 파일입니다.  
  
 원본 사이트 파일이 부분 신뢰 응용 프로그램에서만 사용되는 것은 아니지만 부분 신뢰 응용 프로그램에서는 원본 사이트 파일만을 사용할 수 있습니다. 완전 신뢰 응용 프로그램의 경우에서도 빌드할 때 인식하지 못한 응용 프로그램 데이터 파일을 로드해야 할 경우가 있습니다. 완전 신뢰 응용 프로그램은 file:///을 사용할 수 있지만 이 경우 응용 프로그램 데이터 파일이 응용 프로그램 어셈블리와 같은 폴더 또는 하위 폴더에 설치될 수 있습니다. file:///에는 파일의 전체 경로를 사용해야 하기 때문에 file:///을 사용하는 방법보다 원본 사이트 참조를 사용하는 방법이 쉽습니다.  
  
> [!NOTE]
>  와 캐시 되지 않은 파일은 원본 사이트는 [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] 콘텐츠 파일은 클라이언트 컴퓨터에 있습니다. 따라서 구체적으로 요청된 경우에만 다운로드됩니다. 경우는 [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] 응용 프로그램에 대형 미디어 파일을 초기 응용 프로그램을 시작할 훨씬 빠르게 하 고 파일에 필요할 때만 다운로드 됩니다 있음을 의미 하는 원본 사이트 파일 파일로 구성 합니다.  
  
### <a name="configuring-site-of-origin-files"></a>원본 사이트 파일 구성  
 경우 원본 파일의 사이트가 존재 하지 않거나 알 수 없는 컴파일 타임에, 해야 기존 배포를 사용 하도록 런타임에 사용 하는 등 필요한 파일에 대 한 메커니즘을 사용할 수는 `XCopy` 명령줄 프로그램 또는 [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].  
  
 알 수 경우 컴파일 타임에 파일을 원본 사이트에서 찾아야 할 있지만 명시적 종속성을 방지 하려면, 이러한 파일을 추가할 수 있습니다는 [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] 프로젝트로 `None` 항목입니다. 콘텐츠 파일을 설정 하는 데 필요한 만큼의 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory` 특성 원본 파일의 사이트 중 하나를 지정 하 여 빌드된 어셈블리를 기준으로 하는 위치에 복사 되를 지정 하는 `Always` 값 또는 `PreserveNewest` 값입니다.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <None Include="PageSiteOfOriginFile.xaml">  
    <CopyToOutputDirectory>Always</CopyToOutputDirectory>  
  </None>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], 파일을 프로젝트 설정에 추가 하 여 원본 파일의 사이트를 만들면 해당 `Build Action` 를 `None`합니다.  
  
 프로젝트를 빌드할 때 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] 빌드 출력 폴더에 지정 된 파일을 복사 합니다.  
  
### <a name="using-site-of-origin-files"></a>원본 사이트 파일 사용  
 사이트 원본 파일을 로드 하려면 호출할 수 있습니다는 <xref:System.Windows.Application.GetRemoteStream%2A> 의 메서드는 <xref:System.Windows.Application> 팩을 전달 하는 클래스, [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 원본 파일의 원하는 사이트를 식별 하는 합니다. <xref:System.Windows.Application.GetRemoteStream%2A>반환는 <xref:System.Windows.Resources.StreamResourceInfo> 사이트의 원본 파일을 노출 하는 개체는 <xref:System.IO.Stream> 고 해당 콘텐츠 형식을 설명 합니다.  
  
 예를 들어, 다음 코드를 사용 하는 방법을 보여 줍니다 <xref:System.Windows.Application.GetRemoteStream%2A> 로드 하는 <xref:System.Windows.Controls.Page> 원본 사이트의 내용으로 설정 하 고 파일는 <xref:System.Windows.Controls.Frame> (`pageFrame`).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 호출 하는 동안 <xref:System.Windows.Application.GetRemoteStream%2A> 에 액세스할 수 있습니다는 <xref:System.IO.Stream>, 있습니다 수 수를 설정 하는 속성의 형식에 변환 된 추가 작업을 수행 해야 합니다. 대신, 하도록 할 수 있습니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 열기와 변환을 처리는 <xref:System.IO.Stream> 코드를 사용 하는 형식의 속성에 직접 리소스 파일을 로드 하 여 합니다.  
  
 다음 예제에서는 로드 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.Page> 에 직접는 <xref:System.Windows.Controls.Frame> (`pageFrame`) 코드를 사용 하 여 합니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a>빌드 형식 변경 후 다시 빌드  
 응용 프로그램 데이터 파일의 빌드 형식을 변경한 뒤에는 변경 내용이 적용되도록 전체 응용 프로그램을 다시 빌드해야 합니다. 응용 프로그램만 빌드하면 변경 내용이 적용되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [WPF의 Pack URI](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)
