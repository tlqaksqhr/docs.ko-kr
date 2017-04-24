---
title: "방법: 응용 프로그램 지역화 | Microsoft Docs"
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
  - "응용 프로그램, 지역화"
  - "지역화(localization), 응용 프로그램"
  - "LocBaml 도구"
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
caps.latest.revision: 37
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# 방법: 응용 프로그램 지역화
이 자습서에서는 LocBaml 도구를 사용하여 지역화된 응용 프로그램을 만드는 방법을 설명합니다.  
  
> [!NOTE]
>  LocBaml 도구는 프로덕션용 응용 프로그램이 아닙니다.  지역화 API 중 일부를 사용하며 지역화 도구를 작성하는 방법을 설명하는 샘플로 제공됩니다.  
>   
>    
  
<a name="Introduction"></a>   
## 개요  
 이 설명에서는 응용 프로그램을 지역화하는 단계별 접근 방식을 제공합니다.  먼저 번역할 텍스트를 추출할 수 있도록 응용 프로그램을 준비합니다.  텍스트를 번역한 후에 번역된 텍스트를 원래 응용 프로그램의 새 복사본으로 병합합니다.  
  
<a name="Requirements"></a>   
## 요구 사항  
 이 설명에서는 명령줄에서 실행되는 컴파일러인 [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)]를 사용합니다.  
  
 또한 프로젝트 파일을 사용하도록 지시됩니다.  [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] 및 프로젝트 파일을 사용하는 방법에 대한 자세한 내용은 [빌드 및 배포](../../../../docs/framework/wpf/app-development/building-and-deploying-wpf-applications.md)를 참조하세요.  
  
 이 설명의 모든 예제에서는 문화권으로 en\-US\(영어\-미국\)를 사용합니다.  이렇게 하면 다른 언어를 설치하지 않고 예제의 단계를 수행할 수 있습니다.  
  
<a name="create_sample_app"></a>   
## 샘플 응용 프로그램 만들기  
 이 단계에서는 지역화를 위해 응용 프로그램을 준비합니다.  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 샘플에서는 이 설명의 코드 예제에 사용되는 HelloApp 샘플이 제공됩니다.  이 샘플을 사용하려는 경우 [LocBaml 도구 샘플](http://go.microsoft.com/fwlink/?LinkID=160016)\(영문\)에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일을 다운로드합니다.  
  
1.  지역화를 시작하려는 지점까지 응용 프로그램을 개발합니다.  
  
2.  [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]에서 주 어셈블리와 중립 언어 리소스가 포함될 위성 어셈블리\(확장명이 .resources.dll인 파일\)를 생성하도록 프로젝트 파일에서 개발 언어를 지정합니다.  HelloApp 샘플의 프로젝트 파일은 HelloApp.csproj입니다.  해당 파일에서 다음과 같이 식별된 개발 언어를 찾을 수 있습니다.  
  
     `<UICulture>en-US</UICulture>`  
  
3.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에 Uid를 추가합니다.  Uid는 파일의 변경 내용을 추적하고 번역해야 하는 항목을 식별하는 데 사용됩니다.  파일에 Uid를 추가하려면 프로젝트 파일에서 **updateuid**를 실행합니다.  
  
     **msbuild \/t:updateuid helloapp.csproj**  
  
     누락되었거나 중복된 Uid가 없는지 확인하려면 **checkuid**를 실행합니다.  
  
     **msbuild \/t:checkuid helloapp.csproj**  
  
     **updateuid**를 실행하면 파일에 Uid가 포함되어야 합니다.  예를 들어 HelloApp의 Pane1.xaml 파일에서는 다음을 찾을 수 있습니다.  
  
     `<StackPanel x:Uid="StackPanel_1">`  
  
     `<TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>`  
  
     `<TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>`  
  
     `</StackPanel>`  
  
<a name="create_dll"></a>   
## 중립 언어 리소스 위성 어셈블리 만들기  
 응용 프로그램이 중립 언어 리소스 위성 어셈블리를 생성하도록 구성된 후 응용 프로그램을 빌드합니다.  그러면 지역화를 위해 LocBaml에 필요한 중립 언어 리소스 위성 어셈블리와 주 응용 프로그램 어셈블리가 생성됩니다.  응용 프로그램을 빌드하려면  
  
1.  HelloApp을 컴파일하여 [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)]을 만듭니다.  
  
     **msbuild helloapp.csproj**  
  
