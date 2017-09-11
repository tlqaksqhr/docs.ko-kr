---
title: "확장 메서드를 사용하여 리팩터링(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: c5fc123d-af10-4a2f-b8e4-db921efb2639
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c4145e38a6fc49d53d274520dd155cffb5e7f9d5
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="refactoring-using-an-extension-method-c"></a><span data-ttu-id="70dd3-102">확장 메서드를 사용하여 리팩터링(C#)</span><span class="sxs-lookup"><span data-stu-id="70dd3-102">Refactoring Using an Extension Method (C#)</span></span>
<span data-ttu-id="70dd3-103">이 예제는 확장 메서드로 구현된 순수 함수를 사용하여 문자열의 연결을 리팩터링하는 방법으로 이전 예제인 [단락의 텍스트 검색(C#)](../../../../csharp/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md)을 기반으로 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-103">This example builds on the previous example, [Retrieving the Text of the Paragraphs (C#)](../../../../csharp/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), by refactoring the concatenation of strings using a pure function that is implemented as an extension method.</span></span>  
  
 <span data-ttu-id="70dd3-104">이전 예제에서는 <xref:System.Linq.Enumerable.Aggregate%2A> 표준 쿼리 연산자를 사용하여 여러 문자열을 한 문자열로 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-104">The previous example used the <xref:System.Linq.Enumerable.Aggregate%2A> standard query operator to concatenate multiple strings into one string.</span></span> <span data-ttu-id="70dd3-105">그러나 생성되는 쿼리가 더 작고 간단하기 때문에 이 작업을 수행하는 확장 메서드를 작성하는 것이 간편합니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-105">However, it is more convenient to write an extension method to do this, because the resulting query smaller and more simple.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70dd3-106">예제</span><span class="sxs-lookup"><span data-stu-id="70dd3-106">Example</span></span>  
 <span data-ttu-id="70dd3-107">이 예제에서는 WordprocessingML 문서를 처리하여 단락, 각 단락의 스타일 및 각 단락의 텍스트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-107">This example processes a WordprocessingML document, retrieving the paragraphs, the style of each paragraph, and the text of each paragraph.</span></span> <span data-ttu-id="70dd3-108">이 예제는 이 자습서의 이전 예제를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-108">This example builds on the previous examples in this tutorial.</span></span>  
  
 <span data-ttu-id="70dd3-109">이 예제에는 `StringConcatenate` 메서드의 오버로드가 여러 개 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-109">The example contains multiple overloads of the `StringConcatenate` method.</span></span>  
  
 <span data-ttu-id="70dd3-110">이 예제의 소스 문서 만들기에 대한 지침은 [원본 Office Open XML 문서 만들기(C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-110">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="70dd3-111">이 예제에서는 WindowsBase 어셈블리의 클래스를 사용하고</span><span class="sxs-lookup"><span data-stu-id="70dd3-111">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="70dd3-112"><xref:System.IO.Packaging?displayProperty=fullName> 네임스페이스의 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-112">It uses types in the <xref:System.IO.Packaging?displayProperty=fullName> namespace.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static string StringConcatenate(this IEnumerable<string> source)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item));  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate(this IEnumerable<string> source, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s).Append(separator);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item)).Append(separator);  
        return sb.ToString();  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="70dd3-113">예제</span><span class="sxs-lookup"><span data-stu-id="70dd3-113">Example</span></span>  
 <span data-ttu-id="70dd3-114">`StringConcatenate` 메서드의 오버로드는 네 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-114">There are four overloads of the `StringConcatenate` method.</span></span> <span data-ttu-id="70dd3-115">한 오버로드는 문자열의 컬렉션을 가져와서 단일 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-115">One overload simply takes a collection of strings and returns a single string.</span></span> <span data-ttu-id="70dd3-116">다른 오버로드는 원하는 형식의 컬렉션과 컬렉션의 singleton에서 문자열로 프로젝션하는 대리자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-116">Another overload can take a collection of any type, and a delegate that projects from a singleton of the collection to a string.</span></span> <span data-ttu-id="70dd3-117">나머지 두 오버로드는 구분 기호 문자열을 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-117">There are two more overloads that allow you to specify a separator string.</span></span>  
  
 <span data-ttu-id="70dd3-118">다음 코드에서는 네 오버로드를 모두 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-118">The following code uses all four overloads.</span></span>  
  
```csharp  
string[] numbers = { "one", "two", "three" };  
  
Console.WriteLine("{0}", numbers.StringConcatenate());  
Console.WriteLine("{0}", numbers.StringConcatenate(":"));  
  
int[] intNumbers = { 1, 2, 3 };  
Console.WriteLine("{0}", intNumbers.StringConcatenate(i => i.ToString()));  
Console.WriteLine("{0}", intNumbers.StringConcatenate(i => i.ToString(), ":"));  
```  
  
 <span data-ttu-id="70dd3-119">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-119">This example produces the following output:</span></span>  
  
```  
onetwothree  
one:two:three:  
123  
1:2:3:  
```  
  
## <a name="example"></a><span data-ttu-id="70dd3-120">예제</span><span class="sxs-lookup"><span data-stu-id="70dd3-120">Example</span></span>  
 <span data-ttu-id="70dd3-121">이제 새 확장명 메서드를 활용하기 위해 예제를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-121">Now, the example can be modified to take advantage of the new extension method:</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static string StringConcatenate(this IEnumerable<string> source)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item));  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate(this IEnumerable<string> source, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s).Append(separator);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item)).Append(separator);  
        return sb.ToString();  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        const string fileName = "SampleDoc.docx";  
  
        const string documentRelationshipType =  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
        const string stylesRelationshipType =  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
        const string wordmlNamespace =  
          "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
        XNamespace w = wordmlNamespace;  
  
        XDocument xDoc = null;  
        XDocument styleDoc = null;  
  
        using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
        {  
            PackageRelationship docPackageRelationship =  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
            if (docPackageRelationship != null)  
            {  
                Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative),  
                  docPackageRelationship.TargetUri);  
                PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
                //  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
                //  Find the styles part. There will only be one.  
                PackageRelationship styleRelation =  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
                if (styleRelation != null)  
                {  
                    Uri styleUri =  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
                    PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
                    //  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
                }  
            }  
        }  
  
        string defaultStyle =  
            (string)(  
                from style in styleDoc.Root.Elements(w + "style")  
                where (string)style.Attribute(w + "type") == "paragraph" &&  
                      (string)style.Attribute(w + "default") == "1"  
                select style  
            ).First().Attribute(w + "styleId");  
  
        // Find all paragraphs in the document.  
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
  
        // Retrieve the text of each paragraph.  
        var paraWithText =  
            from para in paragraphs  
            select new  
            {  
                ParagraphNode = para.ParagraphNode,  
                StyleName = para.StyleName,  
                Text = para  
                       .ParagraphNode  
                       .Elements(w + "r")  
                       .Elements(w + "t")  
                       .StringConcatenate(e => (string)e)  
            };  
  
        foreach (var p in paraWithText)  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text);  
    }  
}  
```  
  
 <span data-ttu-id="70dd3-122">[원본 Office Open XML 문서 만들기(C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)에서 설명하는 문서에 적용할 경우 이 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-122">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
```  
StyleName:Heading1 >Parsing WordprocessingML with LINQ to XML<  
StyleName:Normal ><  
StyleName:Normal >The following example prints to the console.<  
StyleName:Normal ><  
StyleName:Code >using System;<  
StyleName:Code ><  
StyleName:Code >class Program {<  
StyleName:Code >    public static void (string[] args) {<  
StyleName:Code >        Console.WriteLine("Hello World");<  
StyleName:Code >    }<  
StyleName:Code >}<  
StyleName:Normal ><  
StyleName:Normal >This example produces the following output:<  
StyleName:Normal ><  
StyleName:Code >Hello World<  
```  
  
 <span data-ttu-id="70dd3-123">이 리팩터링은 순수 함수로의 리팩터링에 대한 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-123">Note that this refactoring is a variant of refactoring into a pure function.</span></span> <span data-ttu-id="70dd3-124">다음 항목에서는 순수 함수로의 팩터링 개념에 대해 자세히 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-124">The next topic will introduce the idea of factoring into pure functions in more detail.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="70dd3-125">다음 단계</span><span class="sxs-lookup"><span data-stu-id="70dd3-125">Next Steps</span></span>  
 <span data-ttu-id="70dd3-126">다음 예제에서는 순수 함수를 사용하여 다른 방식으로 이 코드를 리팩터링하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="70dd3-126">The next example shows how to refactor this code in another way, by using pure functions:</span></span>  
  
-   [<span data-ttu-id="70dd3-127">순수 함수를 사용하여 리팩터링(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70dd3-127">Refactoring Using a Pure Function (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-a-pure-function.md)  
  
## <a name="see-also"></a><span data-ttu-id="70dd3-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70dd3-128">See Also</span></span>  
 <span data-ttu-id="70dd3-129">[자습서: WordprocessingML 문서에서 내용 조작(C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) </span><span class="sxs-lookup"><span data-stu-id="70dd3-129">[Tutorial: Manipulating Content in a WordprocessingML Document (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) </span></span>  
 [<span data-ttu-id="70dd3-130">순수 함수로 리팩터링(C#)</span><span class="sxs-lookup"><span data-stu-id="70dd3-130">Refactoring Into Pure Functions (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md)

