---
title: "래퍼 코드 보안 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "코드 보안, 래퍼 코드"
  - "보안 코딩, 래퍼 코드"
  - "보안[.NET Framework], 래퍼 코드"
  - "래퍼 코드, 보안"
ms.assetid: 1df6c516-5bba-48bd-b450-1070e04b7389
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# 래퍼 코드 보안
특히 래퍼의 신뢰 수준이 래퍼를 사용하는 코드보다 더 높은 래퍼 코드는 고유한 보안 약점 집합을 초래할 수 있습니다. 호출자의 제한된 권한이 적절한 보안 검사에 포함되지 않은 경우 호출자 대신 수행되는 모든 작업은 악용되는 잠재적인 약점이 됩니다.  
  
 래퍼를 통해 호출자가 직접 수행할 수 없는 작업을 사용하도록 설정하지 마세요. 전체 스택 워크 요구와 반대인 제한된 보안 검사와 관련된 작업을 수행할 때는 특히 위험합니다. 단일 수준 검사가 관련된 경우 실제 호출자와 해당 API 요소 사이에 래퍼 코드를 삽입하면 보안 검사가 성공하지 않아야 할 때 쉽게 성공하여 보안이 약화될 수 있습니다.  
  
> [!CAUTION]
>  코드 액세스 보안 및 부분적으로 신뢰할 수 있는 코드  
>   
>  .NET Framework는 동일한 응용 프로그램에서 실행되는 다른 코드에 다양한 신뢰 수준을 적용하기 위한 CAS\(코드 액세스 보안\)라는 메커니즘을 제공합니다.  .NET Framework의 코드 액세스 보안을 부분적으로 신뢰할 수 있는 코드, 특히 출처를 알 수 없는 코드의 보안 경계로 사용하면 안 됩니다. 대체 보안 조치를 적용하지 않고 출처를 알 수 없는 코드를 로드 및 실행하지 않는 것이 좋습니다.  
>   
>  이 정책은 모든 버전의 .NET Framework에 적용되지만 Silverlight에 포함된 .NET Framework에는 적용되지 않습니다.  
  
## 대리자  
 대리자 보안은 .NET Framework 버전마다 다릅니다.  이 섹션에서는 다양한 대리자 동작 및 관련된 보안 고려 사항을 설명합니다.  
  
### .NET Framework 버전 1.0 및 1.1  
 .NET Framework 버전 1.0 및 1.1에서는 대리자 작성자 및 대리자 호출자에 대해 다음과 같은 보안 동작을 수행합니다.  
  
-   대리자를 만들면 대리자 작성자의 권한 부여 집합에 대해 대리자 대상 메서드의 보안 링크 요구가 수행됩니다.  보안 동작을 충족하지 못하면 <xref:System.Security.SecurityException>이 발생합니다.  
  
-   대리자를 호출하면 대리자 호출자의 모든 기존 보안 요구가 수행됩니다.  
  
 사용자 코드가 해당 코드를 호출할 수 있는 덜 신뢰되는 코드에서 <xref:System.Delegate>를 가져오는 경우 덜 신뢰되는 코드가 권한을 에스컬레이션할 수 없도록 해야 합니다. 대리자를 가져와서 나중에 사용하는 경우 대리자를 만든 코드가 호출 스택에 없으며, 대리자의 코드에서 보호된 작업을 시도해도 해당 권한이 테스트되지 않습니다. 사용자 코드와 호출자 코드에 작성자보다 더 높은 권한이 있을 경우 작성자가 호출 스택에 포함되지 않아도 호출 경로를 조정할 수 있습니다.  
  
### .NET Framework 버전 2.0 이상  
 이전 버전과 달리 .NET Framework 버전 2.0에서는 대리자를 만들고 호출할 때 대리자 작성자에 대해 보안 동작을 수행합니다.  
  
-   대리자를 만들면 대리자 작성자의 권한 부여 집합에 대해 대리자 대상 메서드의 보안 링크 요구가 수행됩니다.  보안 동작을 충족하지 못하면 <xref:System.Security.SecurityException>이 발생합니다.  
  
-   대리자를 만드는 동안 대리자 작성자의 권한 부여 집합도 캡처되어 대리자와 함께 저장됩니다.  
  
-   대리자를 호출하면 대리자 작성자와 호출자가 서로 다른 어셈블리에 속하는 경우 대리자 작성자의 캡처된 권한 부여 집합이 현재 컨텍스트의 모든 요구에 대해 먼저 평가됩니다.  다음에는 대리자 호출자의 모든 기존 보안 요구가 수행됩니다.  
  
