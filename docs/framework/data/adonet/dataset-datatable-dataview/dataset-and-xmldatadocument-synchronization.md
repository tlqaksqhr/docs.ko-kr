---
title: "데이터 집합 및 XmlDataDocument 동기화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 923a6b6cf1523c8a11cb509679443b9658e07ce5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="dataset-and-xmldatadocument-synchronization"></a><span data-ttu-id="376ae-102">데이터 집합 및 XmlDataDocument 동기화</span><span class="sxs-lookup"><span data-stu-id="376ae-102">DataSet and XmlDataDocument Synchronization</span></span>
<span data-ttu-id="376ae-103">ADO.NET <xref:System.Data.DataSet>으로 데이터의 관계형 표현을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-103">The ADO.NET <xref:System.Data.DataSet> provides you with a relational representation of data.</span></span> <span data-ttu-id="376ae-104">계층적으로 데이터에 액세스하기 위해 .NET Framework에서 사용 가능한 XML 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-104">For hierarchical data access, you can use the XML classes available in the .NET Framework.</span></span> <span data-ttu-id="376ae-105">지금까지는 데이터의 이와 같은 두 가지 표현이 별도로 사용되어 왔습니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-105">Historically, these two representations of data have been used separately.</span></span> <span data-ttu-id="376ae-106">그러나.NET Framework에서는 통해 데이터의 관계형 및 계층적 표현에 대 한 실시간으로 동시 액세스는 **데이터 집합** 개체 및 <xref:System.Xml.XmlDataDocument> 개체를 각각.</span><span class="sxs-lookup"><span data-stu-id="376ae-106">However, the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the **DataSet** object and the <xref:System.Xml.XmlDataDocument> object, respectively.</span></span>  
  
 <span data-ttu-id="376ae-107">경우는 **DataSet** 와 동기화 되는 **XmlDataDocument**, 두 개체는 단일 데이터 집합을 사용 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-107">When a **DataSet** is synchronized with an **XmlDataDocument**, both objects are working with a single set of data.</span></span> <span data-ttu-id="376ae-108">즉, 한 스키마를 변경 하는 경우는 **데이터 집합**에 변경 내용이 반영:는 **XmlDataDocument**, 그 반대의 합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-108">This means that if a change is made to the **DataSet**, the change will be reflected in the **XmlDataDocument**, and vice versa.</span></span> <span data-ttu-id="376ae-109">간의 관계는 **데이터 집합** 및 **XmlDataDocument** 기반 서비스의 전체 제품군을 액세스 하는 단일 데이터 집합이 사용 하 여 단일 응용 프로그램을 허용 하 여 뛰어난 유연성을 만듭니다. 주위에서 **DataSet** (예: Web Forms 및 Windows Forms 컨트롤 및 Visual Studio.NET 디자이너) 스타일 시트 XSL (Extensible Language), XSLT (XSL Transformations), 및 XML 경로 포함 한 XML 서비스 도구 뿐만 아니라 언어 (XPath)입니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-109">The relationship between the **DataSet** and the **XmlDataDocument** creates great flexibility by allowing a single application, using a single set of data, to access the entire suite of services built around the **DataSet** (such as Web Forms and Windows Forms controls, and Visual Studio .NET designers), as well as the suite of XML services including Extensible Stylesheet Language (XSL), XSL Transformations (XSLT), and XML Path Language (XPath).</span></span> <span data-ttu-id="376ae-110">두 서비스를 모두 사용할 수 있으므로 응용 프로그램의 대상이 될 서비스 집합을 선택할 필요도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-110">You do not have to choose which set of services to target with the application; both are available.</span></span>  
  
 <span data-ttu-id="376ae-111">동기화 할 수 있는 여러 가지는 **DataSet** 와 **XmlDataDocument**합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-111">There are several ways that you can synchronize a **DataSet** with an **XmlDataDocument**.</span></span> <span data-ttu-id="376ae-112">다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-112">You can:</span></span>  
  
-   <span data-ttu-id="376ae-113">채우기는 **데이터 집합** 스키마 (즉, 관계형 구조) 및 데이터를 새 동기화 하십시오 **XmlDataDocument**합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-113">Populate a **DataSet** with schema (that is, a relational structure) and data and then synchronize it with a new **XmlDataDocument**.</span></span> <span data-ttu-id="376ae-114">이렇게 하면 기존 관계형 데이터를 계층적으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-114">This provides a hierarchical view of existing relational data.</span></span> <span data-ttu-id="376ae-115">예:</span><span class="sxs-lookup"><span data-stu-id="376ae-115">For example:</span></span>  
  
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
  
