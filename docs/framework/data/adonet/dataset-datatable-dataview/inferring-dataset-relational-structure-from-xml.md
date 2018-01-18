---
title: "XML에서 데이터 집합 관계형 구조 유추"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd2f41c6-6785-420e-aa43-3ceb0bdccdce
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bae6e82eaf0f01847c304e094d98fe420e6f8b65
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="inferring-dataset-relational-structure-from-xml"></a>XML에서 데이터 집합 관계형 구조 유추
<xref:System.Data.DataSet>의 관계형 구조 또는 스키마는 테이블, 열, 제약 조건 및 관계로 구성됩니다. XML에서 <xref:System.Data.DataSet>을 로드할 때 로드되는 XML에서 스키마를 명시적으로 또는 유추를 통해 미리 정의하거나 만들 수 있습니다. 내용과 스키마를 로드 하는 방법에 대 한 자세한 내용은 <xref:System.Data.DataSet> XML에서 참조 [XML 로부터 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) 및 [XML에서 데이터 집합 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)합니다.  
  
 하는 경우의 스키마는 <xref:System.Data.DataSet> 만들어집니다 XML에서 선호 되는 방법 중 하나는 XML 스키마 정의 언어 (XSD)를 사용 하 여 스키마를 명시적으로 지정 하는 (에 설명 된 대로 [파생 된 데이터 집합 관계형 구조에서 XSD (XML 스키마) ](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)) 또는 XML 데이터 (XDR)를 절감 합니다. XML에서 XML 스키마나 XDR 스키마를 사용할 수 없으면 <xref:System.Data.DataSet>의 스키마는 XML 요소 및 특성의 구조로부터 유추할 수 있습니다.  
  
 이 단원에서는 XML 요소와 특성 및 이들의 구조, 그리고 결과로서 유추된 <xref:System.Data.DataSet> 스키마를 보여 줌으로써 <xref:System.Data.DataSet> 스키마 유추 규칙을 설명합니다.  
  
 XML 문서에 나타난 모든 특성을 유추 과정에 포함시켜야 하는 것은 아닙니다. 네임스페이스로 한정된 특성에서는 XML 문서에는 중요하지만 <xref:System.Data.DataSet> 스키마에는 중요하지 않은 메타데이터를 포함할 수 있습니다. <xref:System.Data.DataSet.InferXmlSchema%2A>를 사용하면 유추 과정에서 네임스페이스를 무시하도록 지정할 수 있습니다. 자세한 내용은 참조 [XML에서 데이터 집합 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [데이터 집합 스키마 유추 프로세스 요약](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/summary-of-the-dataset-schema-inference-process.md)  
 XML로부터 <xref:System.Data.DataSet>의 스키마를 유추하는 규칙에 대한 고급 요약 정보를 제공합니다.  
  
 [테이블 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md)  
 <xref:System.Data.DataSet>에서 테이블로 유추되는 XML 요소에 대해 설명합니다.  
  
 [열 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-columns.md)  
 테이블 열로 유추되는 XML 요소 및 특성에 대해 설명합니다.  
  
 [관계 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-relationships.md)  
 중첩된 유추 테이블에 사용하도록 만들어지는 <xref:System.Data.DataRelation> 및 <xref:System.Data.ForeignKeyConstraint> 개체에 대해 설명합니다.  
  
 [요소 텍스트 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-element-text.md)  
 XML 요소의 텍스트에 사용하기 위해 만드는 열과 XML 요소 내의 텍스트가 무시되는 경우에 대해 설명합니다.  
  
 [유추 제한](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inference-limitations.md)  
 스키마 유추의 제한 사항에 대해 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <xref:System.Data.DataSet> 개체가 XML 데이터와 상호 작용하는 방법을 설명합니다.  
  
 [XML 스키마에서 데이터 집합 관계형 구조 파생(XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 XSD(XML 스키마 정의 언어) 스키마에서 만들어지는 <xref:System.Data.DataSet>의 관계 구조 또는 스키마에 대해 설명합니다.  
  
 [ADO.NET 개요](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 ADO.NET 아키텍처 및 구성 요소에 대해 설명하고, 이를 사용하여 기존 데이터 소스에 액세스하고 응용 프로그램 데이터를 관리하는 방법을 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
