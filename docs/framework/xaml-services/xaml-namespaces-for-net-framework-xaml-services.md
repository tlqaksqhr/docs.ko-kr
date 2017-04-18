---
title: "XAML Namespaces for .NET Framework XAML Services | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
caps.latest.revision: 3
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 3
---
# XAML Namespaces for .NET Framework XAML Services
XAML 네임스페이스는 XML 네임스페이스의 정의를 확장한 개념입니다.  XML 네임스페이스와 마찬가지로 태그에서 `xmlns` 특성을 사용하여 XAML 네임스페이스를 정의할 수 있습니다.  XAML 네임스페이스는 XAML 노드 스트림과 기타 XAML 서비스 API에도 표시됩니다.  이 항목에서는 XAML 네임스페이스의 개념에 대해 설명하고, XAML 네임스페이스를 정의하는 방법과 XAML 스키마 컨텍스트와 .NET Framework XAML 서비스의 기타 요소에서 이를 사용하는 방법에 대해 설명합니다.  
  
## XML 네임스페이스와 XAML 네임스페이스  
 XAML이 XML의 특수화된 형식이고 태그에 기본 XML 형식을 사용하는 것처럼 XAML 네임스페이스는 특수화된 XML 네임스페이스입니다.  태그에서 요소에 적용되는 `xmlns` 특성을 통해 XAML 네임스페이스와 해당 매핑을 선언합니다.  XAML 네임스페이스가 선언된 요소와 동일한 요소에 `xmlns` 선언을 만들 수 있습니다.  요소에 만들어진 XAML 네임스페이스 선언은 해당 요소, 해당 요소의 모든 특성 및 해당 요소의 모든 자식 요소에 대해 유효합니다.  특성은 특성 이름 자체가 태그에서 특성 이름의 일부인 접두사를 참조하는 경우 특성을 포함하는 요소와 동일하지 않은 XAML 네임스페이스를 사용할 수 있습니다.  
  
 XAML 네임스페이스와 XML 네임스페이스의 차이점은 XML 네임스페이스의 경우 스키마를 참조하는 데 사용하거나 단순히 엔터티를 구별하는 데 사용할 수 있다는 점입니다.  XAML의 경우, XAML에서 사용되는 형식 및 멤버는 최종적으로는 지원 형식으로 확인되어야 하며, XML 스키마 개념이 이 기능에는 잘 적용되지 않습니다.  XAML 네임스페이스에는 이 형식 매핑을 수행하기 위해 XAML 스키마 컨텍스트에서 사용할 수 있어야 하는 정보가 포함되어 있습니다.  
  