## 링크 요구 및 래퍼  
 링크 요구를 포함하는 특수 보호 사례가 보안 인프라에서 강화되었지만 여전히 코드에서 보안 약점이 될 수 있습니다.  
  
 완전히 신뢰할 수 있는 코드가 [LinkDemand](../../../docs/framework/misc/link-demands.md)로 보호된 속성, 이벤트 또는 메서드를 호출하는 경우 호출자에 대한 **LinkDemand** 권한 검사가 충족되면 호출이 성공합니다. 또한 완전히 신뢰할 수 있는 코드가 속성의 이름을 가져오는 클래스를 노출하고 리플렉션을 사용하여 해당 **get** 접근자를 호출하는 경우 사용자 코드에 이 속성에 액세스할 수 있는 권한이 없어도 **get** 접근자 호출이 성공합니다. 이는 **LinkDemand**가 완전히 신뢰할 수 있는 코드인 직접 실행 호출자만 검사하기 때문입니다. 기본적으로 완전히 신뢰할 수 있는 코드는 사용자 코드에 해당 호출을 수행할 권한이 있는지 확인하지 않고 사용자 코드 대신 권한 있는 호출을 수행합니다.  
  
 이러한 보안 허점을 방지하기 위해 공용 언어 런타임에서는 **LinkDemand**로 보호된 메서드, 생성자, 속성 또는 이벤트에 대한 모든 간접 호출의 전체 스택 워크 요구로 검사를 확장합니다. 이 보호를 사용할 경우 성능이 약간 저하되고 보안 검사의 의미 체계가 변경됩니다. 보다 신속한 단일 수준 검사는 성공했을 경우에도 전체 스택 워크 요구는 실패할 수 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서는 부분적으로 신뢰할 수 있는 코드가 투명 코드로 다시 정의되었습니다. 투명도 모델은 네이티브 코드 호출과 같은 권한 있는 작업을 수행할 수 있는 코드\(중요한 코드\)와 수행할 수 없는 코드\(투명 코드\)를 구분합니다. 투명도는 완전 신뢰에 대한 <xref:System.Security.Permissions.SecurityAction> 사용을 대체하여 완전히 신뢰할 수 있는 코드를 <xref:System.Security.SecurityCriticalAttribute>로 식별합니다. 이 변경 및 다른 변경에 대한 자세한 내용은 [보안 변경 내용](../../../docs/framework/security/security-changes.md)을 참조하세요.  
  
## 어셈블리 로딩 래퍼  
 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>를 포함하여 관리 코드를 로드하는 데 사용되는 여러 메서드는 호출자의 증거와 함께 어셈블리를 로드합니다. 이러한 메서드를 래핑하는 경우 보안 시스템이 래퍼 호출자의 권한 대신 코드의 권한 부여를 사용하여 어셈블리를 로드할 수 있습니다. 덜 신뢰되는 코드가 래퍼 호출자의 권한보다 더 높은 권한이 부여된 코드를 로드할 수 있도록 허용하면 안 됩니다.  
  
 완전 신뢰 또는 잠재적인 호출자\(인터넷 권한 수준 호출자 포함\)보다 더 높은 신뢰 수준의 코드는 이런 방식으로 보안을 약화시킬 수 있습니다. 코드에 바이트 배열을 가져오고 **Assembly.Load**에 전달하여 호출자 대신 어셈블리를 만드는 public 메서드가 있는 경우 보안이 손상될 수 있습니다.  
  
 이 문제는 다음과 같은 API 요소에 적용됩니다.  
  
-   <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>  
  
## Demand와 LinkDemand 비교  
 선언적 보안은 서로 비슷하지만 전혀 다른 검사를 수행하는 두 종류의 보안 검사를 제공합니다. 잘못 선택하면 보안이 약화되거나 성능이 저하될 수 있으므로 두 형태를 모두 이해해야 합니다.  
  
 선언적 보안은 다음과 같은 보안 검사를 제공합니다.  
  
-   <xref:System.Security.Permissions.SecurityAction>는 코드 액세스 보안 스택 워크를 지정합니다. 성공하려면 스택의 모든 호출자에게 지정된 권한이나 ID가 있어야 합니다. 스택에 다양한 호출자가 포함될 수 있으므로 **Demand**는 각 호출에서 발생합니다. 메서드를 반복해서 호출하는 경우 이 보안 검사는 매번 발생합니다.**Demand**는 유인 공격에 유용한 보호 방법입니다. 권한 없는 코드의 통과 시도가 검색됩니다.  
  
