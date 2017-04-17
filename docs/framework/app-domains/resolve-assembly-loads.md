---
title: "어셈블리 로드 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "어셈블리[.NET Framework], 로드 해결"
  - "응용 프로그램 도메인, 어셈블리 로드"
  - "어셈블리 로드 해결"
  - "어셈블리[.NET Framework], 로딩"
  - "응용 프로그램 도메인, 어셈블리 로드 해결"
ms.assetid: 5099e549-f4fd-49fb-a290-549edd456c6a
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 어셈블리 로드 해결
.NET Framework는 어셈블리 로드에 대한 세부적인 제어가 필요한 응용 프로그램을 위해 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 이벤트를 제공합니다.  응용 프로그램은 이 이벤트를 처리함으로써 정상적인 검색 경로 외부에서 어셈블리를 Load 컨텍스트로 로드하고, 로드할 여러 어셈블리 버전을 선택하고, 동적 어셈블리를 생성하고, 반환하는 등의 작업을 수행할 수 있습니다.  이 항목에서는 <xref:System.AppDomain.AssemblyResolve> 이벤트를 처리하는 방법에 대한 지침을 제공합니다.  
  
> [!NOTE]
>  리플렉션 전용 컨텍스트에서 어셈블리 로드를 확인하려면 대신 <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=fullName> 이벤트를 사용하십시오.  
  
## AssemblyResolve 이벤트의 작동 방법  
 <xref:System.AppDomain.AssemblyResolve> 이벤트에 대한 처리기를 등록하면 런타임에서 어셈블리에 대한 이름별 바인딩을 실패할 때마다 이 처리기가 호출됩니다.  예를 들어 사용자 코드로부터 다음 메서드를 호출하면 <xref:System.AppDomain.AssemblyResolve> 이벤트가 발생할 수 있습니다.  
  
-   첫 번째 인수가 로드할 어셈블리의 표시 이름을 나타내는 문자열 즉, <xref:System.Reflection.Assembly.FullName%2A?displayProperty=fullName> 속성으로 반환된 문자열인 <xref:System.AppDomain.Load%2A?displayProperty=fullName> 메서드 오버로드 또는 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드 오버로드  
  
-   첫 번째 인수가 로드할 어셈블리를 식별하는 <xref:System.Reflection.AssemblyName> 개체인 <xref:System.AppDomain.Load%2A?displayProperty=fullName> 메서드 오버로드 또는 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드 오버로드  
  
-   <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName> 메서드 오버로드  
  
-   다른 응용 프로그램 도메인의 개체를 인스턴스화하는 <xref:System.AppDomain.CreateInstance%2A?displayProperty=fullName> 또는 <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=fullName> 메서드 오버로드  
  
### 이벤트 처리기의 수행 작업  
 <xref:System.AppDomain.AssemblyResolve> 이벤트 처리기는 <xref:System.ResolveEventArgs.Name%2A?displayProperty=fullName> 속성에서 로드할 어셈블리의 표시 이름을 수신합니다.  처리기가 어셈블리 이름을 인식할 수 없으면 null\(Visual Basic의 경우 `Nothing`, Visual C\+\+의 경우 `nullptr`\)을 반환합니다.  
  
 처리기가 어셈블리 이름을 인식할 수 있으면 요청을 만족시키는 어셈블리를 로드하고 반환할 수 있습니다.  다음 목록에서는 일부 샘플 시나리오를 보여 줍니다.  
  
-   처리기가 어셈블리의 버전 위치를 알고 있는 경우 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName> 또는 <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName> 메서드를 사용하여 어셈블리를 로드할 수 있으며, 로드가 성공하면 로드한 어셈블리를 반환할 수 있습니다.  
  
-   처리기가 바이트 배열로 저장된 어셈블리의 데이터베이스에 액세스할 수 있으면 바이트 배열을 사용하는 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드 오버로드 중 하나를 사용하여 바이트 배열을 로드할 수 있습니다.  
  
-   처리기가 동적 어셈블리를 생성하고 이를 반환할 수 있습니다.  
  
