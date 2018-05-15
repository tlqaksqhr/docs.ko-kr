---
title: XSLT 변형을 DataSet에 적용
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09f2e4ee-1d08-4ba8-8936-83394fee319d
ms.openlocfilehash: 05894431f819b968877a4a971027850efe37126a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="applying-an-xslt-transform-to-a-dataset"></a><span data-ttu-id="64a62-102">XSLT 변형을 DataSet에 적용</span><span class="sxs-lookup"><span data-stu-id="64a62-102">Applying an XSLT Transform to a DataSet</span></span>
<span data-ttu-id="64a62-103">**WriteXml** 의 메서드는 <xref:System.Data.DataSet> 의 내용을 쓸 수 있습니다는 **DataSet** XML 데이터로 합니다.</span><span class="sxs-lookup"><span data-stu-id="64a62-103">The **WriteXml** method of the <xref:System.Data.DataSet> enables you to write the contents of a **DataSet** as XML data.</span></span> <span data-ttu-id="64a62-104">그런 다음에는 XSLT(XSL transformations)를 사용하여 해당 XML을 다른 형식으로 변형하는 공통적인 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="64a62-104">A common task is to then transform that XML to another format using XSL transformations (XSLT).</span></span> <span data-ttu-id="64a62-105">그러나 동기화는 **DataSet** 와 <xref:System.Xml.XmlDataDocument> 의 내용에 XSLT 스타일 시트를 적용할 수 있습니다는 **데이터 집합** 먼저의 콘텐츠를 작성 하지 않고도  **데이터 집합** 사용 하 여 XML 데이터 **WriteXml**합니다.</span><span class="sxs-lookup"><span data-stu-id="64a62-105">However, synchronizing a **DataSet** with an <xref:System.Xml.XmlDataDocument> enables you to apply an XSLT stylesheet to the contents of a **DataSet** without having to first write the contents of the **DataSet** as XML data using **WriteXml**.</span></span>  
  
 <span data-ttu-id="64a62-106">다음 예제에서는 **데이터 집합** 테이블 및 관계와 동기화는 **데이터 집합** 와 **XmlDataDocument**는 의일부를기록합니다. **데이터 집합** html, XSLT 스타일 시트를 사용 하 여 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="64a62-106">The following example populates a **DataSet** with tables and relationships, synchronizes the **DataSet** with an **XmlDataDocument**, and writes a portion of the **DataSet** as an HTML file using an XSLT stylesheet.</span></span> <span data-ttu-id="64a62-107">다음은 XSLT 스타일시트의 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="64a62-107">Following are the contents of the XSLT stylesheet.</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
  
<xsl:template match="CustomerOrders">  
  <HTML>  
  <STYLE>  
  BODY {font-family:verdana;font-size:9pt}  
  TD   {font-size:8pt}  
  </STYLE>  
    <BODY>  
    <TABLE BORDER="1">  
      <xsl:apply-templates select="Customers"/>  
    </TABLE>  
    </BODY>  
  </HTML>  
</xsl:template>  
  
<xsl:template match="Customers">  
    <TR><TD>  
      <xsl:value-of select="ContactName"/>, <xsl:value-of select="Phone"/><BR/>  
    </TD></TR>  
      <xsl:apply-templates select="Orders"/>  
</xsl:template>  
  
<xsl:template match="Orders">  
  <TABLE BORDER="1">  
    <TR><TD valign="top"><B>Order:</B></TD><TD valign="top"><xsl:value-of select="OrderID"/></TD></TR>  
    <TR><TD valign="top"><B>Date:</B></TD><TD valign="top"><xsl:value-of select="OrderDate"/></TD></TR>  
    <TR><TD valign="top"><B>Ship To:</B></TD>  
        <TD valign="top"><xsl:value-of select="ShipName"/><BR/>  
        <xsl:value-of select="ShipAddress"/><BR/>  
        <xsl:value-of select="ShipCity"/>, <xsl:value-of select="ShipRegion"/>  <xsl:value-of select="ShipPostalCode"/><BR/>  
        <xsl:value-of select="ShipCountry"/></TD></TR>  
  </TABLE>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
 <span data-ttu-id="64a62-108">다음 코드 채우기는 **DataSet** XSLT 스타일 시트를 적용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64a62-108">The following code fills the **DataSet** and applies the XSLT style sheet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64a62-109">XSLT 스타일 시트를 적용 하는 경우는 **데이터 집합** 설정 하면 최상의 성능을 얻으려면을 관계를 포함 하는 **Nested** 의 속성은 <xref:System.Data.DataRelation> 를 **true**각각에 대 한 관계를 중첩 합니다.</span><span class="sxs-lookup"><span data-stu-id="64a62-109">If you are applying an XSLT style sheet to a **DataSet** that contains relations, you achieve best performance if you set the **Nested** property of the <xref:System.Data.DataRelation> to **true** for each nested relation.</span></span> <span data-ttu-id="64a62-110">그러면 스타일시트 노드 테스트 식에서 쓰는 이전 형제 및 다음 형제와 같이 높은 성능이 필요한 XPath 위치 축을 사용하여 데이터 계층을 탐색하는 대신, 자연스러운 상-하 처리를 구현하는 XSLT 스타일시트를 사용하여 계층을 탐색하고 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64a62-110">This allows you to use XSLT style sheets that implement natural top-down processing to navigate the hierarchy and transform the data, as opposed to using performance-intensive XPath location axes (for example, preceding-sibling and following-sibling in style sheet node test expressions) to navigate it.</span></span> <span data-ttu-id="64a62-111">중첩 된 관계에 대 한 자세한 내용은 참조 하십시오. [Datarelation 중첩](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64a62-111">For more information on nested relations, see [Nesting DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)   
  
Dim xslTran As XslTransform = New XslTransform  
xslTran.Load("transform.xsl")  
  
Dim writer As XmlTextWriter = New XmlTextWriter( _  
  "xslt_output.html", System.Text.Encoding.UTF8)  
  
xslTran.Transform(xmlDoc, Nothing, writer)  
writer.Close()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
DataSet custDS = new DataSet("CustomerDataSet");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(custDS, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(custDS, "Orders");  
  
connection.Close();  
  
custDS.Relations.Add("CustOrders",  
  custDS.Tables["Customers"].Columns["CustomerID"],  
                     custDS.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(custDS);   
  
XslTransform xslTran = new XslTransform();  
xslTran.Load("transform.xsl");  
  
XmlTextWriter writer = new XmlTextWriter("xslt_output.html",   
  System.Text.Encoding.UTF8);  
  
xslTran.Transform(xmlDoc, null, writer);  
writer.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="64a62-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64a62-112">See Also</span></span>  
 [<span data-ttu-id="64a62-113">데이터 집합 및 XmlDataDocument 동기화</span><span class="sxs-lookup"><span data-stu-id="64a62-113">DataSet and XmlDataDocument Synchronization</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 [<span data-ttu-id="64a62-114">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="64a62-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
