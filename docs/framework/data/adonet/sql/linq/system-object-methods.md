---
title: "System.Object 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# System.Object 메서드
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 다음 <xref:System.Object> 메서드를 지원합니다.  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=fullName>|  
|<xref:System.Object.ToString?displayProperty=fullName>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 다음 <xref:System.Object> 메서드를 지원하지 않습니다.  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=fullName>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=fullName>|  
|<xref:System.Object.MemberwiseClone?displayProperty=fullName>|<xref:System.Object.GetType?displayProperty=fullName>|  
|`BINARY`, `VARBINARY`, `IMAGE` 및 `TIMESTAMP`와 같은 이진 형식의 <xref:System.Object.ToString?displayProperty=fullName>입니다.||  
  
## .NET과의 차이점  
 더블에 대한 <xref:System.Object.ToString?displayProperty=fullName>의 출력은 SQL에 대해 SQL `CONVERT`\(NVARCHAR\(30\), @x, 2\)를 사용합니다.  이 경우에 SQL에서는 항상 16 진수와 0을 "0.000000000000000e\+000"으로 표기하는 과학적 표기법을 사용하며  결과적으로 <xref:System.Object.ToString?displayProperty=fullName> 변환에서는 .NET Framework의 <xref:System.Convert.ToString%2A?displayProperty=fullName>에서 생성한 문자열과 동일한 문자열을 생성하지 못합니다.  
  
## 참고 항목  
 [데이터 형식 및 함수](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)