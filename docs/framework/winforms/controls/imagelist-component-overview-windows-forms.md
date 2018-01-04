---
title: "ImageList 구성 요소 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ImageList
helpviewer_keywords:
- collection controls [Windows Forms], images
- icon list control
- ImageList component [Windows Forms], about ImageList component
ms.assetid: 7e25d89b-5633-40c1-afc3-82e0e301ffa2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a913de1a6808c7e600a4f28ed58dedf93506466b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imagelist-component-overview-windows-forms"></a><span data-ttu-id="78c03-102">ImageList 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="78c03-102">ImageList Component Overview (Windows Forms)</span></span>
<span data-ttu-id="78c03-103">Windows Forms <xref:System.Windows.Forms.ImageList> 구성 요소는 컨트롤에 의해 표시될 수 있는 이미지를 저장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c03-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is used to store images, which can then be displayed by controls.</span></span> <span data-ttu-id="78c03-104">이미지 목록을 통해 일관된 단일 이미지 카탈로그에 대한 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c03-104">An image list allows you to write code for a single, consistent catalog of images.</span></span> <span data-ttu-id="78c03-105">예를 들어 단추의 <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> 또는 <xref:System.Windows.Forms.ButtonBase.ImageKey%2A> 속성을 변경하여 <xref:System.Windows.Forms.Button> 컨트롤에 의해 표시되는 이미지를 회전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c03-105">For example, you can rotate images displayed by a <xref:System.Windows.Forms.Button> control simply by changing the button's <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> or <xref:System.Windows.Forms.ButtonBase.ImageKey%2A> property.</span></span> <span data-ttu-id="78c03-106">동일한 이미지 목록을 여러 컨트롤에 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c03-106">You can also associate the same image list with multiple controls.</span></span> <span data-ttu-id="78c03-107">예를 들어 <xref:System.Windows.Forms.ListView> 컨트롤과 <xref:System.Windows.Forms.TreeView> 컨트롤 둘 다를 사용하여 동일한 파일 목록을 표시하는 경우 이미지 목록에서 파일 아이콘을 변경하면 두 보기에 모두 새 아이콘이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="78c03-107">For example, if you are using both a <xref:System.Windows.Forms.ListView> control and a <xref:System.Windows.Forms.TreeView> control to display the same list of files, changing a file's icon in the image list will cause the new icon to appear in both views.</span></span>  
  
## <a name="using-imagelist-with-controls"></a><span data-ttu-id="78c03-108">컨트롤과 함께 ImageList 사용</span><span class="sxs-lookup"><span data-stu-id="78c03-108">Using ImageList with Controls</span></span>  
 <span data-ttu-id="78c03-109">`ImageList` 속성 또는 <xref:System.Windows.Forms.ListView> 컨트롤의 경우 <xref:System.Windows.Forms.ListView.SmallImageList%2A> 및 <xref:System.Windows.Forms.ListView.LargeImageList%2A> 속성이 있는 모든 컨트롤과 함께 이미지 목록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c03-109">You can use an image list with any control that has an `ImageList` property — or in the case of the <xref:System.Windows.Forms.ListView> control, <xref:System.Windows.Forms.ListView.SmallImageList%2A> and <xref:System.Windows.Forms.ListView.LargeImageList%2A> properties.</span></span> <span data-ttu-id="78c03-110">이미지 목록에 연결할 수 있는 컨트롤에는 <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ToolBar>, <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton> 및 <xref:System.Windows.Forms.Label> 컨트롤이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c03-110">The controls that can be associated with an image list include: the <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ToolBar>, <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton>, and <xref:System.Windows.Forms.Label> controls.</span></span> <span data-ttu-id="78c03-111">이미지 목록을 컨트롤에 연결하려면 컨트롤의 `ImageList` 속성을 <xref:System.Windows.Forms.ImageList> 구성 요소의 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="78c03-111">To associate the image list with a control, set the control's `ImageList` property to the name of the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="78c03-112">키 속성</span><span class="sxs-lookup"><span data-stu-id="78c03-112">Key Properties</span></span>  
 <span data-ttu-id="78c03-113"><xref:System.Windows.Forms.ImageList> 구성 요소의 키 속성은 연결된 컨트롤에서 사용할 그림을 포함하는 <xref:System.Windows.Forms.ImageList.Images%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="78c03-113">The key property of the <xref:System.Windows.Forms.ImageList> component is <xref:System.Windows.Forms.ImageList.Images%2A>, which contains the pictures to be used by the associated control.</span></span> <span data-ttu-id="78c03-114">인덱스 값이나 해당 키를 통해 각 개별 이미지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c03-114">Each individual image can be accessed by its index value or by its key.</span></span> <span data-ttu-id="78c03-115"><xref:System.Windows.Forms.ImageList.ColorDepth%2A> 속성은 이미지 렌더링에 사용되는 색 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="78c03-115">The <xref:System.Windows.Forms.ImageList.ColorDepth%2A> property determines the number of colors that the images are rendered with.</span></span> <span data-ttu-id="78c03-116">이미지는 모두 <xref:System.Windows.Forms.ImageList.ImageSize%2A> 속성에 설정된 동일한 크기로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c03-116">The images will all be displayed at the same size, set by the <xref:System.Windows.Forms.ImageList.ImageSize%2A> property.</span></span> <span data-ttu-id="78c03-117">더 큰 이미지는 적절하게 크기가 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c03-117">Images that are larger will be scaled to fit.</span></span>  
  
 <span data-ttu-id="78c03-118">[!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]를 사용 중인 경우 응용 프로그램에서 사용할 수 있는 표준 이미지의 대규모 라이브러리에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c03-118">If you are using [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], you have access to a large library of standard images that you can use in your applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78c03-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78c03-119">See Also</span></span>  
 <xref:System.Windows.Forms.ImageList>  
 [<span data-ttu-id="78c03-120">방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="78c03-120">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
