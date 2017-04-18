---
title: "DiffGrams | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DiffGrams
DiffGram은 현재 및 원래의 데이터 요소 버전을 식별하는 XML 형식입니다.  <xref:System.Data.DataSet>은 DiffGram 형식을 사용하여 자신의 내용을 로드하고 유지시키며 네트워크 연결을 통한 전송을 위해 이 내용을 serialize합니다.  <xref:System.Data.DataSet>이 DiffGram으로 작성되면 DiffGram은 스키마를 통하지 않고 **Original** 및 **Current** 행 버전 모두의 열 값, 행 오류 정보 및 행 순서 등 <xref:System.Data.DataSet>의 내용을 정확하게 다시 만드는 데 필요한 모든 정보로 채워집니다.  
  
 XML Web services로부터 <xref:System.Data.DataSet>을 보내고 검색할 때 DiffGram 형식이 암시적으로 사용됩니다.  또한 **ReadXml** 메서드를 사용하여 XML에서 <xref:System.Data.DataSet>의 내용을 로드하거나 **WriteXml** 메서드를 사용하여 <xref:System.Data.DataSet>의 내용을 XML로 작성할 때 내용을 DiffGram으로 읽거나 작성하도록 지정할 수 있습니다.  자세한 내용은 [XML로부터 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) 및 [DataSet 내용을 XML 데이터로 쓰기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)를 참조하세요.  
  
 DiffGram 형식은 .NET Framework에서 주로 <xref:System.Data.DataSet>의 내용에 대한 serialization 형식으로 사용되지만 DiffGrams을 사용하여 Microsoft SQL Server 데이터베이스의 테이블에 있는 데이터를 수정할 수도 있습니다.  
  
 모든 테이블의 내용을 **\<diffgram\>** 요소에 기록하여 Diffgram을 생성합니다.  
  
### Diffgram을 생성하려면  
  
1.  Root 테이블\(부모가 없는 테이블\) 목록을 생성합니다.  
  
2.  목록의 각 테이블 및 해당 하위 항목에 대해 첫 번째 Diffgram 섹션에 모든 행의 현재 버전을 기록합니다.  
  
3.  <xref:System.Data.DataSet>의 각 테이블에 대해 Diffgram의 **\<before\>** 섹션에 모든 행의 원래 버전\(있는 경우\)을 기록합니다.  
  
4.  오류가 있는 행의 경우 Diffgram의 **\<errors\>** 섹션에 오류 내용을 기록합니다.  
  
 Diffgram은 XML 파일의 시작부터 끝의 순서로 처리됩니다.  
  
### Diffgram을 처리하려면  
  
1.  행의 현재 버전이 포함된 Diffgram의 첫 번째 섹션을 처리합니다.  
  
2.  수정 및 삭제된 행의 원래 행 버전이 포함된 두 번째 또는 **\<before\>** 섹션을 처리합니다.  
  
    > [!NOTE]
    >  행이 삭제된 것으로 표시된 경우 현재 <xref:System.Data.DataSet>의 `Cascade` 속성에 따라 삭제 작업에서 행의 하위 항목도 삭제할 수 있습니다.  
  
3.  **\<errors\>** 섹션을 처리합니다.  이 섹션에서 각 항목에 대한 지정된 행과 열의 오류 정보를 설정합니다.  
  
> [!NOTE]
>  <xref:System.Data.XmlWriteMode>를 Diffgram로 설정하면 대상 <xref:System.Data.DataSet>과 원래 <xref:System.Data.DataSet>의 내용이 다를 수 있습니다.  
  
## DiffGram 형식  
 DiffGram 형식에는 다음 예제에서와 같이 현재 데이터, 원래\(또는 "이전"\) 데이터 및 오류 섹션 등 세 가지 섹션이 있습니다.  
  
