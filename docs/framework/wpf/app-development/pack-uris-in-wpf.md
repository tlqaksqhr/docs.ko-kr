---
title: "WPF의 Pack URI | Microsoft Docs"
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
  - "응용 프로그램 관리[WPF]"
  - "포함 리소스 로드"
  - "리소스가 아닌 파일 로드"
  - "pack URI 체계"
  - "Uniform Resource Identifier(URI)"
  - "URI(Uniform Resource Identifier)"
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
caps.latest.revision: 35
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# WPF의 Pack URI
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]에서 [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)]는 다음과 같은 다양한 방식으로 파일을 식별하고 로드하는 데 사용됩니다.  
  
-   응용 프로그램을 처음으로 시작할 때 표시되는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 지정  
  
-   이미지 로드  
  
-   페이지 탐색  
  
-   비실행 데이터 파일 로드  
  
 또한 다음을 비롯한 다양한 위치에서 파일을 식별하고 로드하는 데 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]를 사용할 수도 있습니다.  
  
-   현재 어셈블리  
  
-   참조된 어셈블리  
  
-   어셈블리에 상대적인 위치  
  
-   응용 프로그램의 원본 사이트  
  
 이러한 위치에서 이러한 형식의 파일을 식별하고 로드하는 일관성 있는 메커니즘을 제공하기 위해 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 *Pack URI 체계*의 확장성을 이용합니다.  이 항목에서는 태그와 코드에서 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]를 사용하는 방법을 보여 주기 전에 이 체계를 개략적으로 소개하고 다양한 시나리오에서 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]를 구성하는 방법을 설명하며 절대 및 상대 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]와 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 확인에 대해 설명합니다.  
  
   
  
