---
title: ".NET Framework의 형식 변환표 | Microsoft Docs"
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
  - "확대 변환"
  - "축소 변환"
  - "형식 변환, 표"
  - "변환 형식, 축소 변환"
  - "변환 형식, 확대 변환"
  - "기본 형식, 변환"
  - "테이블[.NET Framework], 형식 변환"
  - "데이터 형식[.NET Framework], 변환"
ms.assetid: 0ea65c59-85eb-4a52-94ca-c36d3bd13058
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# .NET Framework의 형식 변환표
확대 변환은 특정 형식의 값을 크기가 같거나 큰 다른 형식의 값으로 변환하는 것입니다.  이와는 반대로 축소 변환은 특정 형식의 값을 크기가 작은 다른 형식의 값으로 변환하는 것입니다.  이 항목의 표에서는 두 변환 형식에서 나타나는 동작에 대해 설명합니다.  
  
## 확대 변환  
 다음 표는 정보 손실 없이 변환을 수행할 수 있는 확대 변환을 나타냅니다.  
  
|형식|데이터 손실 없이 변환할 수 있는 형식|  
|--------|---------------------------|  
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
  
 <xref:System.Single> 또는 <xref:System.Double>로 확대 변환을 수행하는 일부 경우에 정밀도가 손실될 수 있습니다.  다음 표는 가끔씩 정보가 손실될 수 있는 확대 변환을 나타냅니다.  
  
|형식|변환할 수 있는 형식|  
|--------|-----------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.UInt64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.Decimal>|<xref:System.Single>, <xref:System.Double>|  
  
## 축소 변환  
 <xref:System.Single> 또는 <xref:System.Double>로 축소 변환을 수행하는 경우에 정보가 손실될 수 있습니다.  대상 형식에서 소스의 크기를 제대로 표시할 수 없는 경우 결과 형식은 상수인 `PositiveInfinity` 또는 `NegativeInfinity`로 설정됩니다.  `PositiveInfinity`는 양수를 0으로 나눈 경우에 생성되며 <xref:System.Single> 또는 <xref:System.Double>이 `MaxValue` 필드의 값을 초과하는 경우에도 반환됩니다.  `NegativeInfinity`는 음수를 0으로 나눈 경우에 생성되며 <xref:System.Single> 또는 <xref:System.Double>이 `MinValue` 필드의 값보다 작은 경우에도 반환됩니다.  <xref:System.Double>에서 <xref:System.Single>로 변환하면 `PositiveInfinity` 또는 `NegativeInfinity`가 생성될 수 있습니다.  
  
 축소 변환에서는 또한 다른 데이터 형식의 정보도 손실될 수 있습니다.  그러나 변환되는 형식의 값이 대상 형식의 `MaxValue` 및 `MinValue` 필드에 지정된 범위 밖에 있고 런타임에서 대상 형식의 값이 `MaxValue` 또는 `MinValue` 필드의 값을 초과하지 않는지 확인하기 위해 이 변환을 검사하는 경우에는 <xref:System.OverflowException>이 throw됩니다.  <xref:System.Convert?displayProperty=fullName> 클래스에 의해 수행되는 변환은 항상 이런 식으로 검사됩니다.  
  
 다음 표에는 변환되는 형식 값이 결과 형식의 정의된 범위 밖에 있는 경우, <xref:System.Convert?displayProperty=fullName> 또는 검사된 변환을 사용하여 <xref:System.OverflowException>을 throw하는 변환의 목록이 나와 있습니다.  
  
|형식|변환할 수 있는 형식|  
|--------|-----------------|  
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
  
## 참고 항목  
 <xref:System.Convert?displayProperty=fullName>   
 [.NET Framework의 형식 변환](../../../docs/standard/base-types/type-conversion.md)