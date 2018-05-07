---
title: 문서 serialization 및 저장소
ms.date: 03/30/2017
helpviewer_keywords:
- 'serialization of documents [WPF], , '
- documents [WPF], storage
- documents [WPF], serialization
ms.assetid: 4839cd87-e206-4571-803f-0200098ad37b
ms.openlocfilehash: 8ee8acb95aa4a7c8dd80ea88594e582f05b71611
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="document-serialization-and-storage"></a>문서 serialization 및 저장소
Microsoft.NET Framework를 만들고 고품질 문서를 표시 하기 위한 강력한 환경을 제공 합니다.  강력한 2d 고정 문서 및 고급 흐름-문서를 모두 지 원하는 향상 된 기능 보기 컨트롤, 결합 및 3D 그래픽 기능과.NET Framework 응용 프로그램의 품질 및 사용자 환경 새로운 수준으로 합니다.  문서의 메모리 내 표현을 유연 하 게 관리할 수.NET Framework의 핵심 기능은 이며을 효율적으로 저장 하 고 데이터 저장소에서 문서를 로드할 수 있으면이 필요 하다는 거의 모든 응용 프로그램.  내부 메모리 내 표현에서 외부 데이터 저장소로 문서를 변환하는 프로세스를 serialization이라고 합니다.  데이터 저장소를 읽고 원래 메모리 내 인스턴스를 다시 만드는 역프로세스는 deserialization이라고 합니다.  
  
 
  
<a name="AboutSerialization"></a>   
## <a name="about-document-serialization"></a>문서 Serialization 정보  
 원칙적으로 응용 프로그램에서 문서를 메모리에서 serialize하고 다시 메모리로 deserialize하는 프로세스는 명확하게 수행됩니다.  응용 프로그램에서는 serializer “write” 메서드를 호출하여 문서를 저장하는 한편, deserializer “read” 메서드는 데이터 저장소에 액세스하여 원래 인스턴스를 메모리에 다시 만듭니다.  serialize 및 deserialize 프로세스를 통해 원래 양식으로 문서를 다시 만드는 경우 데이터가 저장되는 특정 형식은 일반적으로 응용 프로그램에서 문제가 되지 않습니다.  
  
 대부분의 응용 프로그램에서는 사용자가 여러 다른 매체 또는 다른 형식으로 문서를 저장할 수 있도록 하는 여러 serialization 옵션을 제공합니다.  예를 들어, 응용 프로그램에서 “다른 이름으로 저장” 옵션을 제공하여 문서를 디스크 파일, 데이터베이스 또는 웹 서비스에 저장하도록 지원할 수 있습니다.  마찬가지로 서로 다른 serializer마다 HTML, RTF, XML, XPS 등의 다른 형식 또는 타사 형식으로 문서를 저장할 수 있습니다.  응용 프로그램에서는 serialization을 통해 각 특정 serializer의 구현 작업에서 저장소 매체의 세부 정보를 격리하는 인터페이스를 정의합니다.  .NET Framework 저장소 세부 정보를 캡슐화 이점 외에도 <xref:System.Windows.Documents.Serialization> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 다른 몇 가지 중요 한 기능을 제공 합니다.  
  
### <a name="features-of-net-framework-30-document-serializers"></a>.NET Framework 3.0 문서 Serializer의 기능  
  
-   전반적인 문서 개체(논리적 트리 및 시각적 개체)에 직접 액세스하면 페이지를 매긴 콘텐츠, 2D/3D 요소, 이미지, 매체, 하이퍼링크, 주석 및 기타 지원 콘텐츠를 효율적으로 저장할 수 있습니다.  
  
-   동기 및 비동기 작업.  
  
-   다음과 같은 고급 기능이 포함된 플러그 인 serializer 지원:  
  
    -   모든.NET Framework 응용 프로그램에서 사용 하기 위해 시스템 차원의 액세스 합니다.  
  
    -   간단한 응용 프로그램 플러그 인 검색 기능.  
  
    -   사용자 지정 타사 플러그 인의 간단한 배포, 설치 및 업데이트.  
  
    -   사용자 지정 런타임 설정 및 옵션에 맞는 사용자 인터페이스 지원.  
  
