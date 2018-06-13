---
title: '방법: LINQ를 사용하여 XML 변형(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: 94ad5180c7921a5ace09f9161de5f275475e46d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652963"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a><span data-ttu-id="67389-102">방법: LINQ를 사용하여 XML 변형(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67389-102">How to: Transform XML by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="67389-103">[XML 리터럴](../../../../visual-basic/language-reference/xml-literals/index.md) 쉽게를 한 소스에서 XML을 읽고 새 XML 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="67389-103">[XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) make it easy to read XML from one source and transform it to a new XML format.</span></span> <span data-ttu-id="67389-104">LINQ 쿼리를 변환, 콘텐츠를 검색할를 활용 하거나 새 XML 형식으로 기존 문서에서 콘텐츠를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67389-104">You can take advantage of LINQ queries to retrieve the content to transform, or change content in an existing document to a new XML format.</span></span>  
  
 <span data-ttu-id="67389-105">이 항목의 예제 XML 소스 문서에서 콘텐츠를 브라우저에서 볼 수는 HTML로 변형 합니다.</span><span class="sxs-lookup"><span data-stu-id="67389-105">The example in this topic transforms content from an XML source document to HTML to be viewed in a browser.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a><span data-ttu-id="67389-106">XML 문서를 변환 하려면</span><span class="sxs-lookup"><span data-stu-id="67389-106">To transform an XML document</span></span>  
  
1.  <span data-ttu-id="67389-107">Visual Studio에서 새 Visual Basic 프로젝트에서 만들기는 **콘솔 응용 프로그램** 프로젝트 템플릿을 합니다.</span><span class="sxs-lookup"><span data-stu-id="67389-107">In Visual Studio, create a new Visual Basic project in the **Console Application** project template.</span></span>  
  
