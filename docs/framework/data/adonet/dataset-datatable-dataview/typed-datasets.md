---
title: "형식화된 DataSets | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 형식화된 DataSets
<xref:System.Data.DataSet>에서는 약한 형식의 변수를 통해 런타임에 바인딩하여 값에 액세스할 수도 있고 강력한 형식의 메타포를 통해 데이터에 액세스할 수도 있습니다.  **DataSet**의 일부인 테이블과 열에는 사용자에게 익숙한 이름과 강력한 형식의 변수를 사용하여 액세스할 수 있습니다.  
  
 형식화된 **DataSet**은 **DataSet**에서 파생되는 클래스입니다.  따라서, 형식화된 **DataSet**은 모든 메서드, 이벤트 및 속성을 상속합니다.  또한 형식화된 **DataSet**에서는 강력한 형식의 메서드, 이벤트 및 속성을 제공합니다.  즉, 컬렉션 기반의 메서드 대신 이름을 사용하여 테이블과 열에 액세스할 수 있습니다.  형식화된 **DataSet**을 사용하면 코드의 가독성도 개선되지만 Visual Studio .NET 코드 편집기에서 사용자가 입력할 때 줄이 자동으로 완성되도록 만들 수도 있습니다.  
  
 또한, 강력한 형식의 **DataSet**에서는 컴파일 타임에 올바른 형식으로 값에 액세스합니다.  강력한 형식의 **DataSet**을 사용하면 형식이 일치하지 않는 오류가 있을 경우 이를 런타임이 아니라 코드를 컴파일할 때 발견할 수 있습니다.  
  
## 단원 내용  
 [강력한 형식의 DataSets 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 강력한 형식의 **DataSet**을 만들고 사용하는 방법을 설명합니다.  
  
 [형식화된 DataSets 주석 지정](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 강력한 형식의 **DataSet**을 생성하는 데 사용하는 XSD\(XML 스키마 정의 언어\) 스키마에 주석을 달아 기본 스키마를 변경하지 않고서도 **DataSet** 요소의 이름을 사용자에게 익숙한 이름으로 지정하는 방법을 설명합니다.  
  
## 참고 항목  
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)