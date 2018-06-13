---
title: 데이터 집합 및 XmlDataDocument 동기화
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: cb16d4fae5dc153361fe2cb31cfd6af9b4b83c68
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759168"
---
# <a name="dataset-and-xmldatadocument-synchronization"></a>데이터 집합 및 XmlDataDocument 동기화
ADO.NET <xref:System.Data.DataSet>으로 데이터의 관계형 표현을 사용할 수 있습니다. 계층적으로 데이터에 액세스하기 위해 .NET Framework에서 사용 가능한 XML 클래스를 사용할 수 있습니다. 지금까지는 데이터의 이와 같은 두 가지 표현이 별도로 사용되어 왔습니다. 그러나.NET Framework에서는 통해 데이터의 관계형 및 계층적 표현에 대 한 실시간으로 동시 액세스는 **데이터 집합** 개체 및 <xref:System.Xml.XmlDataDocument> 개체를 각각.  
  
 경우는 **DataSet** 와 동기화 되는 **XmlDataDocument**, 두 개체는 단일 데이터 집합을 사용 하는 합니다. 즉, 한 스키마를 변경 하는 경우는 **데이터 집합**에 변경 내용이 반영:는 **XmlDataDocument**, 그 반대의 합니다. 간의 관계는 **데이터 집합** 및 **XmlDataDocument** 기반 서비스의 전체 제품군을 액세스 하는 단일 데이터 집합이 사용 하 여 단일 응용 프로그램을 허용 하 여 뛰어난 유연성을 만듭니다. 주위에서 **DataSet** (예: Web Forms 및 Windows Forms 컨트롤 및 Visual Studio.NET 디자이너) 스타일 시트 XSL (Extensible Language), XSLT (XSL Transformations), 및 XML 경로 포함 한 XML 서비스 도구 뿐만 아니라 언어 (XPath)입니다. 두 서비스를 모두 사용할 수 있으므로 응용 프로그램의 대상이 될 서비스 집합을 선택할 필요도 없습니다.  
  
 동기화 할 수 있는 여러 가지는 **DataSet** 와 **XmlDataDocument**합니다. 다음과 같은 작업을 수행할 수 있습니다.  
  
