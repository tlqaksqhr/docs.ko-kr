---
title: "LINQ to DataSet 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: dc20a8fb-03f6-4b68-9c2b-7f7299e3070b
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# LINQ to DataSet 개요
<xref:System.Data.DataSet>은 가장 많이 사용되는 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 구성 요소 중 하나이며 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]의 기반이 되는 연결되지 않은 프로그래밍 모델의 주요 요소이고 다양한 데이터 소스의 데이터를 명시적으로 캐시하는 데 사용할 수 있습니다. 프레젠테이션 계층의 경우 <xref:System.Data.DataSet>은 데이터 바인딩을 위해 GUI 컨트롤과 밀접하게 통합됩니다. 중간 계층의 경우 데이터의 관계 모양을 유지하는 캐시를 제공하고 빠르고 간단한 쿼리 및 계층 탐색 서비스를 포함합니다.  데이터베이스에 대한 요청 수를 줄이는 가장 일반적인 방법은 중간 계층에서 <xref:System.Data.DataSet>을 캐시 작업에 사용하는 것입니다.  예를 들어 데이터 구동 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 응용 프로그램을 가정해 봅시다.  응용 프로그램 데이터의 많은 부분은 자주 바뀌지 않으면서 세션이나 사용자를 통해 일반적으로 사용됩니다.  이 데이터를 웹 서버의 메모리에 유지하면 데이터베이스에 대한 요청의 수가 줄어서 사용자의 상호 작용 속도가 높아질 수 있습니다.  응용 프로그램에서 하나 이상의 데이터 소스에 있는 데이터의 하위 집합을 응용 프로그램 공간으로 가져올 수 있다는 점 또한 <xref:System.Data.DataSet>의 유용한 장점 중 하나입니다.  이 경우 응용 프로그램에서는 메모리 내 데이터를 조작하는 동시에 관계 모양을 유지할 수 있습니다.  
  
 이러한 탁월함에도 불구하고 <xref:System.Data.DataSet>의 쿼리 기능에는 한계가 있습니다.  <xref:System.Data.DataTable.Select%2A> 메서드는 필터링과 정렬에 사용할 수 있고 <xref:System.Data.DataRow.GetChildRows%2A> 및 <xref:System.Data.DataRow.GetParentRow%2A> 메서드는 계층 탐색에 사용할 수 있습니다.  그러나 더 복잡한 작업을 수행하려면 개발자가 사용자 지정 쿼리를 작성해야 합니다.  이 경우 응용 프로그램의 성능이 저하되고 유지 관리가 어려워질 수 있습니다.  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]을 사용하면 <xref:System.Data.DataSet> 개체에 캐시된 데이터를 쉽고 빠르게 쿼리할 수 있습니다.  이러한 쿼리는 응용 프로그램 코드에 포함된 문자열 리터럴이 아니라 프로그래밍 언어 자체로 표현됩니다.  즉, 개발자가 별도의 쿼리 언어를 배우지 않아도 됩니다.  또한 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] IDE에서 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에 대한 컴파일 타임 검사, 정적 입력 및 IntelliSense 지원을 제공하므로 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 개발자는 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]을 사용하여 생산성을 높일 수 있습니다.  [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]은 하나 이상의 데이터 소스에서 통합된 데이터를 쿼리하는 데도 사용할 수 있습니다.  이 기능은 데이터를 유연하게 표현하고 처리해야 하는 많은 시나리오에서 유용하게 사용할 수 있습니다.  이러한 조작 방법은 일반적인 보고, 분석 및 비즈니스 인텔리전스 응용 프로그램에 특히 필요합니다.  
  
## LINQ to DataSet을 사용한 데이터 집합 쿼리  
 <xref:System.Data.DataSet>을 사용하여 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 개체를 쿼리하려면 먼저 <xref:System.Data.DataSet>을 채워야 합니다. <xref:System.Data.Common.DataAdapter> 클래스 또는 [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)을 사용하는 등 여러 가지 방법으로 <xref:System.Data.DataSet>에 데이터를 로드할 수 있습니다.  데이터가 <xref:System.Data.DataSet> 개체에 로드되면 해당 개체를 쿼리할 수 있습니다.  [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]으로 쿼리를 작성하는 작업은 다른 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] 사용 데이터 소스에 대해 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]를 사용하는 것과 비슷합니다.  [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 쿼리는 <xref:System.Data.DataSet> 및 <xref:System.Linq.Enumerable.Join%2A> 표준 쿼리 연산자를 사용하여 <xref:System.Linq.Enumerable.GroupJoin%2A>의 단일 테이블 또는 여러 테이블에 대해 수행할 수 있습니다.  
  
 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 쿼리는 형식화 및 형식화되지 않은 <xref:System.Data.DataSet> 개체에 대해 지원됩니다.  응용 프로그램 디자인 타임에 <xref:System.Data.DataSet> 스키마가 인식되는 경우 형식화된 <xref:System.Data.DataSet>을 사용하는 것이 좋습니다. 형식화된 <xref:System.Data.DataSet>에서 테이블과 행에는 각 열에 대한 형식화된 멤버가 있으며, 이를 통해 간단하고 이해하기 쉬운 쿼리를 만들 수 있습니다.  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]은 System.Core.dll에 구현된 표준 쿼리 연산자뿐 아니라 <xref:System.Data.DataSet> 개체 집합을 쉽게 쿼리하는 데 도움이 되는 여러 <xref:System.Data.DataRow>별 확장을 추가합니다.  이러한 <xref:System.Data.DataSet>별 확장에는 행의 시퀀스를 비교하는 연산자와 <xref:System.Data.DataRow>의 열 값에 액세스할 수 있도록 하는 메서드가 포함됩니다.  
  
## N 계층 응용 프로그램과 LINQ to DataSet  
 N 계층 데이터 응용 프로그램은 여러 논리 계층으로 분리된 데이터 중심 응용 프로그램입니다.  일반적인 N 계층 응용 프로그램에는 프레젠테이션 계층, 중간 계층 및 데이터 계층이 포함됩니다.  응용 프로그램 구성 요소를 별도의 계층으로 분리하면 응용 프로그램의 유지 관리성과 확장성이 높아집니다.  N 계층 데이터 응용 프로그램에 대한 자세한 내용은 [N 계층 응용 프로그램에서 데이터 집합 작업 작업](../Topic/Work%20with%20datasets%20in%20n-tier%20applications.md)을 참조하세요.  
  
 N 계층 응용 프로그램에서 <xref:System.Data.DataSet>은 주로 중간 계층에 사용되어 웹 응용 프로그램의 정보를 캐시합니다.  [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리 기능은 확장 메서드를 통해 구현되고 기존 ADO.NET 2.0 <xref:System.Data.DataSet>을 확장합니다.  
  
## 참고 항목  
 [DataSet 쿼리](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)