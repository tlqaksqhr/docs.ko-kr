---
title: "WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "응용 프로그램 개발[WPF], 파일"
  - "응용 프로그램 관리[WPF]"
  - "콘텐츠 파일[WPF]"
  - "포함 리소스[WPF]"
  - "파일[WPF]"
  - "느슨한 리소스[WPF]"
  - "응용 프로그램 파일 참조[WPF]"
  - "원격 파일[WPF]"
  - "리소스 파일[WPF]"
  - "원본 사이트 파일[WPF]"
  - "WPF 응용 프로그램, 파일"
ms.assetid: 7ad2943b-3961-41d3-8fc6-1582d43f5d99
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] 응용 프로그램에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 이미지, 비디오 및 오디오와 같은 실행할 수 없는 데이터가 들어 있는 파일을 사용하는 경우가 많습니다.  [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]에서는 응용 프로그램 데이터 파일이라고 하는 이러한 유형의 데이터 파일을 구성하고, 식별하고, 사용할 수 있도록 하는 특별한 지원을 제공합니다.  이러한 지원에는 다음을 포함한 특정 응용 프로그램 데이터 파일 형식 집합이 포함됩니다.  
  
-   **리소스 파일**: 실행 파일 또는 라이브러리 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 어셈블리로 컴파일되는 데이터 파일  
  
-   **콘텐츠 파일**: 실행 가능한 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 어셈블리와 명시적으로 연결된 독립 실행형 데이터 파일  
  
-   **원본 사이트 파일**: 실행 가능한 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 어셈블리와 연결되지 않은 독립 실행형 데이터 파일  
  
 이 세 가지 파일 형식을 구분하는 한 가지 중요한 차이점은 리소스 파일과 콘텐츠 파일은 빌드할 때 인식된다는 점입니다. 어셈블리는 명시적으로 이 파일을 인식합니다.  하지만 원본 사이트 파일의 경우에는 어셈블리가 이를 전혀 인식하지 못하거나 pack [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 참조를 통해 암시적으로 인식합니다. 후자의 경우 참조되는 원본 사이트 파일이 실제로 존재한다는 보장은 없습니다.  
  
 응용 프로그램 데이터 파일을 참조하기 위해 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]는 Pack [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 체계를 사용합니다. 이 체계에 대해서는 [WPF의 Pack URI](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)에서 자세하게 설명합니다.  
  
 이 항목에서는 응용 프로그램 데이터 파일을 구성하고 사용하는 방법을 설명합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Resource_Files"></a>   
## 리소스 파일  
 응용 프로그램에서 응용 프로그램 데이터 파일을 항상 사용할 수 있어야 하는 경우 가용성을 보장하는 유일한 방법은 데이터 파일을 응용 프로그램의 주 실행 어셈블리 또는 참조되는 어셈블리 중 하나로 컴파일하는 것입니다.  이러한 응용 프로그램 데이터 파일을 *리소스 파일*이라고 합니다.  
  
 다음과 같은 경우에 리소스 파일을 사용해야 합니다.  
  
-   어셈블리로 컴파일한 뒤에는 리소스 파일의 콘텐츠를 업데이트할 필요가 없는 경우  
  
-   파일 종속성의 수를 줄여 응용 프로그램 배포의 복잡성을 줄이려는 경우  
  
-   응용 프로그램 데이터 파일을 지역화할 수 있어야 하는 경우\([WPF 전역화 및 지역화 개요](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md) 참조\)  
  
> [!NOTE]
>  이 절에서 설명 하는 리소스 파일 리소스 파일에 설명 되어 있는 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md) 및 설명 포함 또는 연결 된 리소스와 다른 [응용 프로그램 리소스 관리\(.NET\)](../Topic/Managing%20Application%20Resources%20\(.NET\).md).  
  
### 리소스 파일 구성  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 리소스 파일은 [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] 프로젝트에 `Resource` 항목으로 포함되는 파일입니다.  
  