<a name="The_Pack_URI_Scheme"></a>   
## Pack URI 체계  
 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 체계는 콘텐츠를 구성하고 식별하는 모델을 설명하는 OPC\([Open Packaging Conventions](http://go.microsoft.com/fwlink/?LinkID=71255)\) 사양에서 사용됩니다.  이 모델의 핵심 요소는 패키지와 파트입니다. 여기서 *패키지*는 하나 이상의 논리적 *파트*에 대한 논리적 컨테이너입니다.  다음 그림에서는 이 개념을 보여 줍니다.  
  
 ![패키지 및 파트 다이어그램](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure1.png "WPFPackURISchemeFigure1")  
  
 파트를 식별하기 위해 OPC 사양에서는 RFC 2396\(Uniform Resource Identifiers \(URI\): Generic Syntax\)의 확장성을 이용하여 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 체계를 정의합니다.  
  
 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]로 지정되는 이 체계는 접두사로 정의됩니다. http, ftp 및 file은 잘 알려진 접두사의 예입니다.  Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 체계는 "팩"을 해당 구조로 사용하며 인증 기관\(authority\)과 경로\(path\)의 두 가지 구성 요소를 포함합니다.  다음은 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]의 형식입니다.  
  
 pack:\/\/*authority*\/*path*  
  
 *authority*는 파트가 포함된 패키지의 형식을 지정하고 *path*는 패키지 내에서 파트의 위치를 지정합니다.  
  
 다음 그림에서는 이 개념을 보여 줍니다.  
  
 ![패키지, 권한 및 경로의 관계](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure2.png "WPFPackURISchemeFigure2")  
  
 패키지와 파트는 응용 프로그램 및 파일과 유사합니다. 즉, 응용 프로그램\(패키지\)은 다음을 비롯한 하나 이상의 파일\(파트\)을 포함할 수 있습니다.  
  
-   로컬 어셈블리로 컴파일되는 리소스 파일  
  
-   참조된 어셈블리로 컴파일되는 리소스 파일  
  
-   참조하는 어셈블리로 컴파일되는 리소스 파일  
  
-   콘텐츠 파일  
  
-   원본 사이트 파일  
  
 이러한 형식의 파일에 액세스할 수 있도록 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 두 가지 인증 기관인 application:\/\/\/ 및 siteoforigin:\/\/\/을 지원합니다.  application:\/\/\/ 인증 기관은 리소스 및 콘텐츠 파일을 비롯하여 컴파일 시 알려진 응용 프로그램 데이터 파일을 식별합니다.  siteoforigin:\/\/\/ 인증 기관은 원본 사이트 파일을 식별합니다.  다음 그림에서는 각 인증 기관의 범위를 보여 줍니다.  
  
 ![Pack URI 다이어그램](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure4.png "WPFPackURISchemeFigure4")  
  
> [!NOTE]
>  Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]의 인증 기관 구성 요소는 패키지를 가리키는 포함된 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]이며 RFC 2396을 따라야 합니다.  또한 "\/" 문자를 "," 문자로 바꾸고 "%" 및 "?" 같은 예약 문자는 이스케이프해야 합니다.  자세한 내용은 OPC를 참조하십시오.  
  
 다음 단원에서는 이 두 인증 기관과 리소스, 콘텐츠 및 원본 사이트 파일을 식별하는 적절한 경로를 조합하여 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]를 구성하는 방법에 대해 설명합니다.  
  
<a name="Resource_File_Pack_URIs___Local_Assembly"></a>   
## 리소스 파일 Pack URI  
 리소스 파일은 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Resource` 항목으로 구성되며 어셈블리로 컴파일됩니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 로컬 어셈블리로 컴파일되거나 로컬 어셈블리에서 참조되는 어셈블리로 컴파일되는 리소스 파일을 식별하는 데 사용할 수 있는 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]의 생성을 지원합니다.  
  
<a name="Local_Assembly_Resource_File"></a>   
### 로컬 어셈블리 리소스 파일  
 로컬 어셈블리로 컴파일되는 리소스 파일에 대한 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]는 다음 인증 기관과 경로를 사용합니다.  
  
-   **인증 기관**: application:\/\/\/  
  
-   **경로**: 로컬 어셈블리 프로젝트 폴더 루트에 상대적인 경로를 포함한 리소스 파일의 이름  
  
 다음 예제에서는 로컬 어셈블리의 프로젝트 폴더 루트에 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 리소스 파일에 대한 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 보여 줍니다.  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 다음 예제에서는 로컬 어셈블리의 프로젝트 폴더 하위 폴더에 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 리소스 파일에 대한 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 보여 줍니다.  
  
 `pack://application:,,,/Subfolder/ResourceFile.xaml`  
  
<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>   
### 참조된 어셈블리 리소스 파일  
 참조된 어셈블리로 컴파일되는 리소스 파일에 대한 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]는 다음 인증 기관과 경로를 사용합니다.  
  
-   **인증 기관**: application:\/\/\/  
  
-   **경로**: 참조된 어셈블리로 컴파일되는 리소스 파일의 이름.  경로는 다음 형식을 따라야 합니다.  
  
     *AssemblyShortName*\[*;Version*\]\[*;PublicKey*\];component\/*Path*  
  
    -   **AssemblyShortName**: 참조된 어셈블리에 대한 약식 이름  
  
    -   **;Version** \[선택적 요소\]: 리소스 파일을 포함하는 참조된 어셈블리의 버전.  동일한 약식 이름을 갖는 두 개 이상의 참조된 어셈블리가 로드된 경우 사용됩니다.  
  
    -   **;PublicKey** \[선택적 요소\]: 참조된 어셈블리를 서명하는 데 사용된 공개 키.  동일한 약식 이름을 갖는 두 개 이상의 참조된 어셈블리가 로드된 경우 사용됩니다.  
  
    -   **;component**: 참조되는 어셈블리가 로컬 어셈블리에서 참조된다는 것을 지정합니다.  
  
    -   **\/Path**: 참조된 어셈블리 프로젝트 폴더의 루트에 상대적인 경로를 포함한 리소스 파일의 이름  
  
 다음 예제에서는 참조된 어셈블리의 프로젝트 폴더 루트에 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 리소스 파일에 대한 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 보여 줍니다.  
  
 `pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`  
  
 다음 예제에서는 참조된 어셈블리의 프로젝트 폴더 하위 폴더에 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 리소스 파일에 대한 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 보여 줍니다.  
  
 `pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`  
  
 다음 예제에서는 참조된 버전별 어셈블리의 프로젝트 폴더 루트 폴더에 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 리소스 파일에 대한 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 보여 줍니다.  
  
 `pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`  
  
 참조된 어셈블리 리소스 파일에 대한 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 구문은 application:\/\/\/ 인증 기관에만 사용할 수 있습니다.  예를 들어 다음은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 지원되지 않습니다.  
  
 `pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`  
  
<a name="Content_File_Pack_URIs"></a>   
## 콘텐츠 파일 Pack URI  
 콘텐츠 파일에 대한 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]는 다음 인증 기관과 경로를 사용합니다.  
  
-   **인증 기관**: application:\/\/\/  
  
-   **경로**: 응용 프로그램의 주 실행 가능 어셈블리의 파일 시스템 위치에 상대적인 경로를 포함한 콘텐츠 파일의 이름  
  
 다음 예제에서는 실행 가능 어셈블리와 동일한 폴더에 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 콘텐츠 파일에 대한 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 보여 줍니다.  
  
 `pack://application:,,,/ContentFile.xaml`  
  
 다음 예제에서는 응용 프로그램의 실행 가능 어셈블리에 상대적인 하위 폴더에 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 콘텐츠 파일에 대한 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 보여 줍니다.  
  
 `pack://application:,,,/Subfolder/ContentFile.xaml`  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 콘텐츠 파일은 탐색할 수 없습니다.  [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 체계는 원본 사이트에 위치한 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 파일에 대한 탐색만 지원합니다.  
  
<a name="The_siteoforigin_____Authority"></a>   
## 원본 사이트 Pack URI  
 원본 사이트 파일에 대한 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]는 다음 인증 기관과 경로를 사용합니다.  
  
-   **인증 기관**: siteoforigin:\/\/\/  
  
-   **경로**: 실행 가능 어셈블리가 시작된 위치에 상대적인 경로를 포함한 원본 사이트 파일의 이름  
  
 다음 예제에서는 실행 가능 어셈블리가 시작된 위치에 저장되어 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 원본 사이트 파일에 대한 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 보여 줍니다.  
  
 `pack://siteoforigin:,,,/SiteOfOriginFile.xaml`  
  
 다음 예제에서는 응용 프로그램의 실행 가능 어셈블리가 시작된 위치에 상대적인 하위 폴더에 저장되어 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 원본 사이트 파일에 대한 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 보여 줍니다.  
  
 `pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`  
  
<a name="Page_Files"></a>   
## 페이지 파일  
 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` 항목으로 구성된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 리소스 파일과 동일한 방식으로 어셈블리로 컴파일됩니다.  따라서 리소스 파일에 대한 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]를 사용하여 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` 항목을 식별할 수 있습니다.  
  
 일반적으로 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` 항목으로 구성되는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일 형식에는 해당 루트 요소로 다음 중 하나가 포함됩니다.  
  
-   <xref:System.Windows.Window?displayProperty=fullName>  
  
-   <xref:System.Windows.Controls.Page?displayProperty=fullName>  
  
-   <xref:System.Windows.Navigation.PageFunction%601?displayProperty=fullName>  
  
-   <xref:System.Windows.ResourceDictionary?displayProperty=fullName>  
  
-   <xref:System.Windows.Documents.FlowDocument?displayProperty=fullName>  
  
-   <xref:System.Windows.Controls.UserControl?displayProperty=fullName>  
  
<a name="Absolute_vs_Relative_Pack_URIs"></a>   
## 절대 및상대 Pack URI  
 정규화된 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]는 체계, 인증 기관 및 경로를 포함하며 절대 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]로 간주됩니다.  개발자가 쉽게 사용할 수 있도록 일반적으로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 요소에서는 경로만 포함하는 상대 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 사용하여 해당 특성을 설정할 수 있습니다.  
  
 예를 들어 로컬 어셈블리에 있는 리소스 파일에 대한 다음과 같은 절대 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 살펴 봅니다.  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 이 리소스 파일을 참조하는 상대 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]는 다음과 같습니다.  
  
 `/ResourceFile.xaml`  
  
> [!NOTE]
>  원본 사이트 파일은 어셈블리와 연결되어 있지 않기 때문에 절대 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]로만 참조할 수 있습니다.  
  
 기본적으로 상대 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]는 참조가 들어 있는 태그나 코드의 위치에 상대적인 것으로 간주됩니다.  하지만 앞에 백슬래시가 사용되면 상대 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 참조는 응용 프로그램 루트에 상대적인 것으로 간주됩니다.  예를 들어 다음과 같은 프로젝트 구조를 가정해 봅니다.  
  
 `App.xaml`  
  
 `Page2.xaml`  
  
 `\SubFolder`  
  
 `+ Page1.xaml`  
  
 `+ Page2.xaml`  
  
 Page1.xaml에 *Root*\\SubFolder\\Page2.xaml을 참조하는 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]가 들어 있다면 해당 참조에서 다음과 같은 상대 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 사용할 수 있습니다.  
  
 `Page2.xaml`  
  
 Page1.xaml에 *Root*\\Page2.xaml을 참조하는 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]가 들어 있다면 해당 참조에서 다음과 같은 상대 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 사용할 수 있습니다.  
  
 `/Page2.xaml`  
  
<a name="Pack_URI_Resolution"></a>   
## Pack URI 확인  
 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]의 형식에서는 서로 다른 파일 형식에 대한 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]가 동일하게 나타날 수 있습니다.  예를 들어 다음과 같은 절대 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 가정해 봅니다.  
  
 `pack://application:,,,/ResourceOrContentFile.xaml`  
  
 이 절대 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]는 로컬 어셈블리나 콘텐츠 파일의 리소스 파일을 참조할 수 있습니다.  다음과 같은 상대 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]의 경우에도 마찬가지입니다.  
  
 `/ResourceOrContentFile.xaml`  
  
 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]가 참조하는 파일 형식을 확인하기 위해서 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 다음과 같은 경험적 접근을 통해 로컬 어셈블리와 콘텐츠 파일에서 리소스 파일에 대한 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]를 확인합니다.  
  
1.  Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]와 일치하는 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 특성에 대한 어셈블리 메타데이터를 조사합니다.  
  
2.  <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 특성이 있으면 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]의 경로는 콘텐츠 파일을 참조합니다.  
  
3.  <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 특성이 없으면 로컬 어셈블리로 컴파일되는 리소스 파일 집합을 조사합니다.  
  
4.  Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 경로와 일치하는 리소스 파일이 있으면 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]의 경로는 리소스 파일을 참조합니다.  
  
5.  리소스 파일이 없으면 내부적으로 생성된 <xref:System.Uri>가 무효가 됩니다.  
  
 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 확인은 다음을 참조하는 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]에는 적용되지 않습니다.  
  
-   참조되는 어셈블리의 콘텐츠 파일: [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 이러한 파일 형식을 지원하지 않습니다.  
  
-   참조되는 어셈블리의 포함된 파일: 참조되는 어셈블리의 이름과 `;component` 접미사를 모두 포함하기 때문에 이 파일을 식별하는 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]는 고유합니다.  
  
-   원본 사이트 파일: 이 파일은 siteoforigin:\/\/\/ 인증 기관을 포함하는 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]로 식별할 수 있는 유일한 파일이기 때문에 이 파일을 식별하는 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]는 고유합니다.  
  
 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 확인에서 허용하는 한 가지 단순화는 코드가 리소스 및 콘텐츠 파일 위치와 다소 독립적일 수 있다는 것입니다.  예를 들어 로컬 어셈블리에 콘텐츠 파일로 다시 구성되는 리소스 파일이 있는 경우 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 사용하는 코드와 마찬가지로 해당 리소스에 대한 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]가 동일하게 유지됩니다.  
  
<a name="Programming_with_Pack_URIs"></a>   
## Pack URI를 사용한 프로그래밍  
 많은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 클래스가 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]로 설정할 수 있는 다음과 같은 속성을 구현합니다.  
  
-   <xref:System.Windows.Application.StartupUri%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Window.Icon%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Controls.Image.Source%2A?displayProperty=fullName>  
  
 이러한 속성을 태그와 코드 모두에서 설정할 수 있습니다.  이 단원에서는 두 경우에 대한 기본 구조를 설명한 다음 일반적인 시나리오 예제를 보여 줍니다.  
  
<a name="Using_Pack_URIs_in_Markup"></a>   
### 태그에서 Pack URI 사용  
 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]로 특성의 요소를 설정하여 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 태그에 지정합니다.  예를 들면 다음과 같습니다.  
  
 `<element attribute="pack://application:,,,/File.xaml" />`  
  
 표 1에서는 태그에 지정할 수 있는 다양한 절대 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]를 보여 줍니다.  
  
 표 1: 태그의 절대 Pack URI  
  
|파일|절대 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|--------|--------------------------------------------------------------------------|  
|리소스 파일 \- 로컬 어셈블리|`"pack://application:,,,/ResourceFile.xaml"`|  
|하위 폴더의 리소스 파일 \- 로컬 어셈블리|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|  
|리소스 파일 \- 참조된 어셈블리|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|  
|참조된 어셈블리의 하위 폴더에 있는 리소스 파일|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|버전이 있는 참조된 어셈블리의 리소스 파일|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|  
|콘텐츠 파일|`"pack://application:,,,/ContentFile.xaml"`|  
|하위 폴더의 콘텐츠 파일|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|  
|원본 사이트 파일|`"pack://siteoforigin:,,,/SOOFile.xaml"`|  
|하위 폴더의 원본 사이트 파일|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|  
  
 표 2에서는 태그에 지정할 수 있는 다양한 상대 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]를 보여 줍니다.  
  
 표 2: 태그의 상대 Pack URI  
  
|파일|상대 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|--------|--------------------------------------------------------------------------|  
|로컬 어셈블리의 리소스 파일|`"/ResourceFile.xaml"`|  
|로컬 어셈블리의 하위 폴더에 있는 리소스 파일|`"/Subfolder/ResourceFile.xaml"`|  
|참조된 어셈블리의 리소스 파일|`"/ReferencedAssembly;component/ResourceFile.xaml"`|  
|참조된 어셈블리의 하위 폴더에 있는 리소스 파일|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|콘텐츠 파일|`"/ContentFile.xaml"`|  
|하위 폴더의 콘텐츠 파일|`"/Subfolder/ContentFile.xaml"`|  
  
<a name="Using_Pack_URIs_in_Code"></a>   
### 코드에서 Pack URI 사용  
 <xref:System.Uri> 클래스를 인스턴스화하고 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 생성자에 매개 변수로 전달하여 코드에서 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 지정합니다.  다음 예제를 통해 볼 수 있습니다.  
  
```csharp  
Uri uri = new Uri("pack://application:,,,/File.xaml");  
```  
  
 기본적으로 <xref:System.Uri> 클래스는 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]가 절대라고 가정합니다.  따라서 <xref:System.Uri> 클래스의 인스턴스가 상대 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]로 생성되면 예외가 발생합니다.  
  
```csharp  
Uri uri = new Uri("/File.xaml");  
```  
  
 다행히 <xref:System.Uri> 클래스 생성자의 <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> 오버로드가 <xref:System.UriKind> 형식의 매개 변수를 받아들이므로 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]가 절대인지 상대인지를 지정할 수 있습니다.  
  
```csharp  
// Absolute URI (default)  
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);  
// Relative URI  
Uri relativeUri = new Uri("/File.xaml", UriKind.Relative);  
```  
  
 제공된 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]가 절대인지 상대인지 확실히 아는 경우에는 <xref:System.UriKind> 또는 <xref:System.UriKind>만 지정해야 합니다.  하지만 사용자가 런타임에 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 입력하는 경우와 같이 사용되는 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]의 형식을 모르는 경우에는 <xref:System.UriKind>를 대신 사용합니다.  
  
```csharp  
// Relative or Absolute URI provided by user via a text box  
TextBox userProvidedUriTextBox = new TextBox();  
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);  
```  
  
 표 3에서는 <xref:System.Uri?displayProperty=fullName>를 사용하여 코드에 지정할 수 있는 다양한 상대 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]를 보여 줍니다.  
  
 표 3: 코드의 절대 Pack URI  
  
|파일|절대 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|--------|--------------------------------------------------------------------------|  
|리소스 파일 \- 로컬 어셈블리|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|  
|하위 폴더의 리소스 파일 \- 로컬 어셈블리|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|리소스 파일 \- 참조된 어셈블리|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|  
|참조된 어셈블리의 하위 폴더에 있는 리소스 파일|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|버전이 있는 참조된 어셈블리의 리소스 파일|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|  
|콘텐츠 파일|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|  
|하위 폴더의 콘텐츠 파일|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|  
|원본 사이트 파일|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|  
|하위 폴더의 원본 사이트 파일|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|  
  
 표 4에서는 <xref:System.Uri?displayProperty=fullName>를 사용하여 코드에 지정할 수 있는 다양한 상대 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]를 보여 줍니다.  
  
 표 4: 코드의 상대 Pack URI  
  
|파일|상대 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|--------|--------------------------------------------------------------------------|  
|리소스 파일 \- 로컬 어셈블리|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|  
|하위 폴더의 리소스 파일 \- 로컬 어셈블리|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|리소스 파일 \- 참조된 어셈블리|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|  
|하위 폴더의 리소스 파일 \- 참조된 어셈블리|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|콘텐츠 파일|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|  
|하위 폴더의 콘텐츠 파일|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|  
  
<a name="Common_Pack_URI_Scenarios"></a>   
### 일반적인 Pack URI 시나리오  
 이전 단원에서는 리소스, 콘텐츠 및 원본 사이트 파일을 식별하는 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]를 구성하는 방법에 대해 설명했습니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 이러한 구성은 다양한 방식으로 사용되며 다음 단원에서는 몇 가지 일반적인 사용 방법에 대해 설명합니다.  
  
<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>   
#### 응용 프로그램을 시작할 때 표시되는 UI 지정  
 <xref:System.Windows.Application.StartupUri%2A>는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램이 시작될 때 표시되는 첫 번째 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 지정합니다.  다음 샘플과 같이 독립 실행형 응용 프로그램의 경우 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]는 창이 될 수 있습니다.  
  
 [!code-xml[PackURIOverviewSnippets#StartupUriWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]  
  
 다음 예제와 같이 독립 실행형 응용 프로그램과 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]도 페이지를 초기 UI로 지정할 수 있습니다.  
  
 [!code-xml[PackURIOverviewSnippets#StartupUriPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]  
  
 응용 프로그램이 독립 실행형 응용 프로그램이고 <xref:System.Windows.Application.StartupUri%2A>를 사용하여 페이지를 지정한 경우 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 페이지를 호스팅하는 <xref:System.Windows.Navigation.NavigationWindow>를 엽니다.  [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]의 경우 호스트 브라우저에 페이지가 표시됩니다.  
  
<a name="Navigating_to_a_Page"></a>   
#### 페이지 탐색  
 다음 예제에서는 페이지를 탐색하는 방법을 보여 줍니다.  
  
 [!code-xml[NavigationOverviewSnippets#HyperlinkXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xml[NavigationOverviewSnippets#HyperlinkXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xml[NavigationOverviewSnippets#HyperlinkXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 사용할 수 있는 다양한 탐색 방법에 대한 자세한 내용은 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)를 참조하십시오.  
  
<a name="Specifying_a_Window_Icon"></a>   
#### 창 아이콘 지정  
 다음 예제에서는 URI를 사용하여 창 아이콘을 지정하는 방법을 보여 줍니다.  
  
 [!code-xml[WindowIconSnippets#WindowIconSetXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]  
  
 자세한 내용은 <xref:System.Windows.Window.Icon%2A>을 참조하십시오.  
  
<a name="Loading_Image__Audio__and_Video_Files"></a>   
#### 이미지, 오디오 및 비디오 파일 로드  
 다음 예제와 같이 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 사용하면 응용 프로그램에서 다양한 미디어 형식을 사용할 수 있습니다. 이러한 모든 미디어 형식은 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]로 식별하고 로드할 수 있습니다.  
  
 [!code-xml[MediaPlayerVideoSample#VideoPackURIAtSOO](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]  
  
 [!code-xml[MediaPlayerAudioSample#AudioPackURIAtSOO](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]  
  
 [!code-xml[ImageSample#ImagePackURIContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]  
  
 미디어 콘텐츠 작업에 대한 자세한 내용은 [그래픽 및 멀티미디어](../../../../docs/framework/wpf/graphics-multimedia/index.md)를 참조하십시오.  
  
<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>   
#### 원본 사이트에서 리소스 사전 로드  
 리소스 사전\(<xref:System.Windows.ResourceDictionary>\)을 사용하면 응용 프로그램 테마를 지원할 수 있습니다.  테마를 만들고 관리하는 한 가지 방법은 응용 프로그램의 원본 사이트에 위치한 리소스 사전으로 여러 개의 테마를 만드는 것입니다.  이렇게 하면 응용 프로그램을 다시 컴파일하여 배포할 필요 없이 테마를 추가하고 업데이트할 수 있습니다.  다음 예제에서 볼 수 있는 것처럼 Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]를 사용하여 이러한 리소스 사전을 식별하고 로드할 수 있습니다.  
  
 [!code-xml[ResourceDictionarySnippets#ResourceDictionaryPackURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 테마에 대한 개요를 보려면 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)을 참조하십시오.  
  
## 참고 항목  
 [WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)