```  
<?xml version="1.0"?>  
<diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"  
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1"  
         xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  
   <DataInstance>  
   </DataInstance>  
  
  <diffgr:before>  
  </diffgr:before>  
  
  <diffgr:errors>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
 DiffGram 형식은 다음 데이터 블록으로 구성됩니다.  
  
 **\<**  ***DataInstance***  **\>**  
 이 요소의 이름인 ***DataInstance***는 이 문서에서 설명의 편의를 위해 사용됩니다.  ***DataInstance*** 요소는 <xref:System.Data.DataSet>이나 <xref:System.Data.DataTable>의 행을 나타냅니다.  이 요소에는 *DataInstance* 대신 <xref:System.Data.DataSet> 또는 <xref:System.Data.DataTable>이라는 이름이 포함됩니다.  이 DiffGram 형식의 블록에는 수정 여부에 관계없이 현재 데이터가 들어 있습니다.  수정된 요소나 행은 **diffgr:hasChanges** 주석으로 식별됩니다.  
  
 **\<diffgr:before\>**  
 이 DiffGram 블록 형식에는 행의 원래 버전이 포함됩니다.  이 블록에 있는 요소는 **diffgr:id** 주석을 사용하여 ***DataInstance*** 블록에 있는 요소에 일치됩니다.  
  
 **\<diffgr:errors\>**  
 이 DiffGram 블록 형식에는 ***DataInstance*** 블록에 있는 특정 행의 오류 정보가 들어 있습니다.  이 블록에 있는 요소는 **diffgr:id** 주석을 사용하여 ***DataInstance*** 블록에 있는 요소에 일치됩니다.  
  
## DiffGram 주석  
 DiffGrams은 여러 주석을 사용하여 <xref:System.Data.DataSet>에서 다른 행 버전이나 오류 정보를 표시하는 다양한 DiffGrams 블록의 요소를 나타냅니다.  
  
 다음 표에서는 DiffGram 네임스페이스 **urn:schemas\-microsoft\-com:xml\-diffgram\-v1**에 정의된 DiffGram 주석에 대해 설명합니다.  
  
|주석|설명|  
|--------|--------|  
|**id**|**\<diffgr:before\>** 및 **\<diffgr:errors\>** 블록에 있는 요소를 **\<** ***DataInstance*** **\>** 블록에 있는 요소와 연관시키는 데 사용됩니다.  **diffgr:id** 주석이 있는 값의 형태는 *\[TableName\]\[RowIdentifier\]*입니다.  예: `<Customers diffgr:id="Customers1">`|  
|**parentId**|**\<**  ***DataInstance***  **\>** 블록의 요소 중에서 현재 요소의 부모 요소를 식별합니다.  **diffgr:parentId** 주석이 있는 값의 형태는 *\[TableName\]\[RowIdentifier\]*입니다.  예: `<Orders diffgr:parentId="Customers1">`|  
|**hasChanges**|**\<**  ***DataInstance***  **\>** 블록의 행을 수정된 것으로 식별합니다.  **hasChanges** 주석에는 다음 두 값 중 하나가 있습니다.<br /><br /> **inserted**<br /> **Added** 행을 식별합니다.<br /><br /> **modified**<br /> **\<diffgr:before\>** 블록에 **Original** 행 버전이 포함된 **Modified** 행을 식별합니다.  **Deleted** 행의 경우 **\<diffgr:before\>** 블록에 **Original** 행 버전이 있지만 **\<** ***DataInstance*** **\>** 블록에는 주석이 있는 요소가 없습니다.|  
|**hasErrors**|**RowError**가 있는 **\<** ***DataInstance*** **\>** 블록의 행을 식별합니다.  오류 요소는 **\<diffgr:errors\>** 블록에 있습니다.|  
|**오류**|**\<diffgr:errors\>** 블록에 있는 특정 요소의 **RowError** 텍스트를 포함합니다.|  
  
 <xref:System.Data.DataSet>에는 자신의 내용을 DiffGram으로 읽거나 작성할 때 추가 주석이 포함됩니다.  다음 표에서는 네임스페이스 **urn:schemas\-microsoft\-com:xml\-msdata**에 정의되어 있는 이러한 추가 주석에 대해 설명합니다.  
  
|주석|설명|  
|--------|--------|  
|**RowOrder**|원래 데이터의 행 순서를 유지하며 특정 <xref:System.Data.DataTable>에 있는 행의 인덱스를 식별합니다.|  
|**Hidden**|**ColumnMapping** 속성이 **MappingType.Hidden**으로 설정된 열을 식별합니다.  이 특성은 **msdata:hidden** *\[ColumnName\]*\="*value*" 형식으로 작성됩니다.  예: `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`<br /><br /> 데이터가 있는 숨겨진 열만 DiffGram 특성으로 작성됩니다.  데이터가 없는 숨겨진 열은 무시됩니다.|  
  
## 샘플 DiffGram  
 다음은 DiffGram 형식의 예제입니다.  이 예제에서는 변경 사항이 커밋되기 전에 테이블에 있는 행을 업데이트한 결과를 보여 줍니다.  CustomerID가 "ALFKI"인 행이 수정되었지만 업데이트되지는 않았습니다.  그 결과 **\<** ***DataInstance*** **\>** 블록에는 **diffgr:id**가 "Customers1"인 **Current** 행이 생기며 **\<diffgr:before\>** 블록에는 **diffgr:id**가 "Customers1"인 **Original** 행이 생깁니다.  CustomerID가 "ANATR"인 행에는 **RowError**가 있으므로 `diffgr:hasErrors="true"`라는 주석이 추가되고 **\<diffgr:errors\>** 블록에는 관련 요소가 생깁니다.  
  
```  
<diffgr:diffgram xmlns:msdata="urn:schemas-microsoft-com:xml-msdata" xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
  <CustomerDataSet>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0" diffgr:hasChanges="modified">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>New Company</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers2" msdata:rowOrder="1" diffgram:hasErrors="true">  
      <CustomerID>ANATR</CustomerID>  
      <CompanyName>Ana Trujillo Emparedados y Helados</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers3" msdata:rowOrder="2">  
      <CustomerID>ANTON</CustomerID>  
      <CompanyName>Antonio Moreno Taquera</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers4" msdata:rowOrder="3">  
      <CustomerID>AROUT</CustomerID>  
      <CompanyName>Around the Horn</CompanyName>  
    </Customers>  
  </CustomerDataSet>  
  <diffgr:before>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>Alfreds Futterkiste</CompanyName>  
    </Customers>  
  </diffgr:before>  
  <diffgr:errors>  
    <Customers diffgr:id="Customers2" diffgr:Error="An optimistic concurrency violation has occurred for this row."/>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
## 참고 항목  
 [DataSet에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [XML로부터 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [DataSet 내용을 XML 데이터로 쓰기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)   
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)