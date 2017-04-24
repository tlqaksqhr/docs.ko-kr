---
title: "WPF 응용 프로그램 만들기(WPF) | Microsoft Docs"
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
  - "WPF 응용 프로그램, 빌드"
ms.assetid: a58696fd-bdad-4b55-9759-136dfdf8b91c
caps.latest.revision: 45
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 42
---
# WPF 응용 프로그램 만들기(WPF)
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 응용 프로그램은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 실행 파일\(.exe\)이나 라이브러리\(.dll\)로 만들거나 두 형식의 어셈블리를 결합하여 만들 수 있습니다.  이 항목에서는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램을 빌드하는 방법을 소개하고 빌드 프로세스의 주요 단계에 대해 설명합니다.  
  
   
  
<a name="Building_a_WPF_Application_using_Command_Line"></a>   
## WPF 응용 프로그램 빌드  
 WPF 응용 프로그램은 다음과 같은 방법으로 컴파일할 수 있습니다.  
  
-   명령줄을 사용합니다.  응용 프로그램에는 코드\(XAML 제외\)와 응용 프로그램 정의 파일만 포함되어야 합니다.  자세한 내용은 [csc.exe를 사용한 명령줄 빌드](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) 또는 [명령줄에서 빌드\(Visual Basic\)](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md)를 참조하십시오.  
  
-   Microsoft Build Engine\(MSBuild\)을 사용합니다.  응용 프로그램에는 코드와 XAML 파일뿐 아니라 MSBuild 프로젝트 파일도 포함되어야 합니다.  자세한 내용은 [MSBuild](../Topic/MSBuild1.md)를 참조하십시오.  
  
-   Visual Studio  Visual Studio는 MSBuild로 WPF 응용 프로그램을 컴파일하며 UI를 만들기 위한 시각적 디자이너를 포함하는 통합 개발 환경입니다.  자세한 내용은 [Visual Studio에서 응용 프로그램 개발](http://msdn.microsoft.com/ko-kr/97490c1b-a247-41fb-8f2c-bc4c201eff68) 및 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)를 참조하십시오.  
  
<a name="The_Windows_Presentation_Foundation_Build_Pipeline"></a>   
## WPF 빌드 파이프라인  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 프로젝트를 빌드할 때 언어 관련 및 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 관련 대상의 조합이 호출됩니다.  이러한 대상을 실행하는 프로세스를 빌드 파이프라인이라고 합니다. 다음 그림에서는 주요 단계를 보여 줍니다.  
  
 ![WPF 빌드 프로세스](../../../../docs/framework/wpf/app-development/media/wpfbuildsystem-figure1.png "WPFBuildSystem\_Figure1")  
  
<a name="Pre_Build_Initializations"></a>   
### 빌드 전 초기화  
 빌드하기 전에 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]에서 다음을 포함한 중요한 도구 및 라이브러리의 위치를 확인합니다.  
  
-   [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]  
  
-   [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)] 디렉터리  
  
-   [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 참조 어셈블리의 위치  
  
-   어셈블리 검색 경로의 속성  
  
 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]에서 어셈블리를 검색하는 첫 번째 위치는 참조 어셈블리 디렉터리\(%ProgramFiles%\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\\)입니다.  이 단계 중에 빌드 프로세스는 여러 속성 및 항목 그룹을 초기화하고 필요한 모든 정리 작업을 수행합니다.  
  
<a name="Resolving_references"></a>   
### 참조 확인  
 빌드 프로세스에서 응용 프로그램 프로젝트를 빌드하는 데 필요한 어셈블리를 찾아서 바인딩합니다.  이 논리는 `ResolveAssemblyReference` 작업에 포함되어 있습니다.  프로젝트 파일에서 `Reference`로 선언된 모든 어셈블리는 검색 경로에 대한 정보와 시스템에 이미 설치된 어셈블리에 대한 메타데이터와 함께 작업에 제공됩니다.  작업은 어셈블리를 찾고 설치된 어셈블리의 메타데이터를 사용하여 출력 매니페스트에 표시할 필요가 없는 핵심 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 어셈블리를 필터링합니다.  이를 통해 ClickOnce 매니페스트에 정보가 중복되는 것을 피할 수 있습니다.  예를 들어 PresentationFramework.dll은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 기반으로 하는 응용 프로그램을 나타내는 것으로 간주할 수 있으며 모든 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 어셈블리는 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]이 설치된 모든 시스템에서 동일한 위치에 있기 때문에 매니페스트에 모든 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 참조 어셈블리에 대한 모든 정보를 포함할 필요가 없습니다.  
  
