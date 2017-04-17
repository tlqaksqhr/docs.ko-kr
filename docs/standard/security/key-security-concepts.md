---
title: "주요 보안 개념 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "사용 권한[.NET Framework]"
  - "보안[.NET Framework], 보안 정보"
  - "무단 액세스"
ms.assetid: 3cfced4f-ea02-4e66-ae98-d69286363e98
caps.latest.revision: 22
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 20
---
# 주요 보안 개념
Microsoft .NET Framework는 모바일 코드에 대한 보안 문제를 해결하고 사용자에게 수행할 수 있는 권한이 있는 작업을 구성 요소가 확인할 수 있게 해주는 지원을 제공하기 위해 보안 투명도, 코드 액세스 보안 및 역할 기반 보안을 제공합니다.  이러한 보안 메커니즘은 코드 액세스 보안에 익숙한 개발자가 역할 기반 보안을 쉽게 사용할 수 있고 그 반대로 가능하도록 간단하고 일관된 모델을 사용합니다.  코드 액세스 보안과 역할 기반 보안은 둘 다 공용 언어 런타임이 제공하는 공용 인프라를 사용하여 구현되었습니다.  
  
> [!NOTE]
>  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 보안 투명도가 기본 적용 메커니즘입니다.  보안 투명도는 응용 프로그램의 일부로 실행되는 코드와 인프라의 일부로 실행되는 코드를 구분합니다.  자세한 내용은 [보안 투명 코드](../../../docs/framework/misc/security-transparent-code.md)를 참조하세요.  
  
 동일한 모델 및 인프라를 사용하기 때문에 코드 액세스 보안과 역할 기반 보안은 이 섹션에서 설명하는 몇 가지 기본 개념을 공유합니다.  .NET Framework 코드 액세스 보안 및 역할 기반 보안에 대한 설명서를 읽기 전에 이러한 개념을 잘 알고 있어야 합니다.  
  
## 보안 권한  
 공용 언어 런타임은 코드에 수행 권한이 있는 작업만 수행하도록 허용합니다.  런타임은 권한이라는 개체를 사용하여 관리 코드에 제한을 적용합니다.  런타임은 여러 네임스페이스에 기본 제공 권한 클래스를 제공하며 사용자 지정 권한 클래스 디자인 및 구현도 지원합니다.  
  
 다음 두 종류의 권한이 있으며 각각 특정 용도가 있습니다.  
  
-   코드 액세스 권한은 보호된 리소스 또는 보호된 작업을 수행하는 기능에 대한 액세스를 나타냅니다.  
  
-   역할 기반 보안 권한은 사용자\(또는 사용자 역할을 하는 에이전트\)가 특정 ID를 가지고 있는지 또는 지정된 역할의 멤버인지를 확인하는 메커니즘을 제공합니다.  <xref:System.Security.Permissions.PrincipalPermission>은 유일한 역할 기반 보안 권한입니다.  
  
 보안 권한은 권한 클래스\(명령적 보안\) 또는 권한 클래스를 나타내는 특성\(선언적 보안\) 형태일 수 있습니다.  보안 권한에 대한 기본 클래스는 <xref:System.Security.CodeAccessPermission?displayProperty=fullName>이고, 보안 권한 특성에 대한 기본 클래스는 <xref:System.Security.Permissions.CodeAccessSecurityAttribute?displayProperty=fullName>입니다.  
  
 어셈블리 형태인 응용 프로그램에는 응용 프로그램 도메인에 로드될 때 권한 집합이 부여됩니다.  일반적으로 <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=fullName> 메서드에 의해 결정되는 미리 정의된 권한 집합을 통해 권한이 부여됩니다.  권한 부여 집합은 코드가 사용할 수 있는 권한을 결정합니다.  런타임은 코드의 원래 위치\(예: 로컬 컴퓨터, 로컬 인트라넷 또는 인터넷\)에 따라 권한을 부여합니다.  코드가 샌드박스에 로드된 경우 특수 권한이 부여될 수도 있습니다.  샌드박스에서 코드를 실행하는 방법에 대한 자세한 내용은 [방법: 샌드박스에서 부분 신뢰 코드 실행](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)을 참조하세요.  
  
 권한은 주로 다음과 같이 사용됩니다.  
  
