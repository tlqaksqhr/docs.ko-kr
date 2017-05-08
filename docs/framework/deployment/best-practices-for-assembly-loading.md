---
title: "최선의 어셈블리 로드 방법 | Microsoft Docs"
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
  - "어셈블리, 바인딩"
  - "어셈블리, 로드"
  - "어셈블리 로딩 오류"
  - "기본 로드 컨텍스트"
  - "로드 컨텍스트"
  - "로드 컨텍스트"
  - "LoadFrom 메서드"
  - "LoadWithPartialName 메서드"
  - "TypeLoadException 클래스, 절"
ms.assetid: 68d1c539-6a47-4614-ab59-4b071c9d4b4c
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# 최선의 어셈블리 로드 방법
이 문서에서는 <xref:System.InvalidCastException>, <xref:System.MissingMethodException> 및 기타 오류를 발생시킬 수 있는 형식 ID 문제를 방지하는 방법에 대해 설명합니다.  이 문서에는 다음과 같은 권장 사항도 설명되어 있습니다.  
  
-   [로드 컨텍스트의 장점 및 단점 이해](#load_contexts)  
  
-   [부분 어셈블리 이름에 대한 바인딩 방지](#avoid_partial_names)  
  
-   [어셈블리가 여러 컨텍스트에 로드되지 않도록 방지](#avoid_loading_into_multiple_contexts)  
  
-   [어셈블리의 여러 버전이 동일한 컨텍스트에 로드되지 않도록 방지](#avoid_loading_multiple_versions)  
  
-   [기본 로드 컨텍스트로의 전환 고려](#switch_to_default)  
  
 첫 번째 권장 사항 [로드 컨텍스트의 장점 및 단점 이해](#load_contexts)에서는 다른 권장 사항을 이해하는 데 필요한 배경 정보를 제공합니다. 이러한 권장 사항을 이해하려면 로드 컨텍스트에 대한 지식이 있어야 합니다.  
  
<a name="load_contexts"></a>   
## 로드 컨텍스트의 장점 및 단점 이해  
 응용 프로그램 도메인 내에서 어셈블리는 세 가지 컨텍스트 중 하나에 로드하거나 컨텍스트 없이 로드할 수 있습니다.  
  
-   기본 로드 컨텍스트에는 전역 어셈블리 캐시, 런타임이 SQL Server 등에서 호스팅되는 경우 호스트 어셈블리 저장소 및 응용 프로그램 도메인의 <xref:System.AppDomainSetup.ApplicationBase%2A> 및 <xref:System.AppDomainSetup.PrivateBinPath%2A>를 검색하여 찾은 어셈블리가 들어 있습니다.  <xref:System.Reflection.Assembly.Load%2A> 메서드의 오버로드는 대부분 어셈블리를 이 컨텍스트에 로드합니다.  
  
-   위치에서 로드 컨텍스트에는 로더에서 검색되지 않는 위치에서 로드한 어셈블리가 들어 있습니다.  예를 들어, 응용 프로그램 경로에 있지 않은 디렉터리에 추가 기능이 설치되어 있을 수 있습니다.  <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>, <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=fullName> 및 <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=fullName>는 경로를 기준으로 로드되는 메서드의 예입니다.  
  
-   리플렉션 전용 컨텍스트에는 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> 및 <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> 메서드로 로드되는 어셈블리가 들어 있습니다.  이 컨텍스트의 코드는 실행될 수 없으므로 여기서는 이 컨텍스트에 대해 설명하지 않습니다.  자세한 내용은 [방법: 리플렉션 전용 컨텍스트에 어셈블리 로드](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)을 참조하십시오.  
  
-   리플렉션 내보내기를 사용하여 임시 동적 어셈블리를 생성한 경우 어셈블리는 어떤 컨텍스트에도 있지 않습니다.  또한 <xref:System.Reflection.Assembly.LoadFile%2A> 메서드를 사용하여 로드되는 어셈블리의 대부분은 컨텍스트 없이 로드되고, 바이트 배열에서 로드되는 어셈블리는 정책 적용 후 ID를 통해 전역 어셈블리 캐시에 있는 것으로 확인되지 않는 한 컨텍스트 없이 로드됩니다.  
  
 실행 컨텍스트에는 장점과 단점이 있으며 이에 대해서는 다음 단원에서 설명합니다.  
  
### 기본 로드 컨텍스트  
 어셈블리가 기본 로드 컨텍스트에 로드되면 해당 어셈블리의 종속 항목이 자동으로 로드됩니다.  어셈블리가 기본 로드 컨텍스트 또는 위치에서 로드 컨텍스트에 있는 경우 기본 로드 컨텍스트에 로드되는 종속 항목을 자동으로 찾습니다.  어셈블리 ID로 로드하면 알려지지 않은 어셈블리 버전이 사용되지 않게 되므로 응용 프로그램의 안정성이 향상됩니다\([부분 어셈블리 이름에 대한 바인딩 방지](#avoid_partial_names) 단원 참조\).  
  
 기본 로드 컨텍스트를 사용할 경우 다음과 같은 단점이 있습니다.  
  
-   다른 컨텍스트에 로드되는 종속 항목을 사용할 수 없습니다.  
  
-   검색 경로 밖의 위치에 있는 어셈블리를 기본 로드 컨텍스트에 로드할 수 없습니다.  
  
### 위치에서 로드 컨텍스트  
 위치에서 로드 컨텍스트를 사용하면 응용 프로그램 경로에 있지 않아 검색에 포함되지 않는 경로에서 어셈블리를 로드할 수 있습니다.  이 경로 정보는 컨텍스트에 의해 유지되기 때문에 해당 경로에서 종속 항목을 찾아 로드할 수 있습니다.  또한 이 컨텍스트의 어셈블리에서는 기본 로드 컨텍스트에 로드되는 종속 항목을 사용할 수 있습니다.  
  
 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName> 메서드 또는 경로에 따라 로드되는 다른 메서드 중 하나를 사용하여 어셈블리를 로드할 경우 다음과 같은 단점이 있습니다.  
  
-   같은 ID를 가진 어셈블리가 이미 로드되어 있으면 <xref:System.Reflection.Assembly.LoadFrom%2A>은 지정된 경로가 다른 경우에도 로드된 어셈블리를 반환합니다.  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A>을 사용하여 어셈블리를 로드한 이후 기본 로드 컨텍스트에 있는 어셈블리 중 표시 이름이 같은 어셈블리를 로드하려고 하면 로드 작업이 실패합니다.  어셈블리를 deserialize하는 경우에 이 문제가 발생할 수 있습니다.  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A>을 사용하여 어셈블리를 로드할 경우 ID가 같지만 위치가 다른 어셈블리가 검색 경로에 포함되어 있으면 <xref:System.InvalidCastException>, <xref:System.MissingMethodException> 또는 기타 예기치 않은 동작이 발생할 수 있습니다.  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A>을 사용하려면 지정된 경로에 대해 <xref:System.Security.Permissions.FileIOPermissionAccess?displayProperty=fullName>와 <xref:System.Security.Permissions.FileIOPermissionAccess?displayProperty=fullName> 또는 <xref:System.Net.WebPermission>이 있어야 합니다.  
  
-   어셈블리에 대한 네이티브 이미지가 있는 경우 이 이미지는 사용되지 않습니다.  
  
-   어셈블리는 도메인 중립으로 로드할 수 없습니다.  
  
-   .NET Framework 버전 1.0과 1.1에서는 정책이 적용되지 않습니다.  
  
### 컨텍스트 없음  
 리플렉션 내보내기를 통해 생성되는 임시 어셈블리를 위해 선택할 수 있는 유일한 옵션은 컨텍스트 없이 로드하는 것입니다.  컨텍스트 없는 로드는 동일한 ID의 여러 어셈블리를 응용 프로그램 도메인 하나에 로드할 수 있는 유일한 방법이기도 합니다.  이와 같이 로드하면 검색에 따른 비용이 발생하지 않는 장점이 있습니다.  
  
 바이트 배열에서 로드되는 어셈블리의 경우 정책이 적용될 때 설정되는 어셈블리의 ID가 전역 어셈블리 캐시의 ID와 일치하지 않으면 컨텍스트 없이 로드됩니다. 일치할 경우에는 전역 어셈블리 캐시에서 어셈블리가 로드됩니다.  
  
 컨텍스트 없이 어셈블리를 로드할 경우 다음과 같은 단점이 있습니다.  
  
-   <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 이벤트를 처리하지 않는 한 다른 어셈블리에서는 컨텍스트 없이 로드되는 어셈블리에 바인딩할 수 없습니다.  
  
-   종속 항목은 자동으로 로드되지 않습니다.  종속 항목을 컨텍스트 없이 미리 로드하거나 기본 로드 컨텍스트에 미리 로드할 수 있습니다. 또는 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 이벤트를 처리하여 종속 항목을 로드할 수도 있습니다.  
  
-   ID가 동일한 여러 어셈블리를 컨텍스트 없이 로드하면 ID가 동일한 어셈블리를 여러 컨텍스트에 로드하여 발생하는 것과 유사한 형식 ID 문제가 발생할 수 있습니다.  [어셈블리가 여러 컨텍스트에 로드되지 않도록 방지](#avoid_loading_into_multiple_contexts)를 참조하십시오.  
  
-   어셈블리에 대한 네이티브 이미지가 있는 경우 이 이미지는 사용되지 않습니다.  
  
-   어셈블리는 도메인 중립으로 로드할 수 없습니다.  
  
-   .NET Framework 버전 1.0과 1.1에서는 정책이 적용되지 않습니다.  
  
<a name="avoid_partial_names"></a>   
## 부분 어셈블리 이름에 대한 바인딩 방지  
 부분 이름 바인딩은 어셈블리를 로드할 때 어셈블리 표시 이름\(<xref:System.Reflection.Assembly.FullName%2A>\)의 일부만 지정할 경우 발생합니다.  이러한 예로는 버전, 문화권 및 공개 키 토큰을 누락한 채 어셈블리의 단순한 이름만 지정하여 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드를 호출하는 경우가 있습니다.  또는 <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName> 메서드를 호출하는 경우를 예로 들 수 있습니다. 이 메서드는 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드를 먼저 호출한 다음, 어셈블리를 찾지 못하면 전역 어셈블리 캐시를 검색하여 해당 어셈블리의 사용 가능한 최신 버전을 로드합니다.  
  
 부분 이름 바인딩은 다음과 같은 여러 문제를 발생시킬 수 있습니다.  
  
-   <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName> 메서드는 단순한 이름이 동일한 다른 어셈블리를 로드할 수도 있습니다.  예를 들어, 두 응용 프로그램에서 단순한 이름이 `GraphicsLibrary`로 동일하지만 완전히 서로 다른 두 어셈블리를 전역 어셈블리 캐시에 설치하는 경우도 있습니다.  
  
-   실제로 로드되는 어셈블리가 이전 버전과 호환되지 않을 수 있습니다.  예를 들어, 버전을 지정하지 않으면 프로그램에서 원래 사용하도록 되어 있는 버전보다 훨씬 높은 버전이 로드될 수 있습니다.  로드된 높은 버전에서 변경된 사항으로 인해 응용 프로그램에서 오류가 발생할 수 있습니다.  
  
-   실제로 로드되는 어셈블리가 이후 버전과 호환되지 않을 수 있습니다.  예를 들어, 어셈블리의 최신 버전을 사용하여 응용 프로그램을 빌드 및 테스트했지만 부분 바인딩으로 인해 응용 프로그램에서 사용하는 기능이 결여된 훨씬 낮은 버전이 로드될 수 있습니다.  
  
-   새 응용 프로그램 설치로 인해 기존 응용 프로그램이 중단될 수 있습니다.  <xref:System.Reflection.Assembly.LoadWithPartialName%2A> 메서드를 사용하는 응용 프로그램의 경우 공유 어셈블리의 호환되지 않는 새 버전을 설치하면 작동이 중단될 수 있습니다.  
  
-   예기치 않은 종속 항목 로드가 발생할 수 있습니다.  종속 항목을 공유하는 두 어셈블리를 부분 바인딩을 통해 로드하면 빌드 또는 테스트에 사용되지 않은 구성 요소를 한 어셈블리에서 사용하게 될 수도 있습니다.  
  
 <xref:System.Reflection.Assembly.LoadWithPartialName%2A> 메서드는 문제를 발생시킬 수 있기 때문에 사용되지 않습니다.  대신 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드를 사용하고 전체 어셈블리 표시 이름을 지정하는 것이 좋습니다.  [로드 컨텍스트의 장점 및 단점 이해](#load_contexts) 및 [기본 로드 컨텍스트로의 전환 고려](#switch_to_default)를 참조하십시오.  
  
 어셈블리 로드를 간편하게 해 주는 <xref:System.Reflection.Assembly.LoadWithPartialName%2A> 메서드를 사용하려는 경우에는 어셈블리의 알 수 없는 버전을 자동으로 사용하면 예측할 수 없는 동작 및 보안 허점이 발생하고 누락된 어셈블리를 통해 더 나은 사용자 환경을 제공할 수 있음을 알려 주는 오류 메시지가 응용 프로그램 실패 시 표시되도록 하는 것이 좋습니다.  
  
<a name="avoid_loading_into_multiple_contexts"></a>   
## 어셈블리가 여러 컨텍스트에 로드되지 않도록 방지  
 어셈블리를 여러 컨텍스트에 로드하면 형식 ID 문제가 발생할 수 있습니다.  동일한 어셈블리의 동일한 형식이 서로 다른 두 컨텍스트에 로드되면 동일한 이름의 서로 다른 두 형식이 로드되는 것과 마찬가지입니다.  한 형식을 다른 형식으로 캐스팅하려고 하면 <xref:System.InvalidCastException> 예외가 throw되고 형식 `MyType`을 형식 `MyType`으로 캐스팅할 수 없다는 혼란스러운 메시지가 나타납니다.  
  
 예를 들어, `ICommunicate` 인터페이스가 `Utility`라는 어셈블리에 선언되어 있고, 이 어셈블리를 프로그램 및 해당 프로그램에서 로드하는 다른 어셈블리가 참조하는 경우를 가정해 봅니다.  이러한 다른 어셈블리에는 `ICommunicate` 인터페이스를 구현하는 형식이 들어 있고 응용 프로그램에서는 이 형식을 사용할 수 있습니다.  
  
 이제 프로그램을 실행하면 어떻게 되는지 살펴봅니다.  프로그램에서 참조하는 어셈블리는 기본 로드 컨텍스트에 로드됩니다.  <xref:System.Reflection.Assembly.Load%2A> 메서드를 사용하여 ID로 대상 어셈블리를 로드하면 해당 어셈블리 및 종속 항목이 기본 로드 컨텍스트에 있게 됩니다.  프로그램 및 대상 어셈블리 모두 동일한 `Utility` 어셈블리를 사용합니다.  
  
 앞의 경우와 달리 <xref:System.Reflection.Assembly.LoadFile%2A> 메서드를 사용하여 파일 경로를 기준으로 대상 어셈블리를 로드하는 경우를 가정해 봅니다.  이 경우 어셈블리가 컨텍스트 없이 로드되고 종속 항목은 자동으로 로드되지 않습니다.  <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 이벤트 처리기가 종속 항목을 제공하도록 할 수도 있습니다. 이렇게 하면 <xref:System.Reflection.Assembly.LoadFile%2A> 메서드를 사용하여 컨텍스트 없이 `Utility` 어셈블리가 로드될 수 있습니다.  이제 대상 어셈블리에 들어 있는 형식의 인스턴스를 만들어 `ICommunicate` 형식 변수에 할당하려고 하면 런타임에서는 `Utility` 어셈블리의 두 복사본에 있는 `ICommunicate` 인터페이스를 서로 다른 형식으로 간주하기 때문에 <xref:System.InvalidCastException> 예외가 throw됩니다.  
  
 이 밖에도 어셈블리가 여러 컨텍스트에 로드될 수 있는 여러 가지 시나리오가 있습니다.  충돌을 방지하기 위한 최선의 방법은 대상 어셈블리를 응용 프로그램 경로에 재배치하고 <xref:System.Reflection.Assembly.Load%2A> 메서드를 전체 표시 이름과 함께 사용하는 것입니다.  재배치된 어셈블리는 기본 로드 컨텍스트에 로드되고 두 어셈블리에서는 동일한 `Utility` 어셈블리를 사용하게 됩니다.  
  
 대상 어셈블리를 응용 프로그램 경로 밖에 두어야 할 경우에는 <xref:System.Reflection.Assembly.LoadFrom%2A> 메서드를 사용하여 위치에서 로드 컨텍스트에 로드하면 됩니다.  대상 어셈블리가 응용 프로그램의 `Utility` 어셈블리에 대한 참조를 사용하여 컴파일된 경우 대상 어셈블리는 응용 프로그램에서 기본 로드 컨텍스트에 로드한 `Utility` 어셈블리를 사용하게 됩니다.  응용 프로그램 경로 밖에 있는 `Utility` 어셈블리의 복사본에 대해 대상 어셈블리가 종속성을 갖는 경우 문제가 발생할 수 있습니다.  응용 프로그램에서 `Utility` 어셈블리를 로드하기 전에 이 어셈블리가 위치에서 로드 컨텍스트에 로드되어 있으면 응용 프로그램의 로드가 실패하게 됩니다.  
  
 [기본 로드 컨텍스트로의 전환 고려](#switch_to_default) 단원에서는 <xref:System.Reflection.Assembly.LoadFile%2A> 및 <xref:System.Reflection.Assembly.LoadFrom%2A> 같은 파일 경로 로드 대신 사용 가능한 다른 방법에 대해 설명합니다.  
  
<a name="avoid_loading_multiple_versions"></a>   
## 어셈블리의 여러 버전이 동일한 컨텍스트에 로드되지 않도록 방지  
 어셈블리의 여러 버전을 단일 로드 컨텍스트에 로드하면 형식 ID 문제가 발생할 수 있습니다.  동일한 어셈블리의 두 버전이 서로 다른 두 컨텍스트에 로드되면 동일한 이름의 서로 다른 두 형식이 로드되는 것과 마찬가지입니다.  한 형식을 다른 형식으로 캐스팅하려고 하면 <xref:System.InvalidCastException> 예외가 throw되고 형식 `MyType`을 형식 `MyType`으로 캐스팅할 수 없다는 혼란스러운 메시지가 나타납니다.  
  
 예를 들어, 프로그램에서 `Utility` 어셈블리의 특정 버전을 직접 로드한 후, `Utility` 어셈블리의 다른 버전을 로드하는 다른 어셈블리를 로드할 수 있습니다.  또는 코딩 오류로 인해 응용 프로그램의 서로 다른 두 코드 경로에서 어셈블리의 서로 다른 버전이 로드될 수도 있습니다.  
  
 기본 로드 컨텍스트에서 이 문제는 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드를 사용하여 서로 다른 버전 번호를 포함하는 전체 어셈블리 표시 이름을 지정하는 경우에 발생할 수 있습니다.  컨텍스트 없이 로드되는 어셈블리의 경우 이 문제는 <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName> 메서드를 사용하여 여러 경로에서 동일한 어셈블리를 로드하면 발생할 수 있습니다.  런타임에서는 서로 다른 경로에서 로드되는 두 어셈블리의 ID가 동일한 경우에도 두 어셈블리를 서로 다른 어셈블리로 간주합니다.  
  
 어셈블리의 버전이 여러 개이면 형식 ID 문제만 발생하는 것이 아닙니다. 어셈블리의 특정 버전에서 로드되는 형식이 코드에 전달되지만 이 코드에서는 다른 버전의 해당 형식이 사용되는 경우 <xref:System.MissingMethodException>이 발생할 수 있습니다.  예를 들어, 코드에서는 이후 버전에 추가된 메서드가 사용될 수도 있습니다.  
  
 형식의 동작이 버전 간에 다른 경우 사소한 오류가 발생할 수 있습니다.  예를 들어, 메서드에서 예기치 않은 예외를 throw하거나 예기치 않은 값을 반환할 수 있습니다.  
  
 코드를 신중하게 검토하여 특정 어셈블리의 한 가지 버전만 로드되도록 합니다.  <xref:System.AppDomain.GetAssemblies%2A?displayProperty=fullName> 메서드를 사용하면 특정 시점에 로드되어 있는 어셈블리를 확인할 수 있습니다.  
  
<a name="switch_to_default"></a>   
## 기본 로드 컨텍스트로의 전환 고려  
 응용 프로그램의 어셈블리 로드 및 배포 패턴을 검토합니다.  바이트 배열에서 로드되는 어셈블리를 제거할 수 있고,  어셈블리를 검색 경로로 이동할 수 있는지 확인합니다.  어셈블리가 전역 어셈블리 캐시 또는 응용 프로그램 도메인의 검색 경로, 즉 <xref:System.AppDomainSetup.ApplicationBase%2A> 및 <xref:System.AppDomainSetup.PrivateBinPath%2A>에 있으면 ID로 어셈블리를 로드할 수 있습니다.  
  
 모든 어셈블리를 검색 경로에 배치할 수 없으면 .NET Framework 추가 기능 모델 사용, 전역 어셈블리 캐시에 어셈블리 배치 또는 응용 프로그램 도메인 만들기 등의 다른 방법을 고려해 봅니다.  
  
### .NET Framework 추가 기능 모델 사용 고려  
 일반적으로 응용 프로그램 기본 디렉터리에 설치되지 않는 추가 기능을 구현하기 위해 위치에서 로드 컨텍스트를 사용 중이면 .NET Framework 추가 기능 모델을 사용합니다.  이 모델에서는 응용 프로그램 도메인 또는 프로세스 수준에서 격리를 제공하며 사용자가 응용 프로그램 도메인을 직접 관리할 필요가 없습니다.  추가 기능 모델에 대한 자세한 내용은 [추가 기능 및 확장성](../../../ml/index.xml)을 참조하십시오.  
  
### 전역 어셈블리 캐시 사용 고려  
 응용 프로그램 기본 디렉터리 밖에 있는 공유 어셈블리 경로의 이점을 활용하려면 어셈블리를 전역 어셈블리 캐시에 배치합니다. 이렇게 하면 기본 로드 컨텍스트의 장점을 잃거나 다른 컨텍스트의 단점을 감수하지 않아도 됩니다.  
  
### 응용 프로그램 도메인 사용 고려  
 일부 어셈블리를 응용 프로그램의 검색 경로에 배포할 수 없는 것으로 확인되면 이러한 어셈블리를 위한 새 응용 프로그램 도메인을 만드는 것이 좋습니다.  <xref:System.AppDomainSetup>을 사용하여 새 응용 프로그램 도메인을 만들고, <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=fullName> 속성을 사용하여 로드할 어셈블리가 있는 경로를 지정합니다.  검색할 디렉터리가 여러 개 있으면 <xref:System.AppDomainSetup.ApplicationBase%2A>를 루트 디렉터리로 설정하고 <xref:System.AppDomainSetup.PrivateBinPath%2A?displayProperty=fullName> 속성을 사용하여 검색할 하위 디렉터리를 지정하면 됩니다.  또는 여러 응용 프로그램 도메인을 만들고 각 응용 프로그램 도메인의 <xref:System.AppDomainSetup.ApplicationBase%2A>를 해당 어셈블리의 적절한 경로로 설정할 수도 있습니다.  
  
 이러한 어셈블리를 로드하는 데는 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName> 메서드를 사용할 수 있습니다.  이제 어셈블리가 검색 경로에 있기 때문에 위치에서 로드 컨텍스트 대신 기본 로드 컨텍스트에 어셈블리가 로드됩니다.  그러나 항상 올바른 버전이 사용되도록 하려면 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드를 대신 사용하고 전체 어셈블리 표시 이름을 제공하는 것이 좋습니다.  
  
## 참고 항목  
 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>   
 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>   
 <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName>   
 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName>   
 [추가 기능 및 확장성](../../../ml/index.xml)