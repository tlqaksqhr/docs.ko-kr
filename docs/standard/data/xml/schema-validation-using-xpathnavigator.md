---
title: XPathNavigator를 사용하여 스키마 유효성 검사
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 81fa0e41-d9c9-46f0-b22b-50da839c77f5
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98403176c3af8e110bd8d7677fae715fee84baec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578355"
---
# <a name="schema-validation-using-xpathnavigator"></a><span data-ttu-id="c124b-102">XPathNavigator를 사용하여 스키마 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="c124b-102">Schema Validation using XPathNavigator</span></span>
<span data-ttu-id="c124b-103"><xref:System.Xml.XmlDocument> 클래스를 사용하면 두 가지 방법으로 <xref:System.Xml.XmlDocument> 개체에 포함된 XML 내용의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-103">Using the <xref:System.Xml.XmlDocument> class, you can validate the XML content contained in an <xref:System.Xml.XmlDocument> object in two ways.</span></span> <span data-ttu-id="c124b-104">첫 번째 방법은 유효성 검사 <xref:System.Xml.XmlReader> 개체를 사용하여 XML 내용의 유효성을 검사하는 것이고 두 번째 방법은 <xref:System.Xml.XmlDocument.Validate%2A> 클래스의 <xref:System.Xml.XmlDocument> 메서드를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-104">The first way is to validate the XML content using a validating <xref:System.Xml.XmlReader> object and the second way is to use the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="c124b-105"><xref:System.Xml.XPath.XPathDocument> 클래스를 사용하여 XML 내용의 읽기 전용 유효성 검사를 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-105">You can also perform read-only validation of XML content using the <xref:System.Xml.XPath.XPathDocument> class.</span></span>  
  
## <a name="validating-xml-data"></a><span data-ttu-id="c124b-106">XML 데이터 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="c124b-106">Validating XML Data</span></span>  
 <span data-ttu-id="c124b-107">기본적으로 <xref:System.Xml.XmlDocument> 클래스는 DTD나 XSD(XML 스키마 정의 언어) 스키마 유효성 검사를 통해 XML 문서의 유효성을 검사하지 않으며</span><span class="sxs-lookup"><span data-stu-id="c124b-107">The <xref:System.Xml.XmlDocument> class does not validate an XML document using either DTD or XML schema definition language (XSD) schema validation by default.</span></span> <span data-ttu-id="c124b-108">XML 문서가 제대로 구성되었는지만 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-108">It only verifies that the XML document is well formed.</span></span>  
  
 <span data-ttu-id="c124b-109">XML 문서의 유효성을 검사하는 첫 번째 방법은 유효성을 검사하는 <xref:System.Xml.XmlDocument> 개체를 사용하여 <xref:System.Xml.XmlReader> 개체로 XML 문서를 로드할 때 유효성을 검사하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-109">The first way to validate an XML document is to validate the document as it is loaded into an <xref:System.Xml.XmlDocument> object using a validating <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="c124b-110">두 번째 방법은 <xref:System.Xml.XmlDocument.Validate%2A> 클래스의 <xref:System.Xml.XmlDocument> 메서드를 사용하여 이전에 형식화한 XML 문서의 유효성을 검사하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-110">The second way is to validate a previously untyped XML document using the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="c124b-111">두 가지 경우 모두 유효성을 검사한 XML 문서의 변경 내용에 대해 <xref:System.Xml.XmlDocument.Validate%2A> 클래스의 <xref:System.Xml.XmlDocument> 메서드를 사용하여 유효성을 다시 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-111">In both cases, changes to the validated XML document can be revalidated using the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span>  
  