### <a name="xps-print-path"></a>XPS 인쇄 경로  
 Microsoft.NET Framework [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 인쇄 경로 인쇄 출력을 통해 문서를 작성 하기 위한 확장 가능한 메커니즘을 제공 합니다.  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]는 문서 파일 형식으로 사용되며 [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)]의 기본 인쇄 스풀 형식이기도 합니다.  중간 형식으로 변환하지 않아도 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 문서를 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 호환 프린터로 직접 보낼 수 있습니다.  인쇄 경로 출력 옵션과 기능에 대한 추가 정보는 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)를 참조하세요.  
  
<a name="PluginSerializers"></a>   
## <a name="plug-in-serializers"></a>플러그 인 Serializer  
 <xref:System.Windows.Documents.Serialization> Api 플러그 인 직렬 변환기와 응용 프로그램에서 개별적으로 설치 되어 있는 연결 된 직렬 변환기에 대 한 지원을 제공, 실행된 시에 및를 사용 하 여 액세스 되는 <xref:System.Windows.Documents.Serialization.SerializerProvider> 검색 메커니즘입니다.  플러그 인 serializer는 쉽게 배포하여 시스템 전체에서 사용할 수 있는 향상된 이점을 제공합니다.  플러그 인 serializer에 액세스할 수 없는 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 등의 부분 신뢰 환경용으로도 연결된 serializer를 구현할 수 있습니다.  연결 된 파생된 구현의 기반으로 하는 serializer는 <xref:System.Windows.Documents.Serialization.SerializerWriter> 클래스, 컴파일 및 응용 프로그램에 직접 연결 합니다.  플러그 인 serializer와 연결된 serializer는 모두 동일한 공용 메서드와 이벤트를 통해 작동하므로 동일한 응용 프로그램에서 두 serializer 유형 중 하나 또는 둘 다를 쉽게 사용할 수 있습니다.  
  
 플러그 인 serializer는 빌드 시 가능한 모든 형식에 맞게 직접 코딩할 필요가 없는 확장된 새로운 저장소 디자인과 파일 형식을 제공하여 응용 프로그램 개발자를 지원합니다.  플러그 인 serializer는 사용자 지정 또는 독점 파일 형식에 맞게 시스템에서 액세스 가능한 플러그 인을 배포, 설치 및 업데이트하는 표준화된 방식을 제공하여 타사 개발자에게도 이점을 제공합니다.  
  
