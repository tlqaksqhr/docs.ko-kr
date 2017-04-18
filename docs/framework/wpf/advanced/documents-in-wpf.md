---
title: "WPF의 문서 | Microsoft Docs"
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
  - "브라우저 표시 가능 문서"
  - "문서, 브라우저 표시 가능"
  - "문서, 컨트롤"
  - "문서, 패키징"
  - "문서, 텍스트 레이아웃"
  - "문서, 형식"
  - "문서, XPS"
  - "문서 패키지"
  - "XPS 문서"
ms.assetid: 6e8db7bc-050a-4070-aa72-bb8c46e87ff8
caps.latest.revision: 36
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 35
---
# WPF의 문서
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 제공하는 광범위한 문서 기능을 통해 이전 세대의 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]에 비해 보다 쉽게 액세스하고 읽을 수 있도록 디자인된 고품질 콘텐츠를 작성할 수 있습니다.  향상된 기능 및 품질과 더불어 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 문서 표시, 패키지 및 보안에 대한 통합 서비스도 제공합니다.  이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 문서 형식 및 문서 패키지를 소개합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="types_of_documents"></a>   
## 문서의 형식  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 사용 목적에 따라 문서를 크게 두 범주인 "고정 문서" 및 "유동 문서"로 분류합니다.  
  
 고정 문서는 사용된 디스플레이 또는 프린터 하드웨어에 관계없이 정확한 [!INCLUDE[TLA#tla_wys](../../../../includes/tlasharptla-wys-md.md)] 프레젠테이션을 필요로 하는 응용 프로그램에 사용됩니다.  일반적으로 고정 문서는 원래의 페이지 디자인을 반드시 유지해야 하는 DTP, 워드 프로세싱, 폼 레이아웃 등에 사용됩니다.  해당 레이아웃의 일부로서 고정 문서는 사용 중인 디스플레이 또는 인쇄 장치에 관계없이 콘텐츠 요소의 정확한 위치를 유지합니다.  예를 들어 96dpi 디스플레이로 표시되는 고정 문서 페이지의 경우 600dpi의 레이저 프린터로 인쇄하거나 4800dpi의 식자공으로 인쇄해도 모양이 동일하게 나타납니다.  각 장치의 기능에 따라 문서의 품질은 극대화되지만 어떤 경우든 레이아웃은 동일하게 유지됩니다.  
  
 한편 유동 문서는 표시 및 가독성을 최적화하도록 디자인되었으며 문서 사용 시 가독성이 가장 중요한 요소인 경우에 가장 적합합니다.  유동 문서는 하나의 미리 정의된 레이아웃으로 설정되는 대신에 창 크기, 장치 해상도 및 선택적 사용자 기본 설정과 같은 런타임 변수를 기반으로 동적으로 해당 콘텐츠를 조정하고 다시 배치합니다.  페이지 콘텐츠가 현재 창에 맞게 동적으로 형식이 지정되는 유동 문서의 간단한 예로 웹 페이지를 들 수 있습니다.  유동 문서는 런타임 환경을 기반으로 해당 사용자의 보기 및 읽기 환경을 최적화합니다.  예를 들어 같은 유동 문서라도 고해상도 19인치 디스플레이 또는 소형 2x3인치 PDA 화면 등에 따라 최적의 가독성을 위해 동적 형식 지정이 각각 다르게 수행됩니다.  또한 유동 문서에는 검색, 가독성을 최적화하는 보기 모드, 글꼴 크기와 모양을 변경하는 기능 등 여러 기본 제공 기능이 있습니다.  유동 문서에 대한 그림, 예제 및 보다 자세한 정보는 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)를 참조하십시오.  
  
<a name="document_viewer"></a>   
## 문서 컨트롤 및 텍스트 레이아웃  
 [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)]에서는 사용자 응용 프로그램 내에서 고정 문서, 유동 문서 및 일반 텍스트를 간단하게 사용할 수 있게 해 주는 미리 빌드된 컨트롤 집합을 제공합니다.  고정 문서 콘텐츠는 <xref:System.Windows.Controls.DocumentViewer> 컨트롤을 사용하여 표시됩니다.  유동 문서 콘텐츠는 여러 다양한 사용자 시나리오에 사용되는 <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer> 및 <xref:System.Windows.Controls.FlowDocumentScrollViewer>와 같은 세 가지 컨트롤을 사용하여 표시됩니다\(아래 단원 참조\).  다른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤은 일반 텍스트 사용을 지원하는 간단한 레이아웃을 제공합니다\(아래의 [사용자 인터페이스의 텍스트](#text_in_the_user_interface) 참조\).  
  
### 고정 문서 컨트롤 \- DocumentViewer  
 <xref:System.Windows.Controls.DocumentViewer> 컨트롤은 <xref:System.Windows.Documents.FixedDocument> 콘텐츠를 표시하도록 디자인되었습니다.  <xref:System.Windows.Controls.DocumentViewer> 컨트롤은 인쇄 출력, 클립보드에 복사, 확대\/축소, 텍스트 검색 기능과 같은 일반적인 작업을 기본적으로 지원하는 직관적인 사용자 인터페이스를 제공합니다.  이 컨트롤을 사용하면 친숙한 스크롤 메커니즘을 사용하여 콘텐츠 페이지에 액세스할 수 있습니다.  모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤과 마찬가지로 <xref:System.Windows.Controls.DocumentViewer>도 컨트롤을 거의 모든 응용 프로그램이나 환경에 시각적으로 통합될 수 있게 해주는 완전하거나 부분적인 스타일 재설정을 지원합니다.  
  
 <xref:System.Windows.Controls.DocumentViewer>는 읽기 전용 방식으로 콘텐츠를 표시하도록 디자인되었습니다. 콘텐츠를 편집하거나 수정하는 기능은 사용할 수 없으며 지원되지 않습니다.  
  
<a name="flow_document"></a>   
### 유동 문서 컨트롤  
 **참고:** 유동 문서 기능 및 이러한 기능을 만드는 방법에 대한 자세한 내용은 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)를 참조하십시오.  
  
 유동 문서 콘텐츠의 표시는 <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer> 및 <xref:System.Windows.Controls.FlowDocumentScrollViewer>라는 세 가지 컨트롤로 지원됩니다.  
  
#### FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader>에는 단일 페이지\(한 번에 한 페이지\) 보기 모드, 한 번에 두 페이지\(책 읽기 형식\) 보기 모드 및 연속 스크롤\(바닥 없음\) 보기 모드를 비롯한 다양한 보기 모드를 동적으로 선택할 수 있는 기능이 포함되어 있습니다.  이러한 보기 모드에 대한 자세한 내용은 <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>를 참조하십시오.  다른 보기 모드 사이에 동적으로 전환하는 기능이 필요하지 않은 경우 <xref:System.Windows.Controls.FlowDocumentPageViewer> 및 <xref:System.Windows.Controls.FlowDocumentScrollViewer>는 특정 보기 모드에 고정된 간단한 유동 콘텐츠 뷰어를 제공합니다.  
  
#### FlowDocumentPageViewer 및 FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer>가 한 번에 한 페이지 보기 모드로 콘텐츠를 표시하는 반면에 <xref:System.Windows.Controls.FlowDocumentScrollViewer>는 연속 스크롤 모드로 콘텐츠를 표시합니다.  <xref:System.Windows.Controls.FlowDocumentPageViewer>와 <xref:System.Windows.Controls.FlowDocumentScrollViewer>는 모두 특정 보기 모드로 고정됩니다.  <xref:System.Windows.Controls.FlowDocumentReader>에는 사용자가 <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> 열거형에서 제공하는 것처럼 여러 보기 모드를 동적으로 선택할 수 있는 기능이 포함되어 있지만, <xref:System.Windows.Controls.FlowDocumentPageViewer> 또는 <xref:System.Windows.Controls.FlowDocumentScrollViewer>보다 리소스를 많이 소모합니다.  
  
 기본적으로 세로 스크롤 막대는 항상 표시되며 가로 스크롤 막대는 필요한 경우에만 표시됩니다.  <xref:System.Windows.Controls.FlowDocumentScrollViewer>의 기본 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에는 도구 모음이 포함되어 있지 않지만 <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> 속성을 사용하여 기본 제공 도구 모음을 사용하도록 설정할 수 있습니다.  
  
<a name="text_in_the_user_interface"></a>   
### 사용자 인터페이스의 텍스트  
 문서에 텍스트를 추가하는 것 이외에 텍스트를 폼과 같은 응용 프로그램 UI에 명확하게 사용할 수 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 화면에 텍스트를 그리기 위한 다양한 컨트롤이 포함되어 있습니다.  각 컨트롤은 서로 다른 시나리오에 사용되며 컨트롤마다 고유한 기능 및 제한 사항이 있습니다.  [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]의 간단한 문장과 같이 제한된 텍스트 지원이 필요할 경우 일반적으로 <xref:System.Windows.Controls.TextBlock> 요소를 사용해야 합니다.  <xref:System.Windows.Controls.Label>은 최소한의 텍스트 지원만 필요할 경우 사용할 수 있습니다.  자세한 내용은 [TextBlock 개요](../../../../docs/framework/wpf/controls/textblock-overview.md)를 참조하십시오.  
  
<a name="packaging"></a>   
## 문서 패키지  
 <xref:System.IO.Packaging> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]는 간단한 액세스, 이식 및 배포 기능을 제공하는 하나의 컨테이너에 응용 프로그램 데이터, 문서 콘텐츠 및 관련 리소스를 구성할 수 있는 효율적인 방법을 제공합니다.  여러 개의 개체를 하나의 단위에 포함할 수 있는 <xref:System.IO.Packaging.Package> 형식의 한 예로 ZIP 파일을 들 수 있습니다.  패키지 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]는 Open Packaging Conventions 표준과 XML 및 ZIP 파일 아키텍처를 사용하여 디자인된 기본 <xref:System.IO.Packaging.ZipPackage> 구현을 제공합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 패키지 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 사용하면 간단하게 패키지를 만들고 그 안에서 개체를 저장하고 액세스할 수 있습니다.  <xref:System.IO.Packaging.Package>에 저장된 개체를 <xref:System.IO.Packaging.PackagePart> \("파트"\)라고 합니다.  또한 패키지에는 특정 파트의 출처를 식별하고 패키지의 콘텐츠가 변경되지 않았는지 검증하는 데 사용되는 서명된 디지털 인증서가 포함될 수 있습니다.  패키지에는 기존 파트의 콘텐츠를 실제로 수정하지 않고 추가 정보를 패키지에 추가하거나 특정 파트에 연결하는 <xref:System.IO.Packaging.PackageRelationship> 기능이 있습니다.  또한 패키지 서비스는 [!INCLUDE[TLA#tla_rm](../../../../includes/tlasharptla-rm-md.md)]을 지원합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 패키지 아키텍처는 다음과 같은 여러 주요 기술의 기반이 됩니다.  
  
-   [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]를 준수하는 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 문서  
  
-   Microsoft Office "12" Open XML 형식 문서\(.docx\).  
  
-   사용자의 자체 응용 프로그램 디자인을 위한 사용자 지정 저장 형식  
  
 <xref:System.Windows.Xps.Packaging.XpsDocument>는 특히 패키지 API를 기반으로 하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 고정 콘텐츠 문서를 저장하도록 디자인되었습니다.  <xref:System.Windows.Xps.Packaging.XpsDocument>는 뷰어에서 열거나, <xref:System.Windows.Controls.DocumentViewer> 컨트롤에서 표시하거나, 인쇄 스풀로 라우트하거나, [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 호환 프린터로 직접 출력할 수 있는 독립적인 문서입니다.  
  
 다음 단원에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 함께 제공되는 <xref:System.IO.Packaging.Package> 및 <xref:System.Windows.Xps.Packaging.XpsDocument> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]에 대한 추가 정보를 제공합니다.  
  
<a name="packages"></a>   
### 패키지 구성 요소  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 패키지 API를 사용하여 응용 프로그램 데이터와 문서를 이식 가능한 하나의 단위로 구성할 수 있습니다.  ZIP 파일은 가장 많이 사용되는 패키지 형식 중 하나로, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 제공되는 기본 패키지 형식입니다.  <xref:System.IO.Packaging.Package> 자체는 Open XML 표준 및 ZIP 파일 아키텍처를 사용하여 구현되는 <xref:System.IO.Packaging.ZipPackage>의 추상 클래스입니다.  <xref:System.IO.Packaging.Package.Open%2A> 메서드는 기본적으로 <xref:System.IO.Packaging.ZipPackage>를 사용하여 ZIP 파일을 만들고 사용합니다.  패키지에는 다음과 같은 세 가지 기본 항목 형식이 포함될 수 있습니다.  
  
|||  
|-|-|  
|<xref:System.IO.Packaging.PackagePart>|응용 프로그램 콘텐츠, 데이터, 문서 및 리소스 파일|  
|<xref:System.IO.Packaging.PackageDigitalSignature>|확인, 인증 및 검증을 위한 [X.509 인증서](GTMT)|  
|<xref:System.IO.Packaging.PackageRelationship>|패키지 또는 특정 파트와 관련된 추가 정보|  
  
<a name="PackageParts"></a>   
#### PackageParts  
 <xref:System.IO.Packaging.PackagePart>\("파트"\)는 <xref:System.IO.Packaging.Package>에 저장된 개체를 참조하는 추상 클래스입니다.  ZIP 파일에서 패키지 파트는 ZIP 파일에 저장된 개별 파일에 해당합니다.  <xref:System.IO.Packaging.ZipPackagePart>는 <xref:System.IO.Packaging.ZipPackage>에 저장된 serializable 개체를 기본적으로 구현합니다.  파일 시스템과 마찬가지로 패키지에 포함된 파트는 계층적 디렉터리 또는 "폴더 스타일"의 구조로 저장됩니다.  응용 프로그램은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 패키징 API를 사용하여 하나의 ZIP 파일 컨테이너로 여러 개의 <xref:System.IO.Packaging.PackagePart> 개체를 작성하고 저장하고 읽을 수 있습니다.  
  
<a name="PackageDigitalSignatures"></a>   
#### PackageDigitalSignatures  
 보안을 위해 <xref:System.IO.Packaging.PackageDigitalSignature>\("디지털 서명"\)를 패키지 내의 파트와 연관시킬 수 있습니다.  <xref:System.IO.Packaging.PackageDigitalSignature>에서는 다음 두 기능을 제공하는 [509](GTMT)를 통합합니다.  
  
1.  파트의 작성기를 식별하고 인증합니다.  
  
2.  파트가 수정되지 않았는지 확인합니다.  
  
 디지털 서명이 있어도 파트를 수정할 수는 있지만 파트가 어떠한 방식으로든 변경된 경우에는 디지털 서명에 대한 유효성 검사가 실패합니다.  이 경우 응용 프로그램이 적절한 조치를 취할 수 있습니다. 예를 들어 파트가 열리지 않도록 하거나 파트가 수정되어 더 이상 안전하지 않다는 내용을 사용자에게 알릴 수 있습니다.  
  
<a name="PackageRelationships"></a>   
#### PackageRelationships  
 <xref:System.IO.Packaging.PackageRelationship>\("관계"\)는 추가 정보를 패키지 또는 패키지 내 파트와 연관시키는 메커니즘을 제공합니다.  관계는 실제 파트 콘텐츠를 변경하지 않고 추가 정보를 파트와 연관시킬 수 있는 패키지 수준의 기능입니다.  새 데이터를 직접 파트 콘텐츠에 삽입하는 것은 대개의 경우 효율적이지 않습니다.  
  
-   파트 및 해당 콘텐츠 스키마의 실제 형식은 알 수 없습니다.  
  
-   실제 형식을 알아도 콘텐츠 스키마가 새 정보를 추가할 수 있는 방법을 제공하지 않을 수 있습니다.  
  
-   파트에 디지털 서명하거나 파트를 암호화하여 변경을 방지할 수 있습니다.  
  
 패키지 관계는 추가 정보를 추가하거나 개별 파트나 전체 패키지에 연관시킬 수 있는 검색 가능한 수단을 제공합니다.  패키지 관계는 다음과 같은 두 가지 주요 기능에 사용됩니다.  
  
1.  한 파트의 다른 파트에 대한 종속성 관계 정의  
  
2.  파트와 관련된 설명 또는 기타 데이터를 추가하는 정보 관계 정의  
  
 <xref:System.IO.Packaging.PackageRelationship>에서는 종속성을 정의하고 패키지의 파트 또는 전체 패키지와 연관된 기타 정보를 추가할 수 있는 빠르고 검색 가능한 방법을 제공합니다.  
  
<a name="Dependency_Relationships"></a>   
##### 종속성 관계  
 종속성 관계는 한 파트의 다른 파트에 대한 종속성을 설명하는 데 사용됩니다.  예를 들어 패키지에는 하나 이상의 \<img\> 이미지 태그가 들어 있는 HTML 파트가 포함될 수 있습니다.  이미지 태그는 패키지 내부 또는 패키지 외부의 다른 파트\(예: 인터넷으로 액세스할 수 있는 파트\)로 있는 이미지를 참조합니다.  HTML 파일과 연관된 <xref:System.IO.Packaging.PackageRelationship>을 사용하면 종속 리소스를 쉽고 빠르게 찾고 액세스할 수 있습니다.  브라우저 또는 뷰어 응용 프로그램은 스키마를 모르거나 문서를 구문 분석하지 않아도 파트 관계에 직접 액세스하거나 종속 리소스 어셈블을 즉시 시작할 수 있습니다.  
  
<a name="Information_Relationships"></a>   
##### 정보 관계  
 설명이나 주석과 마찬가지로 <xref:System.IO.Packaging.PackageRelationship>은 실제로 파트 콘텐츠 자체를 변경하지 않고도 파트와 연관될 다른 정보 형식을 저장하는 데에도 사용할 수 있습니다.  
  
<a name="XPS_Documents"></a>   
## XPS 문서  
 [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] 문서는 렌더링에 필요한 모든 리소스 및 정보와 함께 하나 이상의 고정 문서가 포함된 패키지입니다.  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]도 네이티브 [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] 인쇄 스풀 파일 형식입니다.  <xref:System.Windows.Xps.Packaging.XpsDocument>는 표준 ZIP 데이터 집합으로 저장되어 있고 XML과 이진 구성 요소\(예: 이미지 및 글꼴 파일\)가 결합되어 포함될 수 있습니다. [PackageRelationships](#PackageRelationships)는 문서를 완전히 렌더링하기 위해 필요한 콘텐츠와 리소스 간의 종속성을 정의하는 데 사용됩니다.  <xref:System.Windows.Xps.Packaging.XpsDocument> 디자인에서는 다음과 같은 여러 가지 기능을 지원하는 단일 고품질 문서 솔루션을 제공합니다.  
  
-   고정 문서 콘텐츠 및 리소스를 이식 가능하고 쉽게 배포할 수 있는 단일 파일로 읽고 작성하고 저장합니다.  
  
-   [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 뷰어 응용 프로그램을 사용하여 문서를 표시합니다.  
  
-   문서를 [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)]의 네이티브 인쇄 스풀 출력 형식으로 출력합니다.  
  
-   문서를 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 호환 프린터로 직접 라우트합니다.  
  
## 참고 항목  
 <xref:System.Windows.Documents.FixedDocument>   
 <xref:System.Windows.Documents.FlowDocument>   
 <xref:System.Windows.Xps.Packaging.XpsDocument>   
 <xref:System.IO.Packaging.ZipPackage>   
 <xref:System.IO.Packaging.ZipPackagePart>   
 <xref:System.IO.Packaging.PackageRelationship>   
 <xref:System.Windows.Controls.DocumentViewer>   
 [텍스트](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)   
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [문서 serialization 및 저장소](../../../../docs/framework/wpf/advanced/document-serialization-and-storage.md)