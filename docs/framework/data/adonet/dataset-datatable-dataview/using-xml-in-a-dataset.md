---
title: 데이터 집합에서 XML 사용
ms.date: 03/30/2017
ms.assetid: 35138159-e199-49ec-baf7-1ec6777e171e
ms.openlocfilehash: c5a4df5f2c77853864f51ee9b226f412f382dd09
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760335"
---
# <a name="using-xml-in-a-dataset"></a>데이터 집합에서 XML 사용
ADO.NET을 사용하면 XML 스트림이나 문서에서 <xref:System.Data.DataSet>을 채울 수 있습니다. XML 스트림이나 문서를 사용하여 데이터, 스키마 정보 또는 두 가지 모두를 <xref:System.Data.DataSet>에 제공할 수 있습니다. XML 스트림이나 문서에서 제공되는 정보를 <xref:System.Data.DataSet>에 있는 기존 데이터나 스키마 정보와 결합할 수 있습니다.  
  
 또한 ADO.NET을 사용하면 스키마 사용 여부에 관계없이 <xref:System.Data.DataSet>의 XML 표현을 만들어 다른 응용 프로그램이나 XML 사용 플랫폼에서 사용할 수 있도록 HTTP를 통해 <xref:System.Data.DataSet>을 전송할 수 있습니다. <xref:System.Data.DataSet>의 XML 표현에서 데이터는 XML로 작성되며, 스키마는 XML 표현의 인라인에 포함되어 있는 경우 XSD(XML 스키마 정의 언어)를 사용하여 작성됩니다. XML 및 XML 스키마에서는 <xref:System.Data.DataSet>의 내용을 원격 클라이언트와 주고 받기에 알맞은 형식을 제공합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [DiffGram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 <xref:System.Data.DataSet>의 내용을 읽거나 쓰는 데 사용하는 XML 형식인 DiffGram에 대해 자세히 설명합니다.  
  
 [XML에서 데이터 집합 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 XML 문서에서 <xref:System.Data.DataSet>의 내용을 로드할 때 고려할 여러 가지 옵션에 대해 설명합니다.  
  
 [데이터 집합 콘텐츠를 XML 데이터로 작성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 <xref:System.Data.DataSet>의 내용을 XML 데이터로 생성하는 방법과 사용할 수 있는 여러 XML 형식 옵션에 대해 설명합니다.  
  
 [XML에서 데이터 집합 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 XML에서 <xref:System.Data.DataSet>의 스키마를 로드하는 데 사용하는 <xref:System.Data.DataSet> 메서드에 대해 설명합니다.  
  
 [데이터 집합 스키마 정보를 XSD로 작성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)  
 XML 스키마의 용도와 <xref:System.Data.DataSet>에서 XML 스키마를 생성하는 방법에 대해 설명합니다.  
  
 [데이터 집합 및 XmlDataDocument 동기화](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 단일 데이터 집합에 대한 관계형 뷰와 계층적 뷰에 동기적으로 액세스할 수 있는 .NET Framework의 기능과 <xref:System.Data.DataSet> 및 <xref:System.Xml.XmlDataDocument> 간에 동기적 관계를 만드는 방법에 대해 설명합니다.  
  
 [DataRelation 중첩](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 <xref:System.Data.DataRelation>의 내용을 XML 데이터로 표현할 경우 중첩된 <xref:System.Data.DataSet> 개체의 중요성과 이러한 개체를 만드는 방법에 대해 설명합니다.  
  
 [XML 스키마에서 데이터 집합 관계형 구조 파생(XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 XML 스키마에서 만들어진 <xref:System.Data.DataSet>의 관계 구조 또는 스키마에 대해 설명합니다.  
  
 [XML에서 데이터 집합 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 XML 요소에서 유추할 때 만들어지는 <xref:System.Data.DataSet>의 관계형 구조 또는 스키마에 대해 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [ADO.NET 개요](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 ADO.NET 아키텍처 및 구성 요소에 대해 설명하고, 이를 사용하여 기존 데이터 소스에 액세스하고 응용 프로그램 데이터를 관리하는 방법을 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