```  
<Project "xmlns=http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]에서는 파일을 프로젝트에 추가하고 `Build Action`을 `Resource`로 설정하여 리소스 파일을 만듭니다.  
  
 프로젝트를 빌드할 때 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]에서 리소스를 어셈블리로 컴파일합니다.  
  
### 리소스 파일 사용  
 리소스 파일을 로드하려면 원하는 리소스 파일을 나타내는 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 전달하여 <xref:System.Windows.Application> 클래스의 <xref:System.Windows.Application.GetResourceStream%2A> 메서드를 호출하면 됩니다.  <xref:System.Windows.Application.GetResourceStream%2A>은 리소스 파일을 <xref:System.IO.Stream>으로 노출하고 해당 콘텐츠 형식을 설명하는 <xref:System.Windows.Resources.StreamResourceInfo> 개체를 반환합니다.  
  
 다음 예제 코드에서는 <xref:System.Windows.Application.GetResourceStream%2A>을 사용하여 <xref:System.Windows.Controls.Page> 리소스 파일을 로드하고 이를 <xref:System.Windows.Controls.Frame>\(`pageFrame`\)의 콘텐츠로 설정하는 방법을 보여 줍니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 <xref:System.Windows.Application.GetResourceStream%2A>을 호출하면 <xref:System.IO.Stream>에 액세스할 수 있지만 이를 설정하는 데 사용할 속성의 형식으로 변환하는 작업을 추가적으로 수행해야 합니다.  대신 코드를 사용해서 리소스 파일을 해당 형식의 속성으로 직접 로드하는 방법으로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 <xref:System.IO.Stream> 열기와 변환을 처리하도록 할 수 있습니다.  
  
 다음 예제에서는 코드를 사용하여 <xref:System.Windows.Controls.Page>를 <xref:System.Windows.Controls.Frame>\(`pageFrame`\)으로 직접 로드하는 방법을 보여 줍니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### 리소스 파일로 사용되는 응용 프로그램 코드 파일  
 창, 페이지, 유동 문서 및 리소스 사전을 비롯한 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]를 사용하여 특별한 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램 코드 파일 집합을 참조할 수 있습니다.  예를 들어 응용 프로그램이 시작될 때 로드할 창이나 페이지를 참조하는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]로 <xref:System.Windows.Application.StartupUri%2A?displayProperty=fullName> 속성을 설정할 수 있습니다.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일이 [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] 프로젝트에 `Page` 항목으로 포함될 때 이렇게 할 수 있습니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Page Include="MainWindow.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]에서는 새 <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument> 또는 <xref:System.Windows.ResourceDictionary>를 프로젝트에 추가하고 태그 파일에 대한 `Build Action`의 기본값으로 `Page`를 사용합니다.  
  
 프로젝트가 `Page` 항목으로 컴파일될 때 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 항목은 이진 형식으로 변환되고 연결된 어셈블리로 컴파일됩니다.  결과적으로 이 파일을 일반적인 리소스 파일과 같은 방법으로 사용할 수 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일이 `Resource` 항목으로 구성되고 코드 숨김 파일이 없는 경우 원시 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]은 원시 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 이진 버전이 아니라 어셈블리로 컴파일됩니다.  
  
<a name="Content_Files"></a>   
## 콘텐츠 파일  
 *콘텐츠 파일*은 실행 가능한 어셈블리와 함께 느슨한 파일로 배포됩니다.  어셈블리로 컴파일되지는 않지만 어셈블리는 각 콘텐츠 파일과 연결되는 메타데이터와 함께 컴파일됩니다.  
  
 데이터 파일을 사용하는 어셈블리를 재컴파일하지 않고 업데이트하고자 하는 응용 프로그램 데이터 파일을 응용 프로그램에서 필요로 할 때는 콘텐츠 파일을 사용해야 합니다.  
  
### 콘텐츠 파일 구성  
 프로젝트에 콘텐츠 파일을 추가하려면 응용 프로그램 데이터 파일이 `Content`로 포함되어야 합니다.  이 경우 콘텐츠 파일이 어셈블리로 직접 컴파일되지 않기 때문에 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]```CopyToOutputDirectory` 메타데이터 요소를 설정하여 콘텐츠 파일이 빌드된 어셈블리에 상대적인 위치로 복사되도록 지정해야 합니다.  프로젝트를 빌드할 때마다 리소스가 빌드 출력 폴더로 복사되게 하려면 `CopyToOutputDirectory` 메타데이터 요소를 `Always` 값으로 설정합니다.  그렇지 않은 경우에는 리소스의 최신 버전만 `PreserveNewest` 값을 사용하여 빌드 출력 폴더로 복사됩니다.  
  
 다음 예제에서는 리소스의 새 버전이 프로젝트에 추가된 경우에만 콘텐츠 파일이 빌드 출력 폴더에 복사되는 방식으로 구성된 파일을 보여 줍니다.  
  
```  
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
>  [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]에서는 파일을 프로젝트에 추가하고 해당 `Build Action`을 `Content`로 설정하고, `Copy to Output Directory`를 `Copy always`\(`Always`와 같음\) 및 `Copy if newer`\(`PreserveNewest`와 같음\)로 설정하여 콘텐츠 파일을 만듭니다.  
  
 프로젝트를 빌드하면 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 특성이 각 콘텐츠 파일에 대한 어셈블리의 메타데이터로 컴파일됩니다.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>의 값은 콘텐츠 파일에 대한 경로를 프로젝트에서의 위치에 상대적인 경로로 포함합니다.  예를 들어 콘텐츠 파일이 프로젝트 하위 폴더에 있는 경우에는 추가적인 경로 정보가 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 값에 통합됩니다.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 값은 빌드 출력 폴더의 콘텐츠 파일 경로에 대한 값이기도 합니다.  
  
