---
title: "병합된 리소스 사전"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- merged resource dictionaries [WPF]
- dictionaries [WPF], merged resources
ms.assetid: d159531f-05d4-49fd-b951-c332de51e5bc
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6cbea4316db159582790f371844f6e65fc22fd5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="merged-resource-dictionaries"></a>병합된 리소스 사전
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 리소스에서는 병합된 리소스 사전 기능을 지원합니다. 이 기능을 사용하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램의 리소스 부분을 컴파일된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 응용 프로그램 외부에서 정의할 수 있습니다. 그런 다음 리소스를 응용 프로그램 간에 공유하고 지역화를 위해 더욱 간편하게 격리할 수도 있습니다.  
  
## <a name="introducing-a-merged-resource-dictionary"></a>병합된 리소스 사전 도입  
 태그에서 다음 구문을 사용하여 병합된 리소스 사전을 페이지에 도입할 수 있습니다.  
  
 [!code-xaml[ResourceMergeDictionary#MergedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourceMergeDictionary/CS/default.xaml#mergedxaml)]  
  
 <xref:System.Windows.ResourceDictionary> 요소가 없는 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md), 리소스 컬렉션에 있는 모든 항목에 대 한 일반적으로 필요 합니다. 하지만 다른 <xref:System.Windows.ResourceDictionary> 내의 참조는 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 컬렉션은이 병합 된 리소스 사전 시나리오에 대 한 예약 하는 특별 한 경우. <xref:System.Windows.ResourceDictionary> 제공 하는 병합 된 리소스 사전을 사용할 수 없습니다는 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md)합니다. 일반적으로 각 <xref:System.Windows.ResourceDictionary> 내에서 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 컬렉션 지정는 <xref:System.Windows.ResourceDictionary.Source%2A> 특성입니다. 값 <xref:System.Windows.ResourceDictionary.Source%2A> 이어야 합니다는 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 병합할 리소스 파일의 위치를 확인 하는 합니다. 목적지에 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 다른 해야 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을와 <xref:System.Windows.ResourceDictionary> 루트 요소로 서입니다.  
  
> [!NOTE]
>  내에서 리소스를 정의 하는 한 <xref:System.Windows.ResourceDictionary> 지정 하는 대신으로 병합된 된 사전으로 지정 된 <xref:System.Windows.ResourceDictionary.Source%2A>, 또는 지정된 된 소스에서 포함 된 리소스에 추가 합니다. 그러나 이는 일반적인 시나리오가 아닙니다. 병합된 사전의 기본 시나리오는 외부 파일 위치에서 리소스를 병합하는 것입니다. 페이지에 대 한 태그 내에서 리소스를 지정 하려는 경우 일반적으로 정의 해야 주에 이러한 <xref:System.Windows.ResourceDictionary> 및 병합된 된 사전에 없는 합니다.  
  
## <a name="merged-dictionary-behavior"></a>병합된 사전 동작  
 병합된 사전의 리소스는 리소스 조회 범위에서 이 사전이 병합된 주 리소스 사전의 범위 바로 뒤에 있는 위치에 있습니다. 개별 사전 내에서는 리소스 키가 고유해야 하지만 하나의 키가 병합된 사전 집합 내에서 여러 번 나올 수 있습니다. 이 경우 반환 되는 리소스에서 순차적으로 찾은 마지막 사전에서 가져옵니다는 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 컬렉션입니다. 경우는 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 컬렉션에 정의 된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 태그에 제공 된 컬렉션의 병합된 된 사전 순서는 요소의 순서입니다. 키를 기본 사전에서 정의하고 병합된 사전에서도 정의하는 경우 반환되는 리소스는 기본 사전에서 가져옵니다. 이러한 범위 지정 규칙은 정적 리소스 참조와 동적 리소스 참조 모두에 동일하게 적용됩니다.  
  
### <a name="merged-dictionaries-and-code"></a>병합된 사전 및 코드  
 병합된 사전을 코드를 통해 `Resources` 사전에 추가할 수 있습니다. 기본적으로 처음에 비어 <xref:System.Windows.ResourceDictionary> 에 대해 존재 하는 `Resources` 속성에는 기본적으로 처음에 비어도 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 컬렉션 속성입니다. 코드를 통해 병합 된 사전에 추가 하려면 원하는 주 복제본에 대 한 참조를 가져올 <xref:System.Windows.ResourceDictionary>, 가져오기의 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 속성 값 및 호출 `Add` 제네릭에 대 `Collection` 에 포함 되어 있는 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>합니다. 추가 하는 개체는 새 해야 <xref:System.Windows.ResourceDictionary>합니다. 코드에서 설정 하지 않으면는 <xref:System.Windows.ResourceDictionary.Source%2A> 속성입니다. 대신, 가져와야는 <xref:System.Windows.ResourceDictionary> 하나를 생성 하거나 하나를 로드 하 여 개체입니다. 기존 로드 하는 한 가지 방법은 <xref:System.Windows.ResourceDictionary> 를 호출할 <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> 기존 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일 스트림에서 <xref:System.Windows.ResourceDictionary> 캐스팅 한 다음 루트는 <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> 값을 반환을 <xref:System.Windows.ResourceDictionary>합니다.  
  