<a name="Markup_Compilation___Pass_1"></a>   
### 태그 컴파일—패스 1  
 이 단계에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 구문 분석하고 컴파일하여 런타임에서 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]을 구문 분석하고 속성 값의 유효성을 검사하는 데 시간이 소비되지 않도록 합니다.  컴파일된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 미리 토큰화되어 런타임에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 로드하는 것보다 훨씬 빠르게 로드됩니다.  
  
 이 단계에서 `Page` 빌드 항목인 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에 대해 다음 작업이 수행됩니다.  
  
1.  태그 컴파일러에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 구문 분석합니다.  
  
2.  해당 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 대해 컴파일된 표현을 만들고 obj\\Release 폴더에 복사합니다.  
  
3.  새 부분 클래스의 CodeDOM 표현을 만들어 obj\\Release 폴더에 복사합니다.  
  
 또한 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에 대한 언어별 코드 파일을 생성합니다. 예를 들어 [!INCLUDE[TLA2#tla_visualb](../../../../includes/tla2sharptla-visualb-md.md)] 프로젝트의 Page1.xaml 페이지에 대해서는 Page1.g.vb를 생성하고 [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] 프로젝트의 Page1.xaml 페이지에 대해서는 Page1.g.cs를 생성합니다.  파일 이름의 ".g"는 해당 파일이 태그 파일의 최상위 요소에 대한 부분 클래스 선언이 있는 생성된 코드임을 나타냅니다\(예: `Page` 또는 `Window`\).  클래스는 [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)]에서 `partial` 한정자\([!INCLUDE[TLA2#tla_visualb](../../../../includes/tla2sharptla-visualb-md.md)]의 경우 `Extends`\)로 선언되어 클래스에 대한 다른 선언이 다른 곳\(일반적으로 코드 숨김 파일 Page1.xaml.cs\)에 있음을 나타냅니다.  
  
 부분 클래스는 적절한 기본 클래스\(예: 페이지에 대한 <xref:System.Windows.Controls.Page>\)에서 확장되며 <xref:System.Windows.Markup.IComponentConnector?displayProperty=fullName> 인터페이스를 구현합니다.  <xref:System.Windows.Markup.IComponentConnector> 인터페이스에는 구성 요소를 초기화하고 해당 콘텐츠에서 요소의 이름과 이벤트를 연결하기 위한 메서드가 있습니다.  결과적으로, 생성된 코드 파일에는 다음과 같은 메서드 구현이 있습니다.  
  
```csharp  
public void InitializeComponent() {  
    if (_contentLoaded) {  
        return;  
    }  
    _contentLoaded = true;  
    System.Uri resourceLocater =   
        new System.Uri(  
            "window1.xaml",   
            System.UriKind.RelativeOrAbsolute);  
    System.Windows.Application.LoadComponent(this, resourceLocater);  
}  
```  
  
```vb  
Public Sub InitializeComponent() _  
  
    If _contentLoaded Then  
        Return  
    End If  
  
    _contentLoaded = True  
    Dim resourceLocater As System.Uri = _  
        New System.Uri("mainwindow.xaml", System.UriKind.Relative)  
  
    System.Windows.Application.LoadComponent(Me, resourceLocater)  
  
End Sub  
```  
  
 기본적으로 태그 컴파일은 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] 엔진과 동일한 <xref:System.AppDomain>에서 실행됩니다.  이를 통해 성능이 크게 향상됩니다.  `AlwaysCompileMarkupFilesInSeparateDomain` 속성을 사용하여 이 동작을 설정\/해제할 수 있습니다.  이렇게 하면 별도의 <xref:System.AppDomain>을 언로드하여 모든 참조 어셈블리를 언로드할 수 있다는 이점이 있습니다.  
  
<a name="Pass_2_of_Markup_Compilation"></a>   
### 태그 컴파일—패스 2  
 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지가 태그 컴파일의 패스 1에서 컴파일되는 것은 아닙니다.  로컬에서 정의된 형식 참조\(동일한 프로젝트의 다른 위치에 있는 코드에서 정의된 형식에 대한 참조\)가 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 이 단계의 컴파일에서 제외됩니다.  이러한 로컬에서 정의된 형식은 소스에만 존재하며 아직 컴파일되지 않았기 때문입니다.  이를 확인하기 위해 파서는 태그 파일에서 `x:Name`과 같은 항목을 찾는 작업을 포함한 경험적 접근을 사용합니다.  이러한 인스턴스가 발견되면 해당 태그 파일의 컴파일은 코드 파일이 컴파일될 때까지 연기됩니다. 그런 다음 두 번째 태그 컴파일 패스가 해당 파일을 처리합니다.  
  
<a name="File_Classification"></a>   
### 파일 분류  
 빌드 프로세스는 출력 파일이 배치될 응용 프로그램 어셈블리를 기반으로 하여 해당 출력 파일을 여러 리소스 그룹에 넣습니다.  일반적인 지역화되지 않은 응용 프로그램에서 `Resource`로 표시된 모든 데이터 파일은 주 어셈블리\(실행 파일 또는 라이브러리\)에 배치됩니다.  프로젝트에 `UICulture`를 설정한 경우 컴파일된 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일과 언어에 한정된 것으로 표시된 리소스는 위성 리소스 어셈블리에 배치됩니다.  또한 모든 언어 중립 리소스는 주 어셈블리에 배치됩니다.  빌드 프로세스의 이 단계에서 이에 대한 결정이 수행됩니다.  
  
 프로젝트 파일에서 `ApplicationDefinition`, `Page` 및 `Resource` 빌드 작업은 파일이 언어에 한정되는지 아니면 언어 중립인지 여부를 지정하는 `Localizable` 메타데이터\(허용되는 값은 `true`와 `false`\)로 확대할 수 있습니다.  
  
<a name="Core_Compilation"></a>   
### 핵심 컴파일  
 핵심 컴파일 단계에는 코드 파일의 컴파일이 포함됩니다.  이 작업은 언어 관련 대상 파일 Microsoft.CSharp.targets 및 Microsoft.VisualBasic.targets의 논리로 조정됩니다.  경험적 접근에 의해 태그 컴파일러의 단일 패스로 충분하다고 결정되면 주 어셈블리가 생성됩니다.  하지만 프로젝트의 하나 이상의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에 로컬로 정의된 형식에 대한 참조가 있는 경우에는 temporary .dll 파일이 생성되므로 최종 응용 프로그램 어셈블리는 태그 컴파일의 두 번째 패스가 완료된 뒤에 생성될 수 있습니다.  
  
<a name="Manifest_generation"></a>   
### 매니페스트 생성  
 빌드 프로세스의 후반부에서 모든 응용 프로그램 어셈블리와 콘텐츠 파일이 준비되면 응용 프로그램에 대한 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 매니페스트가 생성됩니다.  
  
 배포 매니페스트 파일은 배포 모델, 즉 현재 버전, 업데이트 동작, 게시자 ID 및 디지털 서명을 설명합니다.  이 매니페스트는 배포를 처리하는 관리자가 작성합니다.  파일 확장명은 .xbap\([!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]의 경우\)이며 설치된 응용 프로그램의 경우에는 .application입니다.  전자는 `HostInBrowser` 프로젝트 속성으로 지정하며 이에 따라 매니페스트가 응용 프로그램을 브라우저에 호스팅되는 것으로 식별합니다.  
  
 응용 프로그램 매니페스트\(.exe.manifest 파일\)는 응용 프로그램 어셈블리와 종속 라이브러리를 설명하고 응용 프로그램에 필요한 권한을 나열합니다.  이 파일은 응용 프로그램 개발자가 작성합니다.  [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 응용 프로그램을 시작하려면 사용자는 응용 프로그램의 배포 매니페스트 파일을 엽니다.  
  
 이러한 매니페스트 파일은 항상 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]에 대해 생성됩니다.  설치된 응용 프로그램의 경우에는 `GenerateManifests` 속성이 프로젝트 파일에서 `true` 값으로 지정된 경우가 아니면 생성되지 않습니다.  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]에서는 일반적인 인터넷 영역 응용 프로그램에 할당되는 권한을 초과하는 두 개의 추가적인 권한인 <xref:System.Security.Permissions.WebBrowserPermission> 및 <xref:System.Security.Permissions.MediaPermission>을 가집니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 빌드 시스템이 이 권한을 응용 프로그램 매니페스트에서 선언합니다.  
  