-   라이브러리 코드에서 해당 호출자가 특정 권한을 갖도록 요구할 수 있습니다.  권한에 대한 <xref:System.Security.CodeAccessPermission.Demand%2A>를 코드에 배치하는 경우 이 코드를 사용하는 모든 코드는 실행하는 데 해당 권한이 있어야 합니다.  요구를 사용하여 호출자에게 특정 리소스에 대한 액세스 권한이 있는지 여부를 확인하거나 호출자의 ID를 검색할 수 있습니다.  
  
-   코드는 권한을 사용하여 보호하려는 리소스에 대한 액세스를 거부할 수 있습니다.  <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName>를 사용하여 제한된 권한 집합을 지정하고 다른 모든 권한은 암시적으로 거부할 수 있습니다.  그러나 의도적인 악용으로부터 보호하기 위해 <xref:System.Security.Permissions.SecurityAction>를 통해 액세스를 금지하지 않는 것이 좋습니다.  해당 권한 부여 집합에 암시적으로 거부된 권한이 있는 호출된 어셈블리는 사용하려는 권한에 대해 <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName>를 수행하여 거부된 권한을 재정의할 수 있습니다.  예를 들어 <xref:System.Security.Permissions.UIPermission>만 허용하고 기본적으로 <xref:System.Security.Permissions.FileIOPermission>이 있는 어셈블리를 호출한 경우 어셈블리에서 단순히 <xref:System.Security.Permissions.FileIOPermission>에 대해 <xref:System.Security.Permissions.SecurityAction>를 수행하고 파일 작업을 할 수 있습니다.  참조된 어셈블리의 신뢰할 수 없는 코드에서 안전하게 리소스를 보호하는 유일한 방법은 해당 권한을 포함하지 않는 권한 부여 집합으로 코드를 실행하는 것입니다.  
  
### 코드 액세스 권한  
 코드 액세스 권한은 무단 사용으로부터 리소스 및 작업을 보호하는 데 사용되는 권한 개체입니다.  관리 코드에 보안 제한을 적용하는 공용 언어 런타임 메커니즘의 핵심 부분입니다.  
  
 각 코드 액세스 권한은 다음 권한 중 하나를 나타냅니다.  
  
-   파일 또는 환경 변수와 같은 보호된 리소스에 액세스할 수 있는 권한  
  
-   비관리 코드 액세스와 같은 보호된 작업을 수행할 수 있는 권한  
  
 모든 코드 액세스 권한은 코드에서 요구될 수 있으며, 런타임에서 코드에 부여할 권한\(있는 경우\)을 결정합니다.  
  
 각 코드 액세스 권한은 <xref:System.Security.CodeAccessPermission> 클래스에서 파생되므로 모든 코드 액세스 권한에 **Demand**, **Assert**, **Deny**, **PermitOnly**, **IsSubsetOf**, **Intersect**, 및 **Union**과 같은 공통 메서드가 있습니다.  
  
