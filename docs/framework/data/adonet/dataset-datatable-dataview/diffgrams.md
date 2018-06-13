---
title: DiffGram
ms.date: 03/30/2017
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
ms.openlocfilehash: 2b04fd69af94ce49fb5973af5ac74c2933fe58bf
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760036"
---
# <a name="diffgrams"></a>DiffGram
DiffGram은 현재 및 원래의 데이터 요소 버전을 식별하는 XML 형식입니다. <xref:System.Data.DataSet>은 DiffGram 형식을 사용하여 자신의 내용을 로드하고 유지시키며 네트워크 연결을 통한 전송을 위해 이 내용을 serialize합니다. 경우는 <xref:System.Data.DataSet> 필요한 모든 정보를 정확 하 게 다시의 내용을 통해 스키마 하지의 DiffGram 채우는 DiffGram으로 작성 되는 <xref:System.Data.DataSet>, 둘 다에서 열 값을 포함 하는 **원래** 및 **현재** 행 버전, 행 오류 정보 및 행 순서입니다.  
  
 XML Web services로부터 <xref:System.Data.DataSet>을 보내고 검색할 때 DiffGram 형식이 암시적으로 사용됩니다. 또한의 내용을 로드할 때 한 <xref:System.Data.DataSet> 사용 하 여 XML에서는 **ReadXml** 메서드를의 내용을 쓸 때 또는 <xref:System.Data.DataSet> 사용 하 여 XML에는 **WriteXml** 메서드를 지정할 수 있습니다 내용은 읽거나은 DiffGram으로 작성 합니다. 자세한 내용은 참조 [XML 로부터 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) 및 [XML 데이터로 작성 데이터 집합 콘텐츠](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)합니다.  
  
 DiffGram 형식은 .NET Framework에서 주로 <xref:System.Data.DataSet>의 내용에 대한 serialization 형식으로 사용되지만 DiffGrams을 사용하여 Microsoft SQL Server 데이터베이스의 테이블에 있는 데이터를 수정할 수도 있습니다.  
  
 모든 테이블의 내용을 작성 하 여 Diffgram을 생성 한  **\<diffgram >** 요소입니다.  
  
### <a name="to-generate-a-diffgram"></a>Diffgram을 생성하려면  
  
1.  Root 테이블(부모가 없는 테이블) 목록을 생성합니다.  
  
2.  목록의 각 테이블 및 해당 하위 항목에 대해 첫 번째 Diffgram 섹션에 모든 행의 현재 버전을 기록합니다.  
  
3.  각 테이블에는 <xref:System.Data.DataSet>, 있는 경우 모든 행의 원래 버전 기록에  **\<하기 전에 >** Diffgram의 섹션입니다.  
  
4.  오류가 있는 행에 오류 내용을 기록는  **\<오류 >** Diffgram의 섹션입니다.  
  
 Diffgram은 XML 파일의 시작부터 끝의 순서로 처리됩니다.  
  
### <a name="to-process-a-diffgram"></a>Diffgram을 처리하려면  
  
1.  행의 현재 버전이 포함된 Diffgram의 첫 번째 섹션을 처리합니다.  
  
2.  두 번째 처리 또는  **\<하기 전에 >** 의 원래 행 버전이 포함 된 섹션 수정 및 삭제 된 행입니다.  
  
    > [!NOTE]
    >  행이 삭제된 것으로 표시된 경우 현재 `Cascade`의 <xref:System.Data.DataSet> 속성에 따라 삭제 작업에서 행의 하위 항목도 삭제할 수 있습니다.  
  
3.  프로세스는  **\<오류 >** 섹션. 이 섹션에서 각 항목에 대한 지정된 행과 열의 오류 정보를 설정합니다.  
  
> [!NOTE]
>  <xref:System.Data.XmlWriteMode>를 Diffgram로 설정하면 대상 <xref:System.Data.DataSet>과 원래 <xref:System.Data.DataSet>의 내용이 다를 수 있습니다.  
  
## <a name="diffgram-format"></a>DiffGram 형식  
 DiffGram 형식에는 다음 예제에서와 같이 현재 데이터, 원래(또는 "이전") 데이터 및 오류 섹션 등 세 가지 섹션이 있습니다.  
  
