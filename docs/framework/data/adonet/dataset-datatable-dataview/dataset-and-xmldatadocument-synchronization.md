---
title: "DataSet 및 XmlDataDocument 동기화 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataSet 및 XmlDataDocument 동기화
ADO.NET <xref:System.Data.DataSet>으로 데이터의 관계형 표현을 사용할 수 있습니다.  계층적으로 데이터에 액세스하기 위해 .NET Framework에서 사용 가능한 XML 클래스를 사용할 수 있습니다.  지금까지는 데이터의 이와 같은 두 가지 표현이 별도로 사용되어 왔습니다.  그러나 .NET Framework에서는 **DataSet** 개체 및 <xref:System.Xml.XmlDataDocument> 개체를 각각 사용하여 관계형 및 계층적 데이터 표현에 실시간 및 동기적으로 액세스할 수 있습니다.  
  
 **DataSet**이 **XmlDataDocument**와 동기화되면 두 개체는 단일 데이터 집합을 사용하게 됩니다.  이것은 **DataSet**이 변경되면 변경 사항이 **XmlDataDocument**에 적용되며 그 반대의 경우도 마찬가지로 적용됨을 의미합니다.  **DataSet**과 **XmlDataDocument** 사이의 이러한 관계로 인해 단일 데이터 집합을 사용하는 단일 응용 프로그램을 사용할 수 있게 되므로 상당한 융통성이 생깁니다. 따라서 **DataSet** 사용을 위해 빌드된 모든 서비스, 예를 들면 Web Forms 및 Windows Forms 컨트롤과 Visual Studio .NET 디자이너 등에 액세스할 수 있을 뿐 아니라 XSL\(Extensible Stylesheet Language\), XSLT\(XSL Transformations\) 및 XPath\(XML Path Language\)를 포함한 XML 서비스에도 액세스할 수 있습니다.  두 서비스를 모두 사용할 수 있으므로 응용 프로그램의 대상이 될 서비스 집합을 선택할 필요도 없습니다.  
  
 **DataSet**을 **XmlDataDocument**와 동기화할 수 있는 방법에는 여러 가지가 있습니다.  다음과 같은 작업을 수행할 수 있습니다.  
  
-   **DataSet**을 스키마\(관계형 구조\)와 데이터로 채운 다음 새 **XmlDataDocument**와 동기화합니다.  이렇게 하면 기존 관계형 데이터를 계층적으로 표시할 수 있습니다.  예를 들면 다음과 같습니다.  
  
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
  
-   **DataSet**을 강력한 형식의 **DataSet**과 같은 스키마로만 채운 다음 이를 **XmlDataDocument**와 동기화하고 XML 문서로부터 **XmlDataDocument**를 로드합니다.  이렇게 하면 기존 계층적 데이터를 관계형으로 표시할 수 있습니다.  **DataSet** 스키마의 테이블 이름과 열 이름은 함께 동기화할 XML 요소의 이름과 일치해야 합니다.  이 때 대\/소문자도 일치해야 합니다.  
  
     **DataSet**의 스키마는 관계형 뷰에 노출시킬 XML 요소에만 일치하면 됩니다.  이렇게 하면 XML 문서는 아주 크게, 이 문서의 관계형 "창"은 매우 작게 만들 수 있습니다.  **XmlDataDocument**에서는 **DataSet**에서 XML 문서의 극히 일부분만 노출하는 경우에도 전체 XML 문서가 보존됩니다.  이에 대한 자세한 예제는 [DataSet을 XmlDataDocument와 동기화](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)를 참조하세요.  
  
     다음 코드 예제에서는 **DataSet**을 만들고 해당 스키마를 채운 다음 **XmlDataDocument**와 동기화하는 단계를 보여 줍니다.  **DataSet** 스키마는 **DataSet**을 사용하여 노출시킬 **XmlDataDocument**의 요소에만 일치하면 됩니다.  
  
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
  
     데이터가 포함된 **DataSet**과 동기화된 **XmlDataDocument**는 로드할 수 없습니다.  로드하는 경우에는 예외가 throw됩니다.  
  
-   새 **XmlDataDocument**를 만들어 XML 문서로부터 로드한 다음 **XmlDataDocument**의 **DataSet** 속성을 사용하여 데이터의 관계형 뷰에 액세스합니다.  **DataSet**을 사용하여 **XmlDataDocument**에 있는 데이터를 표시하려면 먼저 **DataSet**의 스키마를 설정해야 합니다.  또한 **DataSet** 스키마의 테이블 이름과 열 이름은 함께 동기화할 XML 요소의 이름과 일치해야 합니다.  이 때 대\/소문자도 일치해야 합니다.  
  
     다음 코드 예제에서는 **XmlDataDocument**에 있는 데이터의 관계형 뷰에 액세스하는 방법을 보여 줍니다.  
  
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
  
 **XmlDataDocument**를 **DataSet**과 동기화할 경우의 또 다른 이점은 XML 문서의 신뢰도를 유지할 수 있다는 것입니다.  **ReadXml**을 사용하여 **DataSet**을 XML 문서로부터 채우면 **WriteXml**을 사용하여 데이터를 다시 XML 문서로 작성할 경우 원래 XML 문서와 상당히 달라질 수 있습니다.  이것은 **DataSet**에서 XML 문서에 사용되었던 공백 등의 서식이나 요소 순서 등의 계층적 정보가 유지되지 않기 때문입니다.  **DataSet**에는 XML 문서에서 **Dataset**의 스키마와 일치하지 않았기 때문에 무시되었던 요소도 포함되지 않습니다.  **XmlDataDocument**를 **DataSet**과 동기화하면 원래 XML 문서의 서식 및 계층적 요소 구조를 **XmlDataDocument**에서 유지할 수 있습니다. 반면 **DataSet**에는 해당 **DataSet**에 적합한 데이터와 스키마 정보만이 포함됩니다.  
  
 **DataSet**을 **XmlDataDocument**와 동기화하면 <xref:System.Data.DataRelation> 개체의 중첩 여부에 따라 결과가 달라질 수 있습니다.  자세한 내용은 [DataRelations 중첩](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)을 참조하세요.  
  
## 단원 내용  
 [DataSet을 XmlDataDocument와 동기화](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 최소한의 스키마를 가지고 강력한 형식의 **DataSet**과 **XmlDataDocument**를 동기화하는 예제를 보여 줍니다.  
  
 [DataSet에 XPath 쿼리 수행](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 **DataSet**의 내용에 대해 XPath 쿼리를 수행하는 예제를 보여 줍니다.  
  
 [XSLT 변환을 DataSet에 적용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 **DataSet**의 내용에 XSLT 변환을 적용하는 예제를 보여 줍니다.  
  
## 관련 단원  
 [DataSet에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 **DataSet**의 내용을 로드하여 XML 데이터로 유지하는 것을 포함하여 **DataSet**이 데이터 소스로서 XML과 상호 작용하는 방법을 설명합니다.  
  
 [DataRelations 중첩](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 **DataSet**의 내용을 XML 데이터로 표현할 경우 중첩된 **DataRelation** 개체의 중요성과 이러한 관계를 만드는 방법에 대해 설명합니다.  
  
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 **DataSet**에 대해 설명하고, DataSet을 사용하여 응용 프로그램 데이터를 관리하고 관계형 데이터베이스와 XML을 포함한 데이터 소스와 상호 작용하는 방법을 설명합니다.  
  
 [XmlDataDocument 클래스](frlrfSystemXmlXmlDataDocumentClassTopic)  
 **XmlDataDocument** 클래스에 대한 참조 정보가 포함되어 있습니다.  
  
## 참고 항목  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)