> [!IMPORTANT]
>  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서는 <xref:System.Security.Permissions.SecurityAction>, <xref:System.Security.Permissions.SecurityAction>, <xref:System.Security.Permissions.SecurityAction> 및 <xref:System.Security.Permissions.SecurityAction> 권한 요청 적용에 대한 런타임 지원이 제거되었습니다.  [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 이상을 기반으로 하는 코드에서는 이러한 요청을 사용하면 안 됩니다.  이 변경 내용과 기타 변경 내용에 대한 자세한 내용은 [보안 변경 내용](../../../docs/framework/security/security-changes.md)을 참조하세요.  
  
### 역할 기반 보안 권한  
 <xref:System.Security.Permissions.PrincipalPermission>은 사용자에게 지정된 ID가 있는지 또는 지정된 역할의 멤버인지를 확인하는 데 사용할 수 있는 역할 기반 보안 권한입니다.  **PrincipalPermission**은 .NET Framework 클래스 라이브러리에서 제공하는 유일한 역할 기반 보안 권한입니다.  
  
## 형식 안전성 및 보안  
 형식 안전 코드는 액세스 권한이 부여된 메모리 위치에만 액세스합니다.  이 토론에서 형식 안전성은 특히 메모리 형식 안전성을 가리키며 보다 광범위한 의미의 형식 안전성과 혼동해서는 안 됩니다. 예를 들어 형식 안전 코드는 다른 개체의 전용 필드에서 값을 읽을 수 없습니다.  잘 정의된 허용되는 방식으로만 형식에 액세스합니다.  
  
 JIT\(Just\-In\-Time\) 컴파일 중에 선택적 검증 프로세스는 네이티브 기계어 코드로 JIT 컴파일될 메서드의 메타데이터 및 MSIL\(Microsoft Intermediate Language\)을 검사하여 형식이 안전한지 확인합니다.  코드에 검증을 건너뛸 수 있는 권한이 있으면 이 프로세스를 건너뜁니다.  검증에 대한 자세한 내용은 [관리되는 실행 프로세스](../../../docs/standard/managed-execution-process.md)를 참조하세요.  
  
 형식 안전성 검증은 관리 코드를 실행하기 위한 필수 사항이 아니지만 형식 안전성은 어셈블리 격리 및 보안 적용에서 중요한 역할을 합니다.  코드 형식이 안전한 경우 공용 언어 런타임에서 어셈블리를 서로 완전히 격리할 수 있습니다.  이 격리는 어셈블리가 서로 부정적인 영향을 줄 수 없도록 하며 응용 프로그램 안정성을 향상시킵니다.  형식이 안전한 구성 요소는 서로 다른 수준에서 신뢰된 경우에도 동일한 프로세스에서 안전하게 실행할 수 있습니다.  코드 형식이 안전하지 않은 경우 원치 않는 부작용이 발생할 수 있습니다.  예를 들면, 관리 코드가 네이티브\(비관리\) 코드로 호출되어 부정적인 작업을 수행하는 것을 런타임에서 방지할 수 없습니다.  코드 형식이 안전하면 런타임의 보안 적용 메커니즘에서 권한이 없을 경우 네이티브 코드에 액세스하지 않도록 합니다.  형식이 안전하지 않은 모든 코드를 실행하려면 전달된 열거형 멤버 <xref:System.Security.Permissions.SecurityPermissionAttribute.SkipVerification%2A>과 함께 <xref:System.Security.Permissions.SecurityPermission>이 부여되어야 합니다.  
  
 자세한 내용은 [NIB: Writing Verifiably Type\-Safe Code](http://msdn.microsoft.com/ko-kr/d18f10ef-3b48-4f47-8726-96714021547b)을 참조하세요.  
  
## 보안 주체  
 보안 주체는 사용자의 ID 및 역할을 나타내고 사용자 대신 역할을 수행합니다.  .NET Framework의 역할 기반 보안은 다음 세 종류의 보안 주체를 지원합니다.  
  
-   일반 보안 주체는 Windows 사용자 및 역할과 독립적으로  존재하는 사용자와 역할을 나타냅니다.  
  
-   Windows 보안 주체는 Windows 사용자와 해당 역할\(또는 해당 Windows 그룹\)을 나타냅니다.  Windows 보안 주체는 다른 사용자를 가장할 수 있습니다. 이는 해당 사용자에게 속하는 ID를 제공하는 동안 보안 주체가 사용자 대신 리소스에 액세스할 수 있음을 의미합니다.  
  
-   해당 특정 응용 프로그램에 필요한 방식으로 응용 프로그램에서 사용자 지정 보안 주체를 정의할 수 있습니다.  보안 주체의 ID 및 역할의 기본 개념을 확장할 수 있습니다.  
  
 자세한 내용은 [Principal 개체 및 Identity 개체](../../../docs/standard/security/principal-and-identity-objects.md)를 참조하세요.  
  
## 인증  
 인증은 사용자 자격 증명을 검사하고 일부 권한에 대해 해당 자격 증명의 유효성을 검사하여 보안 주체의 ID를 찾고 확인하는 프로세스입니다.  인증 중에 얻은 정보를 코드에서 직접 사용할 수 있습니다.  .NET Framework 역할 기반 보안을 사용하여 현재 사용자를 인증하고 해당 보안 주체가 코드에 액세스할 수 있도록 할지 여부를 결정할 수도 있습니다.  특정 역할에 대해 보안 주체를 인증하는 방법의 예는 <xref:System.Security.Principal.WindowsPrincipal.IsInRole%2A?displayProperty=fullName> 메서드 오버로드를 참조하세요.  예를 들어 <xref:System.Security.Principal.WindowsPrincipal.IsInRole%28System.String%29?displayProperty=fullName> 오버로드를 사용하여 현재 사용자가 Administrators 그룹의 멤버인지 확인할 수 있습니다.  
  
 현재 다양한 인증 메커니즘이 사용되며, 대부분 .NET Framework 역할 기반 보안과 함께 사용할 수 있습니다.  가장 일반적으로 사용되는 메커니즘 중 일부는 기본, 다이제스트, Passport, 운영 체제\(예: NTLM 또는 Kerberos\) 또는 응용 프로그램 정의 메커니즘입니다.  
  
### 예제  
 다음 예제에서는 활성 보안 주체가 관리자여야 합니다.  `name` 매개 변수는 `null`이므로 관리자인 모든 사용자가 요구를 전달할 수 있습니다.  
  
> [!NOTE]
>  Windows Vista에서는 UAC\(사용자 계정 컨트롤\)가 사용자 권한을 결정합니다.  기본 제공 Administrators 그룹의 멤버인 경우 두 개의 런타임 액세스 토큰\(표준 사용자 액세스 토큰 및 관리자 액세스 토큰\)이 할당됩니다.  기본적으로 표준 사용자 역할이 지정됩니다.  관리자 권한이 필요한 코드를 실행하려면 먼저 표준 사용자에서 관리자로 권한을 높여야 합니다.  응용 프로그램 아이콘을 마우스 오른쪽 단추로 클릭하고 관리자로 실행하도록 지정하여 응용 프로그램을 시작하면 이 작업을 수행할 수 있습니다.  
  
 [!code-cpp[Classic PrincipalPermission Example#1](../../../samples/snippets/cpp/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/CPP/source.cpp#1)]
 [!code-csharp[Classic PrincipalPermission Example#1](../../../samples/snippets/csharp/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/CS/source.cs#1)]
 [!code-vb[Classic PrincipalPermission Example#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/VB/source.vb#1)]  
  
 다음 예제에서는 보안 주체 및 보안 주체가 사용할 수 있는 역할의 ID를 확인하는 방법을 보여 줍니다.  이 예제의 응용 프로그램은 현재 사용자가 응용 프로그램을 사용하도록 허용하는 역할에 있는지 확인하기 위한 것일 수 있습니다.  
  
 [!code-cpp[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/CPP/source.cpp#1)]
 [!code-csharp[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/CS/source.cs#1)]
 [!code-vb[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/VB/source.vb#1)]  
  
## 권한 부여  
 권한 부여는 보안 주체가 요청된 작업을 수행할 수 있는지 여부를 확인하는 프로세스입니다.  권한 부여는 인증 후 발생하며 보안 주체의 ID 및 역할에 대한 정보를 사용하여 보안 주체가 액세스할 수 있는 리소스를 확인합니다.  .NET Framework 역할 기반 보안을 사용하여 권한 부여를 구현할 수 있습니다.  
  
## internal virtual 키워드에 대한 보안 문제  
 C\#의 [internal](../Topic/internal%20\(C%23%20Reference\).md) [virtual](../Topic/virtual%20\(C%23%20Reference\).md) 한정자\(Visual Basic의 [Overloads](../Topic/Overloads%20\(Visual%20Basic\).md) [Overridable](../Topic/Overridable%20\(Visual%20Basic\).md) [Friend](../Topic/Friend%20\(Visual%20Basic\).md) 한정자\)로 표시된 멤버를 기준으로 응용 프로그램 보안을 설정하면 안 됩니다.  이러한 한정자로 표시된 멤버는 현재 어셈블리 내의 다른 멤버만 재정의할 수 있지만 이 규칙은 C\# 및 Visual Basic 언어에서만 적용됩니다.  런타임에서는 이 규칙이 적용되지 않습니다.  따라서 C\#의 **internal virtual** 및 Visual Basic의 **Overloads Overridable Friend**로 표시된 멤버를 Microsoft Intermediate Language 또는 이 규칙을 적용하지 않는 다른 언어로 재정의할 수 있습니다.  
  
## 참고 항목  
 [주요 보안 개념](../../../docs/standard/security/key-security-concepts.md)