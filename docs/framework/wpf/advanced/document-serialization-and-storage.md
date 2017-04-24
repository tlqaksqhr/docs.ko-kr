---
title: "문서 serialization 및 저장소 | Microsoft Docs"
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
  - "문서, serialization"
  - "문서, storage"
  - "문서의 serialization"
  - "문서 저장"
ms.assetid: 4839cd87-e206-4571-803f-0200098ad37b
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# 문서 serialization 및 저장소
[!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]에서는 고품질 문서를 만들고 표시하기 위한 강력한 환경이 제공됩니다.  고급 보기 컨트롤과 고정 문서 및 유동 문서를 모두 지원하는 향상된 기능은 강력한 2D 및 3D 그래픽 기능과 결합되어 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 응용 프로그램에서 새로운 수준의 품질과 사용자 경험을 제공할 수 있게 합니다.  문서의 메모리 내 표현을 유연하게 관리하는 것은 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]의 주요 기능이며 데이터 저장소에서 문서를 효율적으로 저장 및 로드하는 것은 거의 모든 응용 프로그램에서 요구되는 사항입니다.  문서를 내부 메모리 내 표현에서 외부 데이터 저장소로 변환하는 프로세스를 [serialization](GTMT)이라고 합니다.  데이터 저장소를 읽고 원래 메모리 내 인스턴스를 다시 만드는 이와 반대의 프로세스를 deserialization이라고 합니다.  
  
   
  
<a name="AboutSerialization"></a>   
## 문서 serialization 정보  
 문서를 메모리에서 [serialize](GTMT)하고 메모리에 다시 deserialize하는 프로세스는 응용 프로그램에 투명하게 수행되는 것이 가장 좋습니다.  응용 프로그램에서 serializer "write" 메서드를 호출하여 문서를 저장하는 반면에 deserializer "read" 메서드는 데이터 저장소에 액세스하고 원래 인스턴스를 메모리에서 다시 만듭니다.  serialize 및 deserialize 프로세스가 문서를 원래 형태로 다시 만드는 동안에 데이터가 저장되는 특정 형식은 일반적으로 응용 프로그램에서 중요한 사항이 아닙니다.  
  
 일반적으로 응용 프로그램에서는 사용자가 문서를 다른 매체나 다른 형식으로 저장할 수 있게 하는 여러 serialization 옵션이 제공됩니다.  예를 들어 응용 프로그램에서는 문서를 디스크 파일, 데이터베이스 또는 웹 서비스에 저장하기 위한 "다른 이름으로 저장" 옵션이 제공할 수 있습니다.  마찬가지로 여러 다른 serializer가 문서를 HTML, RTF, XML, XPS 또는 타사 형식과 같은 다양한 형식으로 저장할 수 있습니다.  응용 프로그램에 대해 serialization은 각 특정 serializer 구현 내에서 저장소 매체의 세부 정보를 격리시키는 인터페이스를 정의합니다.  저장소 세부 정보를 캡슐화하는 이점 외에도 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] <xref:System.Windows.Documents.Serialization> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]는 여러 다른 중요한 기능을 제공합니다.  
  
### .NET Framework 3.0 문서 Serializer의 기능  
  
-   페이지가 매겨진 콘텐츠, 2D\/3D 요소, 이미지, 미디어, 하이퍼링크, 주석 및 기타 지원 콘텐츠를 효율적으로 저장할 수 있게 하는 고급 문서 개체\([논리 트리](GTMT) 및 시각적 표시\)에 대한 직접 액세스 권한  
  
-   [동기](GTMT) 및 [비동기](GTMT) 작업  
  
-   향상된 기능을 가진 플러그 인 serializer에 대한 지원  
  
    -   모든 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 응용 프로그램에 사용될 시스템 차원의 액세스  
  
    -   간단한 응용 프로그램 플러그 인 검색  
  
    -   사용자 지정 타사 플러그 인을 위한 간단한 배포, 설치 및 업데이트  
  
    -   사용자 지정 런타임 설정 및 옵션을 위한 사용자 인터페이스 지원  
  