### <a name="validating-a-document-as-it-is-loaded"></a><span data-ttu-id="c124b-112">문서를 로드할 때 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="c124b-112">Validating a Document as it is Loaded</span></span>  
 <span data-ttu-id="c124b-113"><xref:System.Xml.XmlReader> 개체를 매개 변수로 사용하는 <xref:System.Xml.XmlReaderSettings> 클래스의 <xref:System.Xml.XmlReader.Create%2A> 메서드에 <xref:System.Xml.XmlReader> 개체를 전달하면 유효성을 검사하는 <xref:System.Xml.XmlReaderSettings> 개체가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-113">A validating <xref:System.Xml.XmlReader> object is created by passing an <xref:System.Xml.XmlReaderSettings> object to the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class that takes an <xref:System.Xml.XmlReaderSettings> object as a parameter.</span></span> <span data-ttu-id="c124b-114">매개 변수로 전달된 <xref:System.Xml.XmlReaderSettings> 개체의 <xref:System.Xml.XmlReaderSettings.ValidationType%2A> 속성은 `Schema`로 설정되어 있으며 <xref:System.Xml.XmlDocument> 속성에 추가된 <xref:System.Xml.XmlReaderSettings.Schemas%2A> 개체에 XML 문서의 XML 스키마가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-114">The <xref:System.Xml.XmlReaderSettings> object passed as a parameter has a <xref:System.Xml.XmlReaderSettings.ValidationType%2A> property set to `Schema` and an XML Schema for the XML document contained in the <xref:System.Xml.XmlDocument> object added to its <xref:System.Xml.XmlReaderSettings.Schemas%2A> property.</span></span> <span data-ttu-id="c124b-115">그러면 유효성을 검사하는 <xref:System.Xml.XmlReader> 개체를 사용하여 <xref:System.Xml.XmlDocument> 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-115">The validating <xref:System.Xml.XmlReader> object is then used to create the <xref:System.Xml.XmlDocument> object.</span></span>  
  
 <span data-ttu-id="c124b-116">다음 예제에서는 `contosoBooks.xml` 개체의 유효성 검사를 통해 <xref:System.Xml.XmlDocument> 개체를 만들어 <xref:System.Xml.XmlDocument> 파일이 <xref:System.Xml.XmlReader> 개체로 로드되면 해당 파일의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-116">The following example validates the `contosoBooks.xml` file as it is loaded into the <xref:System.Xml.XmlDocument> object by creating the <xref:System.Xml.XmlDocument> object using a validating <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="c124b-117">해당 스키마에 따르면 XML 문서가 유효하기 때문에 스키마 유효성 검사 오류 또는 경고가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-117">Because the XML document is valid according to its schema, no schema validation errors or warnings are generated.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Schema  
Imports System.Xml.XPath  
  
Class ValidatingReaderExample  
  
    Shared Sub Main(ByVal args() As String)  
  
        Try  
            Dim settings As XmlReaderSettings = New XmlReaderSettings()  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
            settings.ValidationType = ValidationType.Schema  
  
            Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
            Dim document As XmlDocument = New XmlDocument()  
            document.Load(reader)  
            Dim navigator As XPathNavigator = document.CreateNavigator()  
  
        Catch e As Exception  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message)  
        End Try  
  
    End Sub  
  
    Shared Sub SchemaValidationHandler(ByVal sender As Object, ByVal e As ValidationEventArgs)  
  
        Select Case e.Severity  
            Case XmlSeverityType.Error  
                Console.WriteLine("Schema Validation Error: {0}", e.Message)  
                Exit Sub  
            Case XmlSeverityType.Warning  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message)  
                Exit Sub  
        End Select  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Schema;  
using System.Xml.XPath;  
  