2.  <span data-ttu-id="67389-108">Visual Basic 코드를 수정 하려면 프로젝트에서 만든 Module1.vb 파일을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="67389-108">Double-click the Module1.vb file created in the project to modify the Visual Basic code.</span></span> <span data-ttu-id="67389-109">다음 코드를 추가 하는 `Sub Main` 의 `Module1` 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="67389-109">Add the following code to the `Sub Main` of the `Module1` module.</span></span> <span data-ttu-id="67389-110">이 코드에서는 소스 XML 문서는 <xref:System.Xml.Linq.XDocument> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="67389-110">This code creates the source XML document as an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
    ```vb  
    Dim catalog =   
      <?xml version="1.0"?>  
        <Catalog>  
          <Book id="bk101">  
            <Author>Garghentini, Davide</Author>  
            <Title>XML Developer's Guide</Title>  
            <Price>44.95</Price>  
            <Description>  
              An in-depth look at creating applications  
              with <technology>XML</technology>. For   
              <audience>beginners</audience> or   
              <audience>advanced</audience> developers.  
            </Description>  
          </Book>  
          <Book id="bk331">  
            <Author>Spencer, Phil</Author>  
            <Title>Developing Applications with Visual Basic .NET</Title>  
            <Price>45.95</Price>  
            <Description>  
              Get the expert insights, practical code samples,   
              and best practices you need   
              to advance your expertise with <technology>Visual   
              Basic .NET</technology>.   
              Learn how to create faster, more reliable applications  
              based on professional,   
              pragmatic guidance by today's top <audience>developers</audience>.  
            </Description>  
          </Book>  
        </Catalog>  
    ```  
  
     <span data-ttu-id="67389-111">[방법: 파일, 문자열 또는 스트림에서 XML을 로드](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="67389-111">[How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).</span></span>  
  
3.  <span data-ttu-id="67389-112">원본 XML 문서를 만드는 코드를 다음 모두 검색 하려면 다음 코드를 추가 \<책 > 개체에서 요소를 HTML 문서로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="67389-112">After the code to create the source XML document, add the following code to retrieve all the \<Book> elements from the object and transform them into an HTML document.</span></span> <span data-ttu-id="67389-113">목록이 \<책 > 요소 컬렉션을 반환 하는 LINQ 쿼리를 사용 하 여 만들어집니다 <xref:System.Xml.Linq.XElement> 변환된 된 HTML을 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="67389-113">The list of \<Book> elements is created by using a LINQ query that returns a collection of <xref:System.Xml.Linq.XElement> objects that contain the transformed HTML.</span></span> <span data-ttu-id="67389-114">새 XML 형식으로 원본 문서에서의 끝에 포함된 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67389-114">You can use embedded expressions to put the values from the source document in the new XML format.</span></span>  
  
     <span data-ttu-id="67389-115">결과 HTML 문서를 사용 하 여 파일에 기록 되는 <xref:System.Xml.Linq.XElement.Save%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="67389-115">The resulting HTML document is written to a file by using the <xref:System.Xml.Linq.XElement.Save%2A> method.</span></span>  
  
    ```vb  
    Dim htmlOutput =   
      <html>  
        <body>  
          <%= From book In catalog.<Catalog>.<Book>   
              Select <div>  
                       <h1><%= book.<Title>.Value %></h1>  
                       <h3><%= "By " & book.<Author>.Value %></h3>  
                        <h3><%= "Price = " & book.<Price>.Value %></h3>  
                        <h2>Description</h2>  
                        <%= TransformDescription(book.<Description>(0)) %>  
                        <hr/>  
                      </div> %>  
        </body>  
      </html>  
  
    htmlOutput.Save("BookDescription.html")  
    ```  
  
4.  <span data-ttu-id="67389-116">후 `Sub Main` 의 `Module1`, 새 메서드 추가 (`Sub`) 변환 하는 \<설명 > 지정 된 HTML 형식으로 노드.</span><span class="sxs-lookup"><span data-stu-id="67389-116">After `Sub Main` of `Module1`, add a new method (`Sub`) to transform a \<Description> node into the specified HTML format.</span></span> <span data-ttu-id="67389-117">이 메서드는 이전 단계에서 코드에 의해 호출 되며의 형식을 유지 하는 데 사용 되는 \<설명 > 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="67389-117">This method is called by the code in the previous step and is used to preserve the format of the \<Description> elements.</span></span>  
  
     <span data-ttu-id="67389-118">하위 요소를 대체 하는이 메서드는 \<설명 > html 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="67389-118">This method replaces sub-elements of the \<Description> element with HTML.</span></span> <span data-ttu-id="67389-119">`ReplaceWith` 메서드는 하위 요소의 위치를 유지 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67389-119">The `ReplaceWith` method is used to preserve the location of the sub-elements.</span></span> <span data-ttu-id="67389-120">변환된 된 내용을 \<설명 > 요소는 HTML 단락에 포함 (\<p >) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="67389-120">The transformed content of the \<Description> element is included in an HTML paragraph (\<p>) element.</span></span> <span data-ttu-id="67389-121"><xref:System.Xml.Linq.XContainer.Nodes%2A> 속성의 변환된 된 내용을 검색을 사용 하는 \<설명 > 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="67389-121">The <xref:System.Xml.Linq.XContainer.Nodes%2A> property is used to retrieve the transformed content of the \<Description> element.</span></span> <span data-ttu-id="67389-122">이렇게 하면 하위 요소가 변환된 된 내용에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67389-122">This ensures that sub-elements are included in the transformed content.</span></span>  
  
     <span data-ttu-id="67389-123">다음 코드를 추가 `Sub Main` 의 `Module1`합니다.</span><span class="sxs-lookup"><span data-stu-id="67389-123">Add the following code after `Sub Main` of `Module1`.</span></span>  
  
    ```vb  
    Public Function TransformDescription(ByVal desc As XElement) As XElement  
  
      ' Replace <technology> elements with <b>.  
      Dim content = (From element In desc...<technology>).ToList()  
  
      If content.Count > 0 Then  
        For i = 0 To content.Count - 1  
          content(i).ReplaceWith(<b><%= content(i).Value %></b>)  
        Next  
      End If  
  
      ' Replace <audience> elements with <i>.  
      content = (From element In desc...<audience>).ToList()  
  
      If content.Count > 0 Then  
        For i = 0 To content.Count - 1  
          content(i).ReplaceWith(<i><%= content(i).Value %></i>)  
        Next  
      End If  
  
      ' Return the updated contents of the <Description> element.  
      Return <p><%= desc.Nodes %></p>  
    End Function  
    ```  
  
5.  <span data-ttu-id="67389-124">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="67389-124">Save your changes.</span></span>  
  
6.  <span data-ttu-id="67389-125">F5 키를 눌러 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="67389-125">Press F5 to run the code.</span></span> <span data-ttu-id="67389-126">문서를 저장 된 결과 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="67389-126">The resulting saved document will resemble the following:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <html>  
      <body>  
        <div>  
          <h1>XML Developer's Guide</h1>  
          <h3>By Garghentini, Davide</h3>  
          <h3>Price = 44.95</h3>  
          <h2>Description</h2>  
          <p>  
            An in-depth look at creating applications  
            with <b>XML</b>. For   
            <i>beginners</i> or   
            <i>advanced</i> developers.  
          </p>  
          <hr />  
        </div>  
        <div>  
          <h1>Developing Applications with Visual Basic .NET</h1>  
          <h3>By Spencer, Phil</h3>  
          <h3>Price = 45.95</h3>  
          <h2>Description</h2>  
          <p>  
            Get the expert insights, practical code   
            samples, and best practices you need   
            to advance your expertise with <b>Visual   
            Basic .NET</b>. Learn how to create faster,  
            more reliable applications based on  
            professional, pragmatic guidance by today's   
            top <i>developers</i>.  
          </p>  
          <hr />  
        </div>  
      </body>  
    </html>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="67389-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67389-127">See Also</span></span>  
 [<span data-ttu-id="67389-128">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="67389-128">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="67389-129">Visual Basic에서 XML 조작</span><span class="sxs-lookup"><span data-stu-id="67389-129">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 [<span data-ttu-id="67389-130">XML</span><span class="sxs-lookup"><span data-stu-id="67389-130">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="67389-131">방법: 파일, 문자열 또는 스트림에서 XML 로드</span><span class="sxs-lookup"><span data-stu-id="67389-131">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 [<span data-ttu-id="67389-132">LINQ</span><span class="sxs-lookup"><span data-stu-id="67389-132">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="67389-133">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="67389-133">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
