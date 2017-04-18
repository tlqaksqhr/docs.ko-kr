---
title: "메서드 액세스 보안 | Microsoft Docs"
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
  - "코드 보안, 메서드 액세스"
  - "메서드 액세스 보안"
  - "보안 코딩, 메서드 액세스"
  - "보안[.NET Framework], 메서드 액세스"
ms.assetid: f7c2d6ec-3b18-4e0e-9991-acd97189d818
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# 메서드 액세스 보안
몇몇 메서드는 임의의 신뢰할 수 없는 코드 호출을 허용하는 데 적합하지 않을 수 있습니다. 이러한 메서드는 위험을 가져옵니다. 메서드가 제한된 정보를 제공하거나, 전달된 임의 정보를 신뢰하거나, 매개 변수에서 오류 검사를 수행하지 않거나, 잘못된 매개 변수를 사용하여 오작동하거나 피해를 줄 수 있습니다.  이들 경우에 대해 알고 있어야 하고 메서드 보호를 도와주는 조치를 취해야 합니다.  
  
 경우에 따라 공용으로 제공되지 않지만 공용으로 사용되어야 하는 메서드를 제한해야 할 수 있습니다. 예를 들어 자체 DLL에서 호출되어야 하고 공용으로도 사용되어야 하는 인터페이스를 포함하지만, 이 인터페이스를 고객이 사용하지 않도록 하고 악성 코드가 구성 요소에 대한 진입점으로 악용하지 못하도록 방지하기 위해 이 인터페이스를 공개적으로 노출하지 않고자 할 수 있습니다. 공용으로 제공되지 않은 메서드를 제한하는 또 다른 일반적인 이유는 완전히 내부적인 인터페이스일 수 있는 내용을 문서화하고 지원할 필요가 없도록 하려는 것입니다.  
  
> [!CAUTION]
>  코드 액세스 보안 및 부분적으로 신뢰할 수 있는 코드  
>   
>  .NET Framework는 동일한 응용 프로그램에서 실행되는 다른 코드에 다양한 신뢰 수준을 적용하기 위한 CAS\(코드 액세스 보안\)라는 메커니즘을 제공합니다.  .NET Framework의 코드 액세스 보안을 부분적으로 신뢰할 수 있는 코드, 특히 출처를 알 수 없는 코드의 보안 경계로 사용하면 안 됩니다. 대체 보안 조치를 적용하지 않고 출처를 알 수 없는 코드를 로드 및 실행하지 않는 것이 좋습니다.  
>   
>  이 정책은 모든 버전의 .NET Framework에 적용되지만 Silverlight에 포함된 .NET Framework에는 적용되지 않습니다.  
  
 관리 코드는 메서드 액세스를 제한하는 여러 가지 방법을 제공합니다.  
  
-   액세스 가능성 범위를 신뢰할 수 있는 클래스, 어셈블리 또는 파생 클래스로 제한합니다. 이는 메서드 액세스를 제한하는 가장 간단한 방법입니다. 일반적으로 파생 클래스는 자신이 파생된 소스 클래스보다 신뢰도가 더 낮지만 경우에 따라 부모 클래스의 ID를 공유할 수 있습니다. 특히 보안 컨텍스트에서 반드시 사용할 필요는 없는 **protected** 키워드에서 신뢰를 유추하지 마세요.  
  
