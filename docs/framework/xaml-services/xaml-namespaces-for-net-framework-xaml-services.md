---
title: ".NET Framework XAML 서비스의 XAML 네임스페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
caps.latest.revision: "3"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: e09279209bf3d6925b61d55d6988b5af658f5aab
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="xaml-namespaces-for-net-framework-xaml-services"></a>.NET Framework XAML 서비스의 XAML 네임스페이스
XAML 네임 스페이스는 XML 네임 스페이스 정의 확장 하는 개념입니다. XML 네임 스페이스와 마찬가지로, 정의한 사용 하 여 XAML 네임 스페이스는 `xmlns` 태그에서 특성입니다. XAML 네임 스페이스는 XAML 노드 스트림 및 다른 XAML 서비스 Api에도 표시 합니다. 이 항목 XAML 네임 스페이스 개념을 정의 하 고 XAML 네임 스페이스를 정의할 수 있습니다 및 XAML 스키마 컨텍스트 및.NET Framework XAML 서비스의 다른 측면에서 사용 방법에 대해 설명 합니다.  
  
## <a name="xml-namespace-and-xaml-namespace"></a>XML Namespace 및 XAML Namespace  
 XAML 네임 스페이스와 마찬가지로 XAML은 특수 한 형태의 XML 태그에 대 한 기본 XML 형식을 사용 하 여 특수 한 XML 네임 스페이스는 합니다. XAML 네임 스페이스와 해당 매핑을 통해 선언 태그에서는 `xmlns` 특성이 요소에 적용 합니다. `xmlns` 선언을 XAML 네임 스페이스에 선언 된 동일한 요소를 만들 수 있습니다. 프로그램 요소에 대 한 XAML 네임 스페이스 선언은 해당 요소, 해당 요소의 모든 특성 및 해당 요소의 모든 자식에 대 한 유효 합니다. 특성 하지 않은 특성을 포함 하는 요소와 같은 태그에 특성 이름의 일부로 접두사를 참조 하는 자체 특성 이름으로 XAML 네임 스페이스를 사용할 수 있습니다.  
  
 XAML 네임 스페이스는 XML 네임 스페이스와의 차이는 XML 네임 스페이스 스키마를 참조 하는 데 사용 될 수 있습니다 또는 단순히 엔터티를 구별 하는 데 사용 될 수 있습니다는 합니다. Xaml의 경우 형식 및 멤버 XAML에서 사용 되는 궁극적으로 확인 되어야 합니다 지원 형식, 및 XML 스키마 개념이이 기능에도 적용 되지 않습니다. XAML 네임 스페이스는 XAML 스키마 컨텍스트를이 형식 매핑을 수행 하기 위해 사용할 수 있어야 한다는 정보를 포함 합니다.  
  
