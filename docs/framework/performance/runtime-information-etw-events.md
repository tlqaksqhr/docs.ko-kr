---
title: "런타임 정보 ETW 이벤트 | Microsoft Docs"
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
  - "ETW, 런타임 정보 이벤트"
  - "런타임 정보 이벤트[.NET Framework]"
ms.assetid: 68b4edbc-7f3b-45f6-ab75-4fd066d6af9a
caps.latest.revision: 6
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 6
---
# 런타임 정보 ETW 이벤트
이러한 ETW 이벤트는 SKU, 버전 번호, 런타임이 활성화된 방식, 시작될 때 사용된 명령줄 매개 변수, GUID\(해당하는 경우\), 기타 관련 정보 등 런타임에 대한 정보를 기록합니다.  프로세스 내에서 여러 개의 런타임이 실행되고 있는 경우에는 이러한 이벤트에서 제공하는 정보\(ClrInstanceID\)가 런타임의 모호함을 없애는 데 도움이 됩니다.  
  
 다음 표에서는 두 가지 런타임 정보 이벤트를 보여 줍니다.  이러한 이벤트는 모든 키워드 또는 마스크에서 발생합니다. 자세한 내용은 [CLR ETW 키워드 및 수준](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하십시오.  
  
|Event|이벤트 ID|공급자|설명|  
|-----------|------------|---------|--------|  
|`RuntimeInformationEvent`|187|CLRRuntime|런타임이 로드될 때 발생합니다.|  
|`RuntimeInformationDCStart`|187|CLRRundown|로드된 런타임을 열거합니다.|  
  
 다음 표에서는 이벤트 데이터를 보여 줍니다.  
  
|필드 이름|데이터 형식|설명|  
|-----------|------------|--------|  
|ClrInstanceID|win:UInt16|CLR 또는 CoreCLR 인스턴스의 고유 ID입니다.|  
|Sku|win:UInt16|1 – 데스크톱 CLR<br /><br /> 2 – CoreCLR|  
|BclVersion – 주 버전|win:UInt16|mscorlib.dll의 주 버전입니다.|  
|BclVersion – 부 버전|win:UInt16|mscorlib.dll의 부 버전 번호입니다.|  
|BclVersion – 빌드 번호|win:UInt16|mscorlib.dll의 빌드 번호입니다.|  
|BclVersion – QFE|win:UInt16|mscorlib.dll의 핫픽스 버전 번호입니다.|  
|VMVersion – 주 버전|win:UInt16|SKU에 따라 clr.dll 또는 coreclr.dll의 버전입니다.|  
|VMVersion – 부 버전|win:UInt16|SKU에 따라 clr.dll 또는 coreclr.dll의 부 버전입니다.|  
|VMVersion – 빌드 번호|win:UInt16|clr.dll 또는 coreclr.dll의 빌드 번호입니다.|  
|VMVersion – QFE|win:UInt16|clr.dll 또는 coreclr.dll의 핫픽스 버전 번호입니다.|  
|StartupFlags|win:UInt32|mscoree.h에 정의된 시작 플래그입니다.|  
|StartupMode|win:UInt8|0x01 \- 관리되는 실행 파일<br /><br /> 0x02 \- 호스트되는 CLR<br /><br /> 0x04 \- C\+\+ 관리되는 interop입니다.<br /><br /> 0x08 \- COM 활성화됨<br /><br /> 0x10 \- 기타|  
|CommandLine|win:UnicodeString|StartupMode\=0x01인 경우에만 null이 아닙니다.|  
|ComObjectGUID|win:GUID|StartupMode\=0x08인 경우에만 null이 아닙니다.|  
|RuntimeDLLPath|win:UnicodeString|프로세스에 로드된 CLR .dll 파일의 경로입니다.|  
  
## 참고 항목  
 [CLR ETW 이벤트](../../../docs/framework/performance/clr-etw-events.md)