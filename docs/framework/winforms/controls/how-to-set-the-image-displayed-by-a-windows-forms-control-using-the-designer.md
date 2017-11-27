---
title: "방법: 디자이너를 사용하여 Windows Forms 컨트롤에 표시되는 이미지 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
- setting images [Windows Forms], Windows Forms controls
ms.assetid: ae80d07a-e469-4251-90ca-df71f5852454
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eee3c8c3f3890054e443f6246b8fa43fd2ef09b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="f6390-102">방법: 디자이너를 사용하여 Windows Forms 컨트롤에 표시되는 이미지 설정</span><span class="sxs-lookup"><span data-stu-id="f6390-102">How to: Set the Image Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="f6390-103">여러 Windows Forms 컨트롤 이미지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6390-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="f6390-104">이미지 디스크 아이콘이 단추를 나타내는 것 처럼 컨트롤의 용도 명확히 하는 아이콘 수는 **저장** 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="f6390-104">The image can be an icon that clarifies the purpose of the control, such as a disk icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="f6390-105">또한 아이콘 배경 이미지를 원하는 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6390-105">Alternatively, the icon can be a background image to give the control the appearance you want.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6390-106">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6390-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f6390-107">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f6390-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f6390-108">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f6390-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="f6390-109">컨트롤에서 표시 되는 이미지를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="f6390-109">To set the image displayed by a control</span></span>  
  
1.  <span data-ttu-id="f6390-110">에 **속성** 창의 선택 된 **이미지** 또는 **BackgroundImage** 는 컨트롤의 클릭 줄임표 단추 (</span><span class="sxs-lookup"><span data-stu-id="f6390-110">In the **Properties** window, select the **Image** or **BackgroundImage** property of the control, then click the ellipsis button (</span></span>  
  
     <span data-ttu-id="f6390-111">![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")</span><span class="sxs-lookup"><span data-stu-id="f6390-111">![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")</span></span>  
  
     <span data-ttu-id="f6390-112">)를 표시 하는 **리소스 선택** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="f6390-112">) to display the **Select Resource** dialog box.</span></span>  
  
2.  <span data-ttu-id="f6390-113">표시할 이미지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6390-113">Select the image you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6390-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6390-114">See Also</span></span>  
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [<span data-ttu-id="f6390-115">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="f6390-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
