---
title: "방법: 관리되는 HTML 문서 개체 모델의 요소에 대한 스타일 변경"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: managed HTML DOM [Windows Forms], changing styles on elements
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3726ccdebf310d831fb0d7ea21fab011293f6d99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a><span data-ttu-id="e26b7-102">방법: 관리되는 HTML 문서 개체 모델의 요소에 대한 스타일 변경</span><span class="sxs-lookup"><span data-stu-id="e26b7-102">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>
<span data-ttu-id="e26b7-103">모양을 제어 하는 문서 및 해당 요소의 html에서 스타일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-103">You can use styles in HTML to control the appearance of a document and its elements.</span></span> <span data-ttu-id="e26b7-104"><xref:System.Windows.Forms.HtmlDocument>및 <xref:System.Windows.Forms.HtmlElement> 지원 <xref:System.Windows.Forms.HtmlElement.Style%2A> 는 다음과 같은 형식의 스타일 문자열을 사용 하는 속성:</span><span class="sxs-lookup"><span data-stu-id="e26b7-104"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> support <xref:System.Windows.Forms.HtmlElement.Style%2A> properties that take style strings of the following format:</span></span>  
  
 `name1:value1;...;nameN:valueN;`  
  
 <span data-ttu-id="e26b7-105">다음은 한 `DIV` 을 Arial 고 모든 텍스트를 굵게 글꼴을 설정 하는 스타일 문자열:</span><span class="sxs-lookup"><span data-stu-id="e26b7-105">Here is a `DIV` with a style string that sets the font to Arial and all text to bold:</span></span>  
  
 `<DIV style="font-face:arial;font-weight:bold;">`  
  
 `Hello, world!`  
  
 `</DIV>`  
  
 <span data-ttu-id="e26b7-106">사용 하 여 스타일 조작 문제가 <xref:System.Windows.Forms.HtmlElement.Style%2A> 속성은 수 있다는 것에 추가 하 고 문자열에서 개별 스타일 설정을 제거 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-106">The problem with manipulating styles using the <xref:System.Windows.Forms.HtmlElement.Style%2A> property is that it can prove cumbersome to add to and remove individual style settings from the string.</span></span> <span data-ttu-id="e26b7-107">예를 들어 위에 커서를 가져갈 때마다 기울임꼴로 이전 텍스트를 렌더링 하는 절차는 복잡 해질는 `DIV`, 기울임꼴이 커서를 벗어날 때 해제 되도록 하 고는 `DIV`합니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-107">For example, it would become a complex procedure for you to render the previous text in italics whenever the user positions the cursor over the `DIV`, and take italics off when the cursor leaves the `DIV`.</span></span> <span data-ttu-id="e26b7-108">시간이 많이 스타일 이런이 방식으로 조작 하는 경우 문제가 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-108">Time would become an issue if you need to manipulate a large number of styles in this manner.</span></span>  
  
 <span data-ttu-id="e26b7-109">다음 절차에는 쉽게 HTML 문서와 요소에 대 한 스타일을 조작 하는 데 사용할 수 있는 코드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-109">The following procedure contains code that you can use to easily manipulate styles on HTML documents and elements.</span></span> <span data-ttu-id="e26b7-110">프로시저 새 프로젝트를 만들고 폼에 컨트롤 추가 같은 Windows Forms의 기본 작업을 수행 하는 방법을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-110">The procedure requires that you know how to perform basic tasks in Windows Forms, such as creating a new project and adding a control to a form.</span></span>  
  
### <a name="to-process-style-changes-in-a-windows-forms-application"></a><span data-ttu-id="e26b7-111">Windows Forms 응용 프로그램에 대 한 스타일 변경 내용을 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="e26b7-111">To process style changes in a Windows Forms application</span></span>  
  
1.  <span data-ttu-id="e26b7-112">새 Windows Forms 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-112">Create a new Windows Forms project.</span></span>  
  
2.  <span data-ttu-id="e26b7-113">선택한 프로그래밍 언어에 대 한 적절 한 확장명으로 끝나는 새 클래스 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-113">Create a new class file ending in the extension appropriate for your programming language.</span></span>  
  
3.  <span data-ttu-id="e26b7-114">복사는 `StyleGenerator` 클래스 파일에이 항목의 예 섹션에는 코드를 클래스 및 코드를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-114">Copy the `StyleGenerator` class code in the Example section of this topic into the class file, and save the code.</span></span>  
  
4.  <span data-ttu-id="e26b7-115">다음 HTML Test.htm 라는 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-115">Save the following HTML to a file named Test.htm.</span></span>  
  
    ```  
    <HTML>  
        <BODY>  
  
            <DIV style="font-face:arial;font-weight:bold;">  
                Hello, world!  
            </DIV><P>  
  
            <DIV>  
                Hello again, world!  
            </DIV><P>  
  
        </BODY>  
    </HTML>  
    ```  
  
5.  <span data-ttu-id="e26b7-116">추가 <xref:System.Windows.Forms.WebBrowser> 라는 컨트롤 `webBrowser1` 프로젝트의 기본 폼에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-116">Add a <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1` to the main form of your project.</span></span>  
  
6.  <span data-ttu-id="e26b7-117">프로젝트의 코드 파일에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-117">Add the following code to your project's code file.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e26b7-118">확인은 `webBrowser1_DocumentCompleted` 이벤트 처리기에 대 한 수신기로 구성 된는 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-118">Ensure that the `webBrowser1_DocumentCompleted` event hander is configured as a listener for the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="e26b7-119">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]를 두 번 클릭 하는 <xref:System.Windows.Forms.WebBrowser> 제어할; 텍스트 편집기에서 수신기를 프로그래밍 방식으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-119">In [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], double-click on the <xref:System.Windows.Forms.WebBrowser> control; in a text editor, configure the listener programmatically.</span></span>  
  
     [!code-csharp[ManagedDOMStyles#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]  
  
7.  <span data-ttu-id="e26b7-120">프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-120">Run the project.</span></span> <span data-ttu-id="e26b7-121">커서를 첫 번째 실행 `DIV` 코드의 결과를 관찰 합니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-121">Run your cursor over the first `DIV` to observe the effects of the code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e26b7-122">예</span><span class="sxs-lookup"><span data-stu-id="e26b7-122">Example</span></span>  
 <span data-ttu-id="e26b7-123">다음 코드 예제에 대 한 전체 코드를 보여 줍니다.는 `StyleGenerator` 기존 스타일 값을 구문 분석 하는 클래스 지원 추가, 변경 및 스타일을 제거 하 고 요청된 된 변경 포함 된 새 스타일 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e26b7-123">The following code example shows the full code for the `StyleGenerator` class, which parses an existing style value, supports adding, changing, and removing styles, and returns a new style value with the requested changes.</span></span>  
  
 [!code-csharp[ManagedDOMStyles#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
 [!code-vb[ManagedDOMStyles#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e26b7-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e26b7-124">See Also</span></span>  
 <xref:System.Windows.Forms.HtmlElement>