-   [LinkDemand](../../../docs/framework/misc/link-demands.md)는 JIT\(Just\-In\-Time\) 컴파일 시간에 발생하며 직접 실행 호출자만 검사합니다. 이 보안 검사는 호출자의 호출자를 검사하지 않습니다. 이 검사가 성공하고 나면 호출자가 호출할 수 있는 횟수에 관계없이 추가 보안 오버헤드가 없습니다. 그러나 유인 공격으로부터 보호되지 않습니다.**LinkDemand**를 사용할 경우 테스트에 성공하고 사용자 코드를 참조할 수 있는 모든 코드는 권한 있는 코드를 통해 악성 코드를 호출할 수 있게 하여 잠재적으로 보안을 손상시킬 수 있습니다. 따라서 가능한 모든 보안 약점을 완전히 방지할 수 없는 경우 **LinkDemand**를 사용하지 마세요.  
  
    > [!NOTE]
    >  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서는 링크 요구가 <xref:System.Security.SecurityRuleSet> 어셈블리의 <xref:System.Security.SecurityCriticalAttribute> 특성으로 대체되었습니다.<xref:System.Security.SecurityCriticalAttribute>는 완전 신뢰에 대한 링크 요구와 같지만 상속 규칙에도 영향을 줍니다. 이 변경에 대한 자세한 내용은 [보안 투명 코드, 수준 2](../../../docs/framework/misc/security-transparent-code-level-2.md)을 참조하세요.  
  
 **LinkDemand**를 사용할 때 필요한 추가 예방 조치는 개별적으로 프로그래밍해야 합니다. 보안 시스템은 적용에 도움이 될 수 있습니다. 실수는 보안 약점이 됩니다. 사용자 코드를 사용하는 모든 권한 있는 코드는 다음을 수행하여 추가 보안을 구현해야 합니다.  
  
-   클래스 또는 어셈블리에 대한 호출 코드의 액세스 권한 제한.  
  
-   호출되는 코드에 표시되는 것과 동일한 보안 검사를 호출 코드에 배치하고 호출자도 이렇게 하도록 강제. 예를 들어 <xref:System.Security.Permissions.SecurityPermissionFlag> 플래그가 지정된 <xref:System.Security.Permissions.SecurityPermission>에 대해 **LinkDemand**로 보호된 메서드를 호출하는 코드를 작성하는 경우 메서드에서도 이 권한에 대해 **LinkDemand**\(또는 더 강력한 **Demand**\)를 수행해야 합니다. 단, 사용자 코드에서 **LinkDemand**로 보호된 메서드를 안전한 제한된 방식으로 사용하며 코드에서 요구와 같은 다른 보안 보호 메커니즘이 지정된 경우는 예외입니다. 이 예외적인 경우에서는 내부 코드의 보안 보호 약화에 대한 책임이 호출자에게 있습니다.  
  
-   코드의 호출자가 사용자 코드에서 보호된 코드를 대신 호출하도록 속일 수 없는지 확인. 즉, 호출자는 권한 있는 코드에서 특정 매개 변수를 보호된 코드로 전달하거나 보호된 코드에서 결과를 가져오도록 강제할 수 없습니다.  
  
### 인터페이스 및 링크 요구  
 **LinkDemand**가 있는 가상 메서드, 속성 또는 이벤트가 기본 클래스 메서드를 재정의하는 경우 기본 클래스 메서드에도 재정의된 메서드에 대해 동일한 **LinkDemand**가 있어야 적용됩니다. 악성 코드가 기본 형식으로 다시 캐스팅되어 기본 클래스 메서드를 호출할 수 있습니다. 또한 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 어셈블리 수준 특성이 없는 어셈블리에 링크 요구를 암시적으로 추가할 수 있습니다.  
  
 인터페이스 메서드에도 링크 요구가 있는 경우 링크 요구로 메서드 구현을 보호하는 것이 좋습니다. 인터페이스와 함께 링크 요구를 사용하는 경우에 대한 다음 사항을 확인하세요.  
  
-   **AllowPartiallyTrustedCallersAttribute** 특성이 인터페이스에도 적용됩니다.  
  
-   인터페이스에 링크 요구를 배치하여 부분적으로 신뢰할 수 있는 코드의 사용으로부터 특정 인터페이스를 선택적으로 보호할 수 있습니다\(예: **AllowPartiallyTrustedCallersAttribute** 특성을 사용하는 경우\).  
  
-   **AllowPartiallyTrustedCallersAttribute** 특성을 포함하지 않는 인터페이스가 어셈블리에 정의되어 있는 경우 부분적으로 신뢰할 수 있는 클래스에서 해당 인터페이스를 구현할 수 있습니다.  
  
-   인터페이스 메서드를 구현하는 클래스의 public 메서드에 **LinkDemand**를 배치한 다음 인터페이스로 캐스팅하고 메서드를 호출하는 경우 **LinkDemand**가 적용되지 않습니다. 이 경우 인터페이스에 대해 연결했으므로 인터페이스의 **LinkDemand**만 적용됩니다.  
  
 보안 문제에 대한 다음 항목을 검토합니다.  
  
-   인터페이스 메서드의 명시적 링크 요구 이러한 링크 요구가 필요한 보호를 제공하는지 확인합니다. 앞에서 설명한 대로 악성 코드가 캐스트를 사용하여 링크 요구를 해결할 수 있는지 여부를 확인합니다.  
  
-   링크 요구가 적용된 가상 메서드  
  
-   가상 메서드가 구현하는 형식 및 인터페이스 링크 요구를 일관되게 사용해야 합니다.  
  
## 참고 항목  
 [보안 코딩 지침](../../../docs/standard/security/secure-coding-guidelines.md)