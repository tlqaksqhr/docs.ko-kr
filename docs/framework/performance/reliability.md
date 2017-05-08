---
title: "안정성 | Microsoft Docs"
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
  - "코드, 안정성"
  - "관리 코드, 안정성"
  - "안정성[.NET Framework]"
  - "SQL Server[.NET Framework]"
  - "안정적인 코드 작성"
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# 안정성
SQL Server와 같은 서버 환경에서 실행되는 코드는 비동기 예외로부터 보호되어야 합니다.  여기에 설명된 바와 같이 안정성은 SQL Server에만 한정되는 것이 아니라 .NET Framework 버전 2.0 환경에서 실행되는 모든 호스트의 신뢰할 수 있는 코드 작성에 해당됩니다.  그러나 버전 2.0의 새로운 안정성 기능이 광범위하게 사용된 첫 서비스가 SQL Server이므로 이 설명의 예제로 사용합니다.  
  
 SQL Server에서 실행되는 코드는 다른 서버 환경에 비해 보다 엄격한 안정성 지침을 사용해야 합니다.  자원 소비의 가장자리에 SQL Server 스테디 작업 때문입니다. <xref:System.OutOfMemoryException> 및 <xref:System.Threading.ThreadAbortException> 은 SQL Server 환경에서 드문 예외입니다.  일반적으로 이러한 지침은 안정성보다는 완전히 신뢰할 수 있는 관리 코드가 <xref:System.AppDomain> 수준의 재활용의 경우 안정적으로 실패할 수 있도록 하는 점을 중점적으로 다룹니다. 이 점이 서버가 일관성과 가용성을 유지하는 기본 방법이기 때문입니다.  
  
## 단원 내용  
 [SQL Server 프로그래밍 및 호스트 보호 특성](../../../docs/framework/performance/sql-server-programming-and-host-protection-attributes.md)  
 SQL Server에서 <xref:System.Security.Permissions.HostProtectionAttribute> 특성을 사용하여 관리 코드의 실행을 제한하는 방법을 보여 줍니다.  
  
 [최선의 안정성 구현 방법](../../../docs/framework/performance/reliability-best-practices.md)  
 안정성 요구 사항을 충족시키는 코드 작성을 위한 지침을 제공합니다.  
  
 [제약이 있는 실행 영역](../../../docs/framework/performance/constrained-execution-regions.md)  
 CER\(제약이 있는 실행 영역\)의 기능과 동작에 대해 설명합니다.  
  
## 참조  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>