-   메서드 액세스를 지정된 ID, 기본적으로 선택한 특정 [증거](http://msdn.microsoft.com/ko-kr/64ceb7c8-a0b4-46c4-97dc-6c22da0539da)\(강력한 이름, 게시자, 영역 등\)의 호출자로 제한합니다.  
  
-   메서드 액세스를 선택한 권한을 가진 호출자로 제한합니다.  
  
 마찬가지로 선언적 보안을 통해 클래스 상속을 제어할 수 있습니다.**InheritanceDemand**를 사용하여 다음을 수행할 수 있습니다.  
  
-   지정된 ID 또는 권한을 포함할 파생 클래스가 필요합니다.  
  
-   지정된 ID 또는 권한을 포함하도록 특정 메서드를 재정의하는 파생 클래스가 필요합니다.  
  
 다음 예제에서는 특정 강력한 이름을 통해 호출자에 서명하도록 요구하여 제한된 액세스용 공용 클래스를 보호하도록 도와주는 방법을 보여 줍니다. 이 예제에서는 강력한 이름에 대해 <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute>를 **Demand**와 함께 사용합니다. 강력한 이름으로 어셈블리에 서명하는 방법에 대한 작업 기반 정보는 [강력한 이름의 어셈블리 만들기 및 사용](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)을 참조하세요.  
  
```vb  
<StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey := "…hex…", Name := "App1", Version := "0.0.0.0")>  _ Public Class Class1 End Class  
  
```  
  
```csharp  
[StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey="…hex…", Name="App1", Version="0.0.0.0")] public class Class1 { }   
```  
  
## 신뢰할 수 없는 코드에 의한 클래스 및 멤버 사용 방지  
 이 섹션에 표시된 선언을 사용하여 특정 클래스와 메서드 및 속성과 이벤트가 부분 신뢰 코드에서 사용되지 않도록 방지합니다. 이들 선언을 클래스에 적용하여 모든 메서드, 속성 및 이벤트에 보호를 적용하지만, 필드 액세스는 선언적 보안의 영향을 받지 않습니다. 또한 링크 요청은 직접 실행 호출자 차단에만 도움이 되고 유인 공격의 대상이 될 수 있습니다.  
  
> [!NOTE]
>  새 투명성 모델은 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서 도입되었습니다.[보안 투명 코드, 수준 2](../../../docs/framework/misc/security-transparent-code-level-2.md) 모델은 <xref:System.Security.SecurityCriticalAttribute> 특성으로 보안 코드를 식별합니다. 보안에 중요한 코드에서는 호출자와 상속자를 둘 다 완전히 신뢰할 수 있어야 합니다. 이전 .NET Framework 버전에서 코드 액세스 보안 규칙에 따라 실행 중인 어셈블리는 수준 2 어셈블리를 호출할 수 있습니다. 이 경우 보안에 중요한 특성은 완전 신뢰를 위해 링크 요청으로 처리됩니다.  
  
 강력한 이름이 지정된 어셈블리에서는 완전히 신뢰할 수 있는 호출자로 사용을 제한하도록 [LinkDemand](../../../docs/framework/misc/link-demands.md)는 공개적으로 액세스할 수 있는 모든 메서드, 속성 및 이벤트에 적용됩니다. 이 기능을 사용하지 않도록 설정하려면 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성을 적용해야 합니다. 따라서 신뢰할 수 없는 호출자를 제외하도록 클래스에 명시적으로 표시하는 작업은 서명되지 않은 어셈블리나 이 특성이 포함된 어셈블리에만 필요합니다. 이들 선언을 사용하여 신뢰할 수 없는 호출자로 제공되지 않은 형식 하위 집합을 표시할 수 있습니다.  
  
 다음 예제에서는 클래스와 멤버가 신뢰할 수 없는 코드에서 사용되지 않도록 방지하는 방법을 보여 줍니다.  
  
 봉인되지 않은 공용 클래스의 경우:  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _ System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _ Public Class CanDeriveFromMe End Class  
  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")] [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")] public class CanDeriveFromMe { }  
```  
  
 봉인된 공용 클래스의 경우:  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _ NotInheritable Public Class CannotDeriveFromMe End Class  
  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")] public sealed class CannotDeriveFromMe { }  
```  
  
 공용 추상 클래스의 경우:  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _ System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _ MustInherit Public Class CannotCreateInstanceOfMe_CanCastToMe End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")] [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")] public abstract class CannotCreateInstanceOfMe_CanCastToMe{}  
