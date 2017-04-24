---
title: "응용 프로그램 개발 | Microsoft Docs"
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
  - "응용 프로그램 개발[WPF], 정보"
  - "WPF, 응용 프로그램 개발 정보"
ms.assetid: 2996ce5e-81e9-49ae-881b-952db3dd1b7e
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# 응용 프로그램 개발
<a name="introduction"></a> [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]은 다음과 같은 종류의 응용 프로그램을 개발하는 데 사용할 수 있는 프레젠테이션 프레임워크입니다.  
  
-   독립 실행형 응용 프로그램\(클라이언트 컴퓨터에 설치해서 운영하는 실행 어셈블리로 구성된 전형적인 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 응용 프로그램\)  
  
-   [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]\(탐색 페이지로 이루어져 있고 이 페이지가 [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] 또는 Mozilla Firefox 등의 웹 브라우저를 통해 호스팅되는 실행 어셈블리로 구성된 응용 프로그램\)  
  
-   사용자 지정 컨트롤 라이브러리\(재사용 가능한 컨트롤이 들어 있는 비실행 어셈블리\)  
  
-   클래스 라이브러리\(재사용 가능한 클래스가 들어 있는 비실행 어셈블리\)  
  
> [!NOTE]
>  Windows 서비스에서 WPF 형식을 사용하지 않는 것이 좋습니다.  Windows 서비스에서 이러한 기능을 사용하려고 하면 기능이 예상대로 작동하지 않을 수 있습니다.  
  
 이러한 응용 프로그램 집합을 빌드하기 위해 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 서비스 호스트를 구현합니다.  이 항목에서는 이러한 서비스에 대한 개요와 더 자세한 정보를 찾을 수 있는 링크를 제공합니다.  
  
   
  
<a name="Application_Management"></a>   
## 응용 프로그램 관리  
 실행 가능한 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에는 일반적으로 다음과 같은 핵심 기능 집합이 필요합니다.  
  
-   진입점 메서드와 시스템 및 입력 메시지를 수신하는 Windows 메시지 루프 만들기를 비롯한 공통 응용 프로그램 인프라 만들기 및 관리  
  
-   응용 프로그램의 수명 추적 및 상호 작용  
  
-   명령줄 매개 변수 검색 및 처리  
  
-   응용 프로그램 범위에 속한 속성 및 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 리소스 공유  
  
-   처리되지 않은 예외 검색 및 처리  
  
-   종료 코드 반환  
  
-   독립 실행형 응용 프로그램에서 창 관리  
  
-   [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]와 탐색 창 및 프레임이 있는 독립 실행형 응용 프로그램에서 탐색 추적  
  
 이러한 기능은 *응용 프로그램 정의*를 사용하여 응용 프로그램에 추가하는 <xref:System.Windows.Application> 클래스로 구현됩니다.  
  
 자세한 내용은 [응용 프로그램 관리 개요](../../../../docs/framework/wpf/app-development/application-management-overview.md)를 참조하십시오.  
  
<a name="WPF_Application_Resource__Content__and_Data_Files"></a>   
## WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 리소스, 콘텐츠 및 데이터를 비롯한 세 가지 종류의 비실행 데이터 파일에 대한 지원으로 포함 리소스에 대한 [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]의 핵심 지원을 확장합니다. 자세한 내용은 [WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)을 참조하십시오.  
  
 WPF 비실행 데이터 파일에 대한 지원에서 중요한 구성 요소는 고유한 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 사용하여 데이터 파일을 식별하고 로드하는 기능입니다. 자세한 내용은 [WPF의 Pack URI](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)를 참조하십시오.  
  
<a name="Windows_and_Dialog_Boxes"></a>   
## 창 및 대화 상자  
 사용자는 창을 통해 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 독립 실행형 응용 프로그램과 상호 작용합니다.  창의 용도는 응용 프로그램 콘텐츠를 호스팅하고, 대개 사용자가 콘텐츠와 상호 작용할 수 있게 만드는 응용 프로그램 기능을 노출하는 것입니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 창은 다음을 지원하는 <xref:System.Windows.Window> 클래스로 캡슐화됩니다.  
  
-   창 만들기 및 표시  
  
-   소유자\/소유된 창 관계 설정  
  
-   창 모양 구성\(예: 크기, 위치, 아이콘, 제목 표시줄 텍스트, 테두리\)  
  
-   창의 수명 추적 및 상호 작용  
  
 자세한 내용은 [WPF 창 개요](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.Window>는 대화 상자라고 하는 특수한 유형의 창을 만드는 기능을 지원합니다.  모달 및 모덜리스 유형의 대화 상자를 모두 만들 수 있습니다.  
  
 사용 편의를 높이고 응용 프로그램 간의 재사용 및 일관성 있는 사용자 환경을 제공하기 위해 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 세 가지 공용 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 대화 상자인 <xref:Microsoft.Win32.OpenFileDialog>, <xref:Microsoft.Win32.SaveFileDialog> 및 <xref:System.Windows.Controls.PrintDialog>를 노출합니다.  
  
 메시지 상자는 사용자에게 중요한 텍스트 정보를 표시하고 간단한 예\/아니요\/확인\/취소 질문을 하는 데 사용되는 특수한 유형의 대화 상자입니다.  <xref:System.Windows.MessageBox> 클래스를 사용하여 메시지 상자를 만들고 표시할 수 있습니다.  
  
 자세한 내용은 [대화 상자 개요](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)를 참조하십시오.  
  
<a name="Navigation"></a>   
## 탐색  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 페이지\(<xref:System.Windows.Controls.Page>\)와 하이퍼링크\(<xref:System.Windows.Documents.Hyperlink>\)를 사용하는 웹 스타일의 탐색을 지원합니다.  이러한 탐색 기능은 다음을 비롯한 다양한 방식으로 구현할 수 있습니다.  
  
-   웹 브라우저에서 호스팅되는 독립 실행형 페이지  
  
-   웹 브라우저에서 호스팅되는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]로 컴파일되는 페이지  
  