### XPS 인쇄 경로  
 [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 인쇄 경로는 또한 인쇄 출력을 통해 문서를 작성하기 위한 확장 가능한 메커니즘을 제공합니다.  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]는 [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)]용의 네이티브 인쇄 풀 형식 및 문서 파일 형식 모두로 사용됩니다.  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 문서를 중간 형식으로 변환할 필요 없이 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 호환 프린터로 직접 전송할 수 있습니다.  인쇄 경로 출력 옵션과 기능에 대한 자세한 내용은 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)를 참조하십시오.  
  
<a name="PluginSerializers"></a>   
## 플러그 인 Serializer  
 <xref:System.Windows.Documents.Serialization> API에서는 플러그 인 serializer 및 연결된 serializer가 모두 지원됩니다. 이러한 serializer는 응용 프로그램과 별개로 설치되고 런타임에 바인딩되며 <xref:System.Windows.Documents.Serialization.SerializerProvider> 검색 메커니즘을 통해 액세스합니다.  플러그 인 serializer는 간편한 배포 및 시스템 차원 사용을 위한 향상된 이점을 제공합니다.  또한 연결된 serializer는 플러그 인 serializer에 액세스할 수 없는 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 등과 같은 [부분 신뢰](GTMT) 환경에서 구현할 수 있습니다.  <xref:System.Windows.Documents.Serialization.SerializerWriter> 클래스의 파생된 구현에 기초하는 연결된 serializer는 응용 프로그램에 직접 컴파일 및 연결됩니다.  플러그 인 serializer 및 연결된 serializer는 모두 동일한 공용 메서드 및 이벤트를 통해 작동하므로 동일한 응용 프로그램에서 둘 중 하나 또는 둘 다를 쉽게 사용할 수 있습니다.  
  
 플러그 인 serializer는 빌드할 때 모든 잠재적 형식에 대해 직접 코딩할 필요 없이 새로운 저장소 디자인 및 파일 형식에 대한 확장성을 제공함으로써 응용 프로그램 개발자에게 도움을 줍니다.  또한 플러그 인 serializer는 사용자 지정 또는 독점적인 파일 형식을 위한 시스템 액세스 가능 플러그 인을 배포, 설치 및 업데이트하는 표준화된 수단을 제공하여 타사 개발자를 지원합니다.  
  