```  
  
 공용 가상 함수의 경우:  
  
```vb  
Class Base1 <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _ Public Overridable Sub CanOverrideOrCallMe() End Sub 'CanOverrideOrCallMe End Class 'Base1  
```  
  
```csharp  
class Base1 { [System.Security.Permissions.PermissionSetAttribute( System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")] [System.Security.Permissions.PermissionSetAttribute( System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")] public virtual void CanOverrideOrCallMe() {} }  
```  
  
 공용 추상 함수의 경우:  
  
```vb  
MustInherit Class Base2 <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _ Public Sub MustOverrideMe() End Sub End Class 'Base2  
```  
  
```csharp  
abstract class Base2{ [System.Security.Permissions.PermissionSetAttribute( System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")] [System.Security.Permissions.PermissionSetAttribute( System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")] public abstract void MustOverrideMe(); }  
```  
  
 기본 클래스가 완전 신뢰를 요청하지 않는 공용 재정의 함수의 경우:  
  
```vb  
Class Derived Inherits Base1 <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name:="FullTrust")> _ Public Overrides Sub CanOverrideOrCallMe() MyBase.CanOverrideOrCallMe() End Sub 'CanOverrideOrCallMe End Class 'Derived  
```  
  
```csharp  
class Derived : Base1 { [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name="FullTrust")] public override void CanOverrideOrCallMe() { base.CanOverrideOrCallMe(); } }  
```  
  
 기본 클래스가 완전 신뢰를 요청하는 공용 재정의 함수의 경우:  
  
```vb  
Class Derived Inherits Base1 <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _ Public Overrides Sub CanOverrideOrCallMe() MyBase.CanOverrideOrCallMe() End Sub 'CanOverrideOrCallMe End Class 'Derived  
```  
  
```csharp  
class Derived : Base1 { [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")] public override void CanOverrideOrCallMe() { base.CanOverrideOrCallMe(); } }  
```  
  
 공용 인터페이스의 경우:  
  
```vb  
Public Interface ICanCastToMe <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _ Sub CanImplementMe() End Interface 'ICanCastToMe <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _ Class Implemented Implements ICanCastToMe Public Sub CanImplementMe() End Sub 'CanImplementMe  
```  
  
```csharp  
public interface ICanCastToMe { [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")] [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")] void CanImplementMe(); } [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")] [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")] class Implemented : ICanCastToMe { public void CanImplementMe() { } }  
```  
  
## Virtual Internal 재정의 또는 Overloads Overridable Friend  
  
> [!NOTE]
>  이 섹션에서는 메서드를 `virtual` 및 `internal`\(Visual Basic의 경우 `Overloads``Overridable``Friend`\)로 선언할 때 발생하는 보안 문제에 대해 경고합니다. 이 경고는 .NET Framework 버전 1.0 및 1.1에만 적용되고 버전 2.0에는 적용되지 않습니다.  
  
 .NET Framework 버전 1.0 및 1.1에서는 코드를 다른 어셈블리에 사용할 수 없음을 확인할 때 형식 시스템 액세스 가능성의 미묘한 차이를 인식해야 합니다.**virtual** 및 **internal**\(Visual Basic의 **Overloads Overridable Friend**\)로 선언된 메서드는 부모 클래스의 vtable 항목을 재정의할 수 있고 내부 메서드이므로 같은 어셈블리 내에서만 사용될 수 있습니다. 그러나 재정의에 대한 액세스 가능성은 **virtual** 키워드에 의해 결정되고 해당 코드가 클래스 자체에 액세스할 수 있으면 이 액세스 가능성은 다른 어셈블리에서 재정의될 수 있습니다. 재정의 가능성에 문제가 있으면 선언적 보안을 사용하여 문제를 해결하거나, 엄격한 기준을 적용할 필요가 없으면 **virtual** 키워드를 제거합니다.  
  
 언어 컴파일러에서 컴파일 오류 때문에 이 재정의가 차단되더라도 다른 컴파일러로 작성된 코드는 재정의될 수 있습니다.  
  
## 참고 항목  
 [보안 코딩 지침](../../../docs/standard/security/secure-coding-guidelines.md)