> [!NOTE]
>  처리기는 어셈블리를 Loadfrom 컨텍스트 또는 Load 컨텍스트로 로드하거나 컨텍스트 없이 로드해야 합니다.  처리기가 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=fullName> 또는 <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=fullName> 메서드를 사용하여 리플렉션 전용 컨텍스트로 어셈블리를 로드할 경우 <xref:System.AppDomain.AssemblyResolve> 이벤트가 발생시킨 로드 시도가 실패합니다.  
  
 적합한 어셈블리를 반환하는 작업은 이벤트 처리기에서 수행됩니다.  처리기는 <xref:System.ResolveEventArgs.Name%2A?displayProperty=fullName> 속성 값을 <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29> 생성자로 전달하여 요청한 어셈블리의 표시 이름을 구문 분석할 수 있습니다.  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 처리기가 <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=fullName> 속성을 사용하여 현재 요청이 다른 어셈블리에 종속되는지 여부를 확인할 수 있습니다.  이 정보는 종속성을 만족시키는 어셈블리를 식별하는 데 도움이 됩니다.  
  
 이벤트 처리기는 요청된 것과 다른 버전의 어셈블리를 반환할 수 있습니다.  
  
 대부분의 경우 처리기로 반환되는 어셈블리는 처리기가 로드되는 컨텍스트에 관계없이 Load 컨텍스트로 표시됩니다.  예를 들어 처리기가 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName> 메서드를 사용하여 어셈블리를 Loadfrom 컨텍스트로 로드할 경우 처리기가 어셈블리를 반환할 때 어셈블리가 Load 컨텍스트로 표시됩니다.  하지만 다음과 같은 경우에는 처리기가 어셈블리를 반환할 때 컨텍스트 없이 어셈블리가 표시됩니다.  
  
-   처리기가 어셈블리를 컨텍스트 없이 로드할 경우  
  
-   <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=fullName> 속성이 null인 경우  
  
-   요청 어셈블리\(즉, <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=fullName> 속성으로 반환되는 어셈블리\)가 컨텍스트 없이 로드된 경우  
  
 컨텍스트에 대한 자세한 내용은 <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=fullName> 메서드 오버로드를 참조하십시오.  
  
 동일 어셈블리의 여러 버전을 동일한 응용 프로그램 도메인으로 로드할 수 있습니다.  이 방식은 서식 지정 문제를 일으킬 수 있으므로 권장되지 않습니다.  [최선의 어셈블리 로드 방법](../../../docs/framework/deployment/best-practices-for-assembly-loading.md)를 참조하십시오.  
  
### 이벤트 처리기로 수행해서는 안되는 작업  
 <xref:System.AppDomain.AssemblyResolve> 이벤트를 처리하는 기본 규칙은 인식할 수 없는 어셈블리를 반환하도록 시도하지 않아야 한다는 것입니다.  처리기를 작성할 때는 이벤트를 발생시킬 수 있는 어셈블리가 무엇인지 알아야 합니다.  다른 어셈블리의 경우 처리기에서 null을 반환해야 합니다.  
  
> [!IMPORTANT]
>  [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]부터 <xref:System.AppDomain.AssemblyResolve> 이벤트는 위성 어셈블리에 대해 발생합니다.  이러한 변경 내용은 이전 버전의 .NET Framework에 맞게 작성된 이벤트 처리기가 모든 어셈블리 로드 요청을 확인하려고 시도할 경우 이벤트 처리기에 영향을 줍니다.  인식할 수 없는 어셈블리를 무시하는 이벤트 처리기에는 이러한 변경으로 인한 영향이 없습니다. 이러한 이벤트 처리기는 null을 반환하고 일반적인 fallback 메커니즘이 수행됩니다.  
  
 어셈블리를 로드할 때 이벤트 처리기는 <xref:System.AppDomain.AssemblyResolve> 이벤트가 재귀적으로 발생하도록 만들 수 있는 <xref:System.AppDomain.Load%2A?displayProperty=fullName> 또는 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드 오버로드를 사용해서는 안됩니다. 그렇지 않으면 스택 오버플로가 발생할 수 있습니다. 이 항목의 앞부분에 제공된 목록을 참조하십시오. 로드 요청에 대해 예외 처리를 제공한 경우에도, 모든 이벤트 처리기가 어셈블리를 반환할 때까지 예외가 throw되지 않기 때문에 마찬가지로 문제가 발생합니다.  따라서 다음 코드는 `MyAssembly`를 찾을 수 없는 경우 스택 오버플로를 일으킵니다.  
  
 [!code-cpp[AssemblyResolveRecursive#1](../../../samples/snippets/cpp/VS_Snippets_CLR/assemblyresolverecursive/cpp/example.cpp#1)]
 [!code-csharp[AssemblyResolveRecursive#1](../../../samples/snippets/csharp/VS_Snippets_CLR/assemblyresolverecursive/cs/example.cs#1)]
 [!code-vb[AssemblyResolveRecursive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/assemblyresolverecursive/vb/example.vb#1)]  
  
## 참고 항목  
 [최선의 어셈블리 로드 방법](../../../docs/framework/deployment/best-practices-for-assembly-loading.md)   
 [응용 프로그램 도메인 사용](../../../docs/framework/app-domains/use.md)