## <a name="xaml-namespace-components"></a>XAML Namespace 구성 요소  
 XAML 네임 스페이스 정의 두 구성 요소: 접두사 및 식별자입니다. 이러한 각 구성이 요소는 XAML 네임 스페이스 태그에서 선언 하거나 XAML 형식 시스템에 정의 된 변수가.입니다.  
  
 접두사 모든 문자열일 수에서 허용 된 [XML 1.0 사양에 W3C 네임 스페이스](http://go.microsoft.com/fwlink/?LinkID=161735) 합니다. 규칙에 따라 접두사 되므로 일반적으로 매우 짧은 문자열 접두사 일반적인 태그 파일에 여러 번 반복 됩니다. 여러 XAML 구현에서 사용 하도록 설계 된 특정 XAML 네임 스페이스는 특정 접두사를 사용 합니다. 예를 들어 XAML 언어 XAML 네임 스페이스는 일반적으로 매핑된 접두사를 사용 하 여 `x`합니다. 기본 XAML 네임 여기서 정의에 제공 되지 않습니다 되지만 정의 Framework XAML 서비스 API 경우 빈 문자열로 표현 접두사를 정의할 수 있습니다. 기본 XAML 네임 스페이스 접두사를 생략의 최대 양을 수준을 올리려면 의도적으로 선택 됩니다는 일반적으로 XAML 구현 하는 기술 시나리오 및 어휘를 여는 태그입니다.  
  
 식별자에서 허용 하는 대로 모든 문자열이 될 수는 [XML 1.0 사양에 W3C 네임 스페이스](http://go.microsoft.com/fwlink/?LinkID=161735)합니다. 규칙에 따라 XML 네임 스페이스 또는 XAML 네임 스페이스에 대 한 식별자는 종종 지정 URI 형식에 일반적으로 정규화 된 프로토콜 절대 URI로 합니다. 대개 특정 XAML 어휘를 정의 하는 버전 정보에 경로 문자열의 일부로 포함 됩니다. XAML 네임 스페이스는 XML URI 규칙 초과 하는 추가 식별자 규칙을 추가합니다. XAML 네임 스페이스에 대 한 식별자는 해당 XAML 네임 스페이스에서 요소로 지정 된 형식을 확인 하기 위해 또는 멤버에 특성을 해결 하려면 XAML 스키마 컨텍스트는 필요한 정보를 전달 합니다.  
  
 통신 XAML 스키마 컨텍스트를 정보를 위해 XAML 네임 스페이스에 대 한 식별자 URI 형식에서 중일 수 있습니다. 그러나이 경우 URI로 선언 된 특정 어셈블리 또는 어셈블리의 목록에서 일치 하는 식별자입니다. 사용 하 여 어셈블리 특성을 사용한 어셈블리에 이렇게 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>합니다. XAML 네임 스페이스를 식별 하 고 특성 사용된 어셈블리의 CLR 기반 형식 확인 동작을 지 원하는이 메서드는.NET Framework XAML 서비스의 기본 XAML 스키마 컨텍스트에서 지원 됩니다. 보다 일반적으로 XAML 스키마 컨텍스트 CLR을 통합 하거나 CLR 어셈블리에서 CLR 특성을 읽을 하기 위해 필요한 기본 XAML 스키마 컨텍스트를 기반으로 하는 있는 경우에 대 한이 규칙을 사용할 수 있습니다.  
  
 또한 XAML 네임 스페이스는 CLR 네임 스페이스 및 형식 정의 어셈블리를 전달 하는 규칙으로 식별할 수 있습니다. 이 규칙은 없는 경우에 사용 됩니다 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> attribution 형식이 포함 된 어셈블리에 있습니다. 이 규칙은 잠재적으로 URI 규칙 보다 더 복잡 되며 수도 있는 모호성 및 복제에 대 한 여러 가지 방법으로 어셈블리에 참조 하기 때문에 있습니다.  
  
 CLR 네임 스페이스 및 어셈블리 규칙을 사용 하는 식별자의 가장 기본적인 형태는 다음과 같습니다.  
  
 `clr-namespace:`*clrnsName* `; assembly=` *assemblyShortName*  
  
 `clr-namespace:`및 `; assembly=` 리터럴 구문을 구성 합니다.  
  
 *clrnsName* CLR 네임 스페이스를 식별 하는 문자열 이름입니다. 이 문자열 이름에는 CLR 네임 스페이스와 다른 CLR 네임 스페이스의 관계에 대 한 힌트를 제공 하는 내부 점 문자 (.) 포함 되어 있습니다.  
  
 *assemblyShortName* XAML에서 사용 되는 형식을 정의 하는 어셈블리의 문자열 이름입니다. 어셈블리에서 정의 하 고 명시적으로 지정 된 CLR 네임 스페이스 내에서 선언 형식에 선언 된 XAML 네임 스페이스를 통해 액세스할 수 예상 *clrnsName*합니다. 이 문자열 이름 정보를 보고 일반적으로 기능과 유사한 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>합니다.  
  
 CLR 네임 스페이스 및 어셈블리 규칙 보다 완전 한 정의 다음과 같습니다.  
  
 `clr-namespace:`*clrnsName* `; assembly=` *assemblyName*  
  
 *assemblyName* 으로 유효한 모든 문자열을 나타내는 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 입력 합니다. 이 문자열은 문화권, 공개 키 또는 버전 정보가 포함 될 수 있습니다 (이러한 개념의 정의 대 한 참조 항목에 정의 된 <xref:System.Reflection.Assembly>). COFF 형식 및 증명 정보 (의 다른 오버 로드에서 사용 되는 <xref:System.Reflection.Assembly.Load%2A>) XAML 어셈블리 로드 목적과;에 대 한 관련 되지 않은 모든 정보를 로드할 string으로 표시 되어야 합니다.  
  
 어셈블리에 대 한 공개 키를 지정 하는 단순한 이름에서 로드 되는 어셈블리나 캐시 또는 응용 프로그램 도메인에 미리 존재 하는 경우 있을 수 있는 모호성을 제거 하거나 XAML 보안에 대 한 유용한 기술. 자세한 내용은 참조 [XAML 보안 고려 사항](../../../docs/framework/xaml-services/xaml-security-considerations.md)합니다.  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>XAML 서비스 API의에서 XAML Namespace 선언  
 XAML 서비스 API에서 XAML 네임 스페이스 선언으로 표시 됩니다는 <xref:System.Xaml.NamespaceDeclaration> 개체입니다. 호출 코드의 XAML 네임 스페이스를 선언 하는 경우는 <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29> 생성자입니다. `ns` 및 `prefix` 문자열로 매개 변수를 지정 하 고이 항목의 앞부분에서 설명한 대로 이러한 매개 변수에 대해 제공 하는 입력 XAML 네임 스페이스 식별자 및 XAML 네임 스페이스 접두사의 정의에 해당 합니다.  
  
 일부로 XAML 형식 시스템에 대 한 다른 액세스를 통해 또는 XAML 노드 스트림의 XAML 네임 스페이스 정보를 검사 하는 경우 <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType> XAML 네임 스페이스 식별자를 보고 하 고 <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType> XAML 네임 스페이스 접두사를 보고 합니다.  
  
 XAML 노드 스트림의 XAML 네임 스페이스 정보를 적용할 엔터티를 앞에 있는 XAML 노드 나타날 수 있습니다. 여기에 XAML 네임 스페이스 정보 보다 우선 하는 경우는 `StartObject` XAML 루트 요소입니다. 자세한 내용은 [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)을 참조하십시오.  
  
 .NET Framework XAML 서비스 API를 사용 하는 많은 시나리오에 대 한 XAML 네임 스페이스 선언은 적어도 하나는 존재 해야 하 고 선언을 포함 하거나 XAML 스키마 컨텍스트에 필요한 정보를 참조 해야 합니다. XAML 네임 스페이스, 네임 스페이스 및 어셈블리를 이미 로드 되거나에서 XAML 스키마 컨텍스트 내에서 특정 형식을 확인 하는 데 도움이 또는 어셈블리를 지정 합니다.  
  
 XAML 노드 스트림을 생성 하려면 XAML 형식 정보는 XAML 스키마 컨텍스트를 통해 사용할 수 있어야 합니다. 만들려는 각 노드에 대 한 관련 XAML 네임 스페이스를 먼저 확인 하지 않고 XAML 형식 정보를 확인할 수 없습니다. 이 시점에서 형식 인스턴스는 아직 만들어지지 있지만 XAML 스키마 컨텍스트는 어셈블리를 정의 하 고 지원 형식에서 정보를 검색 해야 할 수 있습니다. 예: 태그를 처리 하기 위해 `<Party><PartyFavor/></Party>`, XAML 스키마 컨텍스트 이름 및 유형을 확인할 수 있어야는 `ContentProperty` 의 `Party`, 따라서도 알고 있어야에 대 한 XAML 네임 스페이스 정보 및 `Party` 및 `PartyFavor`합니다. 기본 XAML 스키마 컨텍스트의 경우 정적 리플렉션을 많은 노드 스트림의 XAML 형식 노드를 생성 하는 데 필요한 XAML 형식 시스템 정보를 보고 합니다.  
  
 XAML 노드 스트림에서 개체 그래프를 생성 하기 위해 XAML 네임 스페이스 선언을 원래 태그에서 사용 하 고 XAML 노드 스트림에 기록 된 각 XAML 접두사에 대 한 존재 해야 합니다. 이 시점에서 인스턴스 생성 되는지 및 true 형식 매핑 문제가 발생 합니다.  
  
 XML 네임 스페이스 선언에서 선언 하는 태그에 사용 하려면 XAML 스키마 컨텍스트를 만들려는 경우 XAML 네임 스페이스를 정의 되지 않은 경우에 XAML 네임 스페이스 정보를 채우는 데 필요한 경우 사용할 수 있습니다 기술이 고 <xref:System.Xml.XmlParserContext> 는 에대한<xref:System.Xml.XmlReader>. 사용 하 여 <xref:System.Xml.XmlReader> XAML 판독기 생성자에 대 한 입력으로 또는 <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType>합니다.  
  
 특성에는.NET Framework XAML 서비스에서 처리 하는 XAML 네임 스페이스와 관련 된 다른 두 개의 API <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 및 <xref:System.Windows.Markup.XmlnsPrefixAttribute>합니다. 이러한 특성은 어셈블리에 적용 됩니다. <xref:System.Windows.Markup.XmlnsDefinitionAttribute>URI를 포함 하는 XAML 네임 스페이스 선언을 해석 하는 XAML 스키마 컨텍스트에서 사용 됩니다. <xref:System.Windows.Markup.XmlnsPrefixAttribute>예측 가능한 접두사가 포함 된 특정 XAML 네임 스페이스를 serialize 할 수 있도록 XAML을 생성 하는 도구에서 사용 됩니다. 자세한 내용은 참조 [사용자 정의 형식 및 라이브러리에 대 한 CLR 특성 XAML-Related](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XAML 노드 스트림 구조 및 개념 이해](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)