-   독립 실행형 응용 프로그램으로 컴파일되고 탐색 창에서 호스팅되는 페이지\(<xref:System.Windows.Navigation.NavigationWindow>\)  
  
-   독립 실행형 페이지 또는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]나 독립 실행형 응용 프로그램으로 컴파일되는 페이지에서 호스팅될 수 있는 프레임\(<xref:System.Windows.Controls.Frame>\)을 통해 호스팅되는 페이지  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 효과적인 탐색을 위해 다음을 구현합니다.  
  
-   <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow> 및 응용 프로그램 간 탐색을 지원하는 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]에서 사용되는 탐색 요청을 처리하기 위한 공유 탐색 엔진인 <xref:System.Windows.Navigation.NavigationService>  
  
-   탐색을 초기화하는 탐색 메서드  
  
-   탐색 수명을 추적하고 상호 작용하는 탐색 이벤트  
  
-   검사 및 조작이 가능한 저널을 사용한 후방 및 전방 탐색 기억  
  
 자세한 내용은 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)를 참조하십시오.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 구조적 탐색이라고 하는 특수한 유형의 탐색도 지원합니다.  구조적 탐색을 사용하면 호출 함수와 일관성을 유지하는 구조적이며 예측 가능한 방식으로 데이터를 반환하는 하나 이상의 페이지를 호출할 수 있습니다.  이 기능은 <xref:System.Windows.Navigation.PageFunction%601> 클래스에 따라 달라집니다. 이 클래스에 대해서는 [구조적 탐색 개요](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md)에서 자세히 설명합니다.  [탐색 토폴로지 개요](../../../../docs/framework/wpf/app-development/navigation-topologies-overview.md)에서 설명하는 것처럼 복잡한 탐색 토폴로지를 간단하게 생성하기 위해서도 <xref:System.Windows.Navigation.PageFunction%601>이 사용됩니다.  
  
<a name="Hosting"></a>   
## 호스팅  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]는 [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] 또는 Firefox에서 호스팅될 수 있습니다.  각 호스팅 모델에는 [호스팅](../../../../docs/framework/wpf/app-development/hosting-wpf-applications.md) 항목에 설명되어 있는 고유한 고려 사항과 제약 조건 집합이 있습니다.  
  
<a name="Build_and_Deploy"></a>   
## 빌드 및 배포  
 명령줄 컴파일러를 사용하면 명령 프롬프트에서 간단한 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램을 빌드할 수 있지만 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]를 통합하여 개발 및 빌드 프로세스를 단순화하는 추가적인 지원을 제공합니다.  자세한 내용은 [WPF 응용 프로그램 만들기](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)를 참조하십시오.  
  
 빌드하는 응용 프로그램의 형식에 따라 하나 이상의 배포 옵션을 선택하여 사용할 수 있습니다.  자세한 내용은 [WPF 응용 프로그램 배포](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)를 참조하십시오.  
  
<a name="related_topics"></a>   
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[응용 프로그램 관리 개요](../../../../docs/framework/wpf/app-development/application-management-overview.md)|응용 프로그램 수명, 창, 응용 프로그램 리소스 및 탐색에 대한 관리를 비롯하여 <xref:System.Windows.Application> 클래스에 대해 간략히 설명합니다.|  
|[WPF의 창](../../../../docs/framework/wpf/app-development/windows-in-wpf-applications.md)|<xref:System.Windows.Window> 클래스 및 대화 상자 사용 방법을 비롯하여 응용 프로그램에서 창을 관리하는 방법에 대한 정보를 제공합니다.|  
|[탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)|응용 프로그램의 페이지 간 탐색 관리에 대해 간략히 설명합니다.|  
|[호스팅](../../../../docs/framework/wpf/app-development/hosting-wpf-applications.md)|[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]를 간략하게 설명합니다.|  
|[빌드 및 배포](../../../../docs/framework/wpf/app-development/building-and-deploying-wpf-applications.md)|WPF 응용 프로그램을 만들고 배포하는 방법에 대해 설명합니다.|  
|[Visual Studio 2015에서의 WPF 소개](../../../../docs/framework/wpf/getting-started/introduction-to-wpf-in-vs.md)|WPF의 주요 기능을 설명합니다.|  
|[연습: WPF 시작](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)|페이지 탐색, 레이아웃, 컨트롤, 이미지, 스타일 및 바인딩을 사용하여 WPF 응용 프로그램을 만드는 방법을 보여 주는 연습을 제공합니다.|