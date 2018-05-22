---
title: 단락 및 해당 스타일 검색(C#)
ms.date: 07/20/2015
ms.assetid: c2f767f8-57b1-4b4b-af04-89ffb1f7067d
ms.openlocfilehash: 11788c1fa46c63c78a9db0255c8e84250285863e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="retrieving-the-paragraphs-and-their-styles-c"></a><span data-ttu-id="99b67-102">단락 및 해당 스타일 검색(C#)</span><span class="sxs-lookup"><span data-stu-id="99b67-102">Retrieving the Paragraphs and Their Styles (C#)</span></span>
<span data-ttu-id="99b67-103">이 예제에서는 WordprocessingML 문서에서 단락 노드를 검색하는 쿼리를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-103">In this example, we write a query that retrieves the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="99b67-104">또한 각 단락의 스타일도 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-104">It also identifies the style of each paragraph.</span></span>  
  
 <span data-ttu-id="99b67-105">이 쿼리는 스타일 목록에서 기본 스타일을 검색하는 이전 예제 [기본 단락 스타일 찾기(C#)](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md)의 쿼리를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-105">This query builds on the query in the previous example, [Finding the Default Paragraph Style (C#)](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md), which retrieves the default style from the list of styles.</span></span> <span data-ttu-id="99b67-106">이 정보는 쿼리에서 스타일이 명시적으로 설정되지 않은 단락의 스타일을 식별할 수 있도록 하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-106">This information is required so that the query can identify the style of paragraphs that do not have a style explicitly set.</span></span> <span data-ttu-id="99b67-107">단락 스타일은 `w:pPr` 요소를 통해 설정되며 단락이 이 요소를 포함하지 않으면 기본 스타일로 서식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-107">Paragraph styles are set through the `w:pPr` element; if a paragraph does not contain this element, it is formatted with the default style.</span></span>  
  
 <span data-ttu-id="99b67-108">이 항목에서는 몇 가지 쿼리 부분의 의미에 대해 설명한 다음 작동하는 전체 예제의 일부로 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-108">This topic explains the significance of some pieces of the query, then shows the query as part of a complete, working example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99b67-109">예</span><span class="sxs-lookup"><span data-stu-id="99b67-109">Example</span></span>  
 <span data-ttu-id="99b67-110">문서의 모든 단락과 단락 스타일을 검색하는 쿼리의 소스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-110">The source of the query to retrieve all the paragraphs in a document and their styles is as follows:</span></span>  
  
```csharp  
xDoc.Root.Element(w + "body").Descendants(w + "p")  
```  
  
 <span data-ttu-id="99b67-111">이 식은 이전 예제 [기본 단락 스타일 찾기(C#)](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md)의 쿼리 소스와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-111">This expression is similar to the source of the query in the previous example, [Finding the Default Paragraph Style (C#)](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md).</span></span> <span data-ttu-id="99b67-112">주요 차이점은 이 식에서는 <xref:System.Xml.Linq.XContainer.Descendants%2A> 축 대신 <xref:System.Xml.Linq.XContainer.Elements%2A> 축을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-112">The main difference is that it uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis instead of the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span> <span data-ttu-id="99b67-113">섹션이 포함된 문서에서 단락은 본문 요소의 직접적 자식이 아니고 계층 구조에서 두 수준 아래에 있기 때문에 쿼리에서는 <xref:System.Xml.Linq.XContainer.Descendants%2A> 축을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-113">The query uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis because in documents that have sections, the paragraphs will not be the direct children of the body element; rather, the paragraphs will be two levels down in the hierarchy.</span></span> <span data-ttu-id="99b67-114">코드에서는 <xref:System.Xml.Linq.XContainer.Descendants%2A> 축을 사용하여 문서에서 섹션을 사용하는지 여부에 대한 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-114">By using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis, the code will work of whether or not the document uses sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99b67-115">예</span><span class="sxs-lookup"><span data-stu-id="99b67-115">Example</span></span>  
 <span data-ttu-id="99b67-116">쿼리에서는 `let` 절을 사용하여 스타일 노드가 포함된 요소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-116">The query uses a `let` clause to determine the element that contains the style node.</span></span> <span data-ttu-id="99b67-117">요소가 없으면 `styleNode`가 `null`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-117">If there is no element, then `styleNode` is set to `null`:</span></span>  
  
```csharp  
let styleNode = para.Elements(w + "pPr").Elements(w + "pStyle").FirstOrDefault()  
```  
  
 <span data-ttu-id="99b67-118">`let` 절에서는 먼저 <xref:System.Xml.Linq.XContainer.Elements%2A> 축을 사용하여 `pPr`이라는 모든 요소를 찾은 다음 <xref:System.Xml.Linq.Extensions.Elements%2A> 확장 메서드를 사용하여 `pStyle`이라는 모든 자식 요소를 찾고, 마지막으로 <xref:System.Linq.Enumerable.FirstOrDefault%2A> 표준 쿼리 연산자를 사용하여 컬렉션을 singleton으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-118">The `let` clause first uses the <xref:System.Xml.Linq.XContainer.Elements%2A> axis to find all elements named `pPr`, then uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method to find all child elements named `pStyle`, and finally uses the <xref:System.Linq.Enumerable.FirstOrDefault%2A> standard query operator to convert the collection to a singleton.</span></span> <span data-ttu-id="99b67-119">컬렉션이 비어 있으면 `styleNode`가 `null`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-119">If the collection is empty, `styleNode` is set to `null`.</span></span> <span data-ttu-id="99b67-120">이 방법은 `pStyle` 하위 노드를 찾을 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-120">This is a useful idiom to look for the `pStyle` descendant node.</span></span> <span data-ttu-id="99b67-121">`pPr` 자식 노드가 없으면 코드에서 예외를 throw하지 않고, 대신 `styleNode`가 `null`로 설정됩니다. 이는 이 `let` 절의 원하는 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-121">Note that if the `pPr` child node does not exist, the code does nor fail by throwing an exception; instead, `styleNode` is set to `null`, which is the desired behavior of this `let` clause.</span></span>  
  
 <span data-ttu-id="99b67-122">쿼리에서는 두 멤버 `StyleName` 및 `ParagraphNode`가 있는 익명 형식의 컬렉션을 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-122">The query projects a collection of an anonymous type with two members, `StyleName` and `ParagraphNode`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99b67-123">예</span><span class="sxs-lookup"><span data-stu-id="99b67-123">Example</span></span>  
 <span data-ttu-id="99b67-124">이 예제에서는 WordprocessingML 문서를 처리하여 WordprocessingML 문서에서 단락 노드를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-124">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="99b67-125">또한 각 단락의 스타일도 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-125">It also identifies the style of each paragraph.</span></span> <span data-ttu-id="99b67-126">이 예제는 이 자습서의 이전 예제를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-126">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="99b67-127">새 쿼리는 아래에 있는 코드의 주석에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-127">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="99b67-128">이 예제의 소스 문서 만들기에 대한 지침은 [원본 Office Open XML 문서 만들기(C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-128">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="99b67-129">이 예제에서는 WindowsBase 어셈블리의 클래스를 사용하고</span><span class="sxs-lookup"><span data-stu-id="99b67-129">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="99b67-130"><xref:System.IO.Packaging?displayProperty=nameWithType> 네임스페이스의 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-130">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative), docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
        if (styleRelation != null)  
        {  
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
        }  
    }  
}  
  
string defaultStyle =   
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
// Following is the new query that finds all paragraphs in the  
// document and their styles.  
var paragraphs =  
    from para in xDoc  
                 .Root  
                 .Element(w + "body")  
                 .Descendants(w + "p")  
    let styleNode = para  
                    .Elements(w + "pPr")  
                    .Elements(w + "pStyle")  
                    .FirstOrDefault()  
    select new  
    {  
        ParagraphNode = para,  
        StyleName = styleNode != null ?  
            (string)styleNode.Attribute(w + "val") :  
            defaultStyle  
    };  
  
foreach (var p in paragraphs)  
    Console.WriteLine("StyleName:{0}", p.StyleName);  
```  
  
 <span data-ttu-id="99b67-131">[원본 Office Open XML 문서 만들기(C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)에서 설명하는 문서에 적용할 경우 이 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-131">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
```  
StyleName:Heading1  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
```  
  
## <a name="next-steps"></a><span data-ttu-id="99b67-132">다음 단계</span><span class="sxs-lookup"><span data-stu-id="99b67-132">Next Steps</span></span>  
 <span data-ttu-id="99b67-133">다음 항목 [단락의 텍스트 검색(C#)](../../../../csharp/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md)에서는 단락의 텍스트를 검색하기 위한 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="99b67-133">In the next topic, [Retrieving the Text of the Paragraphs (C#)](../../../../csharp/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), you'll create a query to retrieve the text of paragraphs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99b67-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99b67-134">See Also</span></span>  
 [<span data-ttu-id="99b67-135">자습서: WordprocessingML 문서에서 내용 조작(C#)</span><span class="sxs-lookup"><span data-stu-id="99b67-135">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