### 플러그 인 Serializer 사용  
 플러그 인 serializer는 사용이 간편합니다.  <xref:System.Windows.Documents.Serialization.SerializerProvider> 클래스는 시스템에 설치된 각 플러그 인에 대한 <xref:System.Windows.Documents.Serialization.SerializerDescriptor> 개체를 열거합니다.  <xref:System.Windows.Documents.Serialization.SerializerDescriptor.IsLoadable%2A> 속성은 현재 구성에 기초하여 설치된 플러그 인을 필터링하고 응용 프로그램에서 serializer을 로그하여 사용할 수 있는지 확인합니다.  또한 <xref:System.Windows.Documents.Serialization.SerializerDescriptor>는 <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DisplayName%2A> 및 <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DefaultFileExtension%2A>과 같은 다른 속성을 제공하며 응용 프로그램은 이러한 속성을 사용하여 사용 가능한 출력 형식을 위한 serializer를 선택하라는 메시지를 사용자에게 표시할 수 있습니다.  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]용 기본 플러그 인 serializer는 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]과 함께 제공되며 항상 열거됩니다.  사용자가 출력 형식을 선택한 후 특정 형식을 위한 <xref:System.Windows.Documents.Serialization.SerializerWriter>를 만들기 위해 <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> 메서드가 사용됩니다.  그런 다음 <xref:System.Windows.Documents.Serialization.SerializerWriter>.<xref:System.Windows.Documents.Serialization.SerializerWriter.Write%2A> 메서드를 호출하여 문서 스트림을 데이터 저장소에 출력할 수 있습니다.  
  
 다음 예제에서는 "PlugInFileFilter" 속성에서 <xref:System.Windows.Documents.Serialization.SerializerProvider> 메서드를 사용하는 응용 프로그램을 보여 줍니다.  PlugInFileFilter는 설치된 플러그 인을 열거하고 <xref:Microsoft.Win32.SaveFileDialog>에 대한 사용 가능한 파일 옵션을 사용하여 필터 문자열을 빌드합니다.  
  
 [!code-csharp[DocumentSerialize#DocSerializeFileFilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializefilefilter)]  
  
 사용자가 출력 파일 이름을 선택한 후 다음 예제에서는 지정된 문서를 지정된 형식으로 저장하기 위해 <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> 메서드가 사용되는 방법을 보여 줍니다.  
  
 [!code-csharp[DocumentSerialize#DocSerializePlugIn](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializeplugin)]  
  
<a name="InstallingPluginSerializers"></a>   
### 플러그 인 Serializer 설치  
 <xref:System.Windows.Documents.Serialization.SerializerProvider> 클래스는 플러그 인 serializer 검색 및 액세스를 위한 상위 수준 응용 프로그램 인터페이스를 제공합니다.  <xref:System.Windows.Documents.Serialization.SerializerProvider>는 시스템에 설치되었으며 액세스할 수 있는 serializer 목록을 찾아 응용 프로그램에 제공합니다.  설치된 serializer의 세부 사항은 레지스트리 설정을 통해 정의됩니다.  <xref:System.Windows.Documents.Serialization.SerializerProvider.RegisterSerializer%2A> 메서드를 사용하여 플러그 인 serializer를 레지스트리에 추가할 수 있습니다. 또는 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]이 아직 설치되지 않은 경우 플러그 인 설치 스크립트에서 레지스트리 값을 직접 설정할 수 있습니다.  <xref:System.Windows.Documents.Serialization.SerializerProvider.UnregisterSerializer%2A> 메서드를 사용하여 이전에 설치된 플러그 인을 제거하거나 제거 스크립트에 의해 레지스트리 설정이 비슷하게 다시 설정될 수 있습니다.  
  
### 플러그 인 Serializer 만들기  
 플러그 인 serializer 및 연결된 serializer는 노출된 동일한 공용 메서드 및 이벤트를 사용하며 [동기](GTMT) 또는 [비동기](GTMT)로 작동하도록 비슷하게 디자인될 수 있습니다.  플러그 인 serializer를 만들기 위해 일반적으로 수행하는 세 가지 기본 단계는 다음과 같습니다.  
  
1.  먼저 연결된 serializer로 serializer를 구현 및 디버깅합니다.  처음에 테스트 응용 프로그램에서 직접 컴파일 및 연결되는 serializer를 만들면 테스트에 도움이 되는 중단점 및 다른 디버깅 서비스에 완전히 액세스할 수 있게 됩니다.  
  
2.  serializer가 완전히 테스트된 후에 플러그 인을 만들기 위해 <xref:System.Windows.Documents.Serialization.ISerializerFactory> 인터페이스가 추가됩니다.  <xref:System.Windows.Documents.Serialization.ISerializerFactory> 인터페이스에서는 논리 트리, <xref:System.Windows.UIElement> 개체, <xref:System.Windows.Documents.IDocumentPaginatorSource> 및 <xref:System.Windows.Media.Visual> 요소를 포함하는 모든 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 개체에 대한 모든 액세스 권한이 허용됩니다.  또한 <xref:System.Windows.Documents.Serialization.ISerializerFactory>는 연결된 serializer에 사용되는 것과 동일한 동기 및 비동기 메서드와 이벤트를 제공합니다.  큰 문서는 출력하는 데 오래 걸릴 수 있으므로 응답하는 사용자 상호 작용을 유지하고 데이터 저장소에 문제가 있을 때 "취소" 옵션을 제공할 수 있도록 비동기 작업을 사용하는 것이 좋습니다.  
  
3.  플러그 인 serializer가 만들어진 후 플러그 인 배포와 설치 및 제거를 위해 설치 스크립트가 구현됩니다\(위의 “[플러그 인 Serializers 설치](#InstallingPluginSerializers)” 참조\).  
  
## 참고 항목  
 <xref:System.Windows.Documents.Serialization>   
 <xref:System.Windows.Xps.XpsDocumentWriter>   
 <xref:System.Windows.Xps.Packaging.XpsDocument>   
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [XML Paper Specification: Overview](http://go.microsoft.com/fwlink/?LinkID=106246)