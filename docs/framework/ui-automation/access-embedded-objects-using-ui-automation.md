---
title: "UI 자동화를 사용하여 포함 개체에 액세스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- embedded objects, accessing
- accessing embedded objects
- UI Automation, accessing embedded objects
ms.assetid: a5b513ec-7fa6-4460-869f-c18ff04f7cf2
caps.latest.revision: "17"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 37110708efa49912d0ed9c81746d125167e17985
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="access-embedded-objects-using-ui-automation"></a><span data-ttu-id="e39ef-102">UI 자동화를 사용하여 포함 개체에 액세스</span><span class="sxs-lookup"><span data-stu-id="e39ef-102">Access Embedded Objects Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="e39ef-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e39ef-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e39ef-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e39ef-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="e39ef-105">이 항목에서는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 을 텍스트 컨트롤의 내용에 포함된 개체를 노출하는 데 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e39ef-105">This topic shows how [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] can be used to expose objects embedded within the content of a text control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e39ef-106">포함된 개체에는 이미지, 하이퍼링크, 단추, 테이블 또는 ActiveX 컨트롤이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e39ef-106">Embedded objects can include images, hyperlinks, buttons, tables, or ActiveX controls.</span></span>  
  
 <span data-ttu-id="e39ef-107">포함된 개체는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 텍스트 공급자의 자식 항목으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="e39ef-107">Embedded objects are considered children of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="e39ef-108">이를 통해 포함된 개체가 기타 모든 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 요소와 동일한 UI 자동화 트리 구조를 통해 노출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e39ef-108">This allows them to be exposed through the same UI Automation tree structure as all other [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] elements.</span></span> <span data-ttu-id="e39ef-109">따라서 포함된 개체 컨트롤 형식에 일반적으로 필요한 컨트롤 패턴을 통해 기능이 노출됩니다(예: 하이퍼링크는 텍스트를 기반으로 하므로 <xref:System.Windows.Automation.TextPattern>을 지원함).</span><span class="sxs-lookup"><span data-stu-id="e39ef-109">Functionality, in turn, is exposed through the control patterns typically required by the embedded objects control type (for example, since hyperlinks are text-based they will support <xref:System.Windows.Automation.TextPattern>).</span></span>  
  
 <span data-ttu-id="e39ef-110">![텍스트 컨테이너에 포함 된 개체입니다. ] (../../../docs/framework/ui-automation/media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")</span><span class="sxs-lookup"><span data-stu-id="e39ef-110">![Embedded objects in a text container.](../../../docs/framework/ui-automation/media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")</span></span>  
<span data-ttu-id="e39ef-111">샘플 문서 ("알고 계십니까?"는 텍스트 콘텐츠로 ...) 과 두 개의 코드 예에서는 대상으로 사용 되는 개체 (고래 및 텍스트 하이퍼링크의 그림)을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e39ef-111">A sample document with textual content, ("Did You Know?"…) and two embedded objects (a picture of a whale and a text hyperlink), used as a target for the code examples.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e39ef-112">예</span><span class="sxs-lookup"><span data-stu-id="e39ef-112">Example</span></span>  
 <span data-ttu-id="e39ef-113">다음 코드 예제는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 텍스트 공급자에서 포함된 개체의 컬렉션을 검색하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e39ef-113">The following code example demonstrates how to retrieve a collection of embedded objects from within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="e39ef-114">소개 부분에 제공된 샘플 문서의 경우 두 개의 개체가 반환됩니다(이미지 요소 및 텍스트 요소).</span><span class="sxs-lookup"><span data-stu-id="e39ef-114">For the sample document provided in the introduction, two objects would be returned (an image element and a text element).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e39ef-115">이미지 요소에는 해당 이미지를 설명하는 연관된 내장 텍스트가 있어야 하며, 일반적으로 <xref:System.Windows.Automation.AutomationElement.NameProperty> 에 있습니다(예: "파란색 고래").</span><span class="sxs-lookup"><span data-stu-id="e39ef-115">The image element should have some intrinsic text associated with it that describes the image, typically in its <xref:System.Windows.Automation.AutomationElement.NameProperty> (for example, "A blue whale.").</span></span> <span data-ttu-id="e39ef-116">하지만 이미지 개체에 걸쳐 있는 텍스트 범위를 가져오면 텍스트 스트림에 이미지 또는 설명 텍스트가 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e39ef-116">However, when a text range spanning the image object is obtained, neither the image nor this descriptive text is returned in the text stream.</span></span>  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#GetChildren](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#getchildren)]
[!code-vb[FindText#GetChildren](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#getchildren)]  
  
## <a name="example"></a><span data-ttu-id="e39ef-117">예</span><span class="sxs-lookup"><span data-stu-id="e39ef-117">Example</span></span>  
 <span data-ttu-id="e39ef-118">다음 코드 예제는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 텍스트 공급자 내에 포함된 개체에서 텍스트 범위를 가져오는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e39ef-118">The following code example demonstrates how to obtain a text range from an embedded object within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="e39ef-119">검색된 텍스트 범위는 빈 범위로서 시작되는 끝점 앞에 "…</span><span class="sxs-lookup"><span data-stu-id="e39ef-119">The text range retrieved is an empty range where the starting endpoint follows "…</span></span> <span data-ttu-id="e39ef-120">ocean.(space)"가 오고 끝나는 끝점 뒤에 닫는 "."가 와서 포함된 하이퍼링크를 나타냅니다(소개 부분에 제공된 이미지 참조).</span><span class="sxs-lookup"><span data-stu-id="e39ef-120">ocean.(space)" and the ending endpoint precedes the closing "." representing the embedded hyperlink (as shown by the image provided in the introduction).</span></span> <span data-ttu-id="e39ef-121">검색된 범위가 비어 있는 범위라 해도, 0이 아닌 범위이기 때문에 중복 제거 범위로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e39ef-121">Even though this is an empty range, it is not considered a degenerate range because it has a non-zero span.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e39ef-122"><xref:System.Windows.Automation.TextPattern> 은 하이퍼링크와 같이 텍스트를 기반으로 하는 포함된 개체를 검색할 수 있지만, 보조 <xref:System.Windows.Automation.TextPattern> 은 포함된 개체에서 가져와야 전체 기능을 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e39ef-122"><xref:System.Windows.Automation.TextPattern> can retrieve a text-based embedded object such as a hyperlink; however, a secondary <xref:System.Windows.Automation.TextPattern> will have to be obtained from the embedded object to expose its full functionality.</span></span>  
  
 [!code-csharp[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#getrangefromchild)]
 [!code-vb[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#getrangefromchild)]  
  
## <a name="see-also"></a><span data-ttu-id="e39ef-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e39ef-123">See Also</span></span>  
 [<span data-ttu-id="e39ef-124">UI 자동화 TextPattern 개요</span><span class="sxs-lookup"><span data-stu-id="e39ef-124">UI Automation TextPattern Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [<span data-ttu-id="e39ef-125">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="e39ef-125">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="e39ef-126">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="e39ef-126">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="e39ef-127">UI 자동화를 사용하여 텍스트 상자에 콘텐츠 추가</span><span class="sxs-lookup"><span data-stu-id="e39ef-127">Add Content to a Text Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [<span data-ttu-id="e39ef-128">UI 자동화를 사용하여 텍스트 찾기 및 강조</span><span class="sxs-lookup"><span data-stu-id="e39ef-128">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
