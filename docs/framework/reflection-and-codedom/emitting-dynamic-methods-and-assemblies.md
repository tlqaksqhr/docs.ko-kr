---
title: "동적 메서드 및 어셈블리 생성 | Microsoft Docs"
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
  - "어셈블리[.NET Framework], 동적 어셈블리 내보내기"
  - "동적 어셈블리"
  - "메타데이터, 내보내기 인터페이스"
  - "리플렉션 내보내기"
  - "리플렉션 내보내기, 개요"
ms.assetid: 8e8e2631-62fd-40e7-a8ee-0039b06749bc
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# 동적 메서드 및 어셈블리 생성
이 섹션에서는 컴파일러 또는 도구가 런타임에 메타데이터 및 MSIL\(Microsoft Intermediate Language\)을 내보내고 선택적으로 디스크에서 PE\(이식 가능한 실행\) 파일을 생성할 수 있게 해주는 <xref:System.Reflection.Emit> 네임스페이스의 관리되는 형식 집합을 설명합니다.  스크립트 엔진과 컴파일러는 이 네임스페이스의 주 사용자입니다.  이 섹션에서는 <xref:System.Reflection.Emit> 네임스페이스에서 제공하는 기능을 리플렉션 내보내기라고 합니다.  
  
 리플렉션 내보내기는 다음 기능을 제공합니다.  
  
-   런타임에 <xref:System.Reflection.Emit.DynamicMethod> 클래스를 사용하여 간단한 전역 메서드를 정의하고 대리자를 사용하여 실행합니다.  
  
-   런타임에 어셈블리를 정의하고 실행하거나 디스크에 저장합니다.  
  
-   런타임에 어셈블리를 정의하고 실행한 다음 언로드하고 가비지 수집에서 해당 리소스를 회수할 수 있게 합니다.  
  
-   런타임에 새 어셈블리에서 모듈을 정의하고 실행하거나 디스크에 저장합니다.  
  
-   런타임에 모듈에서 형식을 정의하고 이러한 형식의 인스턴스를 만든 다음 해당 메서드를 호출합니다.  
  
-   디버거 및 코드 프로파일러와 같은 도구에서 사용할 수 있는 정의된 모듈에 대한 기호 정보를 정의합니다.  
  
 <xref:System.Reflection.Emit> 네임스페이스의 관리되는 형식 외에도 [메타데이터 인터페이스](../../../ocs/framework/unmanaged-api/metadata/metadata-interfaces.md) 참조 설명서에서 설명하는 관리되지 않는 메타데이터 인터페이스가 있습니다.  관리되는 리플렉션 내보내기는 관리되지 않는 메타데이터 인터페이스 보다 강력한 의미 체계 오류 검사 및 높은 수준의 메타데이터 추상화를 제공합니다.  
  
 메타데이터 및 MSIL 작업을 위한 다른 유용한 리소스는 CLI\(공용 언어 인프라\) 설명서, 특히 "Partition II: Metadata Definition and Semantics" 및 "Partition III: CIL Instruction Set"입니다.  이 설명서는 [MSDN](http://go.microsoft.com/fwlink/?LinkID=65555) 및 [Ecma 웹 사이트](http://go.microsoft.com/fwlink/?LinkId=116487)\(영문\)에서 온라인으로 사용할 수 있습니다.  
  
## 단원 내용  
 [리플렉션 내보내기의 보안 문제점](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)  
 리플렉션 내보내기를 사용하여 동적 어셈블리를 만드는 경우와 관련된 보안 문제를 설명합니다.  
  
## 참조  
 <xref:System.Reflection.Emit.OpCodes>  
 메서드 본문을 작성하는 데 사용할 수 있는 MSIL 명령 코드의 카탈로그를 작성합니다.  
  
 <xref:System.Reflection.Emit>  
 동적 메서드, 어셈블리 및 형식을 내보내는 데 사용되는 관리되는 클래스를 포함합니다.  
  
 <xref:System.Type>  
 관리되는 리플렉션 및 리플렉션 내보내기에서 형식을 나타내며 이러한 기술 사용의 핵심 요소인 <xref:System.Type> 클래스를 설명합니다.  
  
 <xref:System.Reflection>  
 메타데이터와 관리 코드를 탐색하는 데 사용되는 관리되는 클래스를 포함합니다.  
  
## 관련 단원  
 [리플렉션](../../../docs/framework/reflection-and-codedom/reflection.md)  
 메타데이터와 관리 코드를 탐색하는 방법을 설명합니다.  
  
 [공용 언어 런타임의 어셈블리](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 .NET Framework의 어셈블리에 대해 간략하게 설명합니다.