### 콘텐츠 파일 사용  
 콘텐츠 파일을 로드하려면 원하는 콘텐츠 파일을 나타내는 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 전달하여 <xref:System.Windows.Application> 클래스의 <xref:System.Windows.Application.GetContentStream%2A> 메서드를 호출하면 됩니다.  <xref:System.Windows.Application.GetContentStream%2A>은 콘텐츠 파일을 <xref:System.IO.Stream>으로 노출하고 해당 콘텐츠 형식을 설명하는 <xref:System.Windows.Resources.StreamResourceInfo> 개체를 반환합니다.  
  
 다음 예제 코드에서는 <xref:System.Windows.Application.GetContentStream%2A>을 사용하여 <xref:System.Windows.Controls.Page> 콘텐츠 파일을 로드하고 이를 <xref:System.Windows.Controls.Frame>\(`pageFrame`\)의 콘텐츠로 설정하는 방법을 보여 줍니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 <xref:System.Windows.Application.GetContentStream%2A>을 호출하면 <xref:System.IO.Stream>에 액세스할 수 있지만 이를 설정하는 데 사용할 속성의 형식으로 변환하는 작업을 추가적으로 수행해야 합니다.  대신 코드를 사용해서 리소스 파일을 해당 형식의 속성으로 직접 로드하는 방법으로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 <xref:System.IO.Stream> 열기와 변환을 처리하도록 할 수 있습니다.  
  
 다음 예제에서는 코드를 사용하여 <xref:System.Windows.Controls.Page>를 <xref:System.Windows.Controls.Frame>\(`pageFrame`\)으로 직접 로드하는 방법을 보여 줍니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## 원본 사이트 파일  
 리소스 파일은 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>에 의해 정의된 것처럼, 함께 배포되는 어셈블리와 명시적인 관계를 가집니다.  하지만 다음과 같이 어셈블리와 응용 프로그램 데이터 파일 사이에 암시적 관계 또는 존재하지 않는 관계를 설정해야 할 경우가 종종 있습니다.  
  
-   컴파일할 때 파일이 존재하지 않는 경우  
  
-   런타임까지 어셈블리에 필요한 파일을 모르는 경우  
  
-   연결된 어셈블리를 재컴파일하지 않고 파일을 업데이트할 수 있어야 하는 경우  
  
-   응용 프로그램에서 오디오나 비디오와 같은 대용량 데이터 파일을 사용하며 사용자가 필요할 때에만 이를 다운로드하도록 하려는 경우  
  
 file:\/\/\/ 및 http:\/\/ 스키마와 같은 기존의 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 스키마를 사용하여 이러한 형식의 파일을 로드할 수 있습니다.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 하지만 file:\/\/\/ 및 http:\/\/ 스키마를 사용하려면 응용 프로그램이 완전히 신뢰되어야 합니다.  응용 프로그램이 인터넷이나 인트라넷에서 시작된 [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]이며 해당 위치에서 시작된 응용 프로그램에 허용되는 권한 집합만 필요로 하는 경우에 느슨한 파일만 응용 프로그램의 원본 사이트\(시작 위치\)에서 로드할 수 있습니다.  이러한 파일을 *원본 사이트* 파일이라고 합니다.  
  
 원본 사이트 파일이 부분 신뢰 응용 프로그램에서만 사용되는 것은 아니지만 부분 신뢰 응용 프로그램에서는 원본 사이트 파일만을 사용할 수 있습니다.  완전 신뢰 응용 프로그램의 경우에서도 빌드할 때 인식하지 못한 응용 프로그램 데이터 파일을 로드해야 할 경우가 있습니다. 완전 신뢰 응용 프로그램은 file:\/\/\/을 사용할 수 있지만 이 경우 응용 프로그램 데이터 파일이 응용 프로그램 어셈블리와 같은 폴더 또는 하위 폴더에 설치될 수 있습니다.  file:\/\/\/에는 파일의 전체 경로를 사용해야 하기 때문에 file:\/\/\/을 사용하는 방법보다 원본 사이트 참조를 사용하는 방법이 쉽습니다.  
  
