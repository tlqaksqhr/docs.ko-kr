---
title: "&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
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
  - "<forcePerformanceCounterUniqueSharedMemoryReads> 요소"
  - "forcePerformanceCounterUniqueSharedMemoryReads 요소"
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; 요소
특정 범주의 공유 메모리 또는 전역 메모리에서 성능 카운터 데이터를 로드할 것인지 결정하는 데 PerfCounter.dll이 .NET Framework 버전 1.1 응용 프로그램의 CategoryOptions 레지스트리 설정을 사용할지 여부를 지정합니다.  
  
## 구문  
  
```  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 특정 범주의 공유 메모리 또는 전역 메모리에서 성능 카운터 데이터를 로드할 것인지 결정하는 데 PerfCounter.dll이 CategoryOptions 레지스트리 설정을 사용할지 여부를 나타냅니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`false`|PerfCounter.dll은 CategoryOptions 레지스트리 설정을 사용하지 않으며 기본값입니다.|  
|`true`|PerfCounter.dll은 CategoryOptions 레지스트리 설정을 사용합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 이전 버전의 .NET Framework에서 로드된 PerfCounter.dll의 버전은 프로세스에 로드된 런타임에 해당했습니다.  컴퓨터에 .NET Framework 버전 1.1 및 [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)]이 설치되어 있을 경우 .NET Framework 1.1 응용 프로그램은 PerfCounter.dll의 .NET Framework 1.1 버전을 로드합니다.  [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]로 시작하여 PerfCounter.dll의 설치된 최신 버전이 로드됩니다.  즉, .NET Framework 1.1 응용 프로그램은 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]이 컴퓨터에 설치된 경우 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 버전의 PerfCounter.dll을 로드합니다.  
  
 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]로 시작하여 성능 카운터를 사용하면 PerfCounter.dll은 범주 특정 공유 메모리 또는 전역 공유 메모리에서 읽어야 할지 여부를 확인하기 위해 각 공급자에 대한 CategoryOptions 레지스트리 항목이 있는지 확인합니다.  .NET Framework 1.1 PerfCounter.dll은 특정 범주의 공유 메모리를 인식하지 못하기 때문에 레지스트리 항목을 읽지 않고 항상 전역 공유 메모리에서 읽습니다.  
  
 이전 버전과의 호환성을 위해 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll은 .NET Framework 1.1 응용 프로그램을 실행할 때 CategoryOptions 레지스트리 항목을 확인하지 않습니다.  .NET Framework 1.1 PerfCounter.dll과 마찬가지로 단순히 전역 공유 메모리를 사용합니다.  그러나 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll에 `<forcePerformanceCounterUniqueSharedMemoryReads>` 요소를 사용하여 레지스트리 설정을 확인하도록 지시할 수 있습니다.  
  
> [!NOTE]
>  `<forcePerformanceCounterUniqueSharedMemoryReads>` 요소를 사용한다고 범주 특정 공유 메모리 사용이 보장되지 않습니다.  `true`에 활성화된 설정만 PerfCounter.dll이 CategoryOptions 레지스트리 설정을 참조하도록 합니다.  CategoryOptions의 기본 설정은 특정 범주의 공유 메모리를 사용하는 것이지만 전역 공유 메모리를 사용해야 함을 나타내기 위해 CategoryOptions를 변경할 수 있습니다.  
  
 CategoryOptions 설정을 포함하는 레지스트리 키는 HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\\<categoryName\>\\Performance입니다.  기본적으로 CategoryOptions은 3으로 설정되어, PerfCounter.dll에 범주 특정 공유 메모리를 사용하도록 지시합니다.  CategoryOptions가 0으로 설정된 경우 PerfCounter.dll은 전역 공유 메모리를 사용합니다.  인스턴스 데이터는 만드는 인스턴스의 이름을 다시 사용할 인스턴스와 동일한 경우에만 다시 사용됩니다.  모든 버전의 범주에 쓸 수 있습니다.  CategoryOptions가 1로 설정된 경우 전역 공유 메모리가 사용되지만 범주 이름이 다시 사용하는 범주와 길이가 같은 경우 인스턴스 데이터를 다시 사용할 수 있습니다.  
  
 설정 0과 1은 성능 카운터 메모리의 메모리 누수 및 채우기를 초래할 수 있습니다.  
  
## 예제  
 다음 예제에서는 특정 범주의 공유 메모리를 사용해야 할지 여부를 결정하기 위해 PerfCounter.dll이 CategoryOptions 레지스트리 항목을 참조할지 지정하는 방법을 보여 줍니다.  
  
```  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)