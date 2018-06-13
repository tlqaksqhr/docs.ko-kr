---
title: '방법: 색 매트릭스를 사용하여 이미지에 알파 값 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: ed129cd9487ba1416cd69b2e13f59747856cb598
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522348"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a><span data-ttu-id="f4806-102">방법: 색 매트릭스를 사용하여 이미지에 알파 값 설정</span><span class="sxs-lookup"><span data-stu-id="f4806-102">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>
<span data-ttu-id="f4806-103"><xref:System.Drawing.Bitmap> 클래스 (에서 상속 되는 <xref:System.Drawing.Image> 클래스) 및 <xref:System.Drawing.Imaging.ImageAttributes> 클래스 가져오고 픽셀 값을 설정 하기 위한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4806-103">The <xref:System.Drawing.Bitmap> class (which inherits from the <xref:System.Drawing.Image> class) and the <xref:System.Drawing.Imaging.ImageAttributes> class provide functionality for getting and setting pixel values.</span></span> <span data-ttu-id="f4806-104">사용할 수는 <xref:System.Drawing.Imaging.ImageAttributes> 알파를 수정 하는 클래스는 전체 이미지에 대 한 값 하거나 호출할 수 있습니다는 <xref:System.Drawing.Bitmap.SetPixel%2A> 의 메서드는 <xref:System.Drawing.Bitmap> 개별 픽셀 값을 수정 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f4806-104">You can use the <xref:System.Drawing.Imaging.ImageAttributes> class to modify the alpha values for an entire image, or you can call the <xref:System.Drawing.Bitmap.SetPixel%2A> method of the <xref:System.Drawing.Bitmap> class to modify individual pixel values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4806-105">예제</span><span class="sxs-lookup"><span data-stu-id="f4806-105">Example</span></span>  
 <span data-ttu-id="f4806-106"><xref:System.Drawing.Imaging.ImageAttributes> 클래스에 렌더링 하는 동안 이미지를 수정 하는 데 사용할 수 있는 여러 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4806-106">The <xref:System.Drawing.Imaging.ImageAttributes> class has many properties that you can use to modify images during rendering.</span></span> <span data-ttu-id="f4806-107">다음 예제에서는 <xref:System.Drawing.Imaging.ImageAttributes> 개체 알파 값을 모두 원래 대로의 80%로 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4806-107">In the following example, an <xref:System.Drawing.Imaging.ImageAttributes> object is used to set all the alpha values to 80 percent of what they were.</span></span> <span data-ttu-id="f4806-108">색 매트릭스를 초기화 하 고 알파 배율 조정 0.8 행렬에는 값을 설정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4806-108">This is done by initializing a color matrix and setting the alpha scaling value in the matrix to 0.8.</span></span> <span data-ttu-id="f4806-109">색 매트릭스의 주소에 전달 되는 <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> 의 메서드는 <xref:System.Drawing.Imaging.ImageAttributes> 개체 및 <xref:System.Drawing.Imaging.ImageAttributes> 를 전달 하는 <xref:System.Drawing.Graphics.DrawString%2A> 의 메서드는 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f4806-109">The address of the color matrix is passed to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object, and the <xref:System.Drawing.Imaging.ImageAttributes> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="f4806-110">렌더링 하는 동안 경우 비트맵의 알파 값은 원래 대로의 80%로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4806-110">During rendering, the alpha values in the bitmap are converted to 80 percent of what they were.</span></span> <span data-ttu-id="f4806-111">따라서 이미지를 배경색과 혼합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4806-111">This results in an image that is blended with the background.</span></span> <span data-ttu-id="f4806-112">다음 그림에 나와 있는 비트맵 이미지 찾아 선택 합니다. 이 통해 검은색 실선을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4806-112">As the following illustration shows, the bitmap image looks transparent; you can see the solid black line through it.</span></span>  
  
 <span data-ttu-id="f4806-113">![행렬을 사용 하 여 알파 혼합](../../../../docs/framework/winforms/advanced/media/image2.png "image2")</span><span class="sxs-lookup"><span data-stu-id="f4806-113">![Alpha Blending Using a Matrix](../../../../docs/framework/winforms/advanced/media/image2.png "image2")</span></span>  
  
 <span data-ttu-id="f4806-114">여기서 이미지는 흰색 부분 배경색, 이미지를 흰색으로 혼합 되 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4806-114">Where the image is over the white portion of the background, the image has been blended with the color white.</span></span> <span data-ttu-id="f4806-115">이미지는 검은색 줄과 교차 검은색 이미지 혼합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4806-115">Where the image crosses the black line, the image is blended with the color black.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f4806-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="f4806-116">Compiling the Code</span></span>  
 <span data-ttu-id="f4806-117">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs>의 매개 변수인 `e`<xref:System.Windows.Forms.PaintEventHandler>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f4806-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4806-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4806-118">See Also</span></span>  
 [<span data-ttu-id="f4806-119">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="f4806-119">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="f4806-120">선 및 채우기 알파 혼합</span><span class="sxs-lookup"><span data-stu-id="f4806-120">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