### <a name="using-a-plug-in-serializer"></a>플러그 인 Serializer 사용  
 플러그 인 serializer는 사용하기가 쉽습니다.  <xref:System.Windows.Documents.Serialization.SerializerProvider> 클래스 열거는 <xref:System.Windows.Documents.Serialization.SerializerDescriptor> 시스템에 각 플러그 인 설치에 대 한 개체입니다.  <xref:System.Windows.Documents.Serialization.SerializerDescriptor.IsLoadable%2A> 속성 현재 구성에 따라 설치 된 플러그 인을 필터링 하 고 serializer를 로드 및 응용 프로그램에서 사용할 수 있는지 확인 합니다.  <xref:System.Windows.Documents.Serialization.SerializerDescriptor> 와 같은 다른 속성도 제공 <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DisplayName%2A> 및 <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DefaultFileExtension%2A>, 응용 프로그램 사용자는 사용 가능한 출력 형식에 대 한 직렬 변환기를 선택 하 라는 메시지 표시 하는 데 사용할 수 있습니다.  에 대 한 기본 플러그 인 직렬 변환기 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] .NET Framework와 함께 제공 되 고 항상 열거 됩니다.  출력 형식으로 선택한 후는 <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> 메서드 만드는 데 사용 되는 <xref:System.Windows.Documents.Serialization.SerializerWriter> 특정 형식에 대 한 합니다.  <xref:System.Windows.Documents.Serialization.SerializerWriter>.<xref:System.Windows.Documents.Serialization.SerializerWriter.Write%2A> 데이터 저장소에 문서 스트림을 출력 하 메서드를 호출할 수 있습니다.  
  
 다음 예제에서는 응용 프로그램을 사용 하는 <xref:System.Windows.Documents.Serialization.SerializerProvider> "PlugInFileFilter" 속성에는 메서드.  PlugInFileFilter 설치 된 플러그 인을 열거 하 고 사용 가능한 파일 옵션에 대 한 필터 문자열을 작성 한 <xref:Microsoft.Win32.SaveFileDialog>합니다.  
  
 [!code-csharp[DocumentSerialize#DocSerializeFileFilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializefilefilter)]  
  
 다음 예제에서는 사용 하 여 출력 파일 이름을 선택한 후에 사용자가을 <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> 메서드를 지정된 된 형식에 지정된 된 문서를 저장 합니다.  
  
 [!code-csharp[DocumentSerialize#DocSerializePlugIn](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializeplugin)]  
  
<a name="InstallingPluginSerializers"></a>   
### <a name="installing-plug-in-serializers"></a>플러그 인 Serializer 설치  
 <xref:System.Windows.Documents.Serialization.SerializerProvider> 클래스 플러그 인 직렬 변환기 검색 및 액세스에 대 한 상위 수준 응용 프로그램 인터페이스를 제공 합니다.  <xref:System.Windows.Documents.Serialization.SerializerProvider> 찾아서 응용 프로그램이 설치 되 고 시스템에 액세스할 수 있는 serializer의 목록을 제공 합니다.  설치된 serializer의 구체적인 내용은 레지스트리 설정을 통해 정의됩니다.  사용 하 여 플러그 인 직렬 변환기를 레지스트리에 추가할 수 있습니다는 <xref:System.Windows.Documents.Serialization.SerializerProvider.RegisterSerializer%2A> 메서드가 또는 레지스트리 값 자체.NET Framework가 아직 설치 된 플러그 인 설치 스크립트 직접 설정할 수 있습니다.  <xref:System.Windows.Documents.Serialization.SerializerProvider.UnregisterSerializer%2A> 메서드 제거 이전에 설치 된 데 사용할 수 있습니다 플러그 인을 사용 하거나 레지스트리 설정을 제거 스크립트에 의해 마찬가지로 재설정할 수 있습니다.  
  
### <a name="creating-a-plug-in-serializer"></a>플러그 인 Serializer 만들기  
 플러그 인 serializer와 연결 serializer는 모두 노출된 동일한 공용 메서드와 이벤트를 사용하며, 동기식 또는 비동기식으로 작동하도록 비슷하게 설계될 수 있습니다.  일반적으로 플러그 인 serializer를 만들기 위해 수행하는 기본 단계는 다음 세 가지입니다.  
  
1.  먼저 serializer를 연결 serializer로 구현하고 디버깅합니다.  처음에 테스트 응용 프로그램에서 직접 컴파일 및 연결된 serializer를 만들면 테스트에 유용한 중단점 및 기타 디버그 서비스에 완벽하게 액세스할 수 있습니다.  
  
2.  Serializer가 완전히 테스트 후는 <xref:System.Windows.Documents.Serialization.ISerializerFactory> 인터페이스 플러그 인을 만들어에 추가 됩니다.  <xref:System.Windows.Documents.Serialization.ISerializerFactory> 논리 트리를 포함 하는 모든.NET Framework 개체에 전체 액세스를 허용 하는 인터페이스 <xref:System.Windows.UIElement> 개체 <xref:System.Windows.Documents.IDocumentPaginatorSource>, 및 <xref:System.Windows.Media.Visual> 요소입니다.  또한 <xref:System.Windows.Documents.Serialization.ISerializerFactory> 동일한 동기 및 비동기 메서드 및 연결 된 serializer 사용 되는 이벤트를 제공 합니다.  큰 문서는 출력하는 데 시간이 걸리므로, 비동기 작업을 통해 반응이 빠른 사용자 조작을 유지 관리하고 데이터 저장소에 문제가 발생하면 “취소” 옵션을 제공하는 것이 좋습니다.  
  
3.  플러그 인 serializer가 만들어지면 플러그 인을 배포하고 설치(및 제거)하기 위한 설치 스크립트가 구현됩니다(위의 “[플러그 인 Serializer 설치](#InstallingPluginSerializers)” 참조).  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Documents.Serialization>  
 <xref:System.Windows.Xps.XpsDocumentWriter>  
 <xref:System.Windows.Xps.Packaging.XpsDocument>  
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [XPS(XML Paper Specification): 개요](http://go.microsoft.com/fwlink?LinkID=106246)