2.  새로 만든 주 응용 프로그램 어셈블리인 HelloApp.exe는 다음 폴더에 만들어집니다.  
  
     `C:\HelloApp\Bin\Debug\`  
  
3.  새로 만든 중립 언어 리소스 위성 어셈블리인 HelloApp.resources.dll은 다음 폴더에 만들어집니다.  
  
     `C:\HelloApp\Bin\Debug\en-US\`  
  
<a name="build_locbaml"></a>   
## LocBaml 도구 빌드  
  
1.  LocBaml을 빌드하는 데 필요한 모든 파일은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 샘플에 있습니다.  [LocBaml 도구 샘플](http://go.microsoft.com/fwlink/?LinkID=160016)\(영문\)에서 [!INCLUDE[TLA#tla_lhcshrp](../../../../includes/tlasharptla-lhcshrp-md.md)] 파일을 다운로드합니다.  
  
2.  명령줄에서 프로젝트 파일\(locbaml.csproj\)을 실행하여 도구를 빌드합니다.  
  
     **msbuild locbaml.csproj**  
  
3.  Bin\\Release 디렉터리로 이동하여 새로 만든 실행 파일\(locbaml.exe\)을 찾습니다.  예: C:\\LocBaml\\Bin\\Release\\locbaml.exe.  
  
4.  LocBaml을 실행할 때 지정할 수 있는 옵션은 다음과 같습니다.  
  
    -   **parse** 또는 **\-p:** Baml, 리소스 또는 [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] 파일을 구문 분석하여 .csv 또는 .txt 파일을 생성합니다.  
  
    -   **generate** 또는 **\-g:** 번역된 파일을 사용하여 지역화된 이진 파일을 생성합니다.  
  
    -   **out** 또는 **\-o** \[*filedirectory*\]**:** 출력 파일 이름입니다.  
  
    -   **culture** 또는 **\-cul** \[*culture*\]**:** 출력 어셈블리의 로캘입니다.  
  
    -   **translation** 또는 **\-trans** \[*translation.csv*\]**:** 번역 또는 지역화된 파일입니다.  
  
    -   **asmpath** 또는 **\-asmpath:** \[*filedirectory*\]**:** [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 코드에 사용자 지정 컨트롤이 포함된 경우 사용자 지정 컨트롤 어셈블리에 **asmpath**를 제공해야 합니다.  
  
    -   **nologo:** 로고 또는 저작권 정보를 표시하지 않습니다.  
  
    -   **verbose:** 자세한 정보 표시 모드 정보를 표시합니다.  
  
    > [!NOTE]
    >  도구를 실행할 때 옵션 목록이 필요하면 **LocBaml.exe**를 입력하고 Enter 키를 누릅니다.  
  
<a name="parse_dll"></a>   
## LocBaml을 사용하여 파일 구문 분석  
 LocBaml 도구를 만들었으므로 이제 이 도구를 통해 HelloApp.resources.dll을 구문 분석하여 지역화할 텍스트 콘텐츠를 추출할 준비가 되었습니다.  
  
1.  주 응용 프로그램 어셈블리가 만들어진 응용 프로그램의 bin\\debug 폴더에 LocBaml.exe를 복사합니다.  
  
2.  위성 어셈블리 파일을 구문 분석하고 출력을 .csv 파일로 저장하려면 다음 명령을 사용합니다.  
  
     **LocBaml.exe \/parse HelloApp.resources.dll \/out:Hello.csv**  
  
    > [!NOTE]
    >  입력 파일 HelloApp.resources.dll이 LocBaml.exe와 동일한 디렉터리에 없는 경우 두 파일이 동일한 디렉터리에 있도록 파일 중 하나를 이동합니다.  
  
3.  LocBaml을 실행하여 파일을 구문 분석하는 경우 출력은 쉼표\(.csv 파일\) 또는 탭\(.txt 파일\)으로 구분된 7개 필드로 구성됩니다.  다음은 HelloApp.resources.dll에 대해 구문 분석된 .csv 파일을 보여 줍니다.  
  
    ||  
    |-|  
    |HelloApp.g.en\-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,\#Text1;\#Text2;|  
    |HelloApp.g.en\-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World|  
    |HelloApp.g.en\-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World|  
  
     7개 필드는 다음과 같습니다.  
  
    1.  **BAML 이름**.  소스 언어 위성 어셈블리와 관련된 BAML 리소스의 이름입니다.  
  
    2.  **리소스 키**.  지역화된 리소스 식별자입니다.  
  
    3.  **범주**.  값 형식입니다.  [지역화 특성 및 주석](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md)을 참조하세요.  
  
    4.  **가독성**.  로컬라이저가 값을 읽을 수 있는지 여부입니다.  [지역화 특성 및 주석](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md)을 참조하세요.  
  
    5.  **수정 가능성**.  로컬라이저가 값을 수정할 수 있는지 여부입니다.  [지역화 특성 및 주석](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md)을 참조하세요.  
  
    6.  **설명**.  값은 지역화하는 방법을 확인하는 데 도움이 되는 값에 대한 추가 설명입니다.  [지역화 특성 및 주석](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md)을 참조하세요.  
  
    7.  **값**.  원하는 문화권으로 번역할 텍스트 값입니다.  
  
     다음 표에서는 이러한 필드가 .csv 파일의 구분된 값에 매핑되는 방법을 보여 줍니다.  
  
    |BAML 이름|리소스 키|범주|가독성|수정 가능성|설명|값|  
    |-------------|-----------|--------|---------|------------|--------|-------|  
    |HelloApp.g.en\-US.resources:window1.baml|Stack1:System.Windows.Controls.StackPanel.$Content|무시|FALSE|FALSE||\#Text1;\#Text2|  
    |HelloApp.g.en\-US.resources:window1.baml|Text1:System.Windows.Controls.TextBlock.$Content|없음|TRUE|TRUE||Hello World|  
    |HelloApp.g.en\-US.resources:window1.baml|Text2:System.Windows.Controls.TextBlock.$Content|없음|TRUE|TRUE||Goodbye World|  
  
     **설명** 필드의 모든 값에는 값이 포함되어 있지 않습니다. 필드에 값이 없는 경우 비어 있습니다.  또한 첫 번째 행의 항목은 읽고 수정할 수 없으며 해당 **범주** 값으로 "무시"가 포함되어 값을 지역화할 수 없음을 나타냅니다.  
  
4.  구문 분석된 파일, 특히 큰 파일에서 지역화 가능한 항목의 검색이 용이하도록 **범주**, **가독성** 및 **수정 가능성**을 기준으로 항목을 정렬하거나 필터링할 수 있습니다.  예를 들어 읽을 수 없는 값과 수정할 수 없는 값을 필터링할 수 있습니다.  
  
<a name="translate_loc_content"></a>   
## 지역화할 수 있는 콘텐츠 번역  
 사용 가능한 임의 도구를 사용하여 추출한 콘텐츠를 번역합니다.  이 작업을 효율적으로 수행하려면 .csv 파일에 리소스를 쓴 다음 [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)]에서 보고 마지막 열\(값\)에서 번역하는 것이 좋습니다.  
  
<a name="merge_translations"></a>   
## LocBaml을 사용하여 새 .resources.dll 파일 생성  
 LocBaml로 HelloApp.resources.dll을 구문 분석하여 식별된 콘텐츠가 번역되었으며 원래 응용 프로그램에 다시 병합해야 합니다.  **generate** 또는 **\-g** 옵션을 사용하여 새 .resources.dll 파일을 생성합니다.  
  
1.  다음 구문을 사용하여 새 HelloApp.resources.dll 파일을 생성합니다.  문화권을 en\-US로 표시합니다\(\/cul:en\-US\).  
  
     **LocBaml.exe \/generate HelloApp.resources.dll \/trans:Hello.csv \/out:c:\\ \/cul:en\-US**  
  
    > [!NOTE]
    >  입력 파일 Hello.csv가 LocBaml.exe 실행 파일과 동일한 디렉터리에 없는 경우 두 파일이 동일한 디렉터리에 있도록 파일 중 하나를 이동합니다.  
  
2.  C:\\HelloApp\\Bin\\Debug\\en\-US\\HelloApp.resources.dll 디렉터리에 있는 기존 HelloApp.resources.dll 파일을 새로 만든 HelloApp.resources.dll 파일로 바꿉니다.  
  
3.  이제 응용 프로그램에서 "Hello World" 및 "Goodbye World"가 번역됩니다.  
  
4.  다른 문화권으로 번역하려면 번역할 대상 언어의 문화권을 사용합니다.  다음 예제에서는 프랑스어\-캐나다로 번역하는 방법을 보여 줍니다.  
  
     **LocBaml.exe \/generate HelloApp.resources.dll \/trans:Hellofr\-CA.csv \/out:c:\\ \/cul:fr\-CA**  
  
5.  주 응용 프로그램 어셈블리와 동일한 어셈블리에서 새 위성 어셈블리를 포함할 새 문화권별 폴더를 만듭니다.  프랑스어\-캐나다의 경우 폴더는 fr\-CA입니다.  
  
6.  생성된 위성 어셈블리를 새 폴더에 복사합니다.  
  
7.  새 위성 어셈블리를 테스트하려면 응용 프로그램이 실행되는 문화권을 변경해야 합니다.  이 작업은 다음 두 가지 방법 중 하나로 수행할 수 있습니다.  
  
    -   운영 체제의 국가별 설정 변경\(**시작** &#124; **제어판** &#124; **국가 및 언어 옵션**\).  
  
    -   응용 프로그램에서 다음 코드를 App.xaml.cs에 추가합니다.  
  
         [!code-xml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]  
  
         [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
         [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
<a name="Some_Tips_for_Using_LocBaml"></a>   
## LocBaml 사용과 관련된 몇 가지 팁  
  
-   사용자 지정 컨트롤을 정의하는 모든 종속 어셈블리를 LocBaml의 로컬 디렉터리에 복사하거나 GAC에 설치해야 합니다.  이 작업은 지역화 API가 [!INCLUDE[TLA#tla_baml](../../../../includes/tlasharptla-baml-md.md)]을 읽을 때 종속 어셈블리에 액세스할 수 있어야 하기 때문에 필요합니다.  
  
-   주 어셈블리가 서명된 경우 생성된 리소스 DLL도 서명되어야 로드됩니다.  
  
-   지역화된 리소스 DLL 버전을 주 어셈블리와 동기화해야 합니다.  
  
<a name="Whats_Next"></a>   
## 새로운 기능  
 지금까지 LocBaml 도구를 사용하는 방법에 대한 기본 사항을 알아보았습니다.  Uid를 포함하는 파일을 만들 수 있어야 합니다.  LocBaml 도구를 통해 파일을 구문 분석하여 지역화할 수 있는 콘텐츠를 추출할 수 있어야 하며, 콘텐츠가 번역된 후 번역된 콘텐츠를 병합하는 .resources.dll 파일을 생성할 수 있어야 합니다.  이 항목에 가능한 모든 세부 정보가 포함되어 있지는 않지만 이제 LocBaml를 응용 프로그램 지역화에 사용하는 데 필요한 지식을 습득했습니다.  
  
## 참고 항목  
 [WPF의 전역화](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)   
 [자동 레이아웃 사용 개요](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)