## XAML 네임스페이스 구성 요소  
 XAML 네임스페이스 정의에는 접두사와 식별자라는 두 개의 구성 요소가 있습니다.  이러한 각 구성 요소는 XAML 네임스페이스가 태그에서 선언되거나 XAML 형식 시스템에서 정의될 때 나타납니다.  
  
 접두사는 [W3C Namespaces in XML 1.0 사양](http://go.microsoft.com/fwlink/?LinkID=161735)에 따라 허용되는 모든 문자열이 될 수 있습니다.  접두사는 일반적인 태그 파일에서 여러 번 반복되므로 규칙에 따라 접두사는 대개 매우 짧은 문자열입니다.  여러 XAML 구현에서 사용되는 일부 XAML 네임스페이스에서는 규칙에 맞는 특정 접두사를 사용합니다.  예를 들어 XAML 언어 XAML 네임스페이스는 대개 `x` 접두사를 사용하여 매핑됩니다.  기본 XAML 네임스페이스를 정의할 수 있습니다. 이때 접두사는 정의에서 지정되지 않지만 .NET Framework XAML 서비스 API에서 정의되거나 쿼리될 경우 빈 문자열로 나타납니다.  일반적으로 기본 XAML 네임스페이스는 XAML 구현 기술과 해당 시나리오 및 어휘에 따라 접두사를 생략하는 태그의 최대 양을 늘릴 수 있도록 신중하게 선택됩니다.  
  
 식별자는 [W3C Namespaces in XML 1.0 사양](http://go.microsoft.com/fwlink/?LinkID=161735)에 따라 허용되는 모든 문자열이 될 수 있습니다.  규칙에 따라 XML 네임스페이스 또는 XAML 네임스페이스의 식별자는 URI 형식\(대개 프로토콜로 정규화된 절대 URI\)으로 지정되는 경우가 많습니다.  특정 XAML 어휘를 정의하는 버전 정보가 경로 문자열의 일부로 포함되기도 합니다.  XAML 네임스페이스에서는 XML URI 규칙 외에도 추가 식별자 규칙이 적용됩니다.  XAML 네임스페이스의 경우 식별자는 XAML 스키마 컨텍스트에서 해당 XAML 네임스페이스 아래에 요소로 지정된 형식을 확인하거나 특성을 멤버로 확인하는 데 필요한 정보를 전달합니다.  
  
 XAML 스키마 컨텍스트에 정보를 전달하기 위해 XAML 네임스페이스의 식별자도 URI 형식을 사용합니다.  그러나 이 경우 URI는 특정 어셈블리 또는 어셈블리 목록에서 일치하는 식별자로 선언되기도 합니다.  이렇게 하려면 어셈블리에서 어셈블리 특성을 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>로 지정합니다.  특성을 사용하는 어셈블리에서 이와 같이 XAML 네임스페이스를 식별하고 CLR 기반 형식 확인 동작을 지원하는 방법은 .NET Framework XAML 서비스의 기본 XAML 스키마 컨텍스트에 의해 지원됩니다.  보다 일반적으로, 이 규칙은 XAML 스키마 컨텍스트가 CLR을 통합하거나 기본 XAML 스키마 컨텍스트를 기반으로 하는 경우에 사용할 수 있습니다. 이러한 경우는 CLR 어셈블리에서 CLR 특성을 읽기 위해 필요합니다.  
  
 XAML 네임스페이스는 CLR 네임스페이스와 형식 정의 어셈블리를 전달하는 규칙으로 식별될 수도 있습니다.  이 규칙은 형식을 포함하는 어셈블리에 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 특성이 없는 경우에 사용됩니다.  이 규칙은 URI 규칙보다 복잡할 수 있으며, 어셈블리를 참조하는 방법에는 여러 가지가 있기 때문에 모호성 또는 중복 문제가 발생할 수도 있습니다.  
  
 CLR 네임스페이스 및 어셈블리 규칙을 사용하는 가장 기본적인 식별자 형식은 다음과 같습니다.  
  
 `clr-namespace:` *clrnsName* `; assembly=` *assemblyShortName*  
  
 `clr-namespace:`와 `; assembly=`은 구문의 리터럴 구성 요소입니다.  
  
 *clrnsName*은 CLRL 네임스페이스를 식별하는 문자열 이름입니다.  이 문자열 이름에는 CLR 네임스페이스 및 해당 네임스페이스와 다른 CLR 네임스페이스의 관계에 대한 힌트를 제공하는 내부 점 문자\(.\)가 포함될 수 있습니다.  
  
 *assemblyShortName*은 XAML에서 유용한 형식을 정의하는 어셈블리의 문자열 이름입니다.  선언된 XAML 네임스페이스를 통해 액세스되는 형식은 어셈블리에서 정의되고 *clrnsName*로 지정된 CLR 네임스페이스 내에서 명시적으로 선언되어야 합니다.  이 문자열 이름은 일반적으로 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=fullName>으로 보고되는 정보와 유사합니다.  
  
 CLR 네임스페이스 및 어셈블리 규칙에 대한 보다 완전한 정의는 다음과 같습니다.  
  
 `clr-namespace:` *clrnsName* `; assembly=` *assemblyName*  
  
 *assemblyName*은 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName> 입력으로 사용할 수 있는 모든 문자열을 나타냅니다.  이 문자열에는 문화권, 공개 키 또는 버전 정보가 포함될 수 있습니다\(이러한 개념에 대한 정의는 <xref:System.Reflection.Assembly>에 대한 참조 항목에 정의되어 있음\).  <xref:System.Reflection.Assembly.Load%2A>의 다른 오버로드에서 사용되는 COFF 형식 및 증명 정보는 XAML 어셈블리 로드 목적과는 관련이 없습니다. 모든 로드 정보는 문자열로 나타내야 합니다.  
  
 어셈블리의 공개 키를 지정하는 것은 XAML 보안 차원에서, 또는 어셈블리를 단순한 이름으로 로드할 경우에 발생할 수 있는 모호성이나 캐시 또는 응용 프로그램 도메인의 기존 모호성을 제거한다는 차원에서 유용한 기술입니다.  자세한 내용은 [XAML Security Considerations](../../../docs/framework/xaml-services/xaml-security-considerations.md)을 참조하십시오.  
  
## XAML 서비스 API에서의 XAML 네임스페이스 선언  
 XAML 서비스 API에서 XAML 네임스페이스 선언은 <xref:System.Xaml.NamespaceDeclaration> 개체로 표시됩니다.  코드에서 XAML 네임스페이스를 선언하는 경우에는 <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29> 생성자를 호출합니다.  `ns` 및 `prefix` 매개 변수는 문자열로 지정하며, 이러한 매개 변수에 대해 제공하는 입력은 이 항목의 앞부분에서 설명한 대로 XAML 네임스페이스 식별자 및 XAML 네임스페이스 접두사의 정의와 일치합니다.  
  
 XAML 네임스페이스 정보를 XAML 노드 스트림의 일부로 또는 XAML 형식 시스템에 대한 다른 액세스를 통해 검사하는 경우, <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=fullName>는 XAML 네임스페이스 식별자를 보고하고 <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=fullName>는 XAML 네임스페이스 접두사를 보고합니다.  
  
 XAML 노드 스트림에서 XAML 네임스페이스 정보는 해당 정보가 적용되는 엔터티 앞의 XAML 노드로 나타날 수 있습니다.  여기에는 XAML 네임스페이스 정보가 XAML 루트 요소의 `StartObject` 앞에 오는 경우가 포함됩니다.  자세한 내용은 [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)를 참조하십시오.  
  
 .NET Framework XAML 서비스 API를 사용하는 대부분의 시나리오에서는 XAML 네임스페이스 선언이 하나 이상 있어야 하며 선언에서는 XAML 스키마 컨텍스트에 필요한 정보를 포함하거나 참조해야 합니다.  XAML 네임스페이스에서는 로드할 어셈블리를 지정하거나 XAML 스키마 컨텍스트에서 이미 로드되거나 알려진 네임스페이스 및 어셈블리 내의 특정 형식을 확인할 수 있도록 지원해야 합니다.  
  
 XAML 노드 스트림을 생성하려면 XAML 스키마 컨텍스트를 통해 XAML 형식 정보를 사용할 수 있어야 합니다.  XAML 형식 정보를 확인하려면 먼저 만들려는 각 노드의 관련 XAML 네임스페이스를 확인해야 합니다.  이 때 형식 인스턴스는 아직 만들어지지 않지만 XAML 스키마 컨텍스트가 정의 어셈블리와 지원 형식에서 정보를 조회해야 할 수 있습니다.  예를 들어 `<Party><PartyFavor/></Party>` 태그를 처리하려면 XAML 스키마 컨텍스트에서는 `Party`에 대한 `ContentProperty`의 이름 및 형식을 확인할 수 있어야 하며, 따라서 `Party` 및 `PartyFavor`에 대한 XAML 네임스페이스 정보도 알고 있어야 합니다.  기본 XAML 스키마 컨텍스트의 경우 정적 리플렉션을 통해 노드 스트림에 XAML 형식 노드를 생성하는 데 필요한 XAML 형식 시스템 정보의 대부분이 보고됩니다.  
  
 XAML 노드 스트림에서 개체 그래프를 생성하려면 원래 태그에 사용되고 XAML 노드 스트림에 기록된 각 XAML 접두사에 대해 XAML 네임스페이스 선언이 있어야 합니다.  이때 인스턴스가 만들어지고 실제 형식 매핑 동작이 수행됩니다.  
  
 XAML 스키마 컨텍스트에서 사용할 XAML 네임스페이스가 태그에 정의되어 있지 않은 경우와 같이 XAML 네임스페이스 정보를 미리 채워야 하는 경우에 사용할 수 있는 한 가지 방법은 <xref:System.Xml.XmlReader>의 <xref:System.Xml.XmlParserContext>에서 XML 네임스페이스 선언을 선언하는 것입니다.  그런 다음 이 <xref:System.Xml.XmlReader>를 XAML 판독기 생성자 또는 <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=fullName>의 입력으로 사용합니다.  
  
 .NET Framework XAML 서비스에서 XAML 네임스페이스를 처리하는 데 관련된 다른 두 개의 API는 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 및 <xref:System.Windows.Markup.XmlnsPrefixAttribute> 특성입니다.  이러한 특성은 어셈블리에 적용됩니다.  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>는 XAML 스키마 컨텍스트에서 URI를 포함하는 XAML 네임스페이스 선언을 해석하는 데 사용됩니다.  <xref:System.Windows.Markup.XmlnsPrefixAttribute>는 특정 XAML 네임스페이스를 예측 가능한 접두사로 serialize할 수 있도록 XAML을 생성하는 도구에서 사용됩니다.  자세한 내용은 [XAML\-Related CLR Attributes for Custom Types and Libraries](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md)을 참조하십시오.  
  
## 참고 항목  
 [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)