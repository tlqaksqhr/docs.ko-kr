---
title: '방법: 이미지 자르기 및 배율 조정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
ms.openlocfilehash: d5acda50a1aa0f0cae6e77a748b011908fcc8c34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521640"
---
# <a name="how-to-crop-and-scale-images"></a><span data-ttu-id="8acb2-102">방법: 이미지 자르기 및 배율 조정</span><span class="sxs-lookup"><span data-stu-id="8acb2-102">How to: Crop and Scale Images</span></span>
<span data-ttu-id="8acb2-103"><xref:System.Drawing.Graphics> 클래스에는 일부의 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드 중 일부는 원본 및 대상 사각형 하는 매개 변수가 이미지 자르기 및 배율에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8acb2-103">The <xref:System.Drawing.Graphics> class provides several <xref:System.Drawing.Graphics.DrawImage%2A> methods, some of which have source and destination rectangle parameters that you can use to crop and scale images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8acb2-104">예제</span><span class="sxs-lookup"><span data-stu-id="8acb2-104">Example</span></span>  
 <span data-ttu-id="8acb2-105">다음 구성 예제는 <xref:System.Drawing.Image> 있는 Apple.gif 디스크 파일에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8acb2-105">The following example constructs an <xref:System.Drawing.Image> object from the disk file Apple.gif.</span></span> <span data-ttu-id="8acb2-106">코드는 원래 크기로 전체 apple 이미지를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="8acb2-106">The code draws the entire apple image in its original size.</span></span> <span data-ttu-id="8acb2-107">호출 된 <xref:System.Drawing.Graphics.DrawImage%2A> 의 메서드는 <xref:System.Drawing.Graphics> 원래 apple 이미지 보다 큰 대상 사각형에 apple 이미지의 일부를 그릴 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8acb2-107">The code then calls the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object to draw a portion of the apple image in a destination rectangle that is larger than the original apple image.</span></span>  
  
 <span data-ttu-id="8acb2-108"><xref:System.Drawing.Graphics.DrawImage%2A> 메서드 다섯 번째 및 여섯 번째 인수는 세 번째, 네 번째, 지정 된 원본 사각형을 확인 하 여 그리는 데 apple의 어떤 부분을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8acb2-108">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines which portion of the apple to draw by looking at the source rectangle, which is specified by the third, fourth, fifth, and sixth arguments.</span></span> <span data-ttu-id="8acb2-109">이 경우 apple 너비의 75% 및 높이의 75%로 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="8acb2-109">In this case, the apple is cropped to 75 percent of its width and 75 percent of its height.</span></span>  
  
 <span data-ttu-id="8acb2-110"><xref:System.Drawing.Graphics.DrawImage%2A> 메서드를 자른된 apple를 그릴 위치와 대상 사각형을 살펴보면 자른된 apple 있도록 최대 크기를 결정은 두 번째 인수로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8acb2-110">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines where to draw the cropped apple and how big to make the cropped apple by looking at the destination rectangle, which is specified by the second argument.</span></span> <span data-ttu-id="8acb2-111">이 경우 대상 사각형에는 더 넓은 30%, 30% 보다 원래 이미지 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8acb2-111">In this case, the destination rectangle is 30 percent wider and 30 percent taller than the original image.</span></span>  
  
 <span data-ttu-id="8acb2-112">다음 그림에서 원래 apple 및 확장 된 잘라 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8acb2-112">The following illustration shows the original apple and the scaled, cropped apple.</span></span>  
  
 <span data-ttu-id="8acb2-113">![자르기 및 배율 조정](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")</span><span class="sxs-lookup"><span data-stu-id="8acb2-113">![Crop & Scale](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8acb2-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8acb2-114">Compiling the Code</span></span>  
 <span data-ttu-id="8acb2-115">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8acb2-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="8acb2-116">대체 해야 `Apple.gif` 있는 이미지 파일 이름 및 시스템에서 사용할 수 있는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="8acb2-116">Make sure to replace `Apple.gif` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8acb2-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8acb2-117">See Also</span></span>  
 [<span data-ttu-id="8acb2-118">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="8acb2-118">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="8acb2-119">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="8acb2-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