> [!NOTE]
>  콘텐츠 파일은 클라이언트 시스템에서 [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]로 캐시되지만 원본 사이트 파일은 캐시되지 않습니다.  따라서 구체적으로 요청된 경우에만 다운로드됩니다.  [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] 응용 프로그램에 용량이 큰 미디어 파일이 있는 경우 이를 원본 사이트 파일로 구성하면 응용 프로그램을 처음 시작할 때의 속도가 훨씬 빨라지고 필요로 할 때만 파일이 다운로드됩니다.  
  
### 원본 사이트 파일 구성  
 원본 사이트 파일이 없거나 컴파일할 때 인식되지 않는 경우 `XCopy` 명령줄 프로그램이나 [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)]을 사용하는 등의 기존에 사용되던 배포 메커니즘을 사용하여 필요한 파일을 런타임에 사용할 수 있도록 해야 합니다.  
  
 컴파일할 때 원본 사이트에서 찾아야 할 파일을 알고 있지만 명시적 종속성을 피하려는 경우에는 해당 파일을 [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] 프로젝트에 `None` 항목으로 추가할 수 있습니다.  이 경우에도 콘텐츠 파일과 마찬가지로 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory` 특성을 설정하고 `Always` 값 또는 `PreserveNewest` 값을 지정하여 원본 사이트 파일이 빌드된 어셈블리에 상대적인 위치로 복사되도록 지정해야 합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <None Include="PageSiteOfOriginFile.xaml">  
    <CopyToOutputDirectory>Always</CopyToOutputDirectory>  
  </None>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]에서는 파일을 프로젝트에 추가하고 `Build Action`을 `None`으로 설정하여 원본 사이트 파일을 만듭니다.  
  
 프로젝트를 빌드할 때 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]에서 지정된 파일을 빌드 출력 폴더로 복사합니다.  
  
### 원본 사이트 파일 사용  
 원본 사이트 파일을 로드하려면 원하는 원본 사이트 파일을 나타내는 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 전달하여 <xref:System.Windows.Application> 클래스의 <xref:System.Windows.Application.GetRemoteStream%2A> 메서드를 호출하면 됩니다.  <xref:System.Windows.Application.GetRemoteStream%2A>은 원본 사이트 파일을 <xref:System.IO.Stream>으로 노출하고 해당 콘텐츠 형식을 설명하는 <xref:System.Windows.Resources.StreamResourceInfo> 개체를 반환합니다.  
  
 다음 예제 코드에서는 <xref:System.Windows.Application.GetRemoteStream%2A>을 사용하여 <xref:System.Windows.Controls.Page> 원본 사이트 파일을 로드하고 이를 <xref:System.Windows.Controls.Frame>\(`pageFrame`\)의 콘텐츠로 설정하는 방법을 보여 줍니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 <xref:System.Windows.Application.GetRemoteStream%2A>을 호출하면 <xref:System.IO.Stream>에 액세스할 수 있지만 이를 설정하는 데 사용할 속성의 형식으로 변환하는 작업을 추가적으로 수행해야 합니다.  대신 코드를 사용해서 리소스 파일을 해당 형식의 속성으로 직접 로드하는 방법으로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 <xref:System.IO.Stream> 열기와 변환을 처리하도록 할 수 있습니다.  
  
 다음 예제에서는 코드를 사용하여 <xref:System.Windows.Controls.Page>를 <xref:System.Windows.Controls.Frame>\(`pageFrame`\)으로 직접 로드하는 방법을 보여 줍니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## 빌드 형식 변경 후 다시 빌드  
 응용 프로그램 데이터 파일의 빌드 형식을 변경한 뒤에는 변경 내용이 적용되도록 전체 응용 프로그램을 다시 빌드해야 합니다.  응용 프로그램만 빌드하면 변경 내용이 적용되지 않습니다.  
  
## 참고 항목  
 [WPF의 Pack URI](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)