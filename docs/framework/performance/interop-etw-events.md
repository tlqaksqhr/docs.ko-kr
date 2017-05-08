---
title: "Interop ETW 이벤트 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ETW, interop 이벤트(CLR)"
  - "interop 이벤트[.NET Framework]"
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Interop ETW 이벤트
<a name="top"></a> Interop 이벤트는 MSIL\(Microsoft Intermediate Language\) 스텁 생성 및 캐싱에 대한 정보를 캡처합니다.  
  
 이 범주는 다음 이벤트로 구성됩니다.  
  
-   [ILStubGenerated 이벤트](#ilstubgenerated_event)  
  
-   [ILStubCacheHit 이벤트](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## ILStubGenerated 이벤트  
 다음 표에서는 키워드와 수준을 보여 줍니다. 자세한 내용은 [CLR ETW 키워드 및 수준](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하세요.  
  
|이벤트를 발생시키기 위한 키워드|수준|  
|-----------------------|--------|  
|`InteropKeyword` \(0x2000\)|정보 제공\(4\)|  
  
 다음 표에서는 이벤트 정보를 보여 줍니다.  
  
|이벤트|이벤트 ID|발생 시기|  
|---------|------------|-----------|  
|`ILStubGenerated`|88|MSIL 스텁이 생성되었습니다.|  
  
 다음 표에서는 이벤트 데이터를 보여 줍니다.  
  
|필드 이름|데이터 형식|설명|  
|-----------|------------|--------|  
|ModuleID|win:UInt16|모듈 식별자입니다.|  
|StubMethodID|win:UInt64|스텁 메서드 식별자입니다.|  
|StubFlags|win:UInt64|스텁에 대한 플래그:<br /><br /> 0x1 \- 역방향 interop<br /><br /> 0x2 \- COM interop<br /><br /> 0x4 \- NGen.exe에서 생성한 스텁<br /><br /> 0x8 \- 대리자<br /><br /> 0x10 \- 가변 인수<br /><br /> 0x20 \- 비관리 호출 수신자|  
|ManagedInteropMethodToken|win:UInt32|관리되는 interop 메서드의 토큰입니다.|  
|ManagedInteropMethodNameSpace|win:UnicodeString|관리되는 interop 메서드의 네임스페이스입니다.|  
|ManagedInteropMethodName|win:UnicodeString|관리되는 interop 메서드의 이름입니다.|  
|ManagedInteropMethodSignature|win:UnicodeString|관리되는 interop 메서드의 서명입니다.|  
|NativeMethodSignature|win:UnicodeString|네이티브 메서드 서명입니다.|  
|StubMethodSignature|win:UnicodeString|스텁 메서드 서명입니다.|  
|StubMethodILCode|win:UnicodeString|스텁 메서드의 MSIL 코드입니다.|  
|ClrInstanceID|win:UInt16|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|  
  
 [맨 위로 이동](#top)  
  
<a name="ilstubcachehit_event"></a>   
## ILStubCacheHit 이벤트  
 다음 표에서는 키워드와 수준을 보여 줍니다.  
  
|이벤트를 발생시키기 위한 키워드|수준|  
|-----------------------|--------|  
|`InteropKeyword` \(0x2000\)|정보 제공\(4\)|  
  
 다음 표에서는 이벤트 정보를 보여 줍니다.  
  
|이벤트|이벤트 ID|발생 시기|  
|---------|------------|-----------|  
|`ILStubCacheHit`|89|MSIL 캐시가 액세스되었습니다.|  
  
 다음 표에서는 이벤트 데이터를 보여 줍니다.  
  
|필드 이름|데이터 형식|설명|  
|-----------|------------|--------|  
|ModuleID|win:UInt16|모듈 식별자입니다.|  
|StubMethodID|win:UInt64|스텁 메서드 식별자입니다.|  
|ManagedInteropMethodToken|win:UInt32|관리되는 interop 메서드의 토큰입니다.|  
|ManagedInteropMethodNameSpace|win:UnicodeString|관리되는 interop 메서드의 네임스페이스입니다.|  
|ManagedInteropMethodName|win:UnicodeString|관리되는 interop 메서드의 이름입니다.|  
|ManagedInteropMethodSignature|win:UnicodeString|관리되는 interop 메서드의 서명입니다.|  
|ClrInstanceID|win:UInt16|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|  
  
 [맨 위로 이동](#top)  
  
## 참고 항목  
 [CLR ETW 이벤트](../../../docs/framework/performance/clr-etw-events.md)