-   채우기는 **데이터 집합** 스키마 (즉, 관계형 구조) 및 데이터를 새 동기화 하십시오 **XmlDataDocument**합니다. 이렇게 하면 기존 관계형 데이터를 계층적으로 표시할 수 있습니다. 예를 들어:  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema and data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema and data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    ```  
  
-   채우기는 **데이터 집합** 스키마만 (같은 강력한 형식의 **데이터 집합**)와 동기화는 **XmlDataDocument**, 한 다음 로드는  **XmlDataDocument** XML 문서에서 합니다. 이렇게 하면 기존 계층적 데이터를 관계형으로 표시할 수 있습니다. 테이블 이름과 열 이름은 프로그램 **DataSet** 스키마와 동기화 할 XML 요소의 이름과 일치 해야 합니다. 이 때 대/소문자도 일치해야 합니다.  
  
     스키마는 **DataSet** 만 관계형 뷰에 노출 시킬 XML 요소와 일치 해야 합니다. 이렇게 하면 XML 문서는 아주 크게, 이 문서의 관계형 "창"은 매우 작게 만들 수 있습니다. **XmlDataDocument** 경우에 전체 XML 문서에서 유지 된 **데이터 집합** 문서의 극히 일부분만 노출 합니다. (이 항목의 자세한 예제를 보려면 [DataSet을 XmlDataDocument와 동기화](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)  
  
     다음 코드 예제를 만들기 위한 단계를 보여 줍니다.는 **DataSet** 및 해당 스키마를 채운와 동기화는 **XmlDataDocument**합니다. **DataSet** 스키마만 요소와 일치 해야는 **XmlDataDocument** 사용 하 여 노출 하려는 **데이터 집합**합니다.  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema, but not data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema, but not data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
     로드할 수 없습니다는 **XmlDataDocument** 와 동기화 하는 경우는 **데이터 집합** 데이터가 들어 있는입니다. 로드하는 경우에는 예외가 throw됩니다.  
  
-   새 **XmlDataDocument** XML 문서 로부터 로드 한 다음 사용 하 여 데이터의 관계형 뷰에 액세스 하 고는 **데이터 집합** 의 속성은 **XmlDataDocument**합니다. 스키마를 설정 해야 합니다는 **데이터 집합** 의 데이터를 볼 수는 **XmlDataDocument** 를 사용 하는 **데이터 집합**합니다. 마찬가지로 테이블 이름과 열 이름은 프로그램 **DataSet** 스키마와 동기화 할 XML 요소의 이름과 일치 해야 합니다. 이 때 대/소문자도 일치해야 합니다.  
  
     다음 코드 예제에 있는 데이터의 관계형 뷰에 액세스 하는 방법을 보여 줍니다는 **XmlDataDocument**합니다.  
  
    ```vb  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument  
    Dim dataSet As DataSet = xmlDoc.DataSet  
  
    ' Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    XmlDataDocument xmlDoc = new XmlDataDocument();  
    DataSet dataSet = xmlDoc.DataSet;  
  
    // Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
 동기화 할 경우의 또 다른 이점은 **XmlDataDocument** 와 **DataSet** XML 문서의 신뢰도 유지할 것입니다. 경우는 **DataSet** 사용 하 여 XML 문서에서 채워집니다 **ReadXml**데이터를 사용 하 여 XML 문서 다시 작성할 때 **WriteXml** 에서 상당히 달라질 수 있습니다는 원본 XML 문서입니다. 때문에 이것이 **DataSet** 공백 또는 XML 문서에서 요소 순서 등의 계층적 정보가 같은 서식을 유지 관리 하지 않습니다. **DataSet** 의 스키마와 일치 하지 않아 무시 되었던 XML 문서에서 요소를 포함 하지 않습니다는 **Dataset**합니다. 동기화는 **XmlDataDocument** 와 **DataSet** 에서 유지할 수는 원래 XML 문서의 서식 및 계층적 요소 구조는 **XmlDataDocument**, 동안는 **데이터 집합** 에 적합 한 데이터와 스키마 정보만 들어는 **데이터 집합**합니다.  
  
 동기화 할 때는 **DataSet** 와 **XmlDataDocument**, 여부에 따라 결과가 달라질 수 있습니다 프로그램 <xref:System.Data.DataRelation> 개체의 중첩 합니다. 자세한 내용은 참조 [Datarelation 중첩](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [XmlDataDocument로 데이터 집합 동기화](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 강력한 형식의 동기화 하는 방법을 보여 줍니다 **데이터 집합**, 최소한의 스키마와 **XmlDataDocument**합니다.  
  
 [데이터 집합에서 XPath 쿼리 수행](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 내용에 대해 XPath 쿼리를 수행 하는 방법을 보여 줍니다는 **DataSet**합니다.  
  
 [XSLT 변형을 DataSet에 적용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 내용에 XSLT 변환을 적용 하는 방법을 보여 줍니다는 **DataSet**합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 설명 방법을 **DataSet** 로드 하 고 유지의 내용을 포함 한 데이터 소스로 XML와 상호 작용 하는 **데이터 집합** XML 데이터로 합니다.  
  
 [DataRelation 중첩](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 중요 성과 중첩 **DataRelation** 의 콘텐츠를 나타내는 개체는 **DataSet** XML 데이터로 이러한 관계를 만드는 방법에 설명 합니다.  
  
 [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 설명의 **데이터 집합** 및 응용 프로그램 데이터를 관리 하 고 관계형 데이터베이스 및 XML을 포함 하 여 데이터 소스와 상호 작용을 사용 하는 방법입니다.  
  
 <xref:System.Xml.XmlDataDocument>  
 에 대 한 참조 정보는 **XmlDataDocument** 클래스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
