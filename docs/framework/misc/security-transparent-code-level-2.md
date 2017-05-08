---
title: "보안 투명 코드, 수준 2 | Microsoft Docs"
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
  - "수준 2 투명도"
  - "보안에 중요한 코드"
  - "보안 투명 코드"
  - "투명성"
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
caps.latest.revision: 37
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 35
---
# 보안 투명 코드, 수준 2
<a name="top"></a> 수준 2 투명도는 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서 새로 추가되었습니다. 이 모델의 세 가지 개념은 투명 코드, 보안 안전에 중요 코드 및 보안에 중요 코드입니다.  
  
-   완전 신뢰로 실행되는 코드를 포함하는 투명 코드는 다른 투명 코드나 보안 안전에 중요 코드만 호출할 수 있습니다. 도메인의 부분 신뢰 권한 집합\(있는 경우\)에서 허용하는 작업만 수행할 수 있습니다. 투명 코드는 다음을 수행할 수 없습니다.  
  
    -   <xref:System.Security.CodeAccessPermission.Assert%2A> 또는 권한 상승을 수행합니다.  
  
    -   안전하지 않거나 확인할 수 없는 코드를 포함합니다.  
  
    -   중요한 코드를 직접 호출합니다.  
  
    -   <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성이 포함된 코드나 네이티브 코드를 호출합니다.  
  
    -   <xref:System.Security.Permissions.SecurityAction>로 보호된 멤버를 호출합니다.  
  
    -   중요한 형식에서 상속합니다.  
  
     또한 투명 메서드는 중요한 가상 메서드를 재정의하거나 중요한 인터페이스 메서드를 구현할 수 없습니다.  
  
-   안전에 중요 코드는 완전히 신뢰할 수 있지만 투명 코드를 통해 호출할 수 있습니다. 이 코드는 완전 신뢰 코드의 제한된 노출 영역을 노출하고, 정확성 및 보안 확인은 안전에 중요 코드에서 수행됩니다.  
  
-   보안에 중요 코드는 모든 코드를 호출할 수 있고 완전히 신뢰할 수 있지만 투명 코드를 통해 호출할 수 없습니다.  
  
