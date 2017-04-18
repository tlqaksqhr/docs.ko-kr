---
title: "ASP.NET을 사용하는 LINQ to SQL N 계층 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# ASP.NET을 사용하는 LINQ to SQL N 계층
[!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)]을 사용하는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 응용 프로그램에서는 <xref:System.Web.UI.WebControls.LinqDataSource> 웹 서버 컨트롤을 사용합니다. 이 컨트롤은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 대해 쿼리하는 데 필요한 대부분의 논리를 처리하고, 데이터를 브라우저에 전달하고 검색하며, 최종적으로 데이터베이스를 업데이트할 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.DataContext>에 데이터를 제출합니다. 컨트롤을 태그에 구성하기만 하면 컨트롤이 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]과 브라우저 사이의 모든 데이터 전송을 처리합니다. 프레젠테이션 계층과의 상호 작용은 이 컨트롤이 처리하고 데이터 계층과의 통신은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]이 처리하기 때문에 [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] 다계층 응용 프로그램에서 사용자는 사용자 지정 비즈니스 논리를 작성하는 데 집중해야 합니다.  
  
 `LINQDataSource`에 대한 자세한 내용은 [NIB: LinqDataSource 웹 서버 컨트롤 개요](http://msdn.microsoft.com/ko-kr/104cfc3f-7385-47d3-8a51-830dfa791136)를 참조하세요.  
  
## 참고 항목  
 [LINQ to SQL을 사용하는 N 계층 및 원격 응용 프로그램](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)