-   <span data-ttu-id="376ae-116">채우기는 **데이터 집합** 스키마만 (같은 강력한 형식의 **데이터 집합**)와 동기화는 **XmlDataDocument**, 한 다음 로드는  **XmlDataDocument** XML 문서에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-116">Populate a **DataSet** with schema only (such as a strongly typed **DataSet**), synchronize it with an **XmlDataDocument**, and then load the **XmlDataDocument** from an XML document.</span></span> <span data-ttu-id="376ae-117">이렇게 하면 기존 계층적 데이터를 관계형으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-117">This provides a relational view of existing hierarchical data.</span></span> <span data-ttu-id="376ae-118">테이블 이름과 열 이름은 프로그램 **DataSet** 스키마와 동기화 할 XML 요소의 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-118">The table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="376ae-119">이 때 대/소문자도 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-119">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="376ae-120">스키마는 **DataSet** 만 관계형 뷰에 노출 시킬 XML 요소와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-120">Note that the schema of the **DataSet** only needs to match the XML elements that you want to expose in your relational view.</span></span> <span data-ttu-id="376ae-121">이렇게 하면 XML 문서는 아주 크게, 이 문서의 관계형 "창"은 매우 작게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-121">This way, you can have a very large XML document and a very small relational "window" on that document.</span></span> <span data-ttu-id="376ae-122">**XmlDataDocument** 경우에 전체 XML 문서에서 유지 된 **데이터 집합** 문서의 극히 일부분만 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-122">The **XmlDataDocument** preserves the entire XML document even though the **DataSet** only exposes a small portion of it.</span></span> <span data-ttu-id="376ae-123">(이 항목의 자세한 예제를 보려면 [DataSet을 XmlDataDocument와 동기화](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)</span><span class="sxs-lookup"><span data-stu-id="376ae-123">(For a detailed example of this, see [Synchronizing a DataSet with an XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)</span></span>  
  
     <span data-ttu-id="376ae-124">다음 코드 예제를 만들기 위한 단계를 보여 줍니다.는 **DataSet** 및 해당 스키마를 채운와 동기화는 **XmlDataDocument**합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-124">The following code example shows the steps for creating a **DataSet** and populating its schema, then synchronizing it with an **XmlDataDocument**.</span></span> <span data-ttu-id="376ae-125">**DataSet** 스키마만 요소와 일치 해야는 **XmlDataDocument** 사용 하 여 노출 하려는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-125">Note that the **DataSet** schema only needs to match the elements from the **XmlDataDocument** that you want to expose using the **DataSet**.</span></span>  
  
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
  
     <span data-ttu-id="376ae-126">로드할 수 없습니다는 **XmlDataDocument** 와 동기화 하는 경우는 **데이터 집합** 데이터가 들어 있는입니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-126">You cannot load an **XmlDataDocument** if it is synchronized with a **DataSet** that contains data.</span></span> <span data-ttu-id="376ae-127">로드하는 경우에는 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-127">An exception will be thrown.</span></span>  
  
