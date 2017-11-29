---
title: "방법: 디자이너를 사용하여 그림 로드(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9049bf5f9467401bff098459b8f5ed55c1ee1975
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="c1125-102">방법: 디자이너를 사용하여 그림 로드(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c1125-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>
<span data-ttu-id="c1125-103">Windows forms <xref:System.Windows.Forms.PictureBox> 컨트롤을 로드 하 고 설정 하 여 폼의 디자인 타임에 그림을 표시할 수는 <xref:System.Windows.Forms.PictureBox.Image%2A> 속성을 유효한 그림을 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1125-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="c1125-104">다음 표에서 허용 되는 파일 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c1125-104">The following table shows the acceptable file types.</span></span>  
  
|<span data-ttu-id="c1125-105">형식</span><span class="sxs-lookup"><span data-stu-id="c1125-105">Type</span></span>|<span data-ttu-id="c1125-106">파일 이름 확장명</span><span class="sxs-lookup"><span data-stu-id="c1125-106">File name extension</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="c1125-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="c1125-107">Bitmap</span></span>|<span data-ttu-id="c1125-108">.bmp</span><span class="sxs-lookup"><span data-stu-id="c1125-108">.bmp</span></span>|  
|<span data-ttu-id="c1125-109">아이콘</span><span class="sxs-lookup"><span data-stu-id="c1125-109">Icon</span></span>|<span data-ttu-id="c1125-110">.ico</span><span class="sxs-lookup"><span data-stu-id="c1125-110">.ico</span></span>|  
|<span data-ttu-id="c1125-111">GIF</span><span class="sxs-lookup"><span data-stu-id="c1125-111">GIF</span></span>|<span data-ttu-id="c1125-112">.gif</span><span class="sxs-lookup"><span data-stu-id="c1125-112">.gif</span></span>|  
|<span data-ttu-id="c1125-113">메타 파일</span><span class="sxs-lookup"><span data-stu-id="c1125-113">Metafile</span></span>|<span data-ttu-id="c1125-114">.wmf</span><span class="sxs-lookup"><span data-stu-id="c1125-114">.wmf</span></span>|  
|<span data-ttu-id="c1125-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="c1125-115">JPEG</span></span>|<span data-ttu-id="c1125-116">.jpg</span><span class="sxs-lookup"><span data-stu-id="c1125-116">.jpg</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c1125-117">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1125-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c1125-118">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1125-118">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c1125-119">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1125-119">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="c1125-120">디자인 타임에 그림을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="c1125-120">To display a picture at design time</span></span>  
  
1.  <span data-ttu-id="c1125-121">그리기는 <xref:System.Windows.Forms.PictureBox> 양식에 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="c1125-121">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>  
  
2.  <span data-ttu-id="c1125-122">속성 창에서 선택 된 <xref:System.Windows.Forms.PictureBox.Image%2A> 속성을 다음 표시 하 고 줄임표 단추를 클릭은 **열려** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="c1125-122">On the Properties window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then click the ellipsis button to display the **Open** dialog box.</span></span>  
  
3.  <span data-ttu-id="c1125-123">특정 파일 형식 (예를 들어.gif 파일)에 대 한 원하는 경우에 선택 된 **파일 형식** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="c1125-123">If you are looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>  
  
4.  <span data-ttu-id="c1125-124">표시 하려는 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1125-124">Select the file you want to display.</span></span>  
  
### <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="c1125-125">디자인 타임에 그림을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="c1125-125">To clear the picture at design time</span></span>  
  
1.  <span data-ttu-id="c1125-126">에 **속성** 창에서는 <xref:System.Windows.Forms.PictureBox.Image%2A> 속성과 이미지 개체의 이름 왼쪽에 표시 되는 작은 축소판 이미지를 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1125-126">On the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property and right-click the small thumbnail image that appears to the left of the name of the image object.</span></span> <span data-ttu-id="c1125-127">선택 **재설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="c1125-127">Choose **Reset**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1125-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1125-128">See Also</span></span>  
 <xref:System.Windows.Forms.PictureBox>  
 [<span data-ttu-id="c1125-129">PictureBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="c1125-129">PictureBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [<span data-ttu-id="c1125-130">방법: 런타임에 그림의 크기 또는 위치 수정</span><span class="sxs-lookup"><span data-stu-id="c1125-130">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [<span data-ttu-id="c1125-131">방법: 런타임에 그림 설정</span><span class="sxs-lookup"><span data-stu-id="c1125-131">How to: Set Pictures at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [<span data-ttu-id="c1125-132">PictureBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c1125-132">PictureBox Control</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
