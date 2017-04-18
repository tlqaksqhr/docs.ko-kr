---
title: "지원되지 않는 기능 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 지원되지 않는 기능
LINQ to SQL에서 다음 SQL 기능은 기존 CLR\(공용 언어 런타임\) 및 .NET Framework 구문의 트랜잭션을 통해 노출될 수 없습니다.  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     `LIKE`는 직접 변환을 통해 지원되지 않지만 유사한 기능이 <xref:System.Data.Linq.SqlClient.SqlMethods> 클래스에 있습니다.  자세한 내용은 [M:System.Data.Linq.SqlClient.SqlMethods.Like\(System.String,System.String](assetId:///M:System.Data.Linq.SqlClient.SqlMethods.Like(System.String,System.String?qualifyHint=True&autoUpgrade=True)을 참조하세요.  
  
-   `DATEDIFF`  
  
     LINQ to SQL에서는 `DATEDIFF`를 제한적으로 지원합니다.  유사한 기능은 [SqlMethods](assetId:///T:System.Data.Linq.SqlClient.SqlMethods?qualifyHint=False&autoUpgrade=True) 클래스에 있습니다.  
  
-   `ROUND`  
  
     LINQ to SQL에서는 `ROUND`를 제한적으로 지원합니다.  자세한 내용은 [System.Math 메서드](../Topic/System.Math%20Methods.md)을 참조하세요.  
  
## 참고 항목  
 [데이터 형식 및 함수](../Topic/Data%20Types%20and%20Functions.md)