```xml  
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
  
 **\<**  ***DataInstance***  **>**  
 이 요소의 이름을 ***DataInstance***,이 설명서에서 설명 용으로 사용 됩니다. A ***DataInstance*** 요소 나타냅니다는 <xref:System.Data.DataSet> 또는 행을 한 <xref:System.Data.DataTable>합니다. 대신 *DataInstance*, 요소에는의 이름만 포함 되는 <xref:System.Data.DataSet> 또는 <xref:System.Data.DataTable>합니다. 이 DiffGram 형식의 블록에는 수정 여부에 관계없이 현재 데이터가 들어 있습니다. 요소 또는 수정 된 행으로 식별 되는 **diffgr: haschanges** 주석입니다.  
  
 **\<diffgr:before>**  
 이 DiffGram 블록 형식에는 행의 원래 버전이 포함됩니다. 이 블록의 요소는 요소에 일치는 ***DataInstance*** 사용 하 여는 **diffgr: id** 주석입니다.  
  
 **\<diffgr:errors>**  
 특정 행에 대 한 오류 정보를 포함 하는이 DiffGram 형식의이 블록에는 ***DataInstance*** 블록입니다. 이 블록의 요소는 요소에 일치는 ***DataInstance*** 사용 하 여는 **diffgr: id** 주석입니다.  
  
## <a name="diffgram-annotations"></a>DiffGram 주석  
 DiffGrams은 여러 주석을 사용하여 <xref:System.Data.DataSet>에서 다른 행 버전이나 오류 정보를 표시하는 다양한 DiffGrams 블록의 요소를 나타냅니다.  
  
 다음 표에서 DiffGram 네임 스페이스에 정의 된 DiffGram 주석에 대해 설명 **:-microsoft-com:xml-diffgram-v1**합니다.  
  
|주석|설명|  
|----------------|-----------------|  
|**ID**|요소와 쌍으로 연결 하는 데 사용 된  **\<diffgr: 하기 전에 >** 및  **\<diffgr:errors >** 블록의 요소에는 **\<** ***DataInstance*** **>** 블록입니다. 와 값의 **diffgr: id** 주석 양식에 있는 *[TableName] [RowIdentifier]* 합니다. 예: `<Customers diffgr:id="Customers1">`|  
|**parentId**|요소를 식별 하는 **\<** ***DataInstance*** **>** 블록은 현재 요소의 부모 요소입니다. 와 값의 **diffgr: parentid** 주석 양식에 있는 *[TableName] [RowIdentifier]* 합니다. 예: `<Orders diffgr:parentId="Customers1">`|  
|**hasChanges**|행을 식별 하는 **\<** ***DataInstance*** **>** 수정 된 것을 차단 합니다. **hasChanges** 주석은 다음 두 값 중 하나일 수 있습니다.<br /><br /> **inserted**<br /> 식별 된 **Added** 행입니다.<br /><br /> **modified**<br /> 식별 한 **Modified** 포함 된 행은 **원래** 행 버전이  **\<diffgr: 하기 전에 >** 블록입니다. **Deleted** 행는 **원래** 행 버전에는  **\<diffgr: 하기 전에 >** 블록 있지만 에주석이달린요소가없습니다**\<** ***DataInstance*** **>** 블록입니다.|  
|**hasErrors**|행을 식별 하는 **\<** ***DataInstance*** **>** 블록와 함께 한 **RowError**합니다. Error 요소에 배치 되는  **\<diffgr:errors >** 블록입니다.|  
|**오류**|텍스트가 표시는 **RowError** 특정 요소에 대 한는  **\<diffgr:errors >** 블록입니다.|  
  
 <xref:System.Data.DataSet>에는 자신의 내용을 DiffGram으로 읽거나 작성할 때 추가 주석이 포함됩니다. 다음 표에서 이러한 추가 주석에 네임 스페이스에 정의 된 설명 **:-microsoft-com:xml-msdata**합니다.  
  
|주석|설명|  
|----------------|-----------------|  
|**RowOrder**|원래 데이터의 행 순서를 유지하며 특정 <xref:System.Data.DataTable>에 있는 행의 인덱스를 식별합니다.|  
|**숨김**|있는 것으로 열을 식별 하는 **ColumnMapping** 속성이로 설정 **MappingType.Hidden**합니다. 특성의 형식으로 기록 됩니다 **msdata: 숨겨진** *[ColumnName]*= "*값*"입니다. 예: `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`<br /><br /> 데이터가 있는 숨겨진 열만 DiffGram 특성으로 작성됩니다. 데이터가 없는 숨겨진 열은 무시됩니다.|  
  
## <a name="sample-diffgram"></a>샘플 DiffGram  
 다음은 DiffGram 형식의 예제입니다. 이 예제에서는 변경 사항이 커밋되기 전에 테이블에 있는 행을 업데이트한 결과를 보여 줍니다. CustomerID가 "ALFKI"인 행이 수정되었지만 업데이트되지는 않았습니다. 결과적으로, 한 **현재** 인 행을 **diffgr: id** "Customers1"에서는 **\<** ***DataInstance*** **>** 블록 및 **원래** 인 행을 **diffgr: id** "Customers1"에서는  **\<diffgr: 하기 전에 >** 블록입니다. "ANATR" 인 CustomerID 행는 **RowError**주석으로 추가 되므로 `diffgr:hasErrors="true"` 있으면 다음에 관련된 요소가  **\<diffgr:errors >** 블록입니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [XML에서 데이터 집합 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [데이터 집합 콘텐츠를 XML 데이터로 작성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
