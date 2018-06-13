---
title: '방법: 축소판 이미지 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 870ea223698e48438bd4dd08597d0a6ab79cec27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521487"
---
# <a name="how-to-create-thumbnail-images"></a><span data-ttu-id="5484c-102">방법: 축소판 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="5484c-102">How to: Create Thumbnail Images</span></span>
<span data-ttu-id="5484c-103">미리 보기 이미지는 이미지의 작은 버전.</span><span class="sxs-lookup"><span data-stu-id="5484c-103">A thumbnail image is a small version of an image.</span></span> <span data-ttu-id="5484c-104">호출 하 여 미리 보기 이미지를 만들 수는 <xref:System.Drawing.Image.GetThumbnailImage%2A> 의 메서드는 <xref:System.Drawing.Image> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5484c-104">You can create a thumbnail image by calling the <xref:System.Drawing.Image.GetThumbnailImage%2A> method of an <xref:System.Drawing.Image> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5484c-105">예제</span><span class="sxs-lookup"><span data-stu-id="5484c-105">Example</span></span>  
 <span data-ttu-id="5484c-106">다음 구성 예제는 <xref:System.Drawing.Image> JPG 파일에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5484c-106">The following example constructs an <xref:System.Drawing.Image> object from a JPG file.</span></span> <span data-ttu-id="5484c-107">원본 이미지의 640 픽셀 너비와 479 픽셀의 높이로 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5484c-107">The original image has a width of 640 pixels and a height of 479 pixels.</span></span> <span data-ttu-id="5484c-108">코드는 100 픽셀의 너비와 높이가 100 픽셀의 축소판 그림 이미지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5484c-108">The code creates a thumbnail image that has a width of 100 pixels and a height of 100 pixels.</span></span>  
  
 <span data-ttu-id="5484c-109">다음 그림에서는 미리 보기 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5484c-109">The following illustration shows the thumbnail image.</span></span>  
  
 <span data-ttu-id="5484c-110">![미리 보기 이미지](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")</span><span class="sxs-lookup"><span data-stu-id="5484c-110">![Thumbnail Image](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5484c-111">이 예제에서는 콜백 메서드로 선언 되지만 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5484c-111">In this example, a callback method is declared, but never used.</span></span> <span data-ttu-id="5484c-112">GDI +의 모든 버전을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5484c-112">This supports all versions of GDI+.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5484c-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5484c-113">Compiling the Code</span></span>  
 <span data-ttu-id="5484c-114">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5484c-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="5484c-115">이 예제를 실행 하려면 다음이 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5484c-115">To run the example, follow these steps:</span></span>  
  
1.  <span data-ttu-id="5484c-116">새 Windows Forms 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5484c-116">Create a new Windows Forms application.</span></span>  
  
2.  <span data-ttu-id="5484c-117">예제 코드를 폼에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5484c-117">Add the example code to the form.</span></span>  
  
3.  <span data-ttu-id="5484c-118">폼의에 대 한 처리기를 만들고 <xref:System.Windows.Forms.Control.Paint> 이벤트</span><span class="sxs-lookup"><span data-stu-id="5484c-118">Create a handler for the form's <xref:System.Windows.Forms.Control.Paint> event</span></span>  
  
4.  <span data-ttu-id="5484c-119">에 <xref:System.Windows.Forms.Control.Paint> 처리기, 호출의 `GetThumbnail` 메서드와 패스 `e` 에 대 한 <xref:System.Windows.Forms.PaintEventArgs>합니다.</span><span class="sxs-lookup"><span data-stu-id="5484c-119">In the <xref:System.Windows.Forms.Control.Paint> handler, call the `GetThumbnail` method and pass `e` for <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
5.  <span data-ttu-id="5484c-120">미리 보기를 확인 하려는 이미지 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5484c-120">Find an image file that you want to make a thumbnail of.</span></span>  
  
6.  <span data-ttu-id="5484c-121">에 `GetThumbnail` 메서드에 경로 지정 하 고 파일 이름을 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="5484c-121">In the `GetThumbnail` method, specify the path and file name to your image.</span></span>  
  
7.  <span data-ttu-id="5484c-122">예를 실행 하려면 F5 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5484c-122">Press F5 to run the example.</span></span>  
  
     <span data-ttu-id="5484c-123">100으로 100 축소판 그림 이미지를 폼에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5484c-123">A 100 by 100 thumbnail image appears on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5484c-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5484c-124">See Also</span></span>  
 [<span data-ttu-id="5484c-125">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="5484c-125">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="5484c-126">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="5484c-126">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
