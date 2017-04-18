---
title: "System.Math 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# System.Math 메서드
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 다음 <xref:System.Math> 메서드를 지원하지 않습니다.  
  
-   <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=fullName>  
  
-   <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=fullName>  
  
-   <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=fullName>  
  
## .NET과의 차이점  
 .NET Framework의 반올림 구문은 SQL Server와 다릅니다.  .NET Framework의 <xref:System.Math.Round%2A> 메서드는 *은행원의 반올림*을 수행합니다. 은행원의 반올림에서는 .5로 끝나는 숫자는 다음 높은 자리수로 반올림되는 것이 아니라 가장 가까운 짝수 정수가 됩니다.  예를 들어 2.5는 2가 되고 3.5는 4가 됩니다.  이 방법은 많은 데이터 트랜잭션에서 값이 높아질수록 발생할 수 있는 체계적 오차를 방지할 수 있습니다.  
  
 SQL에서 `ROUND` 함수는 항상 0 이상의 정수 값으로 반올림됩니다.  따라서 2.5의 경우 .NET Framework에서는 2가 되는데 반해 SQL에서는 3이 됩니다.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 SQL `ROUND` 구문을 따르며 은행원의 반올림을 사용하지 않습니다.  
  
## 참고 항목  
 [데이터 형식 및 함수](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)