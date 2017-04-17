---
title: "Performance Counters and In-Process Side-By-Side Applications | Microsoft Docs"
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
  - "performance counters"
  - "performance counters,and in-process side-by-side applications"
  - "performance,.NET Framework applications"
  - "performance monitoring,counters"
ms.assetid: 6888f9be-c65b-4b03-a07b-df7ebdee2436
caps.latest.revision: 26
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 26
---
# Performance Counters and In-Process Side-By-Side Applications
성능 모니터\(Perfmon.exe\)를 사용하면 런타임별로 성능 카운터를 구별할 수 있습니다.  이 항목에서는 이 기능을 사용하도록 설정하는 데 필요한 레지스트리 변경 내용에 대해 설명합니다.  
  
## 기본 동작  
 기본적으로 성능 모니터는 응용 프로그램별로 성능 카운터를 표시합니다.  그러나 다음과 같은 두 가지 시나리오에서는 이로 인해 문제가 발생합니다.  
  
-   이름이 같은 두 개의 응용 프로그램을 모니터링하는 경우.  예를 들어, 두 응용 프로그램의 이름이 myapp.exe이면 **인스턴스** 열에 한 응용 프로그램은 **myapp**로 표시되고 다른 한 응용 프로그램은 **myapp\#1**로 표시됩니다.  이 경우 성능 카운터와 응용 프로그램을 일치시키기가 어렵습니다.  즉, **myapp\#1**에 대해 수집된 데이터가 첫 번째 myapp.exe에 대한 것인지 아니면 두 번째 myapp.exe에 대한 것인지 명확하지 않습니다.  
  
-   응용 프로그램에서 여러 개의 공용 언어 런타임 인스턴스를 사용하는 경우.  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서는 In\-Process Side\-By\-Side 호스팅 시나리오를 지원합니다. 즉, 하나의 프로세스나 응용 프로그램에서 여러 개의 공용 언어 런타임 인스턴스를 로드할 수 있습니다.  myapp.exe라는 이름의 단일 응용 프로그램에서 두 개의 런타임 인스턴스를 로드하면 기본적으로 이러한 인스턴스는 **인스턴스** 열에 **myapp**와 **myapp\#1**로 지정됩니다.  이 경우 **myapp**와 **myapp\#1**이 같은 이름을 가진 두 개의 응용 프로그램을 나타내는지 아니면 두 개의 런타임이 있는 하나의 응용 프로그램을 나타내는지 명확하지 않습니다.  이름이 같은 여러 응용 프로그램에서 여러 개의 런타임을 로드하는 경우에는 훨씬 더 모호해집니다.  
  
 레지스트리 키를 설정하여 이러한 모호성을 제거할 수 있습니다.  [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]을 사용하여 개발한 응용 프로그램의 경우 이러한 레지스트리 변경을 통해 **인스턴스** 열에 표시되는 해당 응용 프로그램 이름에 프로세스 식별자와 런타임 인스턴스 식별자를 차례로 추가할 수 있습니다.  *application* 또는 *application*\#1 대신에, 응용 프로그램은 이제 *application*\_`p`*processID*\_`r`*runtimeID* 로**Instance**컬럼에서 인식됩니다.  이전 버전의 공용 언어 런타임을 사용하여 개발된 응용 프로그램인 경우, 그 인스턴스는 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]이 설치된 경우 *application\_*`p`*processID*로 표시됩니다.  
  
## In\-Process Side\-By\-Side 응용 프로그램의 성능 카운터  
 하나의 응용 프로그램에서 호스팅되는 여러 공용 언어 런타임 버전의 성능 카운터를 처리하려면 다음 표에 표시된 것처럼 단일 레지스트리 키 설정을 변경해야 합니다.  
  
|||  
|-|-|  
|키 이름|HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\.NETFramework\\Performance|  
|값 이름|ProcessNameFormat|  
|값 형식|REG\_DWORD|  
|값|1 \(0x00000001\)|  
  
 `ProcessNameFormat`의 값이 0이면 Perfmon.exe에서 응용 프로그램별로 성능 카운터를 표시하는 기본 동작을 사용한다는 의미입니다.  이 값을 1로 설정하면 Perfmon.exe에서 여러 버전의 응용 프로그램을 명확하게 구분하여 런타임별로 성능 카운터를 제공합니다.  다른 모든 값은 `ProcessNameFormat` 레지스트리 키 설정에 대해 지원되지 않으며 나중에 사용할 경우에 대비하여 예약되어 있습니다.  
  
 `ProcessNameFormat` 레지스트리 키 설정을 업데이트한 후에는 Perfmon.exe 또는 성능 카운터의 기타 모든 소비자를 다시 시작해야만 새 인스턴스 명명 기능이 올바르게 작동합니다.  
  
 다음 예제에서는 프로그래밍 방식으로 `ProcessNameFormat` 값을 변경하는 방법을 보여 줍니다.  
  
 [!code-csharp[Conceptual.PerfCounters.InProSxS#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.perfcounters.inprosxs/cs/regsetting1.cs#1)]
 [!code-vb[Conceptual.PerfCounters.InProSxS#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.perfcounters.inprosxs/vb/regsetting1.vb#1)]  
  
 이러한 레지스트리 변경을 수행할 때, Perfmon.exe는 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 를 *application*\_`p`*processID*\_`r`*runtimeID*로 대상으로 하는 응용 프로그램의 이름을 표시합니다. 여기서 *application* 는 응용 프로그램의 이름이고, *processID* 는 응용 프로그램의 식별자이고, *runtimeID* 는 공용 언어 런타임 식별자 입니다.  예를 들어 myapp.exe라는 이름의 응용 프로그램에서 두 개의 공용 언어 런타임 인스턴스를 로드하면 Perfmon.exe에서 한 인스턴스는 myapp\_p1416\_r10으로 식별되고 다른 한 인스턴스는 myapp\_p3160\_r10으로 식별될 수 있습니다.  런타임 식별자는 프로세스 내의 런타임을 구별하는 데만 사용되며 런타임에 대한 기타 다른 정보를 제공하지는 않습니다. 예를 들어, 런타임 ID는 런타임의 버전이나 SKU와 관계가 없습니다.  
  
 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]이 설치된 경우 이러한 레지스트리 변경이 이전 버전의 .NET Framework를 사용하여 개발한 응용 프로그램에도 영향을 주기 때문에  이것은 Perfmon.exe에서 *application\_*`p`*processID*로 나타납니다. 여기서 *application* 은 응용 프로그램 이름이고 *processID*는 프로세스 식별자입니다.  예를 들어, myapp.exe라는 이름을 가진 두 개의 응용 프로그램에 대한 성능 카운터를 모니터링하는 경우 한 성능 카운터는 myapp\_p23900으로 표시되고 다른 한 성능 카운터는 myapp\_p24908로 표시될 수 있습니다.  
  
> [!NOTE]
>  프로세스 식별자는 이전 버전의 런타임을 사용하는 이름이 같은 두 개의 응용 프로그램을 명확하게 구별할 수 있게 합니다.  이전 버전의 공용 언어 런타임에서는 Side\-By\-Side 시나리오를 지원하지 않기 때문에 이전 버전에는 런타임 식별자가 필요하지 않습니다.  
  
 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]이 없거나 제거된 경우 이 레지스트리 키를 설정해도 아무 효과가 없습니다.  즉, 이름이 같은 두 개의 응용 프로그램이 Perfmon.exe에서 *application* 와 *application\#1* 로 타납니다. \(예를 들어, **myapp** 와 **myapp\#1**\).