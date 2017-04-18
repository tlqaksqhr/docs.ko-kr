---
title: "&lt;performanceCounters&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<perfomanceCounters> 요소"
  - "performanceCounters 요소"
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# &lt;performanceCounters&gt; 요소
성능 카운터에서 공유하는 전역 메모리의 크기를 지정합니다.  
  
## 구문  
  
```  
<performanceCounters filemappingsize="524288" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|filemappingsize|필수 특성입니다.<br /><br /> 성능 카운터에서 공유하는 전역 메모리의 크기\(바이트\)를 지정합니다.  기본값은 524288입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`Configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|ASP.NET 구성 섹션의 루트 요소를 지정합니다.|  
  
## 설명  
 성능 카운터는 메모리가 매핑된 파일 또는 공유 메모리를 사용하여 성능 데이터를 게시합니다.  공유 메모리의 크기에 따라 한 번에 사용할 수 있는 인스턴스의 수가 결정됩니다.  공유 메모리에는 전역 공유 메모리와 개별 공유 메모리의 두 가지 형식이 있습니다.  전역 공유 메모리는 .NET Framework 버전 1.0 또는 1.1과 함께 설치된 모든 성능 카운터 범주에서 사용됩니다.  .NET Framework 버전 2.0과 함께 설치된 성능 카운터 범주에서는 각 성능 카운터 범주에 자체 메모리가 있는 개별 공유 메모리를 사용합니다.  
  
 전역 공유 메모리의 크기는 구성 파일을 통해서만 설정할 수 있습니다.  기본 크기는 524,288바이트이고, 최대 크기는 33,554,432바이트이며, 최소 크기는 32,768바이트입니다.  전역 공유 메모리는 모든 프로세스와 범주에서 공유되므로 첫 번째 생성자가 크기를 지정합니다.  응용 프로그램 구성 파일에서 크기를 정의하면 응용 프로그램이 성능 카운터를 실행하는 첫 번째 응용 프로그램인 경우에만 해당 크기가 사용됩니다.  따라서 `filemappingsize` 값을 지정할 올바른 위치는 Machine.config 파일입니다.  전역 공유 메모리의 메모리는 개별 성능 카운터에 의해 해제될 수 없으므로 결국 서로 다른 이름을 가진 많은 수의 성능 카운터 인스턴스가 만들어진 경우에는 전역 공유 메모리가 모두 사용됩니다.  
  
 개별 공유 메모리 크기의 경우 우선 레지스트리 키 HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\*\<category name\>*\\Performance의 DWORD FileMappingSize 값을 참조한 다음 구성 파일의 전역 공유 메모리에 지정된 값을 참조합니다.  FileMappingSize 값이 없으면 개별 공유 메모리 크기는 구성 파일에 있는 전역 설정의 1\/4로 설정됩니다.  
  
## 참고 항목  
 <xref:System.Diagnostics.PerformanceCounter>   
 <xref:System.Diagnostics.PerformanceCounterCategory>   
 <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>   
 <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>