### <a name="merged-resource-dictionary-uris"></a>병합된 리소스 사전 URI  
 사용할 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 형식으로 표시된 병합된 리소스 사전을 포함하기 위한 몇 가지 기술이 있습니다. 대체로 이러한 기술은 프로젝트의 일부로 컴파일된 리소스와 프로젝트의 일부로 컴파일되지 않은 리소스의 두 가지 범주로 나눌 수 있습니다.  
  
 프로젝트의 일부로 컴파일된 리소스의 경우 리소스 위치를 참조하는 상대 경로를 사용할 수 있습니다. 상대 경로는 컴파일하는 동안 평가됩니다. 리소스 빌드 작업을 통해 리소스를 프로젝트의 일부로 정의해야 합니다. 리소스 .xaml 파일을 프로젝트에 리소스로 포함하는 경우 리소스 파일을 출력 디렉터리로 복사할 필요가 없습니다. 리소스가 컴파일된 응용 프로그램 내에 이미 포함되어 있습니다. 또한 콘텐츠 빌드 작업을 사용할 수도 있지만 이 경우 파일을 출력 디렉터리에 복사하는 것뿐만 아니라 실행 파일과의 동일한 경로 관계에 리소스 파일을 배포해야 합니다.  
  
> [!NOTE]
>  포함 리소스 빌드 작업은 사용하지 않습니다. 빌드 작업 자체에 대해 사용할 수 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램, 하지만의 해상도 <xref:System.Windows.ResourceDictionary.Source%2A> 통합 하지 <xref:System.Resources.ResourceManager>, 고 따라서를 스트림에서 개별 리소스를 분리할 수 없습니다. 다른 용도로 사용에 대 한 포함 리소스는 계속 사용할 수 <xref:System.Resources.ResourceManager> 리소스에 액세스할 수 있습니다.  
  
 관련 기술로는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에 대한 Pack URI를 소스로 참조하는 방법이 있습니다. Pack URI를 사용하면 참조된 어셈블리 및 다른 기술의 구성 요소를 참조할 수 있습니다. Pack URI에 대한 자세한 내용은 [WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)을 참조하세요.  
  
 프로젝트의 일부로 컴파일되지 않는 리소스의 경우 URI가 런타임에 평가됩니다. file: 또는 http:와 같은 일반 URI 전송을 사용하여 리소스 파일을 참조할 수 있습니다. 컴파일되지 않은 리소스 방법을 사용하는 경우 file: 액세스에 추가 배포 단계가 필요하고 http: 액세스에 인터넷 보안 영역이 수반된다는 단점이 있습니다.  
  
### <a name="reusing-merged-dictionaries"></a>병합된 사전 다시 사용  
 병합할 리소스 사전을 유효한 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]를 통해 참조할 수 있으므로 병합된 리소스 사전을 여러 응용 프로그램에서 공유하거나 다시 사용할 수 있습니다. 이렇게 하는 정확한 방법은 응용 프로그램 배포 전략이나 사용하는 응용 프로그램 모델에 따라 달라집니다. 앞서 설명한 Pack URI 전략에서는 배포하는 동안 어셈블리 참조를 공유하여 여러 프로젝트에서 병합된 리소스를 공통 소스로 지정할 수 있습니다. 이 시나리오에서는 리소스가 계속 클라이언트별로 배포되며 하나 이상의 응용 프로그램에서 참조된 어셈블리를 배포해야 합니다. 또한 http 프로토콜을 사용하는 배포된 URI를 통해 병합된 리소스를 참조할 수도 있습니다.  
  
 병합된 사전을 로컬 응용 프로그램 파일로 작성하거나 로컬 공유 저장소에 기록하는 것도 병합된 사전/응용 프로그램 배포의 사용 가능한 시나리오입니다.  
  
### <a name="localization"></a>지역화  
 지역화해야 하는 리소스를 기본 사전에 병합된 사전으로 격리하고 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 사용 완화로 보관하는 경우 이러한 파일을 별도로 지역화할 수 있습니다. 이 기술은 위성 리소스 어셈블리를 지역화하는 것에 비해 간단합니다. 자세한 내용은 [WPF 세계화 및 지역화 개요](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.ResourceDictionary>  
 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [리소스 및 코드](../../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)
