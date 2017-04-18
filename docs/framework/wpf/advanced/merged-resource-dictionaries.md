---
title: "병합된 리소스 사전 | Microsoft Docs"
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
  - "병합된 리소스 사전"
  - "병합 된 리소스 사전"
ms.assetid: d159531f-05d4-49fd-b951-c332de51e5bc
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 병합된 리소스 사전
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]리소스에서 병합 된 리소스 사전 기능을 지원 합니다. 이 기능은의 resource 부분을 정의 하는 방법을 제공는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컴파일된 모듈 외부에서 응용 프로그램 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 응용 프로그램입니다. 응용 프로그램에서 다음 리소스를 공유할 수 고도 더 편리 하 게 격리 되어 지역화를 위해.  
  
## <a name="introducing-a-merged-resource-dictionary"></a>병합된 된 리소스 사전 소개  
 태그에서 병합된 된 리소스 사전 페이지에 소개 하는 다음 구문을 사용:  
  
 [!code-xml[ResourceMergeDictionary#MergedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourceMergeDictionary/CS/default.xaml#mergedxaml)]  
  
 <xref:System.Windows.ResourceDictionary> 요소가 없는 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md), 리소스 컬렉션의 모든 항목에 대해 일반적으로 필요한 합니다. 하지만 다른 <xref:System.Windows.ResourceDictionary> 내의 참조는 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 컬렉션은이 병합 된 리소스 사전 시나리오에 대 한 예약 하는 특별 한 경우. <xref:System.Windows.ResourceDictionary> 제공 하는 병합 된 리소스 사전에서 사용할 수 없습니다는 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md)합니다. 일반적으로 각 <xref:System.Windows.ResourceDictionary> 내는 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 컬렉션 지정는 <xref:System.Windows.ResourceDictionary.Source%2A> 특성입니다. 값 <xref:System.Windows.ResourceDictionary.Source%2A> 있어야는 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 병합 될 리소스 파일의 위치를 확인 하는 합니다. 목적지에 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 다른 해야 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일인와 <xref:System.Windows.ResourceDictionary> 루트 요소로 합니다.  
  
> [!NOTE]
>  내에서 리소스를 정의 하는 것이 한 <xref:System.Windows.ResourceDictionary> 를 지정 하는 대신 병합된 된 사전으로 지정 된 <xref:System.Windows.ResourceDictionary.Source%2A>, 또는 지정된 된 소스에서 포함 된 리소스에 추가 합니다. 그러나 이것이 일반적인 시나리오입니다. 병합 된 사전에 대 한 주요 시나리오 외부 파일 위치에서 리소스를 병합 하는 것입니다. 페이지에 대 한 태그 내에서 리소스를 지정 하려는 경우 일반적으로 정의 해야 주에 이러한 <xref:System.Windows.ResourceDictionary> 및 병합된 된 사전에 없는 합니다.  
  
## <a name="merged-dictionary-behavior"></a>병합 된 사전 동작  
 병합 된 주 리소스 사전의 범위 바로 뒤에 리소스 조회 범위 내의 위치를 차지 하는 병합 된 사전에는 리소스입니다. 리소스 키 개별 사전 내에서 고유 해야 하지만 키를 여러 번 집합이 병합 된 사전에 존재할 수 있습니다. 이 경우 반환 되는 리소스에서 순차적으로 찾은 마지막 사전에서 가져옵니다는 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 컬렉션입니다. 하는 경우는 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 컬렉션에 정의 된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 컬렉션의 병합된 된 사전 순서 태그에 제공 된 그대로 요소의 순서입니다. 기본 사전 및 병합 된 사전에는 키가 정의 하는 경우 반환 되는 리소스는 기본 사전에서 가져옵니다. 이러한 범위 지정 규칙 동일 하 게 적용 정적 리소스 참조와 동적 리소스에 대 한 참조입니다.  
  
### <a name="merged-dictionaries-and-code"></a>병합 된 사전 및 코드  
 병합 된 사전에 추가할 수는 `Resources` 코드를 통해 사전입니다. 기본적으로 초기에 비어 있는 <xref:System.Windows.ResourceDictionary> 에 대해 존재 하는 `Resources` 속성에는 기본적으로 초기에 비어 있는 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 컬렉션 속성입니다. 코드를 통해 병합 된 사전에 추가 하려면 원하는 주 데이터베이스에 대 한 참조를 얻게 <xref:System.Windows.ResourceDictionary>, 가져오기의 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 속성 값과 통화 `Add` 제네릭에 대 `Collection` 에 포함 된 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>합니다. 추가 하는 개체는 새 해야 <xref:System.Windows.ResourceDictionary>합니다. 코드에서 설정 하지 않으면는 <xref:System.Windows.ResourceDictionary.Source%2A> 속성입니다. 대신, 받아야는 <xref:System.Windows.ResourceDictionary> 만들거나 하나를 로드 하 여 개체입니다. 기존 로드 하는 한 가지 방법은 <xref:System.Windows.ResourceDictionary> 호출할 <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=fullName> 기존 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일 스트림에서 <xref:System.Windows.ResourceDictionary> 캐스팅 한 다음 루트는 <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=fullName> 반환 값을 <xref:System.Windows.ResourceDictionary>.  
  
