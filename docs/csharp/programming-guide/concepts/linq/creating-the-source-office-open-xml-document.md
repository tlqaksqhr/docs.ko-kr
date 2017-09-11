---
title: "원본 Office Open XML 문서 만들기(C#)"
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
ms.assetid: 653c8cdb-73be-4dc2-927f-924cfb4ed9ed
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1ea055d35982e364a6b77281aca1d1b03474aa0b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="creating-the-source-office-open-xml-document-c"></a><span data-ttu-id="f47c4-102">원본 Office Open XML 문서 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="f47c4-102">Creating the Source Office Open XML Document (C#)</span></span>
<span data-ttu-id="f47c4-103">이 항목에서는 이 자습서의 다른 예제에서 사용하는 Office Open XML WordprocessingML 문서를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f47c4-103">This topic shows how to create the Office Open XML WordprocessingML document that the other examples in this tutorial use.</span></span> <span data-ttu-id="f47c4-104">이러한 지침을 따르는 경우 출력은 각 예제에서 제공되는 출력과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="f47c4-104">If you follow these instructions, your output will match the output provided in each example.</span></span>  
  
 <span data-ttu-id="f47c4-105">그러나 이 자습서의 예제는 모든 유효한 WordprocessingML 문서와 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f47c4-105">However, the examples in this tutorial will work with any valid WordprocessingML document.</span></span>  
  
 <span data-ttu-id="f47c4-106">이 자습서에서 사용하는 문서를 만들려면 Microsoft Office 2007 이상이 설치되어 있거나 Word, Excel 및 PowerPoint 2007 파일 형식용 Microsoft Office 호환 기능 팩이 포함된 Microsoft Office 2003이 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f47c4-106">To create the document that this tutorial uses, you must either have Microsoft Office 2007 or later installed, or you must have Microsoft Office 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="creating-the-wordprocessingml-document"></a><span data-ttu-id="f47c4-107">WordprocessingML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="f47c4-107">Creating the WordprocessingML Document</span></span>  
  
#### <a name="to-create-the-wordprocessingml-document"></a><span data-ttu-id="f47c4-108">WordprocessingML 문서를 만들려면</span><span class="sxs-lookup"><span data-stu-id="f47c4-108">To create the WordprocessingML document</span></span>  
  
1.  <span data-ttu-id="f47c4-109">Microsoft Word 문서를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f47c4-109">Create a new Microsoft Word document.</span></span>  
  
2.  <span data-ttu-id="f47c4-110">다음 텍스트를 새 문서에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="f47c4-110">Paste the following text into the new document:</span></span>  
  
    ```  
    Parsing WordprocessingML with LINQ to XML  
  
    The following example prints to the console.  
  
    using System;  
  
    class Program {  
        public static void Main(string[] args) {  
            Console.WriteLine("Hello World");  
        }  
    }  
  
    This example produces the following output:  
  
    Hello World  
    ```  
  
3.  <span data-ttu-id="f47c4-111">"제목 1" 스타일로 첫 번째 줄의 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f47c4-111">Format the first line with the style "Heading 1".</span></span>  
  
4.  <span data-ttu-id="f47c4-112">C# 코드가 포함된 줄을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f47c4-112">Select the lines that contain the C# code.</span></span> <span data-ttu-id="f47c4-113">첫 번째 줄은 `using` 키워드로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f47c4-113">The first line starts with the `using` keyword.</span></span> <span data-ttu-id="f47c4-114">마지막 줄은 마지막 닫는 괄호입니다.</span><span class="sxs-lookup"><span data-stu-id="f47c4-114">The last line is the last closing brace.</span></span> <span data-ttu-id="f47c4-115">courier 글꼴로 줄의 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f47c4-115">Format the lines with the courier font.</span></span> <span data-ttu-id="f47c4-116">새 스타일로 줄의 서식을 지정한 다음 새 스타일의 이름을 "Code"로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f47c4-116">Format them with a new style, and name the new style "Code".</span></span>  
  
5.  <span data-ttu-id="f47c4-117">마지막으로 출력이 포함된 전체 줄을 선택하고 `Code` 스타일로 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f47c4-117">Finally, select the entire line that contains the output, and format it with the `Code` style.</span></span>  
  
6.  <span data-ttu-id="f47c4-118">문서를 저장하고 SampleDoc.docx로 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f47c4-118">Save the document, and name it SampleDoc.docx.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f47c4-119">Microsoft Word 2003을 사용하는 경우 **파일 형식** 드롭다운 목록에서 **Word 2007 문서**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f47c4-119">If you are using Microsoft Word 2003, select **Word 2007 Document** in the **Save as Type** drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f47c4-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f47c4-120">See Also</span></span>  
 [<span data-ttu-id="f47c4-121">자습서: WordprocessingML 문서에서 내용 조작(C#)</span><span class="sxs-lookup"><span data-stu-id="f47c4-121">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)

