---
title: "gcUnmanagedToManaged MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), garbage collection"
  - "GC unmanaged to managed"
  - "transitioning threads unmanaged to managed code"
  - "GcUnmanagedToManaged MDA"
  - "threading [.NET Framework], garbage collection"
  - "managed debugging assistants (MDAs), garbage collection"
  - "threading [.NET Framework], managed debugging assistants"
  - "garbage collection, run-time errors"
  - "unmanaged to managed garbage collection"
ms.assetid: 103eb3a3-1cf0-4406-8a9a-a7798fdc22d1
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# gcUnmanagedToManaged MDA
`gcUnmanagedToManaged` MDA\(관리 디버깅 도우미\)는 위협이 비관리 코드에서 관리 코드로 전환될 때마다 가비지 수집을 발생시킵니다.  
  
## 증상  
 COM 및 플랫폼 호출을 사용하여 관리되지 않는 사용자 구성 요소를 실행하는 응용 프로그램은 CLR에서 비결정적 액세스 위반을 발생시킵니다.  
  
## 원인  
 응용 프로그램이 관리되지 않는 사용자 구성 요소를 실행하는 경우 해당 구성 요소로 인해 가비지 수집된 힙이 손상되었을 수 있습니다.  이 경우 가비지 수집기가 개체 그래프를 검색하려고 하면 CLR에서 액세스 위반이 발생합니다.  
  
## 해결  
 이 도우미를 사용하도록 설정하면 관리되는 각 전환 전에 가비지 수집이 강제로 수행되어 관리되지 않는 구성 요소로 인해 가비지 수집된 힙이 손상되는 시간과 액세스 위반이 발생하는 시간 사이의 간격이 줄어듭니다.  
  
## 런타임에 대한 영향  
 위협이 비관리 코드에서 관리 코드로 전환될 때마다 가비지 수집을 발생시킵니다.  
  
## 출력  
 이 MDA는 출력을 생성하지 않습니다.  
  
## 구성  
  
```  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)   
 [Interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)