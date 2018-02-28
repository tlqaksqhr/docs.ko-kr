---
title: ".NET에서 문자열 구문 분석"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9c2193dd1b1f3c0478efb5fc9c2b80250ef1878f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="parsing-strings-in-net"></a>.NET에서 문자열 구문 분석
구문 분석 작업은 .NET 기본 형식을 나타내는 문자열을 해당 기본 형식으로 변환합니다. 구문 분석 작업을 사용하여 문자열을 부동 소수점 숫자나 날짜 및 시간 값으로 변환하는 경우를 예로 들 수 있습니다. 구문 분석 작업을 수행하는 데 가장 일반적으로 사용되는 메서드는 `Parse` 메서드입니다. 구문 분석은 서식 지정(기본 형식을 문자열 표현으로 변환하는 작업 포함)의 반대 작업으로 많은 동일한 규칙이 적용됩니다. 서식 지정이 <xref:System.IFormatProvider> 인터페이스를 구현하는 개체를 사용하여 문화권을 구분하는 서식 지정 정보를 제공하는 것과 마찬가지로 구문 분석은 <xref:System.IFormatProvider> 인터페이스를 구현하는 개체를 사용하여 문자열 표현을 해석하는 방법을 결정합니다. 자세한 내용은 [서식 지정 형식](../../../docs/standard/base-types/formatting-types.md)을 참조하세요.  
  
## <a name="in-this-section"></a>섹션 내용  
 [숫자 문자열 구문 분석](../../../docs/standard/base-types/parsing-numeric.md)  
 문자열을 .NET 숫자 형식으로 변환하는 방법을 설명합니다.  
  
 [날짜 및 시간 문자열 구문 분석](../../../docs/standard/base-types/parsing-datetime.md)  
 문자열을 .NET **DateTime** 형식으로 변환하는 방법을 설명합니다.  
  
 [기타 문자열 구문 분석](../../../docs/standard/base-types/parsing-other.md)  
 문자열을 **Char**, **부울** 및 **열거형** 형식으로 변환하는 방법에 대해 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [형식 서식 지정](../../../docs/standard/base-types/formatting-types.md)  
 형식 지정자 및 형식 공급자와 같은 기본 서식 지정 개념에 대해 설명합니다.  
  
 [.NET에서 형식 변환](../../../docs/standard/base-types/type-conversion.md)  
 형식을 변환하는 방법에 대해 설명합니다.  
  
 [기본 형식](../../../docs/standard/base-types/index.md)  
 .NET 기본 형식에 대해 수행할 수 있는 일반적인 작업에 관해 설명합니다.