-   <span data-ttu-id="376ae-128">새 **XmlDataDocument** XML 문서 로부터 로드 한 다음 사용 하 여 데이터의 관계형 뷰에 액세스 하 고는 **데이터 집합** 의 속성은 **XmlDataDocument**합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-128">Create a new **XmlDataDocument** and load it from an XML document, and then access the relational view of the data using the **DataSet** property of the **XmlDataDocument**.</span></span> <span data-ttu-id="376ae-129">스키마를 설정 해야 합니다는 **데이터 집합** 의 데이터를 볼 수는 **XmlDataDocument** 를 사용 하는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-129">You need to set the schema of the **DataSet** before you can view any of the data in the **XmlDataDocument** using the **DataSet**.</span></span> <span data-ttu-id="376ae-130">마찬가지로 테이블 이름과 열 이름은 프로그램 **DataSet** 스키마와 동기화 할 XML 요소의 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-130">Again, the table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="376ae-131">이 때 대/소문자도 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-131">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="376ae-132">다음 코드 예제에 있는 데이터의 관계형 뷰에 액세스 하는 방법을 보여 줍니다는 **XmlDataDocument**합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-132">The following code example shows how to access the relational view of the data in an **XmlDataDocument**.</span></span>  
  
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
  
 <span data-ttu-id="376ae-133">동기화 할 경우의 또 다른 이점은 **XmlDataDocument** 와 **DataSet** XML 문서의 신뢰도 유지할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-133">Another advantage of synchronizing an **XmlDataDocument** with a **DataSet** is that the fidelity of an XML document is preserved.</span></span> <span data-ttu-id="376ae-134">경우는 **DataSet** 사용 하 여 XML 문서에서 채워집니다 **ReadXml**데이터를 사용 하 여 XML 문서 다시 작성할 때 **WriteXml** 에서 상당히 달라질 수 있습니다는 원본 XML 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-134">If the **DataSet** is populated from an XML document using **ReadXml**, when the data is written back as an XML document using **WriteXml** it may differ dramatically from the original XML document.</span></span> <span data-ttu-id="376ae-135">때문에 이것이 **DataSet** 공백 또는 XML 문서에서 요소 순서 등의 계층적 정보가 같은 서식을 유지 관리 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-135">This is because the **DataSet** does not maintain formatting, such as white space, or hierarchical information, such as element order, from the XML document.</span></span> <span data-ttu-id="376ae-136">**DataSet** 의 스키마와 일치 하지 않아 무시 되었던 XML 문서에서 요소를 포함 하지 않습니다는 **Dataset**합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-136">The **DataSet** also does not contain elements from the XML document that were ignored because they did not match the schema of the **Dataset**.</span></span> <span data-ttu-id="376ae-137">동기화는 **XmlDataDocument** 와 **DataSet** 에서 유지할 수는 원래 XML 문서의 서식 및 계층적 요소 구조는 **XmlDataDocument**, 동안는 **데이터 집합** 에 적합 한 데이터와 스키마 정보만 들어는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-137">Synchronizing an **XmlDataDocument** with a **DataSet** allows the formatting and hierarchical element structure of the original XML document to be maintained in the **XmlDataDocument**, while the **DataSet** contains only data and schema information appropriate to the **DataSet**.</span></span>  
  
 <span data-ttu-id="376ae-138">동기화 할 때는 **DataSet** 와 **XmlDataDocument**, 여부에 따라 결과가 달라질 수 있습니다 프로그램 <xref:System.Data.DataRelation> 개체의 중첩 합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-138">When synchronizing a **DataSet** with an **XmlDataDocument**, results may differ depending on whether or not your <xref:System.Data.DataRelation> objects are nested.</span></span> <span data-ttu-id="376ae-139">자세한 내용은 참조 [Datarelation 중첩](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-139">For more information, see [Nesting DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="376ae-140">단원 내용</span><span class="sxs-lookup"><span data-stu-id="376ae-140">In This Section</span></span>  
 [<span data-ttu-id="376ae-141">DataSet을 XmlDataDocument와 동기화</span><span class="sxs-lookup"><span data-stu-id="376ae-141">Synchronizing a DataSet with an XmlDataDocument</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 <span data-ttu-id="376ae-142">강력한 형식의 동기화 하는 방법을 보여 줍니다 **데이터 집합**, 최소한의 스키마와 **XmlDataDocument**합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-142">Demonstrates synchronizing a strongly typed **DataSet**, with minimal schema, with an **XmlDataDocument**.</span></span>  
  
 [<span data-ttu-id="376ae-143">데이터 집합에서 XPath 쿼리 수행</span><span class="sxs-lookup"><span data-stu-id="376ae-143">Performing an XPath Query on a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 <span data-ttu-id="376ae-144">내용에 대해 XPath 쿼리를 수행 하는 방법을 보여 줍니다는 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-144">Demonstrates performing an XPath query on the contents of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="376ae-145">XSLT 변환을 DataSet에 적용</span><span class="sxs-lookup"><span data-stu-id="376ae-145">Applying an XSLT Transform to a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 <span data-ttu-id="376ae-146">내용에 XSLT 변환을 적용 하는 방법을 보여 줍니다는 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-146">Demonstrates applying an XSLT transform to the contents of a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="376ae-147">관련 단원</span><span class="sxs-lookup"><span data-stu-id="376ae-147">Related Sections</span></span>  
 [<span data-ttu-id="376ae-148">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="376ae-148">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="376ae-149">설명 방법을 **DataSet** 로드 하 고 유지의 내용을 포함 한 데이터 소스로 XML와 상호 작용 하는 **데이터 집합** XML 데이터로 합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-149">Describes how the **DataSet** interacts with XML as a data source, including loading and persisting the contents of a **DataSet** as XML data.</span></span>  
  
 [<span data-ttu-id="376ae-150">Datarelation 중첩</span><span class="sxs-lookup"><span data-stu-id="376ae-150">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 <span data-ttu-id="376ae-151">중요 성과 중첩 **DataRelation** 의 콘텐츠를 나타내는 개체는 **DataSet** XML 데이터로 이러한 관계를 만드는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-151">Discusses the importance of nested **DataRelation** objects when representing the contents of a **DataSet** as XML data, and describes how to create these relations.</span></span>  
  
 [<span data-ttu-id="376ae-152">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="376ae-152">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="376ae-153">설명의 **데이터 집합** 및 응용 프로그램 데이터를 관리 하 고 관계형 데이터베이스 및 XML을 포함 하 여 데이터 소스와 상호 작용을 사용 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-153">Describes the **DataSet** and how to use it to manage application data and to interact with data sources including relational databases and XML.</span></span>  
  
 <xref:System.Xml.XmlDataDocument>  
 <span data-ttu-id="376ae-154">에 대 한 참조 정보는 **XmlDataDocument** 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="376ae-154">Contains reference information about the **XmlDataDocument** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="376ae-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="376ae-155">See Also</span></span>  
 [<span data-ttu-id="376ae-156">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="376ae-156">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
