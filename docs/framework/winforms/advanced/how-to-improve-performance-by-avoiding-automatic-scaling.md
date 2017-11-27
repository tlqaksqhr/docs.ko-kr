---
title: "방법: 자동 배율 조정 없이 성능 향상"
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
helpviewer_keywords:
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0130e0745dfca20da5dc723bb7cc84748bb0b148
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a><span data-ttu-id="98af3-102">방법: 자동 배율 조정 없이 성능 향상</span><span class="sxs-lookup"><span data-stu-id="98af3-102">How to: Improve Performance by Avoiding Automatic Scaling</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="98af3-103">그릴 때, 성능 저하가 발생 하는 이미지의 배율을 조정 자동으로 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98af3-103"> may automatically scale an image as you draw it, which would decrease performance.</span></span> <span data-ttu-id="98af3-104">이미지의 배율에 대상 사각형의 크기를 전달 하 여 제어할 수 또는 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="98af3-104">Alternatively, you can control the scaling of the image by passing the dimensions of the destination rectangle to the <xref:System.Drawing.Graphics.DrawImage%2A> method.</span></span>  
  
 <span data-ttu-id="98af3-105">다음을 호출 하는 예를 들어는 <xref:System.Drawing.Graphics.DrawImage%2A> 의 왼쪽 위 모퉁이 지정 하는 메서드 (50, 30) 하지만 대상 사각형을 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98af3-105">For example, the following call to the <xref:System.Drawing.Graphics.DrawImage%2A> method specifies an upper-left corner of (50, 30) but does not specify a destination rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 <span data-ttu-id="98af3-106">이 가장 쉬운 버전의는 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드 반드시 가장 효율적인 아니므로 필요한 인수 수를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="98af3-106">Although this is the easiest version of the <xref:System.Drawing.Graphics.DrawImage%2A> method in terms of the number of required arguments, it is not necessarily the most efficient.</span></span> <span data-ttu-id="98af3-107">해결 방법을 사용 하는 경우 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] (일반적으로 96dpi)에 저장 된 해상도와 다른는 <xref:System.Drawing.Image> 개체 면 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드 이미지 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98af3-107">If the resolution used by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] (usually 96 dots per inch) is different from the resolution stored in the <xref:System.Drawing.Image> object, then the <xref:System.Drawing.Graphics.DrawImage%2A> method will scale the image.</span></span> <span data-ttu-id="98af3-108">예를 들어 한 <xref:System.Drawing.Image> 개체에 216 픽셀 너비와 72 인 저장된 수평 해상도 값입니다.</span><span class="sxs-lookup"><span data-stu-id="98af3-108">For example, suppose an <xref:System.Drawing.Image> object has a width of 216 pixels and a stored horizontal resolution value of 72 dots per inch.</span></span> <span data-ttu-id="98af3-109">216/72 3, 이므로 <xref:System.Drawing.Graphics.DrawImage%2A> 을 갖도록 3 인치 너비 96dpi의 해상도 이미지 배율을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98af3-109">Because 216/72 is 3, <xref:System.Drawing.Graphics.DrawImage%2A> will scale the image so that it has a width of 3 inches at a resolution of 96 dots per inch.</span></span> <span data-ttu-id="98af3-110">즉, <xref:System.Drawing.Graphics.DrawImage%2A> 96 x 3 = 288의 너비는 이미지가 표시 됩니다 (픽셀)입니다.</span><span class="sxs-lookup"><span data-stu-id="98af3-110">That is, <xref:System.Drawing.Graphics.DrawImage%2A> will display an image that has a width of 96x3 = 288 pixels.</span></span>  
  
 <span data-ttu-id="98af3-111">화면 해상도 96dpi와에서 다른 경우에 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 할 배율 이미지 하면 화면 해상도 96dpi 인 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="98af3-111">Even if your screen resolution is different from 96 dots per inch, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] will probably scale the image as if the screen resolution were 96 dots per inch.</span></span> <span data-ttu-id="98af3-112">때문는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> 개체가 장치 컨텍스트와 연결 된 시기 및 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 화면 해상도 결과 대 한 장치 컨텍스트는 실제 화면 해상도 관계 없이 96 일반적으로 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="98af3-112">That is because a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> object is associated with a device context, and when [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] queries the device context for the screen resolution, the result is usually 96, regardless of the actual screen resolution.</span></span> <span data-ttu-id="98af3-113">대상 사각형을 지정 하 여 자동 크기 조정 작업을 방지할 수 있습니다는 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="98af3-113">You can avoid automatic scaling by specifying the destination rectangle in the <xref:System.Drawing.Graphics.DrawImage%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98af3-114">예제</span><span class="sxs-lookup"><span data-stu-id="98af3-114">Example</span></span>  
 <span data-ttu-id="98af3-115">다음 예제에서는 두 번 동일한 이미지를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="98af3-115">The following example draws the same image twice.</span></span> <span data-ttu-id="98af3-116">첫 번째 경우에서 대상 사각형의 높이 너비 지정 되지 않은 및 이미지가 자동으로 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98af3-116">In the first case, the width and height of the destination rectangle are not specified, and the image is automatically scaled.</span></span> <span data-ttu-id="98af3-117">두 번째 경우에 너비와 대상 사각형의 높이 (픽셀 단위)를 원본 이미지의 높이 너비와 동일 하 게 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98af3-117">In the second case, the width and height (measured in pixels) of the destination rectangle are specified to be the same as the width and height of the original image.</span></span> <span data-ttu-id="98af3-118">다음 그림에서는 두 번 렌더링 되는 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98af3-118">The following illustration shows the image rendered twice.</span></span>  
  
 <span data-ttu-id="98af3-119">![질감 크기가 조정](../../../../docs/framework/winforms/advanced/media/csscaledtexture1.png "csscaledtexture1")</span><span class="sxs-lookup"><span data-stu-id="98af3-119">![Scaled Texture](../../../../docs/framework/winforms/advanced/media/csscaledtexture1.png "csscaledtexture1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="98af3-120">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="98af3-120">Compiling the Code</span></span>  
 <span data-ttu-id="98af3-121">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="98af3-121">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="98af3-122">이미지 이름 및 시스템에 유효한 경로 Texture.jpg를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="98af3-122">Replace Texture.jpg with an image name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98af3-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98af3-123">See Also</span></span>  
 [<span data-ttu-id="98af3-124">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="98af3-124">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="98af3-125">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="98af3-125">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
