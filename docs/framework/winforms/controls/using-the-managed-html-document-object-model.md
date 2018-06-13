---
title: 관리되는 HTML 문서 개체 모델 사용
ms.date: 03/30/2017
helpviewer_keywords:
- managed HTML DOM
ms.assetid: a017dd5c-cd7b-47e4-952c-f4f54cb48409
ms.openlocfilehash: 95b14ae455ef8fcd0a81decec21b8305f2573643
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535953"
---
# <a name="using-the-managed-html-document-object-model"></a><span data-ttu-id="0f702-102">관리되는 HTML 문서 개체 모델 사용</span><span class="sxs-lookup"><span data-stu-id="0f702-102">Using the Managed HTML Document Object Model</span></span>
<span data-ttu-id="0f702-103">관리 되는 HTML 문서 개체 모델 (DOM) 기반으로 하는 래퍼를 제공는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Internet Explorer에서 노출 하는 HTML 클래스에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f702-103">The managed HTML document object model (DOM) provides a wrapper based on the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] for the HTML classes exposed by Internet Explorer.</span></span> <span data-ttu-id="0f702-104">이러한 클래스를 사용 하 여 HTML 페이지에서 호스트를 조작는 <xref:System.Windows.Forms.WebBrowser> 컨트롤 또는 처음부터 새 페이지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f702-104">Use these classes to manipulate HTML pages hosted in the <xref:System.Windows.Forms.WebBrowser> control, or to build new pages from the beginning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0f702-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="0f702-105">In This Section</span></span>  
 [<span data-ttu-id="0f702-106">방법: 관리되는 HTML 문서 개체 모델에 액세스</span><span class="sxs-lookup"><span data-stu-id="0f702-106">How to: Access the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-managed-html-document-object-model.md)  
 <span data-ttu-id="0f702-107">유효한 인스턴스를 가져오는 방법에 설명 <xref:System.Windows.Forms.HtmlDocument> Windows Forms 응용 프로그램에서 또는 <xref:System.Windows.Forms.UserControl> Internet Explorer에서 호스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f702-107">Describes how to obtain a valid instance of <xref:System.Windows.Forms.HtmlDocument> from either a Windows Forms application or a <xref:System.Windows.Forms.UserControl> hosted in Internet Explorer.</span></span>  
  
 [<span data-ttu-id="0f702-108">방법: 관리되는 HTML 문서 개체 모델의 HTML 소스에 액세스</span><span class="sxs-lookup"><span data-stu-id="0f702-108">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-html-source-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="0f702-109">원래, 수정 되지 않은 HTML 소스를 가져오는 방법 및 DOM의 현재 상태를 반영 하는 "라이브" 소스를 가져오는 방법에 설명</span><span class="sxs-lookup"><span data-stu-id="0f702-109">Describes how to obtain the original, unmodified HTML source, and how to obtain the "live" source that reflects the current state of the DOM.</span></span>  
  
 [<span data-ttu-id="0f702-110">방법: 관리되는 HTML 문서 개체 모델의 요소에 대한 스타일 변경</span><span class="sxs-lookup"><span data-stu-id="0f702-110">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-change-styles-on-an-element-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="0f702-111">요소의 시각적 표시를 제어 하는 데 사용 되는 스타일을 조작 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f702-111">Describes how to manipulate styles, which are used to control the visual display of elements.</span></span>  
  
 [<span data-ttu-id="0f702-112">관리되는 HTML 문서 개체 모델의 프레임에 액세스</span><span class="sxs-lookup"><span data-stu-id="0f702-112">Accessing Frames in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-frames-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="0f702-113">프레임 및 프레임 세트 이란, 및 프레임의 DOM에 액세스 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f702-113">Describes what frames and framesets are, and how to access the DOM of a frame.</span></span>  
  
 [<span data-ttu-id="0f702-114">관리되는 HTML 문서 개체 모델의 노출되지 않은 멤버에 액세스</span><span class="sxs-lookup"><span data-stu-id="0f702-114">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-unexposed-members-on-the-managed-html-document-object-model.md)  
 <span data-ttu-id="0f702-115">관리 되는 항목을 갖지 않는 내부 DOM의 멤버에 액세스 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f702-115">Describes how to access members of the underlying DOM that do not have a managed equivalent.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0f702-116">참조</span><span class="sxs-lookup"><span data-stu-id="0f702-116">Reference</span></span>  
 <xref:System.Windows.Forms.HtmlDocument>  
  
 <xref:System.Windows.Forms.HtmlElement>  
  
 <xref:System.Windows.Forms.HtmlWindow>  
  
## <a name="related-sections"></a><span data-ttu-id="0f702-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="0f702-117">Related Sections</span></span>  
 [<span data-ttu-id="0f702-118">WebBrowser 컨트롤</span><span class="sxs-lookup"><span data-stu-id="0f702-118">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)  
  
## <a name="see-also"></a><span data-ttu-id="0f702-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f702-119">See Also</span></span>  
 [<span data-ttu-id="0f702-120">DHTML 개체 모델에 대 한</span><span class="sxs-lookup"><span data-stu-id="0f702-120">About the DHTML Object Model</span></span>](http://msdn.microsoft.com/library/default.asp?url=/workshop/author/om/doc_object.asp)