<a name="Incremental_Build_Support"></a>   
## 증분 빌드 지원  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 빌드 시스템에서는 증분 빌드를 지원합니다.  태그나 코드의 변경 내용을 상당히 지능적으로 검색하여 변경의 영향을 받은 아티팩트만 컴파일합니다.  증분 빌드 메커니즘에서는 다음 파일을 사용합니다.  
  
-   현재 컴파일러 상태를 유지하기 위한 $\(*AssemblyName*\)\_MarkupCompiler.Cache 파일  
  
-   로컬에서 정의된 형식에 대한 참조로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 캐시하기 위한 $\(*AssemblyName*\)\_MarkupCompiler.lref 파일  
  
 다음은 증분 빌드에 적용되는 규칙 집합입니다.  
  
-   파일은 빌드 시스템이 변경을 검색하는 최소 단위입니다.  따라서 코드 파일의 경우에는 형식이 변경되었는지 또는 코드가 추가되었는지를 빌드 시스템이 파악할 수 없습니다.  이것은 프로젝트 파일의 경우에도 마찬가지입니다.  
  
-   증분 빌드 메커니즘은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지가 클래스를 정의하는지 또는 다른 클래스를 사용하는지 여부를 인식해야 합니다.  
  
-   `Reference` 항목이 변경되면 모든 페이지를 다시 컴파일합니다.  
  
