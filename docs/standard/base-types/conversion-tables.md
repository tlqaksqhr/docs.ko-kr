---
title: ".NET에서 형식 변환 표"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- widening conversions
- narrowing conversions
- type conversion, table
- converting types, narrowing conversions
- converting types, widening conversions
- base types, converting
- tables [.NET Framework], type conversions
- data types [.NET Framework], converting
ms.assetid: 0ea65c59-85eb-4a52-94ca-c36d3bd13058
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 327469f9a151b6ef7e1c42f6669c0a9dae7016fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="type-conversion-tables-in-net"></a>.NET에서 형식 변환 표
확대 변환은 한 형식의 값을 크기가 같거나 더 큰 다른 형식으로 변환할 때 발생합니다. 축소 변환은 한 형식의 값을 크기가 더 작은 다른 형식의 값으로 변환할 때 발생합니다. 이 항목의 표에서는 두 가지 유형의 변환에서 모두 나타나는 동작을 설명합니다.  
  
## <a name="widening-conversions"></a>확대 변환  
 다음 표에서 정보의 손실 없이 수행할 수 있는 확대 변환에 설명 합니다.  
  
|형식|데이터 손실 없이 다음 형식으로 변환할 수 있음|  
|----------|-------------------------------------------|  
|<xref:System.Byte>|<xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.SByte>|<xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int16>|<xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.UInt16>|<xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Char>|<xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int32>|<xref:System.Int64>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.UInt32>|<xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int64>|<xref:System.Decimal>|  
|<xref:System.UInt64>|<xref:System.Decimal>|  
|<xref:System.Single>|<xref:System.Double>|  
  
 일부 확장을 변환 <xref:System.Single> 또는 <xref:System.Double> 정밀도의 손실 될 수 있습니다. 다음 표에서는 때때로 정보 손실이 발생할 수 있는 확대 변환에 대해 설명합니다.  
  
|형식|다음 형식으로 변환할 수 있음|  
|----------|-------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.UInt64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.Decimal>|<xref:System.Single>, <xref:System.Double>|  
  
## <a name="narrowing-conversions"></a>축소 변환  
 범위가 좁은 <xref:System.Single> 또는 <xref:System.Double> 정보의 손실 될 수 있습니다. 대상 형식이 소스 크기를 제대로 표시할 수 없는 경우 결과 형식이 상수 `PositiveInfinity` 또는 `NegativeInfinity`로 설정됩니다. `PositiveInfinity`양의 숫자를 0으로 나눈 결과 및 경우에 반환 됩니다의 값을 <xref:System.Single> 또는 <xref:System.Double> 의 값을 초과 `MaxValue` 필드입니다. `NegativeInfinity`음수 0으로 나눈 결과 및 경우에 반환 됩니다의 값을 <xref:System.Single> 또는 <xref:System.Double> 의 값 보다 작으면는 `MinValue` 필드입니다. 변환 된 <xref:System.Double> 에 <xref:System.Single> 발생할 수 있습니다 `PositiveInfinity` 또는 `NegativeInfinity`합니다.  
  
 축소 변환 시 다른 데이터 형식에 대한 정보 손실도 발생할 수 있습니다. 그러나는 <xref:System.OverflowException> 변환 되는 형식의 값이 있는 대상 유형으로 지정 된 범위를 벗어나는 경우 throw 되 `MaxValue` 및 `MinValue` 필드 및 변환 하는 대상의 값을 확인 하기 위해 런타임에서 확인란이 형식 초과 하지 않는 해당 `MaxValue` 또는 `MinValue`합니다. 변환에 의해 수행 되는 <xref:System.Convert?displayProperty=nameWithType> 클래스는 항상 이런이 방식으로 확인 됩니다.  
  
 다음 표에서 throw 하는 변환은 <xref:System.OverflowException> 를 사용 하 여 <xref:System.Convert?displayProperty=nameWithType> 또는 변환 되는 형식 값의 결과 형식이 정의 된 범위를 벗어나는 경우 검사 된 변환 합니다.  
  
|형식|다음 형식으로 변환할 수 있음|  
|----------|-------------------------|  
|<xref:System.Byte>|<xref:System.SByte>|  
|<xref:System.SByte>|<xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>|  
|<xref:System.Int16>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.UInt16>|  
|<xref:System.UInt16>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>|  
|<xref:System.Int32>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32>|  
|<xref:System.UInt32>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>|  
|<xref:System.Int64>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64>|  
|<xref:System.UInt64>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>|  
|<xref:System.Decimal>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
|<xref:System.Single>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
|<xref:System.Double>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Convert?displayProperty=nameWithType>  
 [.NET에서 형식 변환](../../../docs/standard/base-types/type-conversion.md)