> [!CAUTION]
>  코드 액세스 보안 및 부분적으로 신뢰할 수 있는 코드  
>   
>  .NET Framework는 동일한 응용 프로그램에서 실행되는 다른 코드에 다양한 신뢰 수준을 적용하기 위한 CAS\(코드 액세스 보안\)라는 메커니즘을 제공합니다.  .NET Framework의 코드 액세스 보안을 부분적으로 신뢰할 수 있는 코드, 특히 출처를 알 수 없는 코드의 보안 경계로 사용하면 안 됩니다. 대체 보안 조치를 적용하지 않고 출처를 알 수 없는 코드를 로드 및 실행하지 않는 것이 좋습니다.  
>   
>  이 정책은 모든 버전의 .NET Framework에 적용되지만 Silverlight에 포함된 .NET Framework에는 적용되지 않습니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [사용 예제 및 동작](#examples)  
  
-   [재정의 패턴](#override)  
  
-   [상속 규칙](#inheritance)  
  
-   [추가 정보 및 규칙](#additional)  
  
<a name="examples"></a>   
## 사용 예제 및 동작  
 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 규칙\(수준 2 투명도\)을 지정하려면 어셈블리에 대한 다음 주석을 사용합니다.  
  
```  
[assembly: SecurityRules(SecurityRuleSet.Level2)]  
```  
  
 .NET Framework 2.0 규칙\(수준 1 투명도\)으로 잠그려면 다음 주석을 사용합니다.  
  
```  
[assembly: SecurityRules(SecurityRuleSet.Level1)]  
```  
  
 어셈블리를 주석으로 처리하지 않으면 기본적으로 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 규칙이 사용됩니다. 그러나 기본값과 관계없이 <xref:System.Security.SecurityRulesAttribute> 특성을 사용하는 것이 좋습니다.  
  
### 어셈블리 수준 주석  
 어셈블리 수준에서 특성을 사용할 경우 다음 규칙이 적용됩니다.  
  
-   특성 없음: 특성을 지정하지 않으면 보안에 중요하게 되어 상속 규칙을 위반하는 경우\(예: 투명한 가상 또는 인터페이스 메서드를 재정의하거나 구현할 경우\)를 제외하고 런타임은 모든 코드를 보안에 중요 코드로 해석합니다. 이 경우 메서드는 안전에 중요합니다. 특성을 지정하지 않으면 공용 언어 런타임이 투명도 규칙을 확인합니다.  
  
-   `SecurityTransparent`: 모든 코드가 투명합니다. 전체 어셈블리는 권한이 필요하거나 안전하지 않은 작업을 수행하지 않습니다.  
  
-   `SecurityCritical`: 이 어셈블리에서 형식으로 도입되는 모든 코드가 중요합니다. 기타 모든 코드는 투명합니다. 이 시나리오는 특성을 지정하지 않는 것과 비슷하지만, 공용 언어 런타임이 투명도 규칙을 자동으로 확인하지 않습니다. 예를 들어 가상 또는 추상 메서드를 재정의하거나 인터페이스 메서드를 구현할 경우 기본적으로 해당 메서드는 투명합니다. 메서드를 `SecurityCritical` 또는 `SecuritySafeCritical`로 명시적으로 주석으로 처리해야 합니다. 그러지 않으면 로드 시 <xref:System.TypeLoadException>이 throw됩니다. 이 규칙은 기본 클래스와 파생 클래스가 둘 다 같은 어셈블리에 있을 경우에도 적용됩니다.  
  
-   `AllowPartiallyTrustedCallers`\(수준 2만 해당\): 모든 코드가 기본적으로 투명으로 설정됩니다. 그러나 개별 형식 및 멤버는 다른 특성을 포함할 수 있습니다.  
  
 다음 표에서는 수준 2에 대한 어셈블리 수준 동작을 수준 1과 비교합니다.  
  
|Assembly 특성|수준 2|수준 1|  
|-----------------|----------|----------|  
|부분적으로 신뢰할 수 있는 어셈블리에 대한 특성 없음|형식 및 멤버는 기본적으로 투명하지만 보안에 중요하거나 보안 안전에 중요할 수 있습니다.|모든 형식 및 멤버가 투명합니다.|  
|특성 없음|특성을 지정하지 않으면 공용 언어 런타임이 투명도 규칙을 확인합니다. 보안에 중요하게 되어 상속 규칙을 위반하는 경우를 제외하고 모든 형식 및 멤버가 보안에 중요합니다.|완전히 신뢰할 수 있는 어셈블리\(전역 어셈블리 캐시에 포함 또는 `AppDomain`에서 완전 신뢰로 식별됨\)에서 모든 형식은 투명하고 모든 멤버는 보안 안전에 중요합니다.|  
|`SecurityTransparent`|모든 형식 및 멤버가 투명합니다.|모든 형식 및 멤버가 투명합니다.|  
|`SecurityCritical(SecurityCriticalScope.Everything)`|적용할 수 없음|모든 형식 및 멤버가 보안에 중요합니다.|  
|`SecurityCritical`|이 어셈블리에서 형식으로 도입되는 모든 코드가 중요합니다. 기타 모든 코드는 투명합니다. 가상 또는 추상 메서드를 재정의하거나 인터페이스 메서드를 구현할 경우 해당 메서드를 `SecurityCritical` 또는 `SecuritySafeCritical`로 명시적으로 주석으로 처리해야 합니다.|모든 코드가 기본적으로 투명으로 설정됩니다. 그러나 개별 형식 및 멤버는 다른 특성을 포함할 수 있습니다.|  
  
### 형식 및 멤버 주석  
 형식에 적용되는 보안 특성은 형식에 의해 도입되는 멤버에도 적용됩니다. 그러나 기본 클래스 또는 인터페이스 구현의 가상 또는 추상 재정의에는 적용되지 않습니다. 형식 및 멤버 수준에서 특성을 사용할 경우 다음 규칙이 적용됩니다.  
  
-   `SecurityCritical`: 형식 또는 멤버가 중요하고 완전 신뢰 코드를 통해서만 호출할 수 있습니다. 보안에 중요 형식에 도입된 메서드는 중요합니다.  
  
    > [!IMPORTANT]
    >  기본 클래스 또는 인터페이스에 도입되고 보안에 중요 클래스에서 재정의되거나 구현되는 가상 및 추상 메서드는 기본적으로 투명합니다. 이들 메서드는 `SecuritySafeCritical` 또는 `SecurityCritical`로 식별되어야 합니다.  
  
-   `SecuritySafeCritical`: 형식 또는 멤버가 안전에 중요합니다. 그러나 형식 또는 멤버는 투명\(부분적으로 신뢰할 수 있는\) 코드에서 호출할 수 있고 다른 중요한 코드와 같은 작업을 수행할 수 있습니다. 코드는 보안을 위해 감사해야 합니다.  
  
 [맨 위로 이동](#top)  
  
<a name="override"></a>   
## 재정의 패턴  
 다음 표에서는 수준 2 투명도에 허용되는 메서드 재정의를 보여 줍니다.  
  
|기본 가상\/인터페이스 멤버|재정의\/인터페이스|  
|---------------------|----------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`SafeCritical`|`Transparent`|  
|`SafeCritical`|`SafeCritical`|  
|`Critical`|`Critical`|  
  
 [맨 위로 이동](#top)  
  
<a name="inheritance"></a>   
## 상속 규칙  
 이 섹션에서는 액세스 권한과 기능에 따라 다음 순서가 `Transparent`, `Critical` 및 `SafeCritical` 코드에 할당됩니다.  
  
 `Transparent` \< `SafeCritical` \< `Critical`  
  
-   형식에 대한 규칙: 왼쪽에서 오른쪽으로 이동하면 액세스 권한이 더 제한됩니다. 파생 형식은 기본 형식 이상으로 제한적이어야 합니다.  
  
-   메서드에 대한 규칙: 파생 메서드는 기본 메서드의 접근성을 변경할 수 없습니다. 기본 동작의 경우 주석으로 처리되지 않은 모든 파생 메서드는 `Transparent`입니다. 재정의된 메서드가 `SecurityCritical`로 명시적으로 주석으로 처리되지 않으면 중요한 형식의 파생 항목으로 인해 예외가 throw됩니다.  
  
 다음 표에서는 허용되는 형식 상속 패턴을 보여 줍니다.  
  
|기본 클래스|파생 클래스는 다음과 같을 수 있습니다.|  
|------------|----------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`Transparent`|`Critical`|  
|`SafeCritical`|`SafeCritical`|  
|`SafeCritical`|`Critical`|  
|`Critical`|`Critical`|  
  
 다음 표에서는 허용되지 않는 형식 상속 패턴을 보여 줍니다.  
  
|기본 클래스|파생 클래스는 다음과 같을 수 없습니다.|  
|------------|----------------------------|  
|`SafeCritical`|`Transparent`|  
|`Critical`|`Transparent`|  
|`Critical`|`SafeCritical`|  
  
 다음 표에서는 허용되는 메서드 상속 패턴을 보여 줍니다.  
  
|기본 메서드|파생 메서드는 다음과 같을 수 있습니다.|  
|------------|----------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`SafeCritical`|`Transparent`|  
|`SafeCritical`|`SafeCritical`|  
|`Critical`|`Critical`|  
  
 다음 표에서는 허용되지 않는 메서드 상속 패턴을 보여 줍니다.  
  
|기본 메서드|파생 메서드는 다음과 같을 수 없습니다.|  
|------------|----------------------------|  
|`Transparent`|`Critical`|  
|`SafeCritical`|`Critical`|  
|`Critical`|`Transparent`|  
|`Critical`|`SafeCritical`|  
  
> [!NOTE]
>  이들 상속 규칙은 수준 2 형식 및 멤버에 적용됩니다. 수준 1 어셈블리의 형식은 수준 2 보안에 중요 형식 및 멤버에서 상속할 수 있습니다. 따라서 수준 2 형식 및 멤버에는 수준 1 상속자에 대한 별도의 상속 요청이 있어야 합니다.  
  
 [맨 위로 이동](#top)  
  
<a name="additional"></a>   
## 추가 정보 및 규칙  
  
### LinkDemand 지원  
 수준 2 투명도 모델은 <xref:System.Security.Permissions.SecurityAction>를 <xref:System.Security.SecurityCriticalAttribute> 특성으로 바꿉니다. 레거시\(수준 1\) 코드에서 <xref:System.Security.Permissions.SecurityAction>는 자동으로 <xref:System.Security.Permissions.SecurityAction>로 처리됩니다.  
  
### 반사  
 중요한 메서드를 호출하거나 중요한 필드를 읽으면 private 메서드나 필드를 호출한 것처럼 완전 신뢰에 대한 요청이 트리거됩니다. 따라서 완전 신뢰 코드는 중요한 메서드를 호출할 수 있지만 부분 신뢰 코드는 호출할 수 없습니다.  
  
 형식, 메서드 또는 필드가 `SecurityCritical`, `SecuritySafeCritical` 또는 `SecurityTransparent`인지 확인하려고 <xref:System.Reflection> 네임스페이스에 <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> 및 <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A> 속성이 추가되었습니다. 이들 속성을 사용하여 특성이 있는지 확인하는 것이 아니라 리플렉션을 통해 투명도를 확인합니다. 투명도 규칙은 복잡하고 특성이 있는지 확인하는 것으로는 충분하지 않을 수 있습니다.  
  
> [!NOTE]
>  `SafeCritical` 메서드는 <xref:System.Type.IsSecurityCritical%2A>`` 및 <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>에 대해 둘 다 `true`를 반환합니다. 이는 `SafeCritical`이 중요하기 때문입니다\(중요한 코드와 같은 기능을 포함하지만 투명 코드에서 호출할 수 있음\).  
  
 동적 메서드는 연결된 모듈의 투명도를 상속합니다. 형식의 투명도를 상속하지 않습니다\(형식에 연결된 경우\).  
  
### 완전 신뢰에서 확인 건너뛰기  
 <xref:System.Security.SecurityRulesAttribute> 특성에서 <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> 속성을 `true`로 설정하여 완전히 신뢰할 수 있는 어셈블리에 대한 확인을 건너뛸 수 있습니다.  
  
 `[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`  
  
 <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> 속성은 기본적으로 `false`이므로 확인을 건너뛰려면 속성을 `true`로 설정해야 합니다. 이 작업은 최적화 목적으로만 수행해야 합니다.[PEVerify 도구](../../../docs/framework/tools/peverify-exe-peverify-tool.md)에서 `transparent` 옵션을 사용하여 어셈블리의 투명 코드를 확인할 수 있는지 확인해야 합니다.  
  
## 참고 항목  
 [보안 투명 코드, 수준 1](../../../docs/framework/misc/security-transparent-code-level-1.md)   
 [보안 변경 내용](../../../docs/framework/security/security-changes.md)