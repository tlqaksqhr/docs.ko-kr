---
title: ".NET Framework에서 문자열 구문 분석 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "문자열 구문 분석, 문자열 구문 분석 정보"
  - "IFormatProvider 인터페이스, 문자열 구문 분석"
  - "기본 형식, 문자열 구문 분석"
  - "Parse 메서드"
  - "문자열 구문 분석"
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# .NET Framework에서 문자열 구문 분석
구문 분석 작업은 .NET Framework 기본 형식을 나타내는 문자열을 해당 기본 형식으로 변환합니다.  예를 들어 구문 분석 작업을 사용하여 문자열을 부동 소수 숫자 또는 날짜 및 시간 값으로 변환할 수 있습니다.  구문 분석 작업을 수행하기 위해 가장 일반적으로 사용되는 메서드는 `Parse` 메서드입니다.  구문 분석은 서식 지정\(기본 형식을 문자열 표현으로 변환\)의 반대 작업이므로 여러 가지 동일한 규칙이 적용됩니다.  서식 지정의 경우 <xref:System.IFormatProvider> 인터페이스를 구현하는 개체를 사용하여 문화권별 서식 지정 정보를 제공하는 것과 마찬가지로, 구문 분석을 할 때에도 <xref:System.IFormatProvider> 인터페이스를 구현하는 개체를 사용하여 문자열 표현의 해석 방법을 결정합니다.  자세한 내용은 [형식 서식 지정](../../../docs/standard/base-types/formatting-types.md)을 참조하십시오.  
  
## 단원 내용  
 [숫자 문자열 구문 분석](../../../docs/standard/base-types/parsing-numeric.md)  
 문자열을 .NET Framework 숫자 형식으로 변환하는 방법에 대해 설명합니다.  
  
 [날짜 및 시간 문자열 구문 분석](../../../docs/standard/base-types/parsing-datetime.md)  
 문자열을 .NET Framework **DateTime** 형식으로 변환하는 방법에 대해 설명합니다.  
  
 [기타 문자열 구문 분석](../../../docs/standard/base-types/parsing-other.md)  
 문자열을 **Char**, **Boolean** 및 **Enum** 형식으로 변환하는 방법에 대해 설명합니다.  
  
## 관련 단원  
 [형식 서식 지정](../../../docs/standard/base-types/formatting-types.md)  
 서식 지정자 및 형식 공급자 등의 기본적인 서식 지정 개념에 대해 설명합니다.  
  
 [.NET Framework의 형식 변환](../../../docs/standard/base-types/type-conversion.md)  
 형식을 변환하는 방법에 대해 설명합니다.  
  
 [기본 형식](../../../docs/standard/base-types/index.md)  
 .NET Framework 기본 형식에 대해 수행할 수 있는 일반적인 작업에 대해 설명합니다.