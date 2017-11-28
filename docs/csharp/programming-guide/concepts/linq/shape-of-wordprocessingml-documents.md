---
title: "WordprocessingML 문서의 모양(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 3791b5e0-c502-469b-bb75-a7bf6fdd0a94
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8c1ccbfd71baff50a8055cd89ddecf47bd35cac9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="shape-of-wordprocessingml-documents-c"></a><span data-ttu-id="4e883-102">WordprocessingML 문서의 모양(C#)</span><span class="sxs-lookup"><span data-stu-id="4e883-102">Shape of WordprocessingML Documents (C#)</span></span>
<span data-ttu-id="4e883-103">이 항목에서는 WordprocessingML 문서의 XML 모양에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="4e883-103">This topic introduces the XML shape of a WordprocessingML document.</span></span>  
  
## <a name="microsoft-office-formats"></a><span data-ttu-id="4e883-104">Microsoft Office 형식</span><span class="sxs-lookup"><span data-stu-id="4e883-104">Microsoft Office Formats</span></span>  
 <span data-ttu-id="4e883-105">2007 Microsoft Office system의 기본 파일 형식은 Office Open XML(일반적으로 Open XML이라고 함)입니다.</span><span class="sxs-lookup"><span data-stu-id="4e883-105">The native file format for the 2007 Microsoft Office system is Office Open XML (commonly called Open XML).</span></span> <span data-ttu-id="4e883-106">Open XML은 Ecma 표준이며 현재 ISO-IEC 표준 과정을 거치고 있는 XML 기반 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4e883-106">Open XML is an XML-based format that an Ecma standard and is currently going through the ISO-IEC standards process.</span></span> <span data-ttu-id="4e883-107">Open XML에 있는 워드 프로세서 파일의 마크업 언어를 WordprocessingML이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e883-107">The markup language for word processing files within Open XML is called WordprocessingML.</span></span> <span data-ttu-id="4e883-108">이 자습서에서는 WordprocessingML 소스 파일을 예제의 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4e883-108">This tutorial uses WordprocessingML source files as input for the examples.</span></span>  
  
 <span data-ttu-id="4e883-109">Microsoft Office 2003을 사용하는 경우 Word, Excel 및 PowerPoint 2007 파일 형식용 Microsoft Office 호환 기능 팩을 설치했으면 Office Open XML 형식으로 문서를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e883-109">If you are using Microsoft Office 2003, you can save documents in the Office Open XML format if you have installed the the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="the-shape-of-wordprocessingml-documents"></a><span data-ttu-id="4e883-110">WordprocessingML 문서의 모양</span><span class="sxs-lookup"><span data-stu-id="4e883-110">The Shape of WordprocessingML Documents</span></span>  
 <span data-ttu-id="4e883-111">먼저 WordprocessingML 문서의 모양을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e883-111">The first thing to understand is the shape of WordprocessingML documents.</span></span> <span data-ttu-id="4e883-112">WordprocessingML 문서에는 문서의 단락이 포함된 `w:body`라는 본문 요소가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e883-112">A WordprocessingML document contains a body element (named `w:body`) that contains the paragraphs of the document.</span></span> <span data-ttu-id="4e883-113">각 단락에는 `w:r`이라는 텍스트 실행이 하나 이상 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e883-113">Each paragraph contains one or more text runs (named `w:r`).</span></span> <span data-ttu-id="4e883-114">각 텍스트 실행에는 `w:t`라는 텍스트가 하나 이상 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e883-114">Each text run contains one or more text pieces (named `w:t`).</span></span>  
  
 <span data-ttu-id="4e883-115">다음은 매우 간단한 WordprocessingML 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="4e883-115">The following is a very simple WordprocessingML document:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<w:document  
xmlns:ve="http://schemas.openxmlformats.org/markup-compatibility/2006"  
xmlns:o="urn:schemas-microsoft-com:office:office"  
xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"  
xmlns:m="http://schemas.openxmlformats.org/officeDocument/2006/math"  
xmlns:v="urn:schemas-microsoft-com:vml"  
xmlns:wp="http://schemas.openxmlformats.org/drawingml/2006/wordprocessingDrawing"  
xmlns:w10="urn:schemas-microsoft-com:office:word"  
xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
xmlns:wne="http://schemas.microsoft.com/office/word/2006/wordml">  
  <w:body>  
    <w:p w:rsidR="00E22EB6"  
         w:rsidRDefault="00E22EB6">  
      <w:r>  
        <w:t>This is a paragraph.</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00E22EB6"  
         w:rsidRDefault="00E22EB6">  
      <w:r>  
        <w:t>This is another paragraph.</w:t>  
      </w:r>  
    </w:p>  
  </w:body>  
</w:document>  
```  
  
 <span data-ttu-id="4e883-116">이 문서에는 두 단락이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e883-116">This document contains two paragraphs.</span></span> <span data-ttu-id="4e883-117">두 단락에는 모두 단일 텍스트 실행이 포함되어 있고 각 텍스트 실행에는 단일 텍스트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e883-117">They both contain a single text run, and each text run contains a single text piece.</span></span>  
  
 <span data-ttu-id="4e883-118">XML 형식으로 WordprocessingML 문서의 내용을 보는 가장 쉬운 방법은 Microsoft Word를 사용하여 문서를 만들어 저장한 후 XML을 콘솔에 출력하는 다음 프로그램을 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4e883-118">The easiest way to see the contents of a WordprocessingML document in XML form is to create one using Microsoft Word, save it, and then run the following program that prints the XML to the console.</span></span>  
  
 <span data-ttu-id="4e883-119">이 예제에서는 WindowsBase 어셈블리의 클래스를 사용하고</span><span class="sxs-lookup"><span data-stu-id="4e883-119">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="4e883-120"><xref:System.IO.Packaging?displayProperty=nameWithType> 네임스페이스의 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4e883-120">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
using (Package wdPackage = Package.Open("SampleDoc.docx", FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship relationship =  
        wdPackage  
        .GetRelationshipsByType(documentRelationshipType)  
        .FirstOrDefault();  
    if (relationship != null)  
    {  
        Uri documentUri =  
            PackUriHelper.ResolvePartUri(  
                new Uri("/", UriKind.Relative),  
                relationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Get the officeDocument part from the package.  
        //  Load the XML in the part into an XDocument instance.  
        XDocument xdoc =  
            XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
        Console.WriteLine(xdoc.Root);  
    }  
}  
```  
  
## <a name="external-resources"></a><span data-ttu-id="4e883-121">외부 리소스</span><span class="sxs-lookup"><span data-stu-id="4e883-121">External Resources</span></span>  
 [<span data-ttu-id="4e883-122">Office(2007) Open XML 파일 형식 소개</span><span class="sxs-lookup"><span data-stu-id="4e883-122">Introducing the Office (2007) Open XML File Formats</span></span>](http://go.microsoft.com/fwlink/?LinkId=98093)  
  
 [<span data-ttu-id="4e883-123">WordprocessingML의 개요</span><span class="sxs-lookup"><span data-stu-id="4e883-123">Overview of WordprocessingML</span></span>](http://go.microsoft.com/fwlink/?LinkId=98094)  
  
 [<span data-ttu-id="4e883-124">Office 2003: XML 참조 스키마 다운로드 페이지</span><span class="sxs-lookup"><span data-stu-id="4e883-124">Office 2003: XML Reference Schemas Download page</span></span>](http://go.microsoft.com/fwlink/?LinkId=98095)  
  
## <a name="see-also"></a><span data-ttu-id="4e883-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e883-125">See Also</span></span>  
 [<span data-ttu-id="4e883-126">자습서: WordprocessingML 문서에서 내용 조작(C#)</span><span class="sxs-lookup"><span data-stu-id="4e883-126">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