-   코드 파일이 변경되면 로컬에서 정의된 형식 참조가 있는 모든 페이지를 다시 컴파일합니다.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일이 변경된 경우에는 다음이 수행됩니다.  
  
    -   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]이 프로젝트에서 `Page`로 선언된 경우: [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 로컬로 정의된 형식 참조가 없으면 해당 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]과 로컬 참조가 있는 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지를 다시 컴파일합니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 로컬 참조가 있으면 로컬 참조가 있는 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지를 다시 컴파일합니다.  
  
    -   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]이 프로젝트에서 `ApplicationDefinition`으로 선언된 경우: 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지를 다시 컴파일합니다. 그 이유는 각 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 변경되었을 수 있는 <xref:System.Windows.Application> 형식에 대한 참조가 있기 때문입니다.  
  
-   프로젝트 파일이 코드 파일을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일이 아닌 응용 프로그램 정의로 선언하는 경우에는 다음이 수행됩니다.  
  
    -   프로젝트 파일의 `ApplicationClassName` 값이 변경되었는지 확인합니다\(새 응용 프로그램 종류가 있는지 여부 확인\).  변경되었으면 전체 응용 프로그램을 다시 컴파일합니다.  
  
    -   그렇지 않은 경우에는 로컬 참조가 있는 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지를 다시 컴파일합니다.  
  
-   프로젝트 파일이 변경된 경우에는 앞의 모든 규칙을 적용하고 다시 컴파일해야 하는 대상을 확인합니다.  `AssemblyName`, `IntermediateOutputPath`, `RootNamespace` 및 `HostInBrowser` 속성이 변경되면 전체 다시 컴파일이 트리거됩니다.  
  
 다음과 같은 다시 컴파일 시나리오가 가능합니다.  
  
-   전체 응용 프로그램을 다시 컴파일합니다.  
  
-   로컬로 정의된 형식 참조가 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일만 다시 컴파일합니다.  
  
-   아무것도 다시 컴파일하지 않습니다\(프로젝트에서 아무것도 변경되지 않은 경우\).  
  
## 참고 항목  
 [WPF 응용 프로그램 배포](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)   
 [WPF MSBuild 참조](../Topic/WPF%20MSBuild%20Reference.md)   
 [WPF의 Pack URI](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)   
 [WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)