### <a name="merged-resource-dictionary-uris"></a>병합 된 리소스 사전 Uri  
 여러 가지 기법으로 나타내는 병합된 된 리소스 사전, 포함 하는 방법에 대 한는 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 형식으로 사용 합니다. 대체로 이러한 기법으로 나눌 수 있습니다 두 범주: 프로젝트의 일환으로 컴파일되는 리소스 및 리소스는 프로젝트의 일환으로 컴파일되지 않은 합니다.  
  
 프로젝트의 일환으로 컴파일되는 리소스를 리소스 위치를 참조 하는 상대 경로 사용할 수 있습니다. 상대 경로 컴파일 중에 평가 됩니다. 리소스를 리소스 빌드 작업으로 프로젝트의 일부로 정의 되어야 합니다. 리소스와 프로젝트에 리소스.xaml 파일을 포함 하는 경우 출력 디렉터리에 리소스 파일을 복사할 필요가 없습니다, 리소스 컴파일된 응용 프로그램 내에 포함 되어 있습니다. 콘텐츠 빌드 작업을 사용할 수도 있습니다 하지만 다음은 출력 디렉터리에 파일을 복사 하 고 실행 파일에 같은 경로 관계에 있는 리소스 파일을 배포할 수도 있습니다.  
  
> [!NOTE]
>  포함 리소스 빌드 작업을 사용 하지 마십시오. 빌드 작업 자체에 대 한 지원 되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 있지만의 해상도, <xref:System.Windows.ResourceDictionary.Source%2A> 통합 하지 <xref:System.Resources.ResourceManager>, 고 따라서 스트림에 개별 리소스를 분리할 수 없습니다. 다른 용도로 사용에 대 한 포함 리소스는 계속 사용할 수 <xref:System.Resources.ResourceManager> 리소스에 액세스할 수 있습니다.  
  
 관련 된 기술은 대 한 Pack URI를 사용 하는 것을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 열고 원본으로 참조 합니다. Pack URI는 참조 된 어셈블리 및 기타 기술에 구성 요소에 대 한 참조가 있습니다. Pack Uri에 대 한 자세한 내용은 참조 하십시오. [WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)합니다.  
  
 프로젝트의 일환으로 컴파일되지 않은 리소스에 대 한 URI는 런타임에 평가 됩니다. 파일 같은 일반적인 URI 전송에 사용할 수 있습니다: 또는 http: 리소스 파일을 참조 하도록 합니다. 컴파일되지 않은 리소스 방법의 단점은 해당 파일: 배포 단계를 추가 및 http 액세스 필요: 액세스는 인터넷 보안 영역을 의미 합니다.  
  
### <a name="reusing-merged-dictionaries"></a>병합 된 사전을 다시 사용  
 병합 하 고 리소스 사전을 통해 참조 될 수 있으므로 병합 된 리소스 사전 응용 프로그램 사이 공유 하거나 다시 사용할 수 있습니다 유효한 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]합니다. 어떤 응용 프로그램 모델 및 응용 프로그램 배포 전략에 따라 달라 집니다이 방법은 정확 하 게 수행 합니다. 앞에서 언급 한 Pack URI 전략은 일반적으로 원본 병합 된 리소스 여러 프로젝트에서 개발 하는 동안 어셈블리 참조를 공유 하는 방법을 제공 합니다. 이 시나리오에서는 리소스는 클라이언트에서 배포 여전히 및 응용 프로그램 중 하나 이상을 참조 된 어셈블리를 배포 해야 합니다. Http 프로토콜을 사용 하는 분산된 URI 통해 병합 된 리소스를 참조 하는 것도 가능 합니다.  
  
 로컬 응용 프로그램 파일 또는 로컬 공유 저장소에는 또 다른 가능한 병합 된 사전으로 병합 된 사전 작성 / 응용 프로그램 배포 시나리오입니다.  
  
### <a name="localization"></a>지역화  
 기본 사전에 병합 되어 느슨하게 유지 하는 사전 격리 하는 리소스 지역화 해야 하는 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 이러한 파일을 별도로 지역화할 수 있습니다. 이 방법은 경량 대체 항목인 위성 리소스 어셈블리를 지역화 합니다. 자세한 내용은 다음을 참조 하십시오. [WPF 전역화 및 지역화 개요](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.ResourceDictionary>   
 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [리소스 및 코드](../../../../docs/framework/wpf/advanced/resources-and-code.md)   
 [WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)