class ValidatingReaderExample  
{  
    static void Main(string[] args)  
    {  
        try  
        {  
            XmlReaderSettings settings = new XmlReaderSettings();  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
            settings.ValidationType = ValidationType.Schema;  
  
            XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
            XmlDocument document = new XmlDocument();  
            document.Load(reader);  
            XPathNavigator navigator = document.CreateNavigator();  
        }  
        catch (Exception e)  
        {  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message);  
        }  
    }  
  
    static void SchemaValidationHandler(object sender, ValidationEventArgs e)  
    {  
        switch (e.Severity)  
        {  
            case XmlSeverityType.Error:  
                Console.WriteLine("Schema Validation Error: {0}", e.Message);  
                break;  
            case XmlSeverityType.Warning:  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message);  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="c124b-118">이 예제에서는 `contosoBooks.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-118">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="c124b-119">이 예제에서는 또한 `contosoBooks.xsd`를 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-119">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
 <span data-ttu-id="c124b-120">위 예제에서 <xref:System.Xml.Schema.XmlSchemaValidationException>가 호출될 때 특성 또는 요소 형식이 유효성 검사 스키마에 지정된 해당 형식과 일치하지 않으면 <xref:System.Xml.XmlDocument.Load%2A>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-120">In the above example, an <xref:System.Xml.Schema.XmlSchemaValidationException> will be thrown when <xref:System.Xml.XmlDocument.Load%2A> is called if any attribute or element type does not match the corresponding type specified in the validating schema.</span></span> <span data-ttu-id="c124b-121"><xref:System.Xml.XmlReaderSettings.ValidationEventHandler> 유효성 검사에 <xref:System.Xml.XmlReader>가 설정된 경우 잘못된 형식이 발견될 때마다 <xref:System.Xml.XmlReaderSettings.ValidationEventHandler>가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-121">If a <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> is set on the validating <xref:System.Xml.XmlReader>, the <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> will get called whenever an invalid type is encountered.</span></span>  
  
 <span data-ttu-id="c124b-122"><xref:System.Xml.Schema.XmlSchemaException>가 <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>로 설정된 특성 또는 요소를 `invalid`에서 액세스하는 경우 <xref:System.Xml.XPath.XPathNavigator>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-122">An <xref:System.Xml.Schema.XmlSchemaException> will be thrown when an attribute or element with <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> set to `invalid` is accessed by the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
 <span data-ttu-id="c124b-123"><xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A>로 특성 또는 요소에 액세스할 때 <xref:System.Xml.XPath.XPathNavigator> 속성을 사용하여 개별 특성 또는 요소가 유효한지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-123">The <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> property can be used to determine whether or not an individual attribute or element is valid when accessing attributes or elements with the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c124b-124">기본값을 정의하는 스키마가 연결되어 있는 XML 문서를 <xref:System.Xml.XmlDocument> 개체에 로드하면 <xref:System.Xml.XmlDocument> 개체는 이 기본값이 XML 문서에 나타난 것처럼 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-124">When an XML document is loaded into an <xref:System.Xml.XmlDocument> object with an associated schema that defines default values, the <xref:System.Xml.XmlDocument> object treats these defaults as if they appeared in the XML document.</span></span> <span data-ttu-id="c124b-125">그러므로 빈 요소로 쓰여진 XML 문서에서도 <xref:System.Xml.XPath.XPathNavigator.IsEmptyElement%2A> 속성은 스키마에서 기본값으로 설정된 요소에 대해 항상 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-125">This means that the <xref:System.Xml.XPath.XPathNavigator.IsEmptyElement%2A> property  always returns `false` for an element that was defaulted from the schema, even if in the XML document it was written as an empty element.</span></span>  
  
### <a name="validating-a-document-using-the-validate-method"></a><span data-ttu-id="c124b-126">Validate 메서드를 사용하여 문서의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="c124b-126">Validating a Document using the Validate Method</span></span>  
 <span data-ttu-id="c124b-127"><xref:System.Xml.XmlDocument.Validate%2A> 클래스의 <xref:System.Xml.XmlDocument> 메서드는 <xref:System.Xml.XmlDocument> 개체의 <xref:System.Xml.XmlDocument> 속성에 지정된 스키마에 대해 <xref:System.Xml.XmlDocument.Schemas%2A> 개체에 포함된 XML 문서의 유효성을 검사하고 Infoset 확대를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-127">The <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class validates the XML document contained in an <xref:System.Xml.XmlDocument> object against the schemas specified in the <xref:System.Xml.XmlDocument> object's <xref:System.Xml.XmlDocument.Schemas%2A> property and performs infoset augmentation.</span></span> <span data-ttu-id="c124b-128">그 결과 <xref:System.Xml.XmlDocument> 개체에서 이전에 형식화하지 않은 XML 문서가 형식화된 문서로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-128">The result is a previously untyped XML document in the <xref:System.Xml.XmlDocument> object replaced with a typed document.</span></span>  
  
 <span data-ttu-id="c124b-129"><xref:System.Xml.XmlDocument> 개체는 <xref:System.Xml.Schema.ValidationEventHandler> 메서드에 매개 변수로 전달된 <xref:System.Xml.XmlDocument.Validate%2A> 대리자를 사용하여 스키마 유효성 검사 오류 및 경고를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-129">The <xref:System.Xml.XmlDocument> object reports schema validation errors and warnings using the <xref:System.Xml.Schema.ValidationEventHandler> delegate passed as a parameter to the <xref:System.Xml.XmlDocument.Validate%2A> method.</span></span>  
  
 <span data-ttu-id="c124b-130">다음 예제에서는 `contosoBooks.xml` 개체의 <xref:System.Xml.XmlDocument> 속성에 포함된 `contosoBooks.xsd` 스키마에 대해 <xref:System.Xml.XmlDocument> 개체에 포함된 <xref:System.Xml.XmlDocument.Schemas%2A> 파일의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-130">The following example validates the `contosoBooks.xml` file contained in the <xref:System.Xml.XmlDocument> object against the `contosoBooks.xsd` schema contained in the <xref:System.Xml.XmlDocument> object's <xref:System.Xml.XmlDocument.Schemas%2A> property.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Schema  
Imports System.Xml.XPath  
  
Class ValidateExample  
  
    Shared Sub Main(ByVal args() As String)  
  
        Dim document As XmlDocument = New XmlDocument()  
        document.Load("contosoBooks.xml")  
        Dim navigator As XPathNavigator = document.CreateNavigator()  
  
        document.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
        Dim validation As ValidationEventHandler = New ValidationEventHandler(AddressOf SchemaValidationHandler)  
  
        document.Validate(validation)  
  
    End Sub  
  
    Shared Sub SchemaValidationHandler(ByVal sender As Object, ByVal e As ValidationEventArgs)  
  
        Select Case e.Severity  
            Case XmlSeverityType.Error  
                Console.WriteLine("Schema Validation Error: {0}", e.Message)  
                Exit Sub  
            Case XmlSeverityType.Warning  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message)  
                Exit Sub  
        End Select  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Schema;  
using System.Xml.XPath;  
  
class ValidateExample  
{  
    static void Main(string[] args)  
    {  
        XmlDocument document = new XmlDocument();  
        document.Load("contosoBooks.xml");  
        XPathNavigator navigator = document.CreateNavigator();  
  
        document.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
        ValidationEventHandler validation = new ValidationEventHandler(SchemaValidationHandler);  
  
        document.Validate(validation);  
    }  
  
    static void SchemaValidationHandler(object sender, ValidationEventArgs e)  
    {  
        switch (e.Severity)  
        {  
            case XmlSeverityType.Error:  
                Console.WriteLine("Schema Validation Error: {0}", e.Message);  
                break;  
            case XmlSeverityType.Warning:  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message);  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="c124b-131">이 예제에서는 `contosoBooks.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-131">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="c124b-132">이 예제에서는 또한 `contosoBooks.xsd`를 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-132">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
### <a name="validating-modifications"></a><span data-ttu-id="c124b-133">수정 내용 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="c124b-133">Validating Modifications</span></span>  
 <span data-ttu-id="c124b-134">XML 문서를 수정한 후 <xref:System.Xml.XmlDocument.Validate%2A> 클래스의 <xref:System.Xml.XmlDocument> 메서드를 사용하여 XML 문서의 스키마에 대해 수정 내용의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-134">After modifications are made to an XML document, you can validate the modifications against the schema for the XML document using the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="c124b-135">다음 예제에서는 `contosoBooks.xml` 개체의 유효성 검사를 통해 <xref:System.Xml.XmlDocument> 개체를 만들어 <xref:System.Xml.XmlDocument> 파일이 <xref:System.Xml.XmlReader> 개체로 로드되면 해당 파일의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-135">The following example validates the `contosoBooks.xml` file as it is loaded into the <xref:System.Xml.XmlDocument> object by creating the <xref:System.Xml.XmlDocument> object using a validating <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="c124b-136">스키마 유효성 검사 오류 또는 경고가 생성되지 않고 로드되었으므로 XML 문서의 유효성이 성공적으로 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-136">The XML document is validated successfully as it is loaded without generating any schema validation errors or warnings.</span></span> <span data-ttu-id="c124b-137">그런 다음 예제에서는 `contosoBooks.xsd` 스키마에 따라 XML 문서에서 유효하지 않은 두 가지 사항을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-137">The example then makes two modifications to the XML document that are invalid according to the `contosoBooks.xsd` schema.</span></span> <span data-ttu-id="c124b-138">첫 번째 수정 사항은 잘못된 자식 요소를 삽입하여 스키마 유효성 검사 오류가 발생하도록 하는 것이고 두 번째 수정 사항은 노드 형식에 따르면 유효하지 않은 값으로, 형식화된 노드 값을 설정하여 예외가 발생하도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-138">The first modification inserts an invalid child element resulting in a schema validation error, and the second modification sets the value of a typed node to a value that is invalid according to the type of the node resulting in an exception.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Schema  
Imports System.Xml.XPath  
  
Class ValidatingReaderExample  
  
    Shared Sub Main(ByVal args() As String)  
  
        Try  
            Dim settings As XmlReaderSettings = New XmlReaderSettings()  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
            settings.ValidationType = ValidationType.Schema  
  
            Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
            Dim document As XmlDocument = New XmlDocument()  
            document.Load(reader)  
            Dim navigator As XPathNavigator = document.CreateNavigator()  
  
            Dim validation As ValidationEventHandler = New ValidationEventHandler(AddressOf SchemaValidationHandler)  
  
            navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
            navigator.MoveToChild("book", "http://www.contoso.com/books")  
            navigator.MoveToChild("author", "http://www.contoso.com/books")  
  
            navigator.AppendChild("<title>Book Title</title>")  
  
            document.Validate(validation)  
  
            navigator.MoveToParent()  
            navigator.MoveToChild("price", "http://www.contoso.com/books")  
            navigator.SetTypedValue(DateTime.Now)  
        Catch e As Exception  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message)  
        End Try  
  
    End Sub  
  
    Shared Sub SchemaValidationHandler(ByVal sender As Object, ByVal e As ValidationEventArgs)  
  
        Select Case e.Severity  
            Case XmlSeverityType.Error  
                Console.WriteLine("Schema Validation Error: {0}", e.Message)  
                Exit Sub  
            Case XmlSeverityType.Warning  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message)  
                Exit Sub  
        End Select  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Schema;  
using System.Xml.XPath;  
  
class ValidatingReaderExample  
{  
    static void Main(string[] args)  
    {  
        try  
        {  
            XmlReaderSettings settings = new XmlReaderSettings();  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
            settings.ValidationType = ValidationType.Schema;  
  
            XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
            XmlDocument document = new XmlDocument();  
            document.Load(reader);  
            XPathNavigator navigator = document.CreateNavigator();  
  
            ValidationEventHandler validation = new ValidationEventHandler(SchemaValidationHandler);  
  
            navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
            navigator.MoveToChild("book", "http://www.contoso.com/books");  
            navigator.MoveToChild("author", "http://www.contoso.com/books");  
  
            navigator.AppendChild("<title>Book Title</title>");  
  
            document.Validate(validation);  
  
            navigator.MoveToParent();  
            navigator.MoveToChild("price", "http://www.contoso.com/books");  
            navigator.SetTypedValue(DateTime.Now);  
        }  
        catch (Exception e)  
        {  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message);  
        }  
    }  
  
    static void SchemaValidationHandler(object sender, ValidationEventArgs e)  
    {  
        switch (e.Severity)  
        {  
            case XmlSeverityType.Error:  
                Console.WriteLine("Schema Validation Error: {0}", e.Message);  
                break;  
            case XmlSeverityType.Warning:  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message);  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="c124b-139">이 예제에서는 `contosoBooks.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-139">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="c124b-140">이 예제에서는 또한 `contosoBooks.xsd`를 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-140">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
 <span data-ttu-id="c124b-141">위 예제에서는 <xref:System.Xml.XmlDocument> 개체에 포함된 XML 문서에서 두 가지 사항을 수정했습니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-141">In the example above, two modifications are made to the XML document contained in the <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="c124b-142">XML 문서를 로드할 때 발생한 스키마 유효성 검사 오류는 유효성 검사 이벤트 처리기 메서드에 의해 처리되고 콘솔에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-142">As the XML document was loaded, any schema validation errors encountered would have been handled by the validation event handler method and written to the console.</span></span>  
  
 <span data-ttu-id="c124b-143">이 예제에서는 XML 문서를 로드한 후 유효성 검사 오류가 발생했으며 <xref:System.Xml.XmlDocument.Validate%2A> 클래스의 <xref:System.Xml.XmlDocument> 메서드를 사용하여 오류가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-143">In this example, the validation errors were introduced after the XML document was loaded and were found using the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="c124b-144">노드의 스키마 형식에 따르면 새 값이 유효하지 않기 때문에 <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator> 메서드를 사용하여 수정한 사항으로 인해 <xref:System.InvalidCastException>이 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-144">Modifications made using the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class resulted in an <xref:System.InvalidCastException> because the new value was invalid according to the schema type of the node.</span></span>  
  
 <span data-ttu-id="c124b-145"><xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> 메서드를 사용하여 값을 수정하는 방법에 대한 자세한 내용은 [XPathNavigator를 사용하여 XML 데이터 수정](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c124b-145">For more information about modifying values using the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method, see the [Modify XML Data using XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md) topic.</span></span>  
  
### <a name="read-only-validation"></a><span data-ttu-id="c124b-146">읽기 전용 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="c124b-146">Read-Only Validation</span></span>  
 <span data-ttu-id="c124b-147"><xref:System.Xml.XPath.XPathDocument> 클래스는 읽기 전용 메모리 내 XML 문서 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-147">The <xref:System.Xml.XPath.XPathDocument> class is a read-only, in-memory representation of an XML document.</span></span> <span data-ttu-id="c124b-148"><xref:System.Xml.XPath.XPathDocument> 클래스와 <xref:System.Xml.XmlDocument> 클래스는 <xref:System.Xml.XPath.XPathNavigator> 개체를 만들어 XML 문서를 탐색하고 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-148">Both the <xref:System.Xml.XPath.XPathDocument> class and the <xref:System.Xml.XmlDocument> class create <xref:System.Xml.XPath.XPathNavigator> objects to navigate and edit XML documents.</span></span> <span data-ttu-id="c124b-149"><xref:System.Xml.XPath.XPathDocument> 클래스는 읽기 전용 클래스이므로 <xref:System.Xml.XPath.XPathNavigator> 개체에서 반환된 <xref:System.Xml.XPath.XPathDocument> 개체는 <xref:System.Xml.XPath.XPathDocument> 개체에 포함된 XML 문서를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-149">Because the <xref:System.Xml.XPath.XPathDocument> class is a read-only class, <xref:System.Xml.XPath.XPathNavigator> object's returned from <xref:System.Xml.XPath.XPathDocument> objects cannot edit the XML document contained in the <xref:System.Xml.XPath.XPathDocument> object.</span></span>  
  
 <span data-ttu-id="c124b-150">유효성 검사의 경우 이 항목의 앞부분에서 설명한 대로 유효성을 검사하는 <xref:System.Xml.XPath.XPathDocument> 개체를 사용하여 <xref:System.Xml.XmlDocument> 개체를 만든 것과 같이 <xref:System.Xml.XmlReader> 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-150">In the case of validation, you can create an <xref:System.Xml.XPath.XPathDocument> object just like you create an <xref:System.Xml.XmlDocument> object using a validating <xref:System.Xml.XmlReader> object as described earlier in this topic.</span></span> <span data-ttu-id="c124b-151"><xref:System.Xml.XPath.XPathDocument> 개체는 XML 문서를 로드할 때 이 문서의 유효성을 검사하지만 <xref:System.Xml.XPath.XPathDocument> 개체에서 XML 데이터를 편집할 수 없으므로 XML 문서의 유효성을 다시 검사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c124b-151">The <xref:System.Xml.XPath.XPathDocument> object validates the XML document as it is loaded, but because you cannot edit the XML data in the <xref:System.Xml.XPath.XPathDocument> object, you cannot revalidate the XML document.</span></span>  
  
 <span data-ttu-id="c124b-152">읽기 전용 및 편집 가능한 <xref:System.Xml.XPath.XPathNavigator> 개체에 대한 자세한 내용은 [XPathDocument 및 XmlDocument를 사용하여 XML 데이터 읽기](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c124b-152">For more information about read-only and editable <xref:System.Xml.XPath.XPathNavigator> objects, see the [Reading XML Data using XPathDocument and XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md) topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c124b-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c124b-153">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="c124b-154">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="c124b-154">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="c124b-155">XPathDocument 및 XmlDocument를 사용하여 XML 데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="c124b-155">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 [<span data-ttu-id="c124b-156">XPathNavigator를 사용하여 XML 데이터 선택, 평가 및 일치시키기</span><span class="sxs-lookup"><span data-stu-id="c124b-156">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="c124b-157">XPathNavigator를 사용하여 XML 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="c124b-157">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="c124b-158">XPathNavigator를 사용하여 XML 데이터 편집</span><span class="sxs-lookup"><span data-stu-id="c124b-158">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)
