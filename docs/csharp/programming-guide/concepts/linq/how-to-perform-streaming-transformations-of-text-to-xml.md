---
title: '방법: 텍스트를 XML로 변환 스트리밍 수행(C#)'
ms.date: 07/20/2015
ms.assetid: 9b3bd941-d0ff-4f2d-ae41-7c3b81d8fae6
ms.openlocfilehash: 4313c5263b6a219ec3c8d05a7b7938c41c7cc028
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33328190"
---
# <a name="how-to-perform-streaming-transformations-of-text-to-xml-c"></a><span data-ttu-id="3f222-102">방법: 텍스트를 XML로 변환 스트리밍 수행(C#)</span><span class="sxs-lookup"><span data-stu-id="3f222-102">How to: Perform Streaming Transformations of Text to XML (C#)</span></span>
<span data-ttu-id="3f222-103">텍스트 파일을 처리하는 한 가지 방법은 `yield return` 구문을 사용하여 한 번에 한 줄씩 텍스트 파일을 스트리밍하는 확장 메서드를 작성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f222-103">One approach to processing a text file is to write an extension method that streams the text file a line at a time using the `yield return` construct.</span></span> <span data-ttu-id="3f222-104">그런 다음 지연된 방식으로 텍스트 파일을 처리하는 LINQ 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f222-104">You then can write a LINQ query that processes the text file in a lazy deferred fashion.</span></span> <span data-ttu-id="3f222-105"><xref:System.Xml.Linq.XStreamingElement>를 사용하여 출력을 스트림하면 소스 텍스트 파일의 크기에 관계없이 최소 메모리 크기를 사용하는 XML로 텍스트 파일을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f222-105">If you then use <xref:System.Xml.Linq.XStreamingElement> to stream output, you then can create a transformation from the text file to XML that uses a minimal amount of memory, regardless of the size of the source text file.</span></span>  
  
 <span data-ttu-id="3f222-106">스트리밍 변환과 관련된 몇 가지 주의 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f222-106">There are some caveats regarding streaming transformations.</span></span> <span data-ttu-id="3f222-107">스트리밍 변환은 전체 파일을 한 번만 처리할 수 있는 경우와 소스 문서에서 발생하는 순서대로 줄을 처리할 수 있는 경우에 가장 효과적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f222-107">A streaming transformation is best applied in situations where you can process the entire file once, and if you can process the lines in the order that they occur in the source document.</span></span> <span data-ttu-id="3f222-108">파일을 두 번 이상 처리해야 하거나 줄을 처리하기 전에 정렬해야 하는 경우에는 스트리밍 기법 사용의 많은 이점을 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f222-108">If you have to process the file more than once, or if you have to sort the lines before you can process them, you will lose many of the benefits of using a streaming technique.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f222-109">예</span><span class="sxs-lookup"><span data-stu-id="3f222-109">Example</span></span>  
 <span data-ttu-id="3f222-110">아래에 있는 People.txt 텍스트 파일은 이 예제의 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="3f222-110">The following text file, People.txt, is the source for this example.</span></span>  
  
```  
#This is a comment  
1,Tai,Yee,Writer  
2,Nikolay,Grachev,Programmer  
3,David,Wright,Inventor  
```  
  
 <span data-ttu-id="3f222-111">다음 코드에는 지연된 방식으로 텍스트 파일의 줄을 스트림하는 확장 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f222-111">The following code contains an extension method that streams the lines of the text file in a deferred fashion.</span></span>  
  
```csharp  
public static class StreamReaderSequence  
{  
    public static IEnumerable<string> Lines(this StreamReader source)  
    {  
        String line;  
  
        if (source == null)  
            throw new ArgumentNullException("source");  
        while ((line = source.ReadLine()) != null)  
        {  
            yield return line;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        StreamReader sr = new StreamReader("People.txt");  
        XStreamingElement xmlTree = new XStreamingElement("Root",  
            from line in sr.Lines()  
            let items = line.Split(',')  
            where !line.StartsWith("#")  
            select new XElement("Person",  
                       new XAttribute("ID", items[0]),  
                       new XElement("First", items[1]),  
                       new XElement("Last", items[2]),  
                       new XElement("Occupation", items[3])  
                   )  
        );  
        Console.WriteLine(xmlTree);  
        sr.Close();  
    }  
}  
```  
  
 <span data-ttu-id="3f222-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3f222-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Person ID="1">  
    <First>Tai</First>  
    <Last>Yee</Last>  
    <Occupation>Writer</Occupation>  
  </Person>  
  <Person ID="2">  
    <First>Nikolay</First>  
    <Last>Grachev</Last>  
    <Occupation>Programmer</Occupation>  
  </Person>  
  <Person ID="3">  
    <First>David</First>  
    <Last>Wright</Last>  
    <Occupation>Inventor</Occupation>  
  </Person>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f222-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f222-113">See Also</span></span>  
 <xref:System.Xml.Linq.XStreamingElement>  
 [<span data-ttu-id="3f222-114">고급 쿼리 